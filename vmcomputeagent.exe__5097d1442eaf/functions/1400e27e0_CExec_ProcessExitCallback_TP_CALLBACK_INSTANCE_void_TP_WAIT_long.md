# CExec::ProcessExitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1400e27e0`
- end: `0x1400e2848`
- name: `?ProcessExitCallback@CExec@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `104`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400e27e0`
- `0x1400e4010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1400e283c`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x1400e283c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e282b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400e282b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e27f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400e27f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400e27fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400e27fa`

## pseudocode

```c

```
