# DeleteExtensibleContainer(ushort const *,ushort const *,HKEY__ *)

- ea: `0x18011f02c`
- end: `0x18011f3b2`
- name: `?DeleteExtensibleContainer@@YAJPEBG0PEAUHKEY__@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, HKEY hKey)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18011efa0`

## callees

- `0x1800204f8`
- `0x180025910`
- `0x180046a1c`
- `0x1800eb3e8`
- `0x18011f02c`
- `0x18011f3b8`
- `0x180136748`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e2f30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011f380`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18011f380`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011f10b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18011f10b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18011f323`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18011f323`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011f146`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011f1c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011f24f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011f146`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011f1c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18011f24f`
- `RPCRT4!RpcRevertToSelf` at `0x18011f36e`
- `RPCRT4!RpcRevertToSelf` at `0x18011f36e`

## string_xrefs

- `0x18011f121`: `CachePath`
- `0x18011f22a`: `CacheOptions`
- `0x18011f1a6`: `CacheRelativePath`

## pseudocode

```c

```
