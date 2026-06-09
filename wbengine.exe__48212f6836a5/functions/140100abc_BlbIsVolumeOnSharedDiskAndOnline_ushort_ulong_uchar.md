# BlbIsVolumeOnSharedDiskAndOnline(ushort *,ulong,uchar *)

- ea: `0x140100abc`
- end: `0x140100e33`
- name: `?BlbIsVolumeOnSharedDiskAndOnline@@YAJPEAGKPEAE@Z`
- size: `887`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x14000faac`
- `0x140045dec`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x1400142d8`
- `0x140088ba4`
- `0x140100abc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140100c8d`
- `KERNEL32!CreateFileW` at `0x140100c8d`
- `KERNEL32!CloseHandle` at `0x140100dd5`
- `KERNEL32!CloseHandle` at `0x140100dd5`
- `KERNEL32!GetLastError` at `0x140100c9c`
- `KERNEL32!GetLastError` at `0x140100d34`
- `KERNEL32!GetLastError` at `0x140100c9c`
- `KERNEL32!GetLastError` at `0x140100d34`
- `KERNEL32!DeviceIoControl` at `0x140100d2a`
- `KERNEL32!DeviceIoControl` at `0x140100d2a`
- `ole32!CoTaskMemFree` at `0x140100dea`
- `ole32!CoTaskMemFree` at `0x140100dea`
- `CLUSAPI!GetNodeClusterState` at `0x140100b68`
- `CLUSAPI!GetNodeClusterState` at `0x140100b68`

## pseudocode

```c

```
