# GetPhysicalDriveNumbers(_GUID const &,ulong *,ushort * *,ulong,ulong *)

- ea: `0x1400bf5c0`
- end: `0x1400bf9ce`
- name: `?GetPhysicalDriveNumbers@@YAJAEBU_GUID@@PEAKPEAPEAGK1@Z`
- size: `1038`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned int *, unsigned __int16 **, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1400bf084`
- `0x14045bc40`
- `0x1407757fc`

## callees

- `0x14004f3c4`
- `0x14005c630`
- `0x1400bf5c0`
- `0x1404828e0`
- `0x1404835a0`
- `0x140486128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400bf917`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400bf95e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400bf917`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400bf95e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400bf760`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400bf760`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1400bf8c7`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1400bf8c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf8f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf93e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf64e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf69a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf8f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400bf93e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400bf84e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400bf84e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400bf7e9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400bf7e9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400bf83c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400bf83c`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400bf68a`
- `DEVOBJ!DevObjGetClassDevs` at `0x1400bf68a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1400bf6d4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1400bf6d4`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400bf998`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1400bf998`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400bf73a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400bf7b0`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400bf73a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1400bf7b0`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400bf70b`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1400bf70b`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400bf639`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1400bf639`

## pseudocode

```c

```
