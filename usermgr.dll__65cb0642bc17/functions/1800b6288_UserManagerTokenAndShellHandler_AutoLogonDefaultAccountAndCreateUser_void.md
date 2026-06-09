# UserManagerTokenAndShellHandler::AutoLogonDefaultAccountAndCreateUser(void * *)

- ea: `0x1800b6288`
- end: `0x1800b6432`
- name: `?AutoLogonDefaultAccountAndCreateUser@UserManagerTokenAndShellHandler@@AEAAJPEAPEAX@Z`
- size: `426`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, LPHANDLE lpTargetHandle)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800400fc`
- `0x1800b6648`

## callees

- `0x180007920`
- `0x18000ce48`
- `0x180012890`
- `0x18002799c`
- `0x1800624bc`
- `0x180063ecc`
- `0x1800b6288`
- `0x1800d4384`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b62c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b63e0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b62c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b63e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b62a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b6371`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b62a0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800b6371`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b632e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b632e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b62ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b62fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b62ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b62fa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b6324`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800b6324`

## pseudocode

```c

```
