# 📸 FAMILY PHOTO WORKFLOW (BatchAgent Enhanced)

Author: Mike Mattinson  
Updated: Sep/29/2025 – r3

## ✅ AUTOMATED WORKFLOW STEPS

```
✅ STEP 1 - Load config and setup folders
✅ STEP 2 - Auto-initialize PostgreSQL database if missing
✅ STEP 3 - Detect files in watch folder and form batches
✅ STEP 4 - Batch initialization:
    - Backup original files
    - Compute SHA256 and UUID
    - Identify duplicates and mark them in DB
    - Retain only 1 primary photo per hash
    - Convert .HEIC → .JPG (preserve EXIF)
    - Rename files in-place (initial UUID or timestamp-based)
    - Create batch.meta.json with status
✅ STEP 5 - Evaluate batch metadata quality
✅ STEP 6 - Extract EXIF metadata:
    - DateTimeOriginal
    - CameraModel
    - GPS coordinates
    - Store to DB
✅ STEP 7 - Reverse geocode (if GPS available):
    - Online via Nominatim API or other
    - Offline via local shapefile/CSV
    - Lookup city_id from DB
✅ STEP 8 - Rename and move photos:
    - Use geocode + timestamp to rename: YY-MM-DD_GEOCODE_HH-MM.jpg
    - Organize into folder: YYYY-MM (City, State)
    - Update status = Finalized
✅ STEP 8b - Duplicate handling:
    - If hash exists in DB, mark as DUPLICATE
    - Link duplicate to canonical source
    - Skip renaming/moving for dupes
✅ STEP 9 - Cleanup:
    - Remove empty folders in inbox/watch
    - Optionally archive source files
    - Queue thumbnail sync to PhotoPrism or Nextcloud
✅ STEP 10 - Generate summary:
    - summary.csv with camera usage, year, file type
    - contact_sheet.jpg per output folder
```

## ⚠️ SEMI-AUTOMATED & USER-ASSISTED PATHS

```
⚠️ STEP 5 - If Date but no GPS:
    - Try folder name or config-based fallback
    - Prompt for manual geotag (CLI or GUI dashboard)
⚠️ STEP 6/7 - If Date missing or malformed:
    - Mark file as status = Missing
    - Defer until human provides EXIF override or metadata patch
⛔ STEP 7 - If GPS also missing:
    - Flag for human review
    - Prompt via future dashboard or batch-level TODO
```

## 🧠 FUTURE UPGRADE IDEAS

- [ ] Predict location based on date & camera model history
- [ ] Learn camera usage patterns per user/device
- [ ] Visual dashboard to show photo clusters on map
- [ ] GUI prompt or approval panel for flagged photos
- [ ] Smart camera alias learning from repeated patterns
- [ ] Location inference using batch group clustering
- [ ] Embed thumbnail and metadata into EXIF comments or IPTC
- [ ] Add QR code to images linking to DB record (for prints)
- [ ] Editable contact sheet metadata (who/what/where)
- [ ] Photo timeline view with gaps and groupings
- [ ] GUI dashboard with status breakdown:
    - ✅ Finalized
    - ⚠️ Pending GPS
    - ⛔ No timestamp
    - ⏳ Needs user override
- [ ] Auto-test batches with edge cases and sample images
- [ ] Plugin support for custom pre-processing/post-processing
