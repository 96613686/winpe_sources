# DllGetClassObject

- ea: `0x180028a00`
- end: `0x180028af0`
- name: `DllGetClassObject`
- size: `240`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004120`
- `0x180025a40`
- `0x180028a00`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028a38`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028a38`

## pseudocode

```c

```
