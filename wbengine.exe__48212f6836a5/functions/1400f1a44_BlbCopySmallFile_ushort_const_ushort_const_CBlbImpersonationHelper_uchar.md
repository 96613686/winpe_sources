# BlbCopySmallFile(ushort const *,ushort const *,CBlbImpersonationHelper *,uchar)

- ea: `0x1400f1a44`
- end: `0x1400f1ef4`
- name: `?BlbCopySmallFile@@YAJPEBG0PEAVCBlbImpersonationHelper@@E@Z`
- size: `1200`
- prototype: `__int64 __fastcall(unsigned __int16 *, WCHAR *, struct CBlbImpersonationHelper *this, char)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x140020034`
- `0x1400f16ac`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140014260`
- `0x1400142d8`
- `0x14003cb70`
- `0x14008ca7c`
- `0x14008e808`
- `0x1400c4178`
- `0x1400f007c`
- `0x1400f07dc`
- `0x1400f1a44`
- `0x14012458c`

## import_xrefs

- `KERNEL32!FlushFileBuffers` at `0x1400f1df5`
- `KERNEL32!FlushFileBuffers` at `0x1400f1df5`
- `KERNEL32!WriteFile` at `0x1400f1d30`
- `KERNEL32!WriteFile` at `0x1400f1d30`
- `KERNEL32!CloseHandle` at `0x1400f1e60`
- `KERNEL32!CloseHandle` at `0x1400f1e84`
- `KERNEL32!CloseHandle` at `0x1400f1e60`
- `KERNEL32!CloseHandle` at `0x1400f1e84`
- `KERNEL32!GetLastError` at `0x1400f1d3a`
- `KERNEL32!GetLastError` at `0x1400f1e07`
- `KERNEL32!GetLastError` at `0x1400f1d3a`
- `KERNEL32!GetLastError` at `0x1400f1e07`
- `ntdll!RtlGetLastNtStatus` at `0x1400f1dff`
- `ntdll!RtlGetLastNtStatus` at `0x1400f1dff`
- `ole32!CoTaskMemFree` at `0x1400f1c17`
- `ole32!CoTaskMemFree` at `0x1400f1c17`

## pseudocode

```c

```
