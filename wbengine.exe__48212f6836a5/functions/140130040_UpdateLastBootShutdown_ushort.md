# UpdateLastBootShutdown(ushort *)

- ea: `0x140130040`
- end: `0x1401302e1`
- name: `?UpdateLastBootShutdown@@YAJPEAG@Z`
- size: `673`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x14007d630`

## callees

- `0x14000bb24`
- `0x14000bb4c`
- `0x140014260`
- `0x140028500`
- `0x14008863c`
- `0x140088ba4`
- `0x140130040`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140130118`
- `KERNEL32!CreateFileW` at `0x140130118`
- `KERNEL32!GetLastError` at `0x140130127`
- `KERNEL32!GetLastError` at `0x140130127`
- `ntdll!RtlGetSetBootStatusData` at `0x14013019d`
- `ntdll!RtlGetSetBootStatusData` at `0x1401301d5`
- `ntdll!RtlGetSetBootStatusData` at `0x140130231`
- `ntdll!RtlGetSetBootStatusData` at `0x14013019d`
- `ntdll!RtlGetSetBootStatusData` at `0x1401301d5`
- `ntdll!RtlGetSetBootStatusData` at `0x140130231`
- `ntdll!RtlUnlockBootStatusData` at `0x140130273`
- `ntdll!RtlUnlockBootStatusData` at `0x140130273`
- `ole32!CoTaskMemFree` at `0x14013028b`
- `ole32!CoTaskMemFree` at `0x14013028b`

## pseudocode

```c

```
