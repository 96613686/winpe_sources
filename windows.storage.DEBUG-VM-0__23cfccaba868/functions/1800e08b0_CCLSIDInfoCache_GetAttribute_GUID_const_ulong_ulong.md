# CCLSIDInfoCache::GetAttribute(_GUID const &,ulong,ulong)

- ea: `0x1800e08b0`
- end: `0x1800e0c2e`
- name: `?GetAttribute@CCLSIDInfoCache@@QEAAKAEBU_GUID@@KK@Z`
- size: `894`
- prototype: `unsigned int(CCLSIDInfoCache *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180167770`
- `0x18031a800`
- `0x18031ec30`

## callees

- `0x18009b780`
- `0x1800ccbd0`
- `0x1800e08b0`
- `0x1800e1b30`
- `0x1800e1c70`
- `0x1800e4730`
- `0x1801d5d70`
- `0x18027fca0`
- `0x180288824`
- `0x180329374`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e0ad6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e0b86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e0ad6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e0b86`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e0969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e09b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e0bc2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e0969`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e09b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e0bc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e09da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e09da`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0913`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0ba7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0913`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0ba7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e0950`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e0950`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e093c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e093c`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e08fe`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e09a2`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e08fe`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e09a2`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x1800e0b6f`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x1800e0b6f`

## pseudocode

```c

```
