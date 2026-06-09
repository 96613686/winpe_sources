# PolicyChangeCallback(void *,uchar)

- ea: `0x1800c0190`
- end: `0x1800c02a4`
- name: `?PolicyChangeCallback@@YAXPEAXE@Z`
- size: `276`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callees

- `0x1800085d0`
- `0x180013ad0`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x1800c0190`
- `0x1800c030c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c01ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c01ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c021f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c021f`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c0275`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800c0275`

## string_xrefs

- `0x1800c01c7`: `Recived a notification to update group policy.`

## pseudocode

```c

```
