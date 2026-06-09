# SHGetCorrectOwnerSid

- ea: `0x1800f7e70`
- end: `0x1800f8529`
- name: `SHGetCorrectOwnerSid`
- size: `1721`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e9100`

## callees

- `0x180054f30`
- `0x1800551d0`
- `0x1800f7e70`
- `0x1800f8530`
- `0x1800f8694`
- `0x1800f8720`
- `0x1800f8980`
- `0x1800f8b50`
- `0x180147bfc`
- `0x1802c6678`
- `0x180317b8c`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f7fb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f7ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f7fb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800f7ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f833f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8518`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f833f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f8518`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f7ed0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800f7ed0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8019`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f8019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f8189`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800f8189`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f816c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800f816c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f832c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f832c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800f80be`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800f80be`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f805e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f805e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f8122`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f8122`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f8222`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f8222`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f8419`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f84e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f8419`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f84e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f83de`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f83de`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f835e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f83fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f835e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800f83fc`

## string_xrefs

- `0x1800f80f1`: `ProfileImagePath`

## pseudocode

```c

```
