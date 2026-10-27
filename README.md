<!-- BEACON COMPUTING INITIATIVE | Developer Seal: CJB-DEV-2026 | Chance Joaquin Boone -->
<!-- SHA-256: see docs/HYGIENE_SHA256SUMS from the repository root -->

# BCIStudio

Podcast production and multitrack audio workspace, developed independently from [BCIWhisper](https://github.com/BeaconComputingInitiative/BCIWhisper).

**Developer:** Chance Joaquin Boone · **Developer Seal:** CJB-DEV-2026  
**Status:** recovered source baseline; no verified standalone executable or published release.

## What is here

The `upstream/` directory consolidates Studio work from Whisper scripts 59.0–60.0. It includes the podcast transport, secondary capture, multitrack recording, timeline, program bus, QML workspaces and 3D visualization. These are imported sources; their presence does not establish a functioning independent application.

**Source provenance:** [Whisper commit a0fd61376e05](https://github.com/BeaconComputingInitiative/BCIWhisper/tree/a0fd61376e05dcd9be44887ddbf0875bf3fbf65f).

| Path | Purpose |
| --- | --- |
| `upstream/bciwhisper/` | Extracted Studio runtime, UI and supporting modules |
| `upstream/tests/` | Imported regression tests |
| `upstream/requirements-qml-desktop.txt` | Imported dependency reference; not an independent Studio setup |
| `.github/workflows/release-studio-baseline.yml` | Manual source-archive packaging, syntax gate and SHA-256 manifests |

## Development boundary

Do not advertise a runnable installer yet. The import still needs its missing Whisper dependencies resolved, a Studio-owned entry point and packaging definition, tests against the complete runtime, and device validation for synchronized capture, recording and playback. Syntax compilation alone is insufficient.

```bash
python3 -m compileall -q upstream/bciwhisper upstream/tests
sha256sum -c docs/HYGIENE_SHA256SUMS
```

Source archives may be produced manually after their packaging gates pass. They must remain labeled source-only previews until standalone acceptance succeeds. The release workflow no longer publishes merely because its own file changes.

See [commit audit](docs/PORTFOLIO_AUDIT.md) and [maintenance rules](docs/REPOSITORY_HYGIENE.md). Historical Studio downloads remain under Whisper until a verified replacement exists here.
