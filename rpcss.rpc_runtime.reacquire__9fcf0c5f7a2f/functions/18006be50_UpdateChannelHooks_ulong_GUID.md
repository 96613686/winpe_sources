# UpdateChannelHooks(ulong *,_GUID * *)

- ea: `0x18006be50`
- end: `0x18006c1ba`
- name: `?UpdateChannelHooks@@YAXPEAKPEAPEAU_GUID@@@Z`
- size: `874`
- prototype: `void __fastcall(unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18008c830`

## callees

- `0x18006be50`
- `0x1800b7ac0`
- `0x1800b7e90`
- `0x1800fdb8c`
- `0x180112d84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006bfe2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c0cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006bfe2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006c0cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006c05b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006c05b`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006bf3f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18006bf3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c18e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006c18e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006bf6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006bf6b`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006c124`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18006c124`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bfac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006bfac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006be9d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006be9d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bee7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006bee7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006bebb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006bebb`

## pseudocode

```c

```
