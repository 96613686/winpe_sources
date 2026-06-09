# ShellDDEExec::DDEExecute(uchar,int,Windows::Internal::Storage::DDEContinuationState *)

- ea: `0x18014e6d0`
- end: `0x18014e9e4`
- name: `?DDEExecute@ShellDDEExec@@UEAAJEHPEAW4DDEContinuationState@Storage@Internal@Windows@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(ShellDDEExec *__hidden this, unsigned __int8, int, enum Windows::Internal::Storage::DDEContinuationState *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18014e2f0`

## callees

- `0x18000d6cc`
- `0x1800dd190`
- `0x18014e6d0`
- `0x180268120`
- `0x1802ba650`
- `0x1802ba7cc`
- `0x18035278c`
- `0x180363330`
- `0x1803a4cb0`
- `0x18053558c`
- `0x1805370a4`
- `0x180538978`
- `0x180538ba4`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014e738`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014e738`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014e746`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014e8c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014e8c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e99a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e99a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014e8b2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014e9a8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014e8b2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014e9a8`
- `SHCORE!__imp_SHFreeShared` at `0x18014e8d0`
- `SHCORE!__imp_SHFreeShared` at `0x18014e8d0`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18014e859`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18014e859`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18014e973`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18014e973`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18014e965`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18014e965`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18014e826`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18014e826`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowUnicode` at `0x18014e813`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowUnicode` at `0x18014e813`

## pseudocode

```c

```
