# SqliteDatabase::SelectNotifications(ushort const *,ushort const *,ushort const *,ushort const *,INotificationCollection * *)

- ea: `0x18000c5f0`
- end: `0x18000cae6`
- name: `?SelectNotifications@SqliteDatabase@@QEAAJPEBG000PEAPEAUINotificationCollection@@@Z`
- size: `1270`
- prototype: `__int64 __fastcall(SqliteDatabase *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct INotificationCollection **)`
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007bc40`
- `0x1800f1be0`

## callees

- `0x18000c5f0`
- `0x18000caec`
- `0x18000de40`
- `0x18000e5f4`
- `0x18001575c`
- `0x18001592c`
- `0x180029750`
- `0x180029f44`
- `0x180049644`
- `0x1800a0b2c`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c650`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c650`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c938`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c929`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c74f`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c7a4`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c7fc`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c84e`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c74f`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c7a4`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c7fc`
- `winsqlite3!sqlite3_bind_text16` at `0x18000c84e`

## pseudocode

```c

```
