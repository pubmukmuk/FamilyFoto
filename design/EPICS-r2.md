
# 📦 FamilyFoto Project – Epics and Task Summary

## 🧩 ConfigSystem
- [ ] Create photo.config and environment file support
- [ ] Define default input/output/temp/log folders
- [ ] Load configuration at runtime and expose via config_utils

## 🧩 ImportPhotos
- [ ] Support import from GPS-enabled devices
- [ ] Support import from scans and old cameras
- [ ] Preserve original folder structure on copy

## 🧩 ConvertMedia
- [ ] Convert HEIC to JPG using pyheif or pillow-heif
- [ ] Maintain original timestamps
- [ ] Log all conversion results

## 🧩 ExtractMetadata
- [ ] Extract DateTimeOriginal, CameraModel, GPS
- [ ] Write metadata to coordinates.csv
- [ ] Add UUID and hash to each photo

## 🧩 Geolocation
- [ ] Perform reverse geocoding using geopy
- [ ] Generate city and street codes
- [ ] Cache results and update coordinates.csv

## 🧩 Filenaming
- [ ] Generate filenames using config template
- [ ] Support multiple formats (ISO, Compact, Narrative)
- [ ] Integrate GEOCODE and timestamps into filenames

## 🧩 OrganizeFolders
- [ ] Move files to folders based on year and location
- [ ] Support folder structures: Flat, Hybrid, Location-first
- [ ] Preserve originals in optional backup folder

## 🧩 DuplicateDetection
- [ ] Generate SHA256 hash of photo files
- [ ] Detect and record duplicates in duplicates.txt
- [ ] Skip or reference duplicate entries

## 🧩 SummarizeCollection
- [ ] Generate summary.csv grouped by year, camera, and type
- [ ] Include stats for visual QA
- [ ] Run summary via CLI or cron job

## 🧩 PhotoTagging
- [ ] Add CLI support for tagging files or folders
- [ ] Store tags in metadata or sidecar file
- [ ] Support tag-based queries later

## 🧩 FinderCLI
- [ ] Implement CLI to search by name, folder, tag, or date
- [ ] Use rich output to preview results
- [ ] Support fuzzy matching and filters

## 🧩 Dashboard
- [ ] Build CLI dashboard to view system status
- [ ] List photos needing action (GPS/date/tag)
- [ ] Allow human-in-the-loop fixes

## 🧩 SecureStorage
- [ ] Organize backups of originals
- [ ] Validate integrity using hash check
- [ ] Support sync/archive to external drive or cloud

## 🧩 GUIWrapper
- [ ] Design optional GUI around fffcli.py
- [ ] Provide family-friendly access to view or rename photos
- [ ] Enable tagging and basic search from GUI

## 🧩 FinalPolish
- [ ] Cleanup unused scripts and temp files
- [ ] Write README, usage docs, versions.csv
- [ ] Run final integration tests

## 🧩 DataAndSQL
- [ ] Design FamilyFoto schema, uml and readme
- [ ] Add `init_database.py` to create tables and indexes
- [ ] Refactor all scripts to use centralized DB connection (via `data_utils.get_connection()`)
- [ ] Migrate metadata from `coordinates.csv` into SQL tables
- [ ] Implement database backup tool (manual + automated)
- [ ] Write SQL queries for:
  - [ ] Photo counts by year/month/camera
  - [ ] Missing GPS or Date
  - [ ] Duplicate detection summary
- [ ] Add utility to export SQL reports to CSV or markdown
- [ ] Support database config in `photo.config`
- [ ] Add test cases for DB logic
- [ ] Track all EXIF and geocode status changes in SQL
- [ ] Track photo renaming, moving and deletion changes in SQL

<br>Author: ChatGPT 4o
<br>Author: Mike Mattinson
<br>Updated: Aug/25/2025 - r1
<br>Updated: Aug/27/2025 - r2 - add data/sql
