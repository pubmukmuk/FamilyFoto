## FAMILY PHOTO WORKFLOW - v1.0.0

### 🔧 STEP 1: Configuration and Setup
- Define default folders (`inbox`, `organized`, `log`, `temp`)
- Create a `photo.config` or `.env` file for:
  - default timezone
  - GPS fallback (manual entry, default location, etc.)
  - camera model aliases
  - filename template
- Load configuration at runtime

### 📥 STEP 2: Import Photos
#### A. From GPS-enabled sources
- iPhone, Android, modern digital cameras
- Copy directly to `inbox/` preserving original structure
- No immediate conversion needed

#### B. From non-GPS sources
- Import scans, old digital cameras, or downloaded files
- Mark for manual geotagging or use folder context as hints
- Add fallback logic in the pipeline

### 🔄 STEP 3: Convert Media Formats
- Convert `.HEIC` to `.JPG` using `pillow-heif` or `pyheif` + `Pillow`
- Maintain original timestamps and preserve metadata
- Optional: convert `.MOV` to `.MP4` using `ffmpeg`

### 🔍 STEP 4: Extract Metadata
- Read EXIF metadata: `DateTimeOriginal`, `CameraModel`, `GPS`
- Store in `coordinates.csv`:
  - filename
  - timestamp
  - latitude / longitude
  - camera model
  - hash
  - status (Initialized, Located, Finalized)

### 📌 STEP 5: Identify GPS + Dated Photos
- Flag:
  - ✅ Date + GPS present (fully automatic)
  - ⚠️ Date only (requires geocoding or manual input)
  - ⛔ Missing EXIF (prompt for human input)

### 🌍 STEP 6: Reverse Geocode GPS
- Use `geopy.Nominatim` or another API
- Derive: Street, City, State/Country
- Append to `coordinates.csv` and cache results

### 🏷️ STEP 7: Rename & Organize
- Generate `GEOCODE` (short ID from location)
- Rename files to: `YY-MM-DD_GEOCODE_HH-MM.jpg`
- Move to folders by `YY-MM (City, State)`
- Optional: preserve original as `originals/`

### 🔁 STEP 8: Detect and Eliminate Duplicates
- Hash using SHA256
- Check for existing hash in `duplicates.txt` or metadata DB
- Skip or link duplicates to canonical source

### 🧹 STEP 9: Clean Up
- Remove empty folders
- Archive moved files
- Sync thumbnails to photo manager (e.g., PhotoPrism, NextCloud)

### 📊 STEP 10: Summarize Collection
- Use `summarize-photos-r3.py`
- Group by year, camera, filetype
- Export summary to `summary.csv`
- Visual QA of camera usage and photo spread

### 📋 FUTURE IDEAS
- Photo rating or tagging system
- Location clustering and map preview
- Dashboard with pending photos needing action
- GUI wrapper for `fffcli.py`

Author: Mike Mattinson
Updated: Aug/24/20215