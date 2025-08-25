# 📸 FamilyFoto CLI Toolkit

**FamilyFoto** is a modular, scriptable command-line pipeline for organizing, renaming, tagging, and archiving family photos and videos. It supports metadata extraction, GPS reverse geocoding, duplicate detection, and flexible folder structures — ideal for large-scale personal or historical media libraries.

<br>Latest release: v0.6.0
<br>Updated: Aug/25/2025
<br>Lead: Mike Mattinson
<br>@devmukmuk
<br>@pubmukmuk
<br>@MikeMMattinson

## 🚀 Features

- ✅ Import from phone backups, SD cards, scanned archives
- 🕵️‍♂️ Extract EXIF metadata including timestamps, GPS, camera model
- 🌍 Reverse geocode GPS data to derive City, State, Country
- 🏷️ Rename files based on date, location, and camera info
- 📂 Organize into flexible folder structures by decade, city, or flat
- 🔁 Detect and skip duplicates using SHA256 hashes
- 📊 Generate summaries and logs for QA and audits

## 📁 Project Structure

```
FamilyFoto/
├── familyfoto/           # Core Python package
│   ├── cli.py            # Main CLI entry point
│   ├── commands/         # Individual CLI modules (fotonamer, fototagger...)
│   ├── logic/            # Reusable processing logic
│   └── utils/            # Config, EXIF, location, file helpers
├── config/               # Default config files (photo.config)
├── data/                 # City/street codes, lookup tables
├── docs/                 # Project docs and diagrams
├── log/                  # Generated logs (duplicates, metadata, summary)
├── tools/                # Dev tools, versioning, build scripts
├── tests/                # Unit tests and test assets
└── treeviewer/           # CLI tool for visualizing folder structure
```

## 🛠️ Setup

```bash
git clone git@github.com:devmukmuk/FamilyFoto.git
cd FamilyFoto
python -m venv .venv
source .venv/Scripts/activate  # On Windows Git Bash
pip install -r requirements.txt
```

## 🧰 CLI Tools

Run the main menu:
```bash
python -m familyfoto.cli
```

Or directly call a tool:
```bash
python -m familyfoto.commands.fotonamer --help
python -m familyfoto.commands.fotomover --input inbox --out organized
```

## 📸 Photo Workflow

See [`docs/WORKFLOW.md`](docs/WORKFLOW.md) for detailed step-by-step.

1. Import media into `inbox/`
2. Convert `.HEIC` → `.JPG` if needed
3. Extract GPS and timestamp metadata
4. Reverse geocode to get city/state/country
5. Rename files using `YYYY-MM-DD_(Street, State-City)_HHMM.jpg`
6. Move to organized folders by location/year/month
7. Summarize and clean up

## 🧠 Learn More

- 📄 [FILENAMING-OPTIONS.md](docs/FILENAMING-OPTIONS.md)
- 📄 [ORGANIZED-OPTIONS.md](docs/ORGANIZED-OPTIONS.md)
- 🌳 [RECOMMENDED-TREE.md](docs/RECOMMENDED-TREE.md)
- 📦 [SETUP-SSH-KEY.md](docs/SETUP-SSH-KEY.md)
- 🗂️ [PROJECT-DOCS.md](docs/PROJECT-DOCS.md)

## 👤 Author

**Mike Mattinson**  
GitHub: [@devmukmuk](https://github.com/devmukmuk)  
Project: [FamilyFoto](https://github.com/devmukmuk/FamilyFoto)

## 📜 License

MIT License – see [LICENSE](LICENSE) file for details.