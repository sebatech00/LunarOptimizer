# Usage and recovery

Connect Shizuku, inspect device information, and review the proposed changes. Start with a small set. Keep apps you depend on for messages, alarms, authentication, accessibility, or device management out of background restrictions.

The journal records supported original values, verifies restoration, and tracks overlapping owners. Failed restoration remains recorded.

| Operation | Recovery limits |
| --- | --- |
| Journaled settings/background controls | Restore through the corresponding feature while records remain intact. |
| Disabled package | Re-enable through Debloat or matching restore controls. |
| Preinstalled package removed for user 0 | `install-existing` can restore it when the system copy remains. Data recovery is not guaranteed. |
| Cache cleanup | Apps regenerate caches; previous contents are not restored. |
| Deleted junk/user file | No journal recovery. Check paths and selections before deleting. |
| Compilation/process termination | Not an exact restoration of runtime state; Android manages later launches. |

Do not clear app data or uninstall while you still need original-value records.

Compare results under the same firmware, temperature, charge state, apps, and workload. Benchmark comparisons require three runs per side; the 3% noise threshold is a project heuristic, not statistical proof. Pack launch timing deliberately starts the selected app. Frame metrics and long-term battery tests remain unfinished.

If a command is refused, preserve the error and exact OS/permission state. Restore any changes already made rather than repeatedly applying broad profiles.
