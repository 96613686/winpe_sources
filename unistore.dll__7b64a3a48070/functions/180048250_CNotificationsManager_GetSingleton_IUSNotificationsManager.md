# CNotificationsManager::GetSingleton(IUSNotificationsManager * *)

- ea: `0x180048250`
- end: `0x1800483e0`
- name: `?GetSingleton@CNotificationsManager@@SAJPEAPEAUIUSNotificationsManager@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(struct IUSNotificationsManager **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180048240`

## callees

- `0x1800068f0`
- `0x180022ee0`
- `0x180048250`
- `0x180058490`
- `0x180070130`
- `0x180079030`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048320`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048320`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800482a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004835d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800482a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004835d`

## string_xrefs

- `0x180048345`: `onecoreuap\base\AppModel\UserDataAccess\PublishedInternal\Inc\globalclean.h`
- `0x1800482be`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\notificationsmanager.cpp`
- `0x18004837d`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\notificationsmanager.cpp`

## pseudocode

```c

```
