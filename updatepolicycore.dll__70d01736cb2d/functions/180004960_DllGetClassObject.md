# DllGetClassObject

- ea: `0x180004960`
- end: `0x180004a63`
- name: `DllGetClassObject`
- size: `259`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004960`
- `0x180005fc4`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a0d`

## pseudocode

```c

```
