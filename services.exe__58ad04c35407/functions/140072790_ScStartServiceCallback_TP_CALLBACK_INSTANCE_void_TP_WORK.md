# ScStartServiceCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140072790`
- end: `0x140072822`
- name: `?ScStartServiceCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `146`
- prototype: `void(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_WORK *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x140007960`
- `0x14001761c`
- `0x140072790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400727d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400727d0`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1400727a0`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x1400727a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x14007281b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400727da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400727da`
- `ntdll!RtlFreeHeap` at `0x140072808`
- `ntdll!RtlFreeHeap` at `0x140072808`

## pseudocode

```c

```
