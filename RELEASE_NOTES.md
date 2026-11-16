Lunar Optimizer 3.2.0 is an experimental native Android toolkit targeting Xiaomi 14 / HyperOS 3, with Android 11+ as the minimum.

The source includes device diagnostics, reviewed optimizer steps, Lunar Pack, automatic app recommendations, debloat, selected Deep Clean actions, a read-only audio report, benchmark readiness and score comparison, and a journal for supported system changes.

### Downloads

- `LunarOptimizer-3.2.0-unsigned-aligned.apk`: original supplied APK, unchanged and **unsigned**. Sign it with your own trusted key before installation. The certificate must match an existing installation to update it.
- `LunarOptimizer-source-3_2_0.zip`: original supplied source archive, unchanged. Refreshed project documentation lives in the repository.
- `SHA256SUMS`: checksums for both supplied files.

### Validation and current limits

Both downloads passed ZIP integrity checks. The supplied APK passed the included DEX verifier with no invoke-custom call sites. Source contains 61 unit test annotations; tests were not rerun for publication. No phone installation or performance validation was performed here. General frame/jank measurement remains incomplete, and no battery-life or smoothness improvement is established.

Read the build/signing, privacy, and recovery guides before installing or making system changes. Uninstalling or clearing app data erases the rollback journal; deleted files and caches cannot be restored by it. Application-wide licensing and artwork provenance remain pending.
