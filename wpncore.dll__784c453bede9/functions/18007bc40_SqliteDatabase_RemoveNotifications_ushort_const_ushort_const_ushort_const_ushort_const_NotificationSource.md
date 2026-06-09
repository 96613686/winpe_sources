# SqliteDatabase::RemoveNotifications(ushort const *,ushort const *,ushort const *,ushort const *,NotificationSource)

- ea: `0x18007bc40`
- end: `0x18007bf8e`
- name: `?RemoveNotifications@SqliteDatabase@@UEAAJPEBG000W4NotificationSource@@@Z`
- size: `846`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, enum NotificationSource)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callees

- `0x180004e38`
- `0x1800082c4`
- `0x18000c5f0`
- `0x18000e598`
- `0x18000e5f4`
- `0x18001575c`
- `0x18001592c`
- `0x18002b6d4`
- `0x18002ee38`
- `0x180049644`
- `0x18006ee68`
- `0x18007bc40`
- `0x1800a0b2c`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bc7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007bc7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bd64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bf63`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bccf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bd64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007bf63`

## string_xrefs

- `0x18007bdd1`: `DELETE FROM [Notification] WHERE [HandlerId] IN (SELECT [RecordId] FROM [NotificationHandler] WHERE [PrimaryId]=?) AND [Type]=? AND [Group]=? AND [Tag]=?`
- `0x18007bdd8`: `DELETE FROM [Notification] WHERE [HandlerId] IN (SELECT [RecordId] FROM [NotificationHandler] WHERE [PrimaryId]=?) AND [Type]=? AND [Group]=?`

## pseudocode

```c

```
