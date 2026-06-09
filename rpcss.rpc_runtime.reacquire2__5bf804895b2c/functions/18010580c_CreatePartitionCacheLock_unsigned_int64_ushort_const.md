# CreatePartitionCacheLock(unsigned __int64,ushort const *)

- ea: `0x18010580c`
- end: `0x180105a10`
- name: `?CreatePartitionCacheLock@@YAJ_KPEBG@Z`
- size: `516`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180105b88`

## callees

- `0x18001037c`
- `0x180034260`
- `0x18008172c`
- `0x18010580c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801058c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105972`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801058c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180105972`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801059f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801059f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180105867`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180105867`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18010595a`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18010595a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801058b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1801058b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801059d9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1801059d9`

## string_xrefs

- `0x18010591d`: `onecore\com\combase\rpcss\olescm\partitioncache.cxx`
- `0x1801059c4`: `onecore\com\combase\rpcss\olescm\partitioncache.cxx`
- `0x180105911`: `CreatePartitionCacheLock`
- `0x1801059b8`: `CreatePartitionCacheLock`

## pseudocode

```c

```
