##================= Sprint Closeout & Release Tag Checklist =================

Release: _________ Major   _________ Minor  _________ Patch 

Type:   [   ] alpha    [   ] beta    [    ] dev   [    ] public

Date/Time Begin:   ____________________________________________

Released by: _________________________________________

NOTE. You should begin this checklist in the main, clean

1. Final Code Commit 
   [ ] Create branch, 'git checkout -b sprint/0-4-0-dev'
   [ ] Ensure all feature/bugfix branches are merged to `main`  
   [ ] Clear Problems [Show Warnings] [Show Errors] in IDE:  
   [ ] Address runtime or type-checking errors  
   [ ] Review and resolve compiler warnings:   
   [ ] Search "Show Infos" `TODO`, `FIXME`, `HACK` comments:  
   [ ] Convert critical items into GitHub issues  
   [ ] Add `// TODO (backlog)` to non-sprint TODOs  
   [ ] Remove stale or irrelevant TODOs 

2. Final release dashboard     
   [ ] Label open issues [CARRYFORWARD] and move to later milestone
   [ ] Generate final sprint dashboard, 'python ./tools/dashboard.py --milestone v0.04.0 --save'
   [ ] Copy to 'docs/release/v0.4.0/dashboard-v0.4.0.txt' 

3. Run Final Maven Tests and Build  
   [ ] `./tools/run-tests.sh` - mvn clean test 
   [ ] Review output `test-results` - latest applicable test
   [ ] Append 'tag v0.4.0' to the test folder 
   [ ] From space folder, `mvn clean install`  
   [ ] Verify final `.jar` and assets in `target/`  
   [ ] Copy final .jar folder to test desktop
   [ ] Run .jar from terminal, 'java -jar .\Orbis-0.4.0.jar'
   [ ] Run verification test case
   [ ] Verify no runtime exceptions
   [ ] Verify logs   

4. Create Temporary Tag for Release Summary  
   [ ] Run: `git tag -a v0.4.0 -m "Draft release v0.4.0"` (DO NOT push)

5. Generate Release Summary  
   [ ] Run: `./release-summary.sh v0.3.0 v0.4.0`  
   [ ] Copy output and update:  
   [ ] `CHANGELOG.md`  
   [ ] `README.md` (if version/date listed)  
   [ ] Any version metadata files (`BuildInfo`, `VERSIONS.csv`, etc.)

6. Delete Temporary Tag  
   [ ] Run: `git tag -d v0.4.0`

==============PAGE BREAK===============
<div style="page-break-after: always;"></div>

7. Generate Final Documents  
   [ ] Review and update `README.md` with:  
   [ ] New features added  
   [ ] Any updated dependencies  
   [ ] Notable instructions for usage or new tools  
   [ ] Update `CHANGELOG.md` with summary of sprint deliverables  
   [ ] Confirm `USAGE.md`, `VERSIONS.csv`, and milestone files reflect final state

8. Commit Final Documents  
   [ ] Run: `git add CHANGELOG.md README.md`  
   [ ] Run: `git commit -m "📄 Update changelog and docs for v0.4.0 release"`

9. Create Final Release Tag  
   [ ] Run: `git tag -a v0.4.0 -m "Release v0.4.0"`  
   [ ] Run: `git push origin v0.4.0`

git tag -d v0.4.0                      # delete local tag
git push origin :refs/tags/v0.4.0     # delete remote tag
git tag -a v0.4.0 -m "Release v0.4.0" # create new tag
git push origin v0.4.0                # push new tag
git log v0.3.99..v0.4.0 > docs/releases/v0.04.0/GIT-LOG-v0.4.0.txt

10. Create Sprint Artifacts  
   [ ] Run or update scripts in `scripts/`:  
   [ ] `scripts/create-chat-bundle-zip.py`  
   [ ] `scripts/github_dashboard.py`  
   [ ] Save bundle as `chat-bundles/sprint-vX.Y.Z.zip`  
   [ ] Create `docs/releases/sprint-vX.Y.Z.md` with:  
   [ ] Tag  
   [ ] Date  
   [ ] Summary  
   [ ] Contributors  
   [ ] Key commits / PRs

11. Close GitHub Milestone  
   [ ] Review milestone issues:  
   [ ] Mark completed  
   [ ] Label uncompleted as `carry-forward`  
   [ ] Close milestone `vX.Y.Z`

12. Start Next Sprint Prep  
   [ ] Create new milestone `vX.Y+1.0`  
   [ ] Optionally create branch `sprint/x-y-z-dev`  
   [ ] Groom backlog and select next sprint stories

13. Notify Team / Stakeholders  
   [ ] Share release summary and tag reference  
   [ ] Confirm milestone closed on GitHub  
   [ ] (Optional) Draft release notes on GitHub using `CHANGELOG.md`

Date/Time Completed:   ____________________________________________

##============================================================================
