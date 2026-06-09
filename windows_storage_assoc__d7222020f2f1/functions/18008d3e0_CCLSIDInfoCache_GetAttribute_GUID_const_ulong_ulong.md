# CCLSIDInfoCache::GetAttribute(_GUID const &,ulong,ulong)

- ea: `0x18008d3e0`
- end: `0x18008d7ad`
- name: `?GetAttribute@CCLSIDInfoCache@@QEAAKAEBU_GUID@@KK@Z`
- size: `973`
- prototype: `unsigned int(CCLSIDInfoCache *__hidden this, const struct _GUID *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18016e070`
- `0x18032c640`
- `0x180331290`

## callees

- `0x18004c4dc`
- `0x18008b6c0`
- `0x18008d3e0`
- `0x18008e7a0`
- `0x18008ec90`
- `0x180092970`
- `0x1800dd900`
- `0x1801ee9a0`
- `0x18028ec20`
- `0x1802952c8`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d636`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d6f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d636`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d6f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d4b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d73b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d4b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d509`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d73b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008d534`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008d534`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d449`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d71a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d449`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d71a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008d492`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008d492`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d478`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d478`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d42e`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d4f0`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d42e`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d4f0`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18008d6d6`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18008d6d6`

## pseudocode

```c

```
