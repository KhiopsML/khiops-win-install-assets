Khiops Windows Install Assets
=============================

This repository contains the files necessary for a Khiops installer for Windows as releases. These
are mostly installer and other rather large binaries that would be burdensome to keep in the main
repo.

Assets Release Contents
-----------------------

The `assets-info.env` contains the information of the assets in the form of environment variables.
There are three variables for each asset:
  - `<ASSET>_URL`: Source URL to download the asset.
  - `<ASSET>_FILENAME`: Output filename to use.
  - `<ASSET>_VERSION`: The version of the asset.
- The assets themselves are:
  - `MSMPI`: Microsoft MPI runtime.
  - `JRE`: Java Runtime Environment.
  - `KHIOPS_VIZ`: Khiops Visualization App.
  - `KHIOPS_COVIZ`: Khiops Co-Visualization App.
  - `SAMPLES`: Khiops sample datasets (saved to `SAMPLES_DIR`)
  - Documentation (saved to `KHIOPS_DOC_DIR`):
    - `KHIOPS_DOC`: Khiops PDF documentation guide.
    - `KHIOPS_CC_DOC`: Khiops Coclustering PDF documentation guide.
    - `KHIOPS_TUTO`: Khiops PDF tutorial.
    - `KHIOPS_VIZ_DOC`: Khiops Visualization PDF guide.
    - `KHIOPS_COVIZ_DOC`: Khiops Covisualization PDF guide.

Updating the Repository
-----------------------

The `download-assets` script uses the `assets-info.env` to update the assets. The update procedure
is as follows:
- Edit `assets-info.env` with the updated information of any of the assets.
- Commit and tag the changes
```bash
git add -u
git commit -m'Update to <VERSION>'
git tag <VERSION>
git push
git push --tags
```
- Github will create a release with the downloaded assets.
