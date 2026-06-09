# DllGetClassObject

- ea: `0x18004cb20`
- end: `0x18004ccdc`
- name: `DllGetClassObject`
- size: `444`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004cb20`
- `0x18004cce4`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004cc6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004cc98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004cca3`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004cb63`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18004cb63`
- `RPCRT4!NdrDllGetClassObject` at `0x18004cc2c`
- `RPCRT4!NdrDllGetClassObject` at `0x18004cc2c`

## pseudocode

```c

```
