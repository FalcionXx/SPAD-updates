# Repository Guidelines

## Structure
- Public updater repo for `SPAD`
- Keep `update.json` at repo root for GitHub Pages
- Publish APK files only through GitHub Releases assets referenced by `update.json`

## Commands
- Validate manifest locally: `python -m json.tool update.json > /dev/null`
- CI validation runs from `.github/workflows/validate-update-manifest.yml`

## Rules
- `latestVersionCode` must increase on every release
- `latestVersionName` must match the published APK version
- `apkUrl` must point to the exact GitHub Release asset
- `sha256` must match the exact uploaded APK file
