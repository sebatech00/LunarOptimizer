# Build, sign, and verify

## Requirements

Linux, JDK 17+ (`java`, `jar`, `keytool`), Python 3, curl, unzip, and zip. Main build: Kotlin, Android platform 34, build-tools 34.0.0. Run from the project root:

```bash
bash tools/get-toolchain.sh
bash build.sh
```

Setup downloads tools and prompts for Android SDK licenses. Downloads are not yet checksum-pinned. For existing tools, set `KOTLIN_HOME`, `ANDROID_JAR`, and `BUILD_TOOLS`, or source `toolchain/env.sh`.

The D8 build compiles, dexes, packages, aligns, signs, and runs `tools/verify_dex.py`. Do not bypass a failing gate.

## Build signing

Set `KEYSTORE`, `KEY_ALIAS`, `KS_PASS`, and `KEY_PASS` privately before building. Never commit keys or credentials. Without a supplied key, the existing script creates a development key; it cannot update an app signed by another key. The script's hard-coded historical certificate fingerprint predates the current debug-key installation: compare actual certificates rather than relying on its historical match message.

## Sign the supplied APK

The APK in `` is aligned but **unsigned**. Use Android build-tools and your existing key:

```bash
apksigner sign --ks /absolute/path/to/your-private.keystore \
  --ks-key-alias YOUR_ALIAS \
  --out LunarOptimizer-3.2.0-signed.apk \
  LunarOptimizer-3.2.0-unsigned-aligned.apk
apksigner verify --verbose --print-certs LunarOptimizer-3.2.0-signed.apk
python3 tools/verify_dex.py LunarOptimizer-3.2.0-signed.apk
```

Passwords are prompted. For an existing Android debug key, `tools/sign-with-debug-key.sh` is another option; read it before use. Keep the same key for updates. Restore changes in the installed app before uninstalling a differently signed version; uninstalling deletes the rollback journal.

## JVM tests

Set `KOTLIN_HOME`, `ANDROID_JAR`, and `JUNIT_DIR` (default `/usr/share/java`, containing `junit4.jar` and `hamcrest-core.jar`):

```bash
bash build-test.sh
```

Tests use fakes for shell and journal logic. They do not prove HyperOS compatibility. The runner has historical fallback paths; explicitly set the environment variables above.

## Workflows

- **Project checks** validates publication files and the supplied APK on pushes/PRs.
- **build-apk** is manual. Read it before running: signing secrets are `KEYSTORE_B64`, `KS_PASS`, `KEY_ALIAS`, `KEY_PASS`; without them it uses a throwaway development key. It has not been executed for publication.
- **Project website** manually deploys `site/`. Enable GitHub Pages with GitHub Actions in repository settings first.
