# CAppxStreamingDataSource::GetFileMapEntryForFile(ulong,CAppxStreamingDataSource::GetFileMapEntryLoad,CAppxStreamingDataSource::HandleAndProgressInfo * *)

- ea: `0x180216580`
- end: `0x18021686c`
- name: `?GetFileMapEntryForFile@CAppxStreamingDataSource@@AEAAJKW4GetFileMapEntryLoad@1@PEAPEAUHandleAndProgressInfo@1@@Z`
- size: `748`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1802157a0`
- `0x1802160b0`
- `0x180216220`
- `0x1802162c4`
- `0x180216874`
- `0x180216ac0`
- `0x180216d6c`
- `0x180221a10`

## callees

- `0x1800582c8`
- `0x180113ae8`
- `0x1801142c4`
- `0x18012b618`
- `0x180216580`
- `0x18021f4d8`
- `0x180239110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180216658`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180216658`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18021680b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18021680b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802165d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802166f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802165d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802166f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802166b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18021671f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1802166b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18021671f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180216838`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180216838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021679e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18021679e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216820`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180216820`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021678f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18021678f`
- `OLEAUT32!__imp_SysFreeString` at `0x18021684c`
- `OLEAUT32!__imp_SysFreeString` at `0x18021684c`

## string_xrefs

- `0x1802167d6`: `CreateFile(%ws) failed`

## pseudocode

```c

```
