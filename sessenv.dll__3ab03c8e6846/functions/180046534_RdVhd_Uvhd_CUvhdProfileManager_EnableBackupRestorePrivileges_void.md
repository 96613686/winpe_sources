# RdVhd::Uvhd::CUvhdProfileManager::EnableBackupRestorePrivileges(void)

- ea: `0x180046534`
- end: `0x180046634`
- name: `?EnableBackupRestorePrivileges@CUvhdProfileManager@Uvhd@RdVhd@@IEAAJXZ`
- size: `256`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdProfileManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180045530`

## callees

- `0x1800141e8`
- `0x180019b38`
- `0x180046534`
- `0x180048220`
- `0x180048b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004654a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004654a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046621`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180046621`

## string_xrefs

- `0x1800465d1`: `SeRestorePrivilege`
- `0x180046571`: `EnableBackupRestorePrivileges() privileges for user %s, count %d`
- `0x180046593`: `SeBackupPrivilege`

## pseudocode

```c

```
