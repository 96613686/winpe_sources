# TaskOperationContext::NextWeeklyDate(_FILETIME,ulong,ulong,_FILETIME *)

- ea: `0x180093ff0`
- end: `0x180094160`
- name: `?NextWeeklyDate@TaskOperationContext@@QEAAJU_FILETIME@@KKPEAU2@@Z`
- size: `368`
- prototype: `__int64 __fastcall(TaskOperationContext *__hidden this, struct _FILETIME, unsigned int, unsigned int, LPFILETIME lpFileTime)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18009443c`

## callees

- `0x180093ff0`
- `0x180094d00`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009403e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009411c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009403e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009411c`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180094034`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180094034`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180094112`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180094112`
- `UserDataTimeUtil!DowFromDate` at `0x18009406e`
- `UserDataTimeUtil!DowFromDate` at `0x18009406e`
- `UserDataTimeUtil!IncrSystemTime` at `0x180094099`
- `UserDataTimeUtil!IncrSystemTime` at `0x180094104`
- `UserDataTimeUtil!IncrSystemTime` at `0x180094099`
- `UserDataTimeUtil!IncrSystemTime` at `0x180094104`

## pseudocode

```c

```
