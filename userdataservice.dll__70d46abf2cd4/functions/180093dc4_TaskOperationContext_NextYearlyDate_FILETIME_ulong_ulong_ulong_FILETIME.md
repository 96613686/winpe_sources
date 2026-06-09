# TaskOperationContext::NextYearlyDate(_FILETIME,ulong,ulong,ulong,_FILETIME *)

- ea: `0x180093dc4`
- end: `0x180093eae`
- name: `?NextYearlyDate@TaskOperationContext@@QEAAJU_FILETIME@@KKKPEAU2@@Z`
- size: `234`
- prototype: `__int64 __fastcall(TaskOperationContext *__hidden this, struct _FILETIME, unsigned int, unsigned int, unsigned int, LPFILETIME lpFileTime)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18009443c`

## callees

- `0x180093dc4`
- `0x180094d00`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093e76`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093dfe`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093dfe`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093e6c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093e6c`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093e42`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093e42`
- `UserDataTimeUtil!GetDaysForMonth` at `0x180093e53`
- `UserDataTimeUtil!GetDaysForMonth` at `0x180093e53`

## pseudocode

```c

```
