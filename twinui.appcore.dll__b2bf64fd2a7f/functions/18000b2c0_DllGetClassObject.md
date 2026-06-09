# DllGetClassObject

- ea: `0x18000b2c0`
- end: `0x18000b4ea`
- name: `DllGetClassObject`
- size: `554`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b2c0`
- `0x180012360`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b2ef`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000b2ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b3a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b3a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b3ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b3ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b457`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b457`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4c9`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b471`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000b471`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b3c1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b4ac`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b3c1`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000b4ac`

## pseudocode

```c

```
