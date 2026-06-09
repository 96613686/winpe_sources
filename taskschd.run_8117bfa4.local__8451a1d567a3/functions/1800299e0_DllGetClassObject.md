# DllGetClassObject

- ea: `0x1800299e0`
- end: `0x180029b2b`
- name: `DllGetClassObject`
- size: `331`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800299e0`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029af2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029af2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029abf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029abf`

## pseudocode

```c

```
