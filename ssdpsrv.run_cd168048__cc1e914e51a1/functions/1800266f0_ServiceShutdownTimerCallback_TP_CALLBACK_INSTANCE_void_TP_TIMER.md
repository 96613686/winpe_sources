# ServiceShutdownTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x1800266f0`
- end: `0x180026740`
- name: `?ServiceShutdownTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `80`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800266f0`
- `0x180029d70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026734`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800266fb`

## pseudocode

```c

```
