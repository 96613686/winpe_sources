# DllGetClassObject

- ea: `0x180016370`
- end: `0x1800165da`
- name: `DllGetClassObject`
- size: `618`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180016370`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001639f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001639f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016463`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016463`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001658b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001658b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800164b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800165a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800164b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800165a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001651c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001651c`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001647f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180016568`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001647f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180016568`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001653c`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001653c`

## pseudocode

```c

```
