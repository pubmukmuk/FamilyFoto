# 🤖 FAMILYFOTO AGENTS – Modular Architecture (r1)

Author: Mike Mattinson  
Updated: Sep/29/2025 – r1

---

## 🔧 OVERVIEW

To support scalable, testable, and maintainable automation, the FamilyFoto pipeline is split into modular agents. Each agent is responsible for a distinct phase of the workflow and updates shared resources such as the database and `batch.meta.json`.

---

## 🧩 AGENT ROLES

### 🟡 WatcherAgent
- Monitors the WATCH_FOLDER for new photo files
- Detects new content or .trigger file as batching signal
- Optionally logs photo counts or readiness
- (Future) May notify downstream agents or flag DB
- Does NOT move, group, or rename files
- Leaves batch grouping to BatchAgent
- Acts as the "eyes" of the system – lightweight, event-driven

### 🔵 `BatchAgent`
- Activated manually or downstream from WatcherAgent
- Backs up files to BACKUP_DIR
- Moves files into an INBOX_DIR/BATCH-* folder
- Creates a batch.meta.json with initial metadata
- Computes SHA256 hash + UUID for each photo
- Converts .HEIC to .JPG (retaining EXIF)
- Extracts EXIF metadata (Date, GPS, CameraModel)
- Flags duplicates and stores results in the database
- Marks batch as READY for geocoding and naming
- Performs all heavy lifting — batching, hashing, metadata extraction, and backup

### 🟢 `GeoAgent`
- If GPS is present, performs reverse geocoding:
  - Online (e.g. Nominatim API)
  - Offline (e.g. OSM CSV or shapefiles)
- If GPS is missing:
  - Attempts location from folder context or default fallback
  - Flags file for manual override
- Updates `city_id`, `state`, `country` in the DB

### 🟣 `NameAgent`
- Builds short `GEOCODE` ID (e.g. `UT-SLC`)
- Renames files using: `YY-MM-DD_GEOCODE_HH-MM.jpg`
- Moves photos to output folders: `YYYY-MM (City, State)`
- Updates status to `Finalized`

### 🔴 `SummaryAgent`
- Generates contact sheet(s) for each output folder
- Exports CSV summary of batch contents:
  - File types, date ranges, camera usage
- Flags anomalies (missing EXIF, duplicates, etc.)

| Area                           | **WatcherAgent** 🟡                               | **BatchAgent** 🔵                                              | Overlap?      |
| ------------------------------ | ------------------------------------------------- | -------------------------------------------------------------- | ------------- |
| **Primary Role**               | Detect new files in `watch/` and trigger batching | Process and register batches once file set is identified       | ❌             |
| **Runs as a daemon**           | ✅ Polls regularly or waits for trigger            | ❌ Usually invoked per batch (script or CLI)                    | ❌             |
| **Target folder**              | `WATCH_FOLDER`                                    | `INBOX_DIR` and `BACKUP_DIR`                                   | ⬅️ transition |
| **Trigger mechanism**          | ✅ Detects new files or `.trigger` file            | ❌ Assumes files already moved into inbox                       | ❌             |
| **Batch file grouping**        | 🚧 Possible future feature (early filtering)      | ✅ Groups files into batches (300–500), tags them with metadata | ⚠️ Some       |
| **Backup of source files**     | ❌ Not responsible                                 | ✅ Copies to `BACKUP_DIR`                                       | ❌             |
| **Hash + UUID generation**     | ❌                                                 | ✅ Computes SHA256 and UUID for each photo                      | ❌             |
| **EXIF extraction**            | ❌                                                 | ✅ Reads EXIF and evaluates camera/date/GPS info                | ❌             |
| **Batch folder creation**      | ❌                                                 | ✅ Creates `BATCH-YYYY-MM-DD_xxxx` folder in inbox              | ❌             |
| **batch.meta.json generation** | ❌                                                 | ✅ Writes initial batch metadata                                | ❌             |
| **Duplicate detection**        | ❌                                                 | ✅ Checks for duplicates using hash                             | ❌             |
| **Logging activity**           | ✅ Logs detection events                           | ✅ Logs batch creation steps                                    | ✅             |
| **Triggers next agent**        | 🚧 Planned (e.g. triggers BatchAgent or flags DB) | ❌ Completes and passes to GeoAgent                             | ❌             |

### WATCHER VS BATCH OVERLAP

| Category            | Summary                                                               |
| ------------------- | --------------------------------------------------------------------- |
| **Responsibility**  | Watcher = detection, Batch = processing                               |
| **Temporal Scope**  | Watcher is continuous, Batch is discrete                              |
| **Overlap**         | Minimal – only in logging and possibly in future early file filtering |
| **Interface Point** | Watcher *hands off* files to BatchAgent via file move or trigger      |




## 📊 STATUS PIPELINE

Each agent transitions the batch through statuses:

```
batch.status = Initialized
  └── watcher detects and groups photos

batch.status = Registered
  └── batch hashes, backups, metadata extracted

batch.status = Located
  └── reverse geocode complete, city/state/country resolved

batch.status = Named
  └── renamed and organized into final folders

batch.status = Finalized
  └── contact sheets created, summary complete
```

---

## 🗂 PROPOSED FILE STRUCTURE

```text
familyfoto/
└── agents/
    ├── watcher_agent.py      # Detects new files and creates batches
    ├── batch_agent.py        # Handles backup, hashing, EXIF extraction, conversion
    ├── geo_agent.py          # Reverse geocoding using GPS or fallback
    ├── name_agent.py         # Renames photos and moves to structured folders
    ├── summary_agent.py      # Generates contact sheets and summary reports
```

Each file implements a CLI entrypoint or callable class with full logging and config support.

---

## 🧠 FUTURE: Master Controller

A `BatchRunner` or `fffcli.py` script can invoke each agent in order, or allow flags like:

```bash
fffcli.py run-batch --batch-id B20250929 --from watcher --to summary
```


## CORE AGENT LAYERS

| Agent Name       | `agents/`            | `commands/`          | `logic/`             | `utils/`                   |
| ---------------- | -------------------- | -------------------- | -------------------- | -------------------------- |
| **WatcherAgent** | ✅ `watcher_agent.py` | ✅ `watcher_agent.py` | ✅ `watcher_agent.py` | ✅ `watcher_agent_utils.py` |
| **BatchAgent**   | ✅ `batch_agent.py`   | ✅ `batch_agent.py`   | ✅ `batch_agent.py`   | ✅ `batch_agent_utils.py`   |
| **GeoAgent**     | ✅ `geo_agent.py`     | ✅ `geo_agent.py`     | ✅ `geo_agent.py`     | ✅ `geo_agent_utils.py`     |
| **NameAgent**    | ✅ `name_agent.py`    | ✅ `name_agent.py`    | ✅ `name_agent.py`    | ✅ `name_agent_utils.py`    |
| **SummaryAgent** | ✅ `summary_agent.py` | ✅ `summary_agent.py` | ✅ `summary_agent.py` | ✅ `summary_agent_utils.py` |


## LAYER ROLES

| Layer       | Role                                                                 |
| ----------- | -------------------------------------------------------------------- |
| `agents/`   | Defines high-level class with `.run()` or `.process()` method        |
| `commands/` | CLI interface using `argparse`, `--batch-id`, `--config`, etc.       |
| `logic/`    | Core business logic functions used by the agent class                |
| `utils/`    | Reusable support functions (I/O, folder helpers, filtering, logging) |

