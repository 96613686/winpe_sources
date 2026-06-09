# CCLSIDInfoCache::GetPerUserAttributes(_GUID const &)

- ea: `0x1800e05b0`
- end: `0x1800e089f`
- name: `?GetPerUserAttributes@CCLSIDInfoCache@@QEAAKAEBU_GUID@@@Z`
- size: `751`
- prototype: `unsigned int(CCLSIDInfoCache *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e0c40`

## callees

- `0x18009b780`
- `0x1800ccbd0`
- `0x1800e05b0`
- `0x1800e1b30`
- `0x1800e1c70`
- `0x1800e4730`
- `0x1801d5d70`
- `0x18027fca0`
- `0x180288824`
- `0x1803a4cb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e07c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e0804`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e07c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800e0804`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e0659`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e06a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e083f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e0659`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e06a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800e083f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e06c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800e06c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0603`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0824`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0603`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800e0824`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e0640`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800e0640`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e062c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800e062c`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e05ee`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e0691`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e05ee`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800e0691`

## pseudocode

```c

```
