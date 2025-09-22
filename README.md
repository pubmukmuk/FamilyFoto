# 📸 FamilyFoto CLI Toolkit

**FamilyFoto** is a modular, scriptable command-line pipeline for organizing, renaming, tagging, and archiving family photos and videos. It supports metadata extraction, GPS reverse geocoding, duplicate detection, and flexible folder structures — ideal for large-scale personal or historical media libraries.

## 📦 Release History

### Release: v0.6.0 - 2025-08-25


## 👤 Author
<br>Lead: Mike Mattinson
<br>GitHub.com/devmukmuk devmukmuk@gmail.com
<br>GitHub.com/pubmukmuk pubmukmuk@gmail.com
<br>GitHub.com/MikeMMattinson mike.mattinson@gmail.com

## 🚀 Features

- ✅ Import from phone backups, SD cards, scanned archives
- 🕵️‍♂️ Extract EXIF metadata including timestamps, GPS, camera model
- 🌍 Reverse geocode GPS data to derive City, State, Country
- 🏷️ Rename files based on date, location, and camera info
- 📂 Organize into flexible folder structures by decade, city, or flat
- 🔁 Detect and skip duplicates using SHA256 hashes
- 📊 Generate summaries and logs for QA and audits


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
python -m familyfoto --config ./test_data/config.ini menu
```


## 📜 License

MIT License – see [LICENSE](LICENSE) file for details.