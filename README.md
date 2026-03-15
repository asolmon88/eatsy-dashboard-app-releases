# Eatsy Dashboard App Releases

This repository hosts public Windows release artifacts for the Eatsy Dashboard App.

Stable update manifest:
`latest/update-manifest.json`

## Naming Conventions

- Release tags: `vX.Y.Z`
  - Example: `v1.0.0`
- Windows installer filename: `eatsy-orders-setup.exe`
- Checksum filename: `eatsy-orders-setup.exe.sha256`

## Release Checklist

1. Bump the app version in the private source repo `pubspec.yaml`.
2. Build the Windows release from the private source repo.
3. Package the Windows app as `eatsy-orders-setup.exe`.
4. Generate the SHA-256 checksum for the installer and save it as `eatsy-orders-setup.exe.sha256`.
5. Create a GitHub Release in this repo using tag format `vX.Y.Z`.
6. Upload these assets to the GitHub Release:
   - `eatsy-orders-setup.exe`
   - `eatsy-orders-setup.exe.sha256`
7. Update `latest/update-manifest.json` with:
   - `latest_version`
   - `minimum_supported_version`
   - `installer_url`
   - `sha256`
   - `notes`
   - `published_at`
8. Commit and push the updated stable manifest.
9. Verify that:
   - the manifest URL is publicly readable
   - the installer URL downloads without authentication
   - the manifest `sha256` matches the published installer exactly
