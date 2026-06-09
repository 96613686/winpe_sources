# DllGetClassObject

- ea: `0x180032760`
- end: `0x180032994`
- name: `DllGetClassObject`
- size: `564`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180032760`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003278f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003278f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003290e`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003290e`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180032862`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180032955`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180032862`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x180032955`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003288e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003294a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003288e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18003294a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800328f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800328f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032923`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180032923`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032850`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180032850`

## pseudocode

```c

```
