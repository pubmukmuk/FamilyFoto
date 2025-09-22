## FAMILY PHOTO WORKFLOW - v1.0.0

### 🔧 STEP 1: Configuration and Setup
- Define default folders (`inbox`, `outbox`, `log`, `watch`, 'backup')
- Create a `photo.config` file for:
  - default timezone
  - GPS fallback (manual entry, default location, etc.)
  - camera model aliases
  - filename template
- Load configuration at runtime
- Update default folders during runtime

### STEP 2: Setup PostgreSQL Database

### 📥 STEP 3: Move Photos Into Watch Folder

### STEP 4: BATCH AGENT DETECTS PHOTOS
- Agent creates small batches of photos from Watch in groups of 300-500 files
- Backup original photos to Backup
- Moves batch of photos into Inbox
- Creates a database record with UUID and Hash256 for everyphone
- Identifies duplicates and updates status to 'DUPLICATE'
- One file will be the primary
- After backing up files, renames every file in-place
- Converts .HEIC to .JPG and retains all original EXIF metadata
- Batch is able to keep groups of related photos and videos together
- Copies selected EXIF metadata to the database [LinkText](../docs/EXIF-TAGS-r1.md)
- Create, modify and move the batch.meta.json with batch details and status
- Agent is able to make a determination of the basic geo-region of the group of batch photographs, the basic timeframe and the camera identification

### STEP 5: User Processes a Batch
- Uses FamilyFoto modules
- Verifies or overrides file and/or folder name
- Moves files to Outbox according to folder naming specifications

#### STEP 5A. From GPS-enabled sources - Quick
- iPhone, Android, modern digital cameras
- Copy directly to `watch/` folder preserving original structure
- No immediate conversion needed

#### STEP 5B. From non-GPS sources - Not Quick
- Import scans, old digital cameras, or downloaded files
- Mark for manual geotagging or use folder context as hints
- Add fallback logic in the pipeline

### 🔍 STEP 6: Extract Metadata
- Read EXIF metadata: `DateTimeOriginal`, `CameraModel`, `GPS`
- Store in database:
  - filename
  - timestamp
  - latitude / longitude
  - camera model
  - hash
  - status (Initialized, Located, Finalized, Named, Renamed, Moved, Duplicate, Missing)
- Flag:
  - ✅ Date + GPS present (fully automatic)
  - ⚠️ Date only (requires geocoding or manual input)
  - ⛔ Missing EXIF (prompt for human input)

### 🌍 STEP 7: Reverse Geocode GPS ONLINE
- Use `geopy.Nominatim` or another API
- Derive: Street, City, State/Country
- Find matching city_id from cities table
- Update database

### 🌍 or, STEP 7: Reverse Geocode GPS OFFLINE
- Use publicly available geodata to reverse geocode each photo to the nearest known city, state, county, or country
- Find matching city_id from cities table
- Update database

### 🏷️ STEP 8: Rename & Organize
- Generate `GEOCODE` (short ID from location)
- Rename files to: `YY-MM-DD_GEOCODE_HH-MM.jpg` according to user specification (photo.config)
- Move to folders by `YY-MM (City, State)` according to user specifications (photo.config)

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
- Create contact sheets for every folder with thumbnail images of the images in that folder

### 📋 FUTURE IDEAS
- Photo rating or tagging system
- Location clustering and map preview
- Dashboard with pending photos needing action
- GUI wrapper for `fffcli.py`

Author: Mike Mattinson
Updated: Aug/24/20215 - r1
Updated: Aug/28/2025 - r2