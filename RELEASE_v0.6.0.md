📦 Release: v0.6.0 – First Public Alpha Release
Release Date: 2025-08-25
Milestone: [v0.06.0 - 2025W35 Sprint](https://github.com/MikeMMattinson/FamilyFoto/milestone/6)
Tag: v0.6.0
Branch: main (merged from sprint/0-6-0-dev)
Built with: Python 3.13.5

✨ Highlights
This marks the first official alpha release of the FamilyFoto CLI toolset — designed to organize and preserve large family photo collections using EXIF metadata, GPS coordinates, and human-friendly file structures.

🧰 Included CLI Tools
- cli.py — CLI entrypoint
- fotonamer — rename photo files by date, location, and metadata
- fotomover — move photos into organized folders
- fototagger — apply tags to photos
- fotofinder — locate photos by name, folder, tag, or date
- fotomenu — interactive terminal-based menu for running tools
- treeviewer — console tree of folder structure

📄 Core Features
✅ EXIF metadata extraction (date, GPS, camera)
✅ Automatic reverse geocoding using geopy.Nominatim
✅ Filename generation using flexible templates (FILENAMING-OPTIONS.md)
✅ Folder structure support (ORGANIZED-OPTIONS.md, RECOMMENDED-TREE.md)
✅ Support for .HEIC → .JPG conversion using pillow_heif
✅ Detect and log duplicates via SHA256
✅ Configurable settings via photo.config
✅ Unit tested core utilities (get_exif_data, get_gps_from_exif, etc.)

Test Coverage
$ python -m pytest -v
✅ test_reverse_geocode.py — 2 tests passed
✅ test_gps.py — 1 test passed, 1 expected failure (missing file)
✅ test_datetime.py — 1 test failed (missing file)
➕ Assets folder added for future test data (tests/assets/test_known_gps.jpg)

📁 Folder Conventions
📥 inbox/         # Raw photo dumps
📤 organized/     # Final output by date + location
📚 log/           # Metadata, debug, and summary logs

📦 Distribution
✅ .exe build via pyinstaller (tools/build_exe.py)
✅ Supports portable CLI deployments (no installer needed)

🛠 Known Issues
📸 Missing test image inbox/test.JPG causes 2 unit test failures
🐛 GUI wrapper not yet implemented (planned for future milestone)
🌐 Reverse geocoding relies on live internet access to Nominatim

Release: v0.6.0
Lead: Mike Mattinson
Updated: Aug/25/2025

