# SqliteDatabase::GetChannelForHandler(ushort const *,IWNSChannelDetails * *)

- ea: `0x1800074a0`
- end: `0x1800077f2`
- name: `?GetChannelForHandler@SqliteDatabase@@UEAAJPEBGPEAPEAUIWNSChannelDetails@@@Z`
- size: `850`
- prototype: `int(SqliteDatabase *__hidden this, const unsigned __int16 *, struct IWNSChannelDetails **)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004e38`
- `0x180005e78`
- `0x180005f98`
- `0x1800074a0`
- `0x1800077f8`
- `0x18000823c`
- `0x1800082c4`
- `0x18000e074`
- `0x18000e5f4`
- `0x180011a90`
- `0x18001575c`
- `0x18001592c`
- `0x18002b6d4`
- `0x180049644`
- `0x18004d6f0`
- `0x1800a0b2c`
- `0x1800b99f0`
- `0x1800b9a20`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800074f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800074f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007580`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000776c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007580`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000776c`
- `winsqlite3!sqlite3_column_int64` at `0x180007609`
- `winsqlite3!sqlite3_column_int64` at `0x180007622`
- `winsqlite3!sqlite3_column_int64` at `0x18000763b`
- `winsqlite3!sqlite3_column_int64` at `0x180007609`
- `winsqlite3!sqlite3_column_int64` at `0x180007622`
- `winsqlite3!sqlite3_column_int64` at `0x18000763b`

## string_xrefs

- `0x180007532`: `SELECT [ChannelId], [Uri], [ExpiryTime], [CreatedTime], [DeviceVersion] FROM [WNSPushChannel] WHERE [HandlerId] IN (SELECT [RecordId] FROM [NotificationHandler] WHERE [PrimaryId]=?)`

## pseudocode

```c

```
