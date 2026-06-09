# wil::details::WilApiImpl_SubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x180050cb0`
- end: `0x180050dbd`
- name: `?WilApiImpl_SubscribeFeatureStateChangeNotification@details@wil@@YAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `269`
- prototype: `void __fastcall(struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18004ed10`
- `0x18004ee0c`
- `0x180050cb0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050da7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050da7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050d00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050d00`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050d51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050d51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180050d3a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180050d3a`

## string_xrefs

- `0x180050d33`: `ntdll.dll`
- `0x180050d47`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
