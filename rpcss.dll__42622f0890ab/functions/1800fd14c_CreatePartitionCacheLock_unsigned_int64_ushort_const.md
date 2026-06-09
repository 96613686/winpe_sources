# CreatePartitionCacheLock(unsigned __int64,ushort const *)

- ea: `0x1800fd14c`
- end: `0x1800fd325`
- name: `?CreatePartitionCacheLock@@YAJ_KPEBG@Z`
- size: `473`
- prototype: `__int64 __fastcall(unsigned __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800fd480`

## callees

- `0x18000bbe8`
- `0x180034540`
- `0x18007e3d4`
- `0x1800fd14c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd1f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd1f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fd29a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fd30d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800fd30d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fd1a7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800fd1a7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800fd288`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800fd288`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800fd1ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800fd1ed`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800fd2fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800fd2fb`

## string_xrefs

- `0x1800fd24b`: `onecore\com\combase\rpcss\olescm\partitioncache.cxx`
- `0x1800fd2e6`: `onecore\com\combase\rpcss\olescm\partitioncache.cxx`
- `0x1800fd23f`: `CreatePartitionCacheLock`
- `0x1800fd2da`: `CreatePartitionCacheLock`

## pseudocode

```c

```
