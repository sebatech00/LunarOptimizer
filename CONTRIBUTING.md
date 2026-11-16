# Contributing

Start with README.md and STATUS.md; historical plans may describe older behavior.

Reports should include device, exact Android/HyperOS build, Lunar version, Shizuku state, reproduction steps, expected/actual behavior, and the smallest useful redacted log. Remove serial numbers, account identifiers, and network details.

For system changes, explain the mechanism, original-state read, apply verification, failure behavior, restore path, and overlapping ownership. Add meaningful failure-path tests where appropriate. Label experimental features and preserve normal animations by default.

Run JVM tests for logic changes and the DEX gate for APKs. Distinguish local checks from device tests. Never commit signing keys, credentials, or other users' logs. The application-wide license is pending; record the origin and terms of third-party additions.
