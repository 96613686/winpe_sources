# ServiceShutdownTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180024ba0`
- end: `0x180024be5`
- name: `?ServiceShutdownTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180024ba0`
- `0x180027f90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024bde`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024bab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024bab`

## pseudocode

```c

```
