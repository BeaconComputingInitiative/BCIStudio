<!-- BEACON COMPUTING INITIATIVE | Developer Seal: CJB-DEV-2026 | Chance Joaquin Boone -->
<!-- SHA-256: see docs/HYGIENE_SHA256SUMS -->

# Repository review: BCIStudio

Reviewed: October 26, 2026. Default branch: `main`. Audited commit: `cca059b6edbed5d4eb59d0e53c07d8b1b54e9c04`.

## Verified findings and follow-up

- README accurately labels this as an extracted source baseline, not a validated standalone build.
- Source is under `upstream/` and retains bciwhisper package names. This is a recovery boundary, not evidence that a second runnable Whisper product should be maintained here.
- Missing runtime dependencies must be separated before selecting a canonical Studio launcher. Renaming or moving files now could break relative imports.
- No published releases were returned, despite a release-baseline workflow existing. Do not describe that workflow as an already published release.
- Historical version suffixes in tests identify regression coverage and are not automatically obsolete copies.

## Repository rules

- Maintain one documented current source tree and one supported starting point per product/platform. Give genuinely distinct tools purpose-based names.
- Use Git commits, branches and tags for revisions. Avoid final, latest, new, old, backup and copy suffixes on source files.
- Put downloadable builds and checksums in GitHub Releases. Keep recordings, telemetry, local environments and generated dependencies outside tracked source.
- Keep version-qualified protocol/API names and regression-test names when they describe an actual compatibility contract.
- Write commits as a concrete action and affected component, followed by the reason and relevant validation when needed. A late-night timestamp alone is not a quality defect.
- Release if and only if the documented acceptance gates pass on the exact release commit. Clearly label previews, recovered source, device validation gaps and historical releases.
- Keep the BCI header and developer seal on new authored files. Record their exact bytes in a SHA-256 manifest; do not attempt a self-referential file hash.

## Automated prevention

`Repository hygiene` runs on pushes and pull requests with read-only repository permissions. It inspects tracked files without executing project/application code. It rejects new confusing copy-style filenames, generated/runtime artifacts, recovery snapshot directories and byte-identical nonempty source copies. Existing paths are grandfathered against the audited commit, so this is prevention rather than a claim that historical issues are resolved. Empty package initializers are excluded from duplicate detection. Dataset duplicates are reported separately and left untouched.

Run locally: `python3 tools/repository_hygiene.py --baseline cca059b6edbed5d4eb59d0e53c07d8b1b54e9c04` and `sha256sum -c docs/HYGIENE_SHA256SUMS`.

This check is advisory until merged, and it does not become a mandatory branch-protection rule automatically. It cannot prove semantic equivalence, runtime correctness, README accuracy or release readiness. Intentional shared code should be extracted into a common module; deliberate compatibility exceptions require a reviewed policy adjustment.

## Review limits

The complete non-truncated default-branch tree, available branch names, up to six recent commits, and published release metadata were inspected. Selected README and status/entrypoint contents were also read. Other branch contents, full historical commits, executable dependencies, hardware behavior, secrets, and deep code correctness were not audited. No history, datasets, release assets, runtime paths or existing branches are deleted by this change.
