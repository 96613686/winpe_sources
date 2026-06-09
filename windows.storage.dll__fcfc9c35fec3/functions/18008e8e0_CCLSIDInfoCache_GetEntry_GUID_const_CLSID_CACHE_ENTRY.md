# CCLSIDInfoCache::_GetEntry(_GUID const &,CLSID_CACHE_ENTRY *)

- ea: `0x18008e8e0`
- end: `0x18008ec80`
- name: `?_GetEntry@CCLSIDInfoCache@@AEAAXAEBU_GUID@@PEAUCLSID_CACHE_ENTRY@@@Z`
- size: `928`
- prototype: `void(CCLSIDInfoCache *__hidden this, const struct _GUID *, struct CLSID_CACHE_ENTRY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008f380`

## callees

- `0x18004c4dc`
- `0x18008e7a0`
- `0x18008e8e0`
- `0x18008ec90`
- `0x1800dd900`
- `0x1801ee9a0`
- `0x18028ec20`
- `0x1802952c8`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008eb11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008eb4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008eb11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18008eb4d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008e99e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008e9f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ec58`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008e99e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008e9f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008ec58`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ea17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18008ea17`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008e936`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008eb70`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008e936`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008eb70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e97f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ebd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e97f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ebd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e965`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ebb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e965`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ebb6`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008e91b`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008e9d9`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008eb87`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008ec04`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008e91b`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008e9d9`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008eb87`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18008ec04`

## pseudocode

```c

```
