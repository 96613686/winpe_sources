# CAgentServiceManager::DSRemoveServiceAndUpdateServiceObject(ISusDatastore *,_GUID const &)

- ea: `0x18005cef8`
- end: `0x18005d0fe`
- name: `?DSRemoveServiceAndUpdateServiceObject@CAgentServiceManager@@QEAAJPEAUISusDatastore@@AEBU_GUID@@@Z`
- size: `518`
- prototype: `__int64 __fastcall(CAgentServiceManager *__hidden this, struct ISusDatastore *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180047790`
- `0x18004a180`
- `0x180052758`
- `0x18005d6e8`

## callees

- `0x18001d708`
- `0x18005cef8`
- `0x18005d304`
- `0x18005d56c`
- `0x180062124`
- `0x180062264`
- `0x1800db208`
- `0x18012b618`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005cf50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d013`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005cf50`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005d013`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005cf6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d031`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005cf6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005d031`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d06a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005d06a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005cf9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005cf9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cfdf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cfdf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d07b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005d07b`

## string_xrefs

- `0x18005d095`: `Failed to delete service from the backup store`
- `0x18005d0d2`: `CAgentServiceManager::DSRemoveServiceAndUpdateServiceObject`

## pseudocode

```c

```
