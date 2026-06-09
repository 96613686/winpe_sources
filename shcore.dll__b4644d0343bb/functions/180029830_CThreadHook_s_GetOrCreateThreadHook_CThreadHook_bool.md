# CThreadHook::s_GetOrCreateThreadHook(CThreadHook * *,bool *)

- ea: `0x180029830`
- end: `0x180029923`
- name: `?s_GetOrCreateThreadHook@CThreadHook@@CAJPEAPEAV1@PEA_N@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct CThreadHook **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180029794`

## callees

- `0x180023730`
- `0x180029830`
- `0x180068d9c`
- `0x180092464`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002985e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18002985e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029898`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800298e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800298e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002987b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002987b`

## pseudocode

```c

```
