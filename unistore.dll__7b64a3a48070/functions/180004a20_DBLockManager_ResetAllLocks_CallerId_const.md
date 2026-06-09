# DBLockManager::ResetAllLocks(CallerId const &)

- ea: `0x180004a20`
- end: `0x180004d34`
- name: `?ResetAllLocks@DBLockManager@@UEAAXAEBUCallerId@@@Z`
- size: `788`
- prototype: `void __fastcall(DBLockManager *__hidden this, const struct CallerId *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180004a20`
- `0x1800053e4`
- `0x18006f180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004a46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004ac7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180004aaa`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180004aaa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b51`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004b51`

## string_xrefs

- `0x180004a56`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180004b7c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180004cef`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180004c8f`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\DBLockManager.h`

## pseudocode

```c

```
