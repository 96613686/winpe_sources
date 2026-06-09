# BlbExtendFileSystemToVolumeSize(ushort *)

- ea: `0x1400f222c`
- end: `0x1400f25b9`
- name: `?BlbExtendFileSystemToVolumeSize@@YAJPEAG@Z`
- size: `909`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x14005a62c`

## callees

- `0x14000bb4c`
- `0x140014260`
- `0x14003c9cc`
- `0x1400f222c`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1400f229d`
- `KERNEL32!CreateFileW` at `0x1400f229d`
- `KERNEL32!CloseHandle` at `0x1400f255d`
- `KERNEL32!CloseHandle` at `0x1400f255d`
- `KERNEL32!GetLastError` at `0x1400f22ac`
- `KERNEL32!GetLastError` at `0x1400f2348`
- `KERNEL32!GetLastError` at `0x1400f2515`
- `KERNEL32!GetLastError` at `0x1400f22ac`
- `KERNEL32!GetLastError` at `0x1400f2348`
- `KERNEL32!GetLastError` at `0x1400f2515`
- `KERNEL32!DeviceIoControl` at `0x1400f233e`
- `KERNEL32!DeviceIoControl` at `0x1400f250b`
- `KERNEL32!DeviceIoControl` at `0x1400f233e`
- `KERNEL32!DeviceIoControl` at `0x1400f250b`
- `ntdll!RtlNtStatusToDosError` at `0x1400f240a`
- `ntdll!RtlNtStatusToDosError` at `0x1400f240a`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400f23fe`
- `ntdll!NtQueryVolumeInformationFile` at `0x1400f23fe`

## pseudocode

```c

```
