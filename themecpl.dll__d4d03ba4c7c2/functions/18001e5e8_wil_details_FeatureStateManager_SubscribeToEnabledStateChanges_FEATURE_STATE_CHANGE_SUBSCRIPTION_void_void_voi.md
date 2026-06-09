# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18001e5e8`
- end: `0x18001e6e0`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `248`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ec60`

## callees

- `0x18001e5e8`
- `0x18001e7fc`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e674`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e674`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e657`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e657`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e618`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e618`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6c6`

## string_xrefs

- `0x18001e650`: `ntdll.dll`
- `0x18001e66a`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c

```
