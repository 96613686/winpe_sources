# CCLSIDInfoCache::GetPerUserAttributes(_GUID const &)

- ea: `0x18008d090`
- end: `0x18008d3cb`
- name: `?GetPerUserAttributes@CCLSIDInfoCache@@QEAAKAEBU_GUID@@@Z`
- size: `827`
- prototype: `unsigned int(CCLSIDInfoCache *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008d7c0`

## callees

- `0x18004c4dc`
- `0x18008d090`
- `0x18008e7a0`
- `0x18008ec90`
- `0x180092970`
- `0x1800dd900`
- `0x1801ee9a0`
- `0x18028ec20`
- `0x1802952c8`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d2d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d31b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d2d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008d31b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d151`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d1a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d362`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d151`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d1a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d362`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008d1d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008d1d3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d0e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d341`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d0e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008d341`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008d132`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008d132`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d118`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008d118`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d0ce`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d18f`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d0ce`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008d18f`

## pseudocode

```c

```
