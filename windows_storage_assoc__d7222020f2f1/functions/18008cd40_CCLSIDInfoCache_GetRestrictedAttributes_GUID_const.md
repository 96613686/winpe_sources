# CCLSIDInfoCache::GetRestrictedAttributes(_GUID const &)

- ea: `0x18008cd40`
- end: `0x18008d07b`
- name: `?GetRestrictedAttributes@CCLSIDInfoCache@@QEAAKAEBU_GUID@@@Z`
- size: `827`
- prototype: `unsigned int(CCLSIDInfoCache *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18032c640`

## callees

- `0x18004c4dc`
- `0x18008cd40`
- `0x18008e7a0`
- `0x18008ec90`
- `0x180092970`
- `0x1800dd900`
- `0x1801ee9a0`
- `0x18028ec20`
- `0x1802952c8`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008cf81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008cfcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008cf81`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008cfcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ce01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ce58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d012`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ce01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ce58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008d012`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ce83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ce83`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cd99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cff1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cd99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008cff1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008cde2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008cde2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008cdc8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008cdc8`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008cd7e`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008ce3f`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008cd7e`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008ce3f`

## pseudocode

```c

```
