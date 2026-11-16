# Privacy note

Scope: supplied 3.2.0 application source inspected on 2026-11-16. This describes observed implementation, not future versions.

Device/package metadata, diagnostics, and usage/battery information are read where permissions allow. Settings, rollback records, errors, change history, battery samples, keep-list choices, and benchmark scores live in app-private storage. Crash text may be shown on the next launch. Android app backup is disabled.

No account system, advertising/analytics SDK, or automatic log upload was found. Manual clipboard export is present. Subsequent sharing depends on its destination. Clearing data or uninstalling deletes private records.

## DNS and external services

`Net.blocked()` resolves `example.com`, then these hosts through the configured DNS resolver:

- `tracking.intl.miui.com`
- `data.mistat.intl.xiaomi.com`
- `sdkconfig.ad.intl.xiaomi.com`
- `api.ad.intl.xiaomi.com`
- `adv.sec.miui.com`
- `globalapi.ad.xiaomi.com`

These are DNS lookups, not HTTP requests to tracker domains. The optional DNS tweak changes Android Private DNS to the provider shown in the app; that provider's privacy practices apply. Review and preserve the previous setting.

The Shizuku download control opens its external page in a browser. Build-tool downloads happen on the build computer, separately from app runtime behavior.

## Project website

The static landing page has no analytics, forms, page-set cookies, or external font loads. Links open GitHub or Shizuku. Hosting providers may process normal request information under their own policies.
