# DllGetClassObject

- ea: `0x18000f1e0`
- end: `0x18000f35a`
- name: `DllGetClassObject`
- size: `378`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002840`
- `0x180007e04`
- `0x18000f1e0`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f2af`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f2af`

## pseudocode

```c

```
