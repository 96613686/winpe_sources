# TaskOperationContext::NextMonthlyDate(_FILETIME,ulong,ulong,ulong,_FILETIME *)

- ea: `0x180094168`
- end: `0x180094302`
- name: `?NextMonthlyDate@TaskOperationContext@@QEAAJU_FILETIME@@KKKPEAU2@@Z`
- size: `410`
- prototype: `__int64 __fastcall(TaskOperationContext *__hidden this, struct _FILETIME, unsigned int, unsigned int, unsigned int, LPFILETIME lpFileTime)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18009443c`

## callees

- `0x180094168`
- `0x180094d00`
- `0x1800ebe20`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800941b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800941b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800942bf`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800941a8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800941a8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800942b5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800942b5`
- `UserDataTimeUtil!DowFromDate` at `0x180094204`
- `UserDataTimeUtil!DowFromDate` at `0x180094204`
- `UserDataTimeUtil!IncrSystemTime` at `0x1800941ef`
- `UserDataTimeUtil!IncrSystemTime` at `0x18009425a`
- `UserDataTimeUtil!IncrSystemTime` at `0x18009427a`
- `UserDataTimeUtil!IncrSystemTime` at `0x1800942a8`
- `UserDataTimeUtil!IncrSystemTime` at `0x1800941ef`
- `UserDataTimeUtil!IncrSystemTime` at `0x18009425a`
- `UserDataTimeUtil!IncrSystemTime` at `0x18009427a`
- `UserDataTimeUtil!IncrSystemTime` at `0x1800942a8`

## pseudocode

```c

```
