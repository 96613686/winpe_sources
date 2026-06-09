# CAppxStreamingDataSource::DeleteFileByIndex(ulong)

- ea: `0x180216ac0`
- end: `0x180216c6a`
- name: `?DeleteFileByIndex@CAppxStreamingDataSource@@AEAAJK@Z`
- size: `426`
- prototype: `__int64 __fastcall(CAppxStreamingDataSource *this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180214730`
- `0x180216934`

## callees

- `0x180113ae8`
- `0x18012b618`
- `0x180216580`
- `0x180216ac0`
- `0x18021f4d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180216b5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180216b5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180216af6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180216af6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180216b1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180216b1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180216c11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180216c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180216bc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180216bc7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216b6d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216b6d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180216bbd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180216bbd`

## string_xrefs

- `0x180216b91`: `CAppxStreamingDataSource::DeleteFileByIndex`
- `0x180216c2a`: `CAppxStreamingDataSource::DeleteFileByIndex`
- `0x180216bf4`: `Failed to delete file %ws`

## pseudocode

```c

```
