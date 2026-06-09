# UpdateChannelHooks(ulong *,_GUID * *)

- ea: `0x180066fac`
- end: `0x1800672d3`
- name: `?UpdateChannelHooks@@YAXPEAKPEAPEAU_GUID@@@Z`
- size: `807`
- prototype: `void __fastcall(unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180087d70`

## callees

- `0x180066fac`
- `0x1800b27e0`
- `0x1800b2bb0`
- `0x1800f5c74`
- `0x18010a084`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180067119`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800671f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180067119`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800671f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006718c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006718c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180067088`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180067088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800672ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800672ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800670ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800670ae`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180067249`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180067249`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800670e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800670e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180066ff9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180066ff9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067037`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067037`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180067011`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180067011`

## pseudocode

```c

```
