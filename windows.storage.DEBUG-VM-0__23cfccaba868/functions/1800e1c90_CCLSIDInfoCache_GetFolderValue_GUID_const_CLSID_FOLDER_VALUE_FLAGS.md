# CCLSIDInfoCache::GetFolderValue(_GUID const &,CLSID_FOLDER_VALUE_FLAGS)

- ea: `0x1800e1c90`
- end: `0x1800e1f95`
- name: `?GetFolderValue@CCLSIDInfoCache@@QEAAHAEBU_GUID@@W4CLSID_FOLDER_VALUE_FLAGS@@@Z`
- size: `773`
- prototype: `int __high(const struct _GUID *, enum CLSID_FOLDER_VALUE_FLAGS)`
- caller_count: `24`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007abd4`
- `0x180096180`
- `0x1800d2810`
- `0x1800d7690`
- `0x1800d8af0`
- `0x1800e2c40`
- `0x180108c84`
- `0x18014de80`
- `0x180169ea0`
- `0x18016a210`
- `0x18016b1a0`
- `0x18016ca10`
- `0x18016d020`
- `0x18016da90`
- `0x180174660`
- `0x180199438`
- `0x1801de0c0`
- `0x1801f2c40`
- `0x180252328`
- `0x180298d88`
- `0x1802a0ed0`
- `0x18050d3ac`
- `0x18052e038`
- `0x18052ea70`

## callees

- `0x18009b780`
- `0x1800ccbd0`
- `0x1800e1b30`
- `0x1800e1c70`
- `0x1800e1c90`
- `0x1800e4730`
- `0x1801d5d70`
- `0x18027fca0`
- `0x180288824`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e1ea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e1ef7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e1ea9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e1ef7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1d3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1d89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1f32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1d3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1d89`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e1f32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e1dae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e1dae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e1ce8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e1f17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e1ce8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e1f17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e1d25`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e1d25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e1d11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e1d11`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e1cd3`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e1d76`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e1cd3`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e1d76`

## pseudocode

```c

```
