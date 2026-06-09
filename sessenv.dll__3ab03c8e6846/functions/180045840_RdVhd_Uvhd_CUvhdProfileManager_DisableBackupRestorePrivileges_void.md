# RdVhd::Uvhd::CUvhdProfileManager::DisableBackupRestorePrivileges(void)

- ea: `0x180045840`
- end: `0x18004593c`
- name: `?DisableBackupRestorePrivileges@CUvhdProfileManager@Uvhd@RdVhd@@IEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdProfileManager *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180045530`

## callees

- `0x1800141e8`
- `0x180019b38`
- `0x180045840`
- `0x180048220`
- `0x180048b28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045856`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045856`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045929`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045929`

## string_xrefs

- `0x1800458d9`: `SeRestorePrivilege`
- `0x18004589e`: `SeBackupPrivilege`
- `0x18004587d`: `DisableBackupRestorePrivileges() privileges for user %s, count %d`

## pseudocode

```c

```
