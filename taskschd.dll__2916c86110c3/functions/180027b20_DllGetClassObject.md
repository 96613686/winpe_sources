# DllGetClassObject

- ea: `0x180027b20`
- end: `0x180027c57`
- name: `DllGetClassObject`
- size: `311`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180027b20`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027c2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027c2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027bfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027bfe`

## pseudocode

```c

```
