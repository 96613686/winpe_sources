# CImmersiveState::UpdateInfoIfTaskbar(CWindowData const *)

- ea: `0x18001a374`
- end: `0x18001a517`
- name: `?UpdateInfoIfTaskbar@CImmersiveState@@AEAA_NPEBVCWindowData@@@Z`
- size: `419`
- prototype: `bool __fastcall(CImmersiveState *__hidden this, const struct CWindowData *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x18001bbb4`

## callees

- `0x18001a374`
- `0x18006c718`
- `0x180095130`
- `0x1800e6074`

## import_xrefs

- `USER32!GetClassNameW` at `0x18001a3ba`
- `USER32!GetClassNameW` at `0x18001a3ba`
- `USER32!MonitorFromWindow` at `0x18001a423`
- `USER32!MonitorFromWindow` at `0x18001a423`
- `USER32!GetMonitorInfoW` at `0x18001a477`
- `USER32!GetMonitorInfoW` at `0x18001a477`

## pseudocode

```c

```
