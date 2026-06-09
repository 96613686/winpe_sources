# GetDriveTypeByHandle(void *,uint *)

- ea: `0x140025b74`
- end: `0x140025e33`
- name: `?GetDriveTypeByHandle@@YAHPEAXPEAI@Z`
- size: `703`
- prototype: `__int64 __fastcall(HANDLE hDevice, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1400253dc`

## callees

- `0x14001f7b4`
- `0x140021ca0`
- `0x1400235a8`
- `0x140025b74`
- `0x140091560`
- `0x1400d257c`
- `0x1400d2c1c`
- `0x1400d7ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140025e0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140025e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025d79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025d54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025d79`
- `ntdll!NtQueryVolumeInformationFile` at `0x140025c42`
- `ntdll!NtQueryVolumeInformationFile` at `0x140025c8b`
- `ntdll!NtQueryVolumeInformationFile` at `0x140025c42`
- `ntdll!NtQueryVolumeInformationFile` at `0x140025c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025df7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140025df7`

## pseudocode

```c

```
