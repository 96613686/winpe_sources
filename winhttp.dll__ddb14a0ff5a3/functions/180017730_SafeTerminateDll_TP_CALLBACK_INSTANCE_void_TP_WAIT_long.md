# SafeTerminateDll(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x180017730`
- end: `0x180017820`
- name: `?SafeTerminateDll@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `240`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE pci, HANDLE hObject, struct _TP_WAIT *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800176f0`

## callees

- `0x180017730`
- `0x18001851c`
- `0x1800a1d10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017799`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001780c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017799`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001780c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800177f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001776a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001776a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017803`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180017803`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017789`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017789`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180017778`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x180017778`

## pseudocode

```c

```
