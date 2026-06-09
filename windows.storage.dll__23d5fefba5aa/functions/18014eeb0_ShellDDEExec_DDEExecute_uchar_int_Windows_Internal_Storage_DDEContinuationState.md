# ShellDDEExec::DDEExecute(uchar,int,Windows::Internal::Storage::DDEContinuationState *)

- ea: `0x18014eeb0`
- end: `0x18014f20d`
- name: `?DDEExecute@ShellDDEExec@@UEAAJEHPEAW4DDEContinuationState@Storage@Internal@Windows@@@Z`
- size: `861`
- prototype: `__int64 __fastcall(ShellDDEExec *__hidden this, unsigned __int8, int, enum Windows::Internal::Storage::DDEContinuationState *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18014eadc`

## callees

- `0x180009fc0`
- `0x1800899a4`
- `0x18014eeb0`
- `0x180277268`
- `0x1802c924c`
- `0x1802c93dc`
- `0x18036327c`
- `0x1803757d0`
- `0x1803b1f60`
- `0x18054c30c`
- `0x18054df14`
- `0x18054ffc8`
- `0x180550230`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014ef18`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18014ef18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ef2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18014ef2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014f0c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18014f0c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014f1b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014f1b6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014f0b0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014f1ca`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014f0b0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18014f1ca`
- `SHCORE!__imp_SHFreeShared` at `0x18014f0da`
- `SHCORE!__imp_SHFreeShared` at `0x18014f0da`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18014f051`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18014f051`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18014f189`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!DestroyWindow` at `0x18014f189`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18014f175`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!IsWindow` at `0x18014f175`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18014f018`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x18014f018`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowUnicode` at `0x18014efff`
- `ext-ms-win-ntuser-window-l1-1-1!IsWindowUnicode` at `0x18014efff`

## pseudocode

```c

```
