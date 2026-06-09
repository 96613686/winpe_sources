# DBLockManager::_ValidateLocks(CallerId const &,ulong,__MIDL___MIDL_itf_unistore_0000_0002_0001 const *,DB_LOCK_TYPE const *)

- ea: `0x1800287b8`
- end: `0x180028987`
- name: `?_ValidateLocks@DBLockManager@@AEAAJAEBUCallerId@@KPEBW4__MIDL___MIDL_itf_unistore_0000_0002_0001@@PEBW4DB_LOCK_TYPE@@@Z`
- size: `463`
- prototype: `__int64 __fastcall(DBLockManager *__hidden this, const struct CallerId *, unsigned int, const enum __MIDL___MIDL_itf_unistore_0000_0002_0001 *, const enum DB_LOCK_TYPE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180027e7c`

## callees

- `0x180002e50`
- `0x180005490`
- `0x1800287b8`
- `0x1800514c0`
- `0x180055670`
- `0x18006f180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800287de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800287de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028897`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028897`

## string_xrefs

- `0x180028803`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180028873`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`
- `0x180028974`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dblockmanager.cpp`

## pseudocode

```c

```
