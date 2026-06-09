# TaskOperationContext::NextMonthlyOnDayDate(_FILETIME,ulong,ulong,_FILETIME *)

- ea: `0x180093c00`
- end: `0x180093ce6`
- name: `?NextMonthlyOnDayDate@TaskOperationContext@@QEAAJU_FILETIME@@KKPEAU2@@Z`
- size: `230`
- prototype: `__int64 __fastcall(TaskOperationContext *__hidden this, struct _FILETIME, unsigned int, unsigned int, LPFILETIME lpFileTime)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18009443c`

## callees

- `0x180093c00`
- `0x180094d00`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093c44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093cae`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093c3a`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093c3a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093ca4`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093ca4`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093c7d`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093c7d`
- `UserDataTimeUtil!GetDaysForMonth` at `0x180093c8b`
- `UserDataTimeUtil!GetDaysForMonth` at `0x180093c8b`

## pseudocode

```c

```
