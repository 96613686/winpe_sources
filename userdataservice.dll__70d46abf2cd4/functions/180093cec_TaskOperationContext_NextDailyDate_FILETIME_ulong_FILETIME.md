# TaskOperationContext::NextDailyDate(_FILETIME,ulong,_FILETIME *)

- ea: `0x180093cec`
- end: `0x180093dbd`
- name: `?NextDailyDate@TaskOperationContext@@QEAAJU_FILETIME@@KPEAU2@@Z`
- size: `209`
- prototype: `int(TaskOperationContext *__hidden this, struct _FILETIME, unsigned int, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18009443c`

## callees

- `0x180093cec`
- `0x180094d00`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093d86`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093d21`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180093d21`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093d7c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180093d7c`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093d6e`
- `UserDataTimeUtil!IncrSystemTime` at `0x180093d6e`

## pseudocode

```c

```
