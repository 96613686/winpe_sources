# CShellTaskScheduler::TT_TransitionThreadToRunningOrTerminating(int,CShellTaskThread *)

- ea: `0x180053b80`
- end: `0x180053fcb`
- name: `?TT_TransitionThreadToRunningOrTerminating@CShellTaskScheduler@@QEAA_NHPEAVCShellTaskThread@@@Z`
- size: `1099`
- prototype: `bool __fastcall(CShellTaskScheduler *__hidden this, int, struct CShellTaskThread *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x1800532b0`

## callees

- `0x18004d470`
- `0x18004d720`
- `0x1800529d0`
- `0x180053b80`
- `0x180054f30`
- `0x1800b3210`
- `0x180113058`
- `0x180157188`
- `0x1801577cc`
- `0x1803b1f60`
- `0x1803b69b9`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053bb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053bb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180053d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053be1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053ca9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053d19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053e7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053be1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053ca9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053d19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180053e7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053e56`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180053c02`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180053f16`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180053c02`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180053f16`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180053ce2`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180053ce2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x180053efd`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x180053fa7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x180053efd`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PeekMessageW` at `0x180053fa7`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x180053f86`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DispatchMessageW` at `0x180053f86`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjects` at `0x180053c2c`
- `ext-ms-win-rtcore-ntuser-synch-ext-l1-1-0!MsgWaitForMultipleObjects` at `0x180053c2c`

## pseudocode

```c

```
