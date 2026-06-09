# TaskOperationContext::NextRegeneratingDate(_FILETIME,ulong,ulong,_FILETIME *)

- ea: `0x180094308`
- end: `0x180094434`
- name: `?NextRegeneratingDate@TaskOperationContext@@QEAAJU_FILETIME@@KKPEAU2@@Z`
- size: `300`
- prototype: `__int64 __fastcall(TaskOperationContext *__hidden this, struct _FILETIME, unsigned int, unsigned int, LPFILETIME lpFileTime)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18009443c`

## callees

- `0x180094308`
- `0x180094d00`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800943f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094353`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800943f3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180094349`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180094349`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800943e9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800943e9`
- `UserDataTimeUtil!IncrSystemTime` at `0x1800943db`
- `UserDataTimeUtil!IncrSystemTime` at `0x1800943db`

## pseudocode

```c

```
