# DsmutilEnumerateAndDelete(DsmDirectoryInfo *,ulong,DsmDirectoryStack &,unsigned __int64 &,uchar &,uchar *,IDsmDeleteCallback *)

- ea: `0x1400e663c`
- end: `0x1400e6daf`
- name: `?DsmutilEnumerateAndDelete@@YAJPEAUDsmDirectoryInfo@@KAEAVDsmDirectoryStack@@AEA_KAEAEPEAEPEAUIDsmDeleteCallback@@@Z`
- size: `1907`
- prototype: `__int64 __fastcall(struct DsmDirectoryInfo *, int, struct DsmDirectoryStack *, unsigned __int64 *, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task`

## callers

- `0x1400e59cc`

## callees

- `0x1400063b4`
- `0x140006984`
- `0x140006d88`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14003c54c`
- `0x140051e98`
- `0x1400db940`
- `0x1400dba10`
- `0x1400e3aa4`
- `0x1400e4518`
- `0x1400e5894`
- `0x1400e58c8`
- `0x1400e6320`
- `0x1400e663c`
- `0x1400e6fe4`
- `0x1400e7310`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindClose` at `0x1400e6da4`
- `KERNEL32!FindClose` at `0x1400e6da4`
- `KERNEL32!FindNextFileW` at `0x1400e6ce1`
- `KERNEL32!FindNextFileW` at `0x1400e6ce1`
- `KERNEL32!FindFirstFileW` at `0x1400e6a21`
- `KERNEL32!FindFirstFileW` at `0x1400e6a21`
- `KERNEL32!GetLastError` at `0x1400e6a32`
- `KERNEL32!GetLastError` at `0x1400e6cf2`
- `KERNEL32!GetLastError` at `0x1400e6a32`
- `KERNEL32!GetLastError` at `0x1400e6cf2`
- `ole32!CoTaskMemAlloc` at `0x1400e698f`
- `ole32!CoTaskMemAlloc` at `0x1400e698f`
- `ole32!CoTaskMemFree` at `0x1400e6a97`
- `ole32!CoTaskMemFree` at `0x1400e6a97`

## pseudocode

```c

```
