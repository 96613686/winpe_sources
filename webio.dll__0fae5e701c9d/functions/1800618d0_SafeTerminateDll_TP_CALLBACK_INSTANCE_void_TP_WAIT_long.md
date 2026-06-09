# SafeTerminateDll(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800618d0`
- end: `0x1800619f5`
- name: `?SafeTerminateDll@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `293`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE pci, HANDLE hObject, struct _TP_WAIT *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180061790`

## callees

- `0x1800618d0`
- `0x1800619fc`
- `0x1800722f0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18006190a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18006190a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006194b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800619db`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006194b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800619db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006198c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800619bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006198c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800619bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061935`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061935`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18006191e`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x18006191e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800619cc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800619cc`

## pseudocode

```c

```
