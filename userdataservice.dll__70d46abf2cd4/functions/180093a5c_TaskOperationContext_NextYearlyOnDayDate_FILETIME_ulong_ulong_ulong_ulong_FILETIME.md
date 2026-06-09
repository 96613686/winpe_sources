# TaskOperationContext::NextYearlyOnDayDate(_FILETIME,ulong,ulong,ulong,ulong,_FILETIME *)

- ea: `0x180093a5c`
- end: `0x180093bfa`
- name: `?NextYearlyOnDayDate@TaskOperationContext@@QEAAJU_FILETIME@@KKKKPEAU2@@Z`
- size: `414`
- prototype: `__int64 __fastcall(TaskOperationContext *__hidden this, struct _FILETIME, unsigned int, unsigned int, unsigned int, unsigned int, LPFILETIME lpFileTime)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18009443c`

## callees

- `0x180093a5c`
- `0x180094d00`
- `0x1800ebe20`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093bb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093bb7`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093a9c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093a9c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093bad`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093bad`
- `UserDataTimeUtil!DowFromDate` at `0x180093af9`
- `UserDataTimeUtil!DowFromDate` at `0x180093af9`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093ae6`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093b4f`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093b72`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093ba0`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093ae6`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093b4f`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093b72`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093ba0`

## pseudocode

```c

```
