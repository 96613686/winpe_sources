# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000df00`
- end: `0x18000e00d`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18000d54c`
- `0x18000d648`
- `0x18000df00`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dfa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000df8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dff7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dff7`

## string_xrefs

- `0x18000df83`: `ntdll.dll`
- `0x18000df97`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
