# CPolicyCache::GetValue(SHPOLICYTABLE_ *,_GUID const &,ulong,void *,ulong *)

- ea: `0x180004df0`
- end: `0x180005340`
- name: `?GetValue@CPolicyCache@@SAJPEAUSHPOLICYTABLE_@@AEBU_GUID@@KPEAXPEAK@Z`
- size: `1360`
- prototype: `__int64 __usercall@<rax>(struct SHPOLICYTABLE_ *@<rcx>, const struct _GUID *@<rdx>, unsigned int@<r8d>, void *@<r9>, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800049f0`
- `0x180004c10`

## callees

- `0x1800045e0`
- `0x180004df0`
- `0x180005350`
- `0x180005534`
- `0x1800056a8`
- `0x180005724`
- `0x180005a64`
- `0x1800672e8`
- `0x180068d9c`
- `0x180093410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004f88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180004f88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ff6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005151`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004ff6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005151`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004fd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004fd7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000504e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005184`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000504e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005184`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800050ff`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800050ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005322`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005262`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005322`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000532d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005335`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000532d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180005335`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180005206`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800052dd`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180005206`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x1800052dd`

## pseudocode

```c

```
