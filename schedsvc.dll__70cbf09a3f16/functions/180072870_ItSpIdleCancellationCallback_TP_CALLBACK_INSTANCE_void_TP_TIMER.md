# ItSpIdleCancellationCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180072870`
- end: `0x1800728f5`
- name: `?ItSpIdleCancellationCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `133`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180072870`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007289c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007289c`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800728d1`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800728d1`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800728ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800728ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800728df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800728df`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800728c8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x1800728c8`

## pseudocode

```c

```
