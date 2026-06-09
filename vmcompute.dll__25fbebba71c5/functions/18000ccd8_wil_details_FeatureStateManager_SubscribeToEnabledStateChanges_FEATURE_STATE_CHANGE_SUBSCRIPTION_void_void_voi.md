# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000ccd8`
- end: `0x18000cdd0`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e280`

## callees

- `0x18000ccd8`
- `0x18000cef4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd47`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd47`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd64`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd64`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd08`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cd08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cdb6`

## string_xrefs

- `0x18000cd40`: `ntdll.dll`
- `0x18000cd5a`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
