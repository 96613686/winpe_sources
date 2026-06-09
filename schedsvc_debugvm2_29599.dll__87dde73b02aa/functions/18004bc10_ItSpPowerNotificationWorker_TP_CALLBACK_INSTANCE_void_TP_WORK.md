# ItSpPowerNotificationWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x18004bc10`
- end: `0x18004bc9d`
- name: `?ItSpPowerNotificationWorker@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `141`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004bc10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bc2c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004bc2c`
- `ntdll!RtlReleaseSRWLockShared` at `0x18004bc79`
- `ntdll!RtlReleaseSRWLockShared` at `0x18004bc79`
- `ntdll!RtlAcquireSRWLockShared` at `0x18004bc3c`
- `ntdll!RtlAcquireSRWLockShared` at `0x18004bc3c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004bc87`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004bc87`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18004bc70`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18004bc70`

## pseudocode

```c

```
