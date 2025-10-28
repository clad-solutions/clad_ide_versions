# Chad IDE Version Manifests

Public repository for auto-update manifests. Chad IDE checks these files to discover new versions.

## Directory Structure

```
stable/darwin/arm64/latest.json  - macOS Apple Silicon (M1/M2/M3)
stable/darwin/x64/latest.json    - macOS Intel
```

## JSON Schema

Each `latest.json` file contains:

```json
{
  "url": "https://github.com/clad-solutions/clad_ide_binaries/releases/download/{version}/Chad-darwin-{arch}-{version}.zip",
  "name": "{version}",
  "version": "{vscode-commit-hash}",
  "productVersion": "{version}",
  "hash": "{sha1-of-zip}",
  "timestamp": {unix-timestamp-ms},
  "sha256hash": "{sha256-of-zip}"
}
```

## Update Process

These files are automatically updated by the `clad_builder_void` CI pipeline after a successful build, signing, and notarization.

Users do not need authentication to read these files - they are fetched via GitHub Raw URLs.
