# TESector Android experimental build attempt

This is **NOT a working APK**. It is a GitHub Actions build workflow added to the supplied SS14 Mobile source ZIP.

## Purpose
1. Check out JasmineRickards/TESector at the selected commit.
2. Use TESector's own pinned RobustToolbox submodule (or an explicitly supplied engine commit).
3. Verify the original Android port's engine and client patches apply, and fail clearly if not.
4. Attempt an Android APK build and upload it as a GitHub Actions artifact only if all stages succeed.

## Run
Create a GitHub repository from the contents of this ZIP (including `.github/workflows/tesector-android.yml`). Open **Actions > TESector Android compatibility build (experimental) > Run workflow**. Set `tesector_ref` to the commit deployed on the live server if known. Do NOT assume `master` matches the server.

## Known blockers
- The archive originally has no contents in the `space-station-14/` and `RobustToolbox/` directories: those are unpopulated Git submodules in a GitHub source ZIP.
- The Android patches were developed for a different engine/content revision. They are likely to fail against TESector and will need manual adaptation.
- Exact network compatibility requires the **deployed** TESector and RobustToolbox commits, not just a version string.
- GitHub Actions has not been run here. No APK exists yet, and connection to 169.0.198.75:1213 has not been tested.
- This workflow is exploratory, and its source code and build tooling may require further changes.
