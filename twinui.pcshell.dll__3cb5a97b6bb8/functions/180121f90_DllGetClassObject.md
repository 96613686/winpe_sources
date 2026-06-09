# DllGetClassObject

- ea: `0x180121f90`
- end: `0x1801221c2`
- name: `DllGetClassObject`
- size: `562`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180121f90`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180121fbd`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180121fbd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012209a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18012209a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180122117`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180122117`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801220cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801220cd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180122155`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180122169`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180122155`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180122169`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180122129`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180122174`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180122129`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180122174`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1801220b8`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1801220b8`

## pseudocode

```c

```
