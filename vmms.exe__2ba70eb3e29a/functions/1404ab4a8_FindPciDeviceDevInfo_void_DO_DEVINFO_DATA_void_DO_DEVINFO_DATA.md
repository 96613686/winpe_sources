# FindPciDeviceDevInfo(void *,_DO_DEVINFO_DATA *,void * *,_DO_DEVINFO_DATA *)

- ea: `0x1404ab4a8`
- end: `0x1404ab75c`
- name: `?FindPciDeviceDevInfo@@YAJPEAXPEAU_DO_DEVINFO_DATA@@PEAPEAX1@Z`
- size: `692`
- prototype: `__int64 __fastcall(void *, struct _DO_DEVINFO_DATA *, void **, struct _DO_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1404ab814`

## callees

- `0x1404828e0`
- `0x1404ab4a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404ab6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404ab711`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404ab6e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1404ab711`
- `ntdll!RtlInitUnicodeString` at `0x1404ab57a`
- `ntdll!RtlInitUnicodeString` at `0x1404ab692`
- `ntdll!RtlInitUnicodeString` at `0x1404ab57a`
- `ntdll!RtlInitUnicodeString` at `0x1404ab692`
- `ntdll!RtlEqualUnicodeString` at `0x1404ab593`
- `ntdll!RtlEqualUnicodeString` at `0x1404ab6ab`
- `ntdll!RtlEqualUnicodeString` at `0x1404ab593`
- `ntdll!RtlEqualUnicodeString` at `0x1404ab6ab`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1404ab632`
- `DEVOBJ!DevObjOpenDeviceInfo` at `0x1404ab632`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1404ab703`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1404ab703`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1404ab55b`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1404ab679`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1404ab55b`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1404ab679`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1404ab5fa`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1404ab5fa`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1404ab5b2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Parent` at `0x1404ab5b2`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1404ab5d7`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_IDW` at `0x1404ab5d7`

## pseudocode

```c

```
