# CCLSIDInfoCache::GetFolderValue(_GUID const &,CLSID_FOLDER_VALUE_FLAGS)

- ea: `0x18008ecb0`
- end: `0x18008effe`
- name: `?GetFolderValue@CCLSIDInfoCache@@QEAAHAEBU_GUID@@W4CLSID_FOLDER_VALUE_FLAGS@@@Z`
- size: `846`
- prototype: `int __high(const struct _GUID *, enum CLSID_FOLDER_VALUE_FLAGS)`
- caller_count: `24`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180047190`
- `0x1800644f0`
- `0x1800693e0`
- `0x18006a8c0`
- `0x180091620`
- `0x1800941d0`
- `0x180094390`
- `0x1800953e0`
- `0x1800badcc`
- `0x18010f754`
- `0x1801101e0`
- `0x18016ac90`
- `0x180180ba0`
- `0x18018b9f0`
- `0x1801b031c`
- `0x180201330`
- `0x1802034f0`
- `0x1802087ac`
- `0x180254380`
- `0x180261d48`
- `0x1802a5ac4`
- `0x180523820`
- `0x180544b2c`
- `0x1805455f0`

## callees

- `0x18004c4dc`
- `0x18008e7a0`
- `0x18008ec90`
- `0x18008ecb0`
- `0x180092970`
- `0x1800dd900`
- `0x1801ee9a0`
- `0x18028ec20`
- `0x1802952c8`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008eef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008ef4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008eef9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008ef4e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ed76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008edcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ef95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ed76`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008edcd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ef95`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008edf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008edf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ed0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ef74`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ed0e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008ef74`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ed57`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ed57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ed3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ed3d`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008ecf3`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008edb4`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008ecf3`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008edb4`

## pseudocode

```c

```
