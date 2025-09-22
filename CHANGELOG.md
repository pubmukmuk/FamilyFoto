# 📸 CHANGELOG

All notable changes to this project will be documented in this file.

## [v0.6.0] - 2025-08-25
🎉 First Official Release

### 🚀 Highlights
- First release of the **Family Foto** toolset.
- Designed for personal digital photo management and archival.
- Modular pipeline to process, convert, tag, rename, and organize photo collections.
- Photos are processed, renamed and moved and then added to Sqlite3 database, data/photos.db. The database tracks each processed photo by the photo's unique hash code.
- User's configuration file located .familyfoto/photo.config in the user's Home folder, ie, for windows, c:\users\username\.familyfoto\photo.config.

### 🧭 Workflow Features
- [x] Defined 10-step photo workflow in `WORKFLOW.md`:
  - Import photos from user-specified inbox/
  - Convert `.HEIC` to `.JPG`
  - Extract EXIF metadata (timestamp, GPS, camera model)
  - Geocode and rename based on city/state
  - Move files to structured folders to a user-specified outbox/
  - Detect and handle duplicates
  - Summarize collection by camera/year
  - Tools: remove empty folders
  - Tools: clean out junk files

### 🧰 CLI Tools
- `fotonamer.py` – Rename photos using date, location, and metadata
- `fotomover.py` – Organize photos into folders like `2025-04 (Orlando, FL)`
- `fototagger.py` – Apply tags to photos or folders
- `fotofinder.py` – Search and filter based on name, tag, date, or location
- `fotomenu.py` – Simple interactive menu interface
- 'logger.py' - logging functions

### 🧪 Test Coverage
- Initial test suite for EXIF, geolocation, and renaming logic:
  - `test_datetime.py`
  - `test_gps.py`
  - `test_reverse_geocode.py`

### 📄 Documentation
- `README.md` – Project tree and overview
- `WORKFLOW.md` – Step-by-step processing workflow
- `FILENAMING-OPTIONS.md` – Human-friendly naming formats
- `ORGANIZED-OPTIONS.md` – Folder layout strategies
- `RECOMMENDED-TREE.md` – File structure best practices

---

