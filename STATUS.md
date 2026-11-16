# Current project status

Publication snapshot: 2026-11-16. App **3.2.0**, versionCode **16**, ID `com.lunaroptimizer.app`, minSdk **30**, target/compile SDK **34**.

| Item | Evidence |
| --- | --- |
| Supplied source ZIP | Integrity checked; original preserved under ``. |
| Supplied APK | ZIP integrity checked; requires signing. |
| DEX check | Passed: DEX 038, 1,784 classes, zero call-site IDs and zero methods using `invoke-custom`. Structural check only. |
| Unit tests | 61 `@Test` annotations. Historical handover reports 61 passing JVM tests; not rerun for publication. |
| Compilation | Not rerun; no Kotlin/Android build toolchain available here. |
| Device behavior | No installation, real-device recovery test, or HyperOS parser verification performed here. |

## Known limitations

- `Pipeline.measure` still has placeholder frame/jank/percentile and general cold-start fields. The separate Pack launch test exists; complete animation measurement does not.
- No battery-life or benchmark gain is established by this publication.
- Shell commands, output formats, allowed settings, and package names vary by firmware.
- Shizuku uses a patched `newProcess` path; migration to UserService remains future work.
- Recovery covers supported journaled state. Deleted files and caches cannot be restored, and not every operation is reversible.
- Historical handover/audit/plan entries can be stale. Start with the README and this document.
- Gradle has no wrapper and is unverified. D8 is the intended build path; legacy dx scripts are historical.
- Downloads are not checksum-pinned. Stable signing, application licensing, and artwork provenance remain maintainer decisions.

## Publication changes

Added current documentation, notices, contribution guidance, issue forms, checksums, a landing page, workflows, and a publishing helper. Removed obsolete signature sidecars and Python bytecode from the editable copy. Android sources, resources, and supplied downloads remain unchanged.
