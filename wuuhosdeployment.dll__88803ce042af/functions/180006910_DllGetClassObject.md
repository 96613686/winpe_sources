# DllGetClassObject

- ea: `0x180006910`
- end: `0x180006a00`
- name: `DllGetClassObject`
- size: `240`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006910`
- `0x180006b10`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006948`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180006948`

## pseudocode

```c

```
