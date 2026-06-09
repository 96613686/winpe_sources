# CheckDevicePathIsWritable(ushort const *)

- ea: `0x180085d80`
- end: `0x180086217`
- name: `?CheckDevicePathIsWritable@@YAJPEBG@Z`
- size: `1175`
- prototype: `__int64 __fastcall(WCHAR *Src)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000eed8`
- `0x18004c4c4`

## callees

- `0x180001f18`
- `0x1800081d8`
- `0x180008200`
- `0x180085d80`
- `0x1800c97c2`
- `0x1800c97ce`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `ntdll!NtClose` at `0x1800861b1`
- `ntdll!NtClose` at `0x1800861b1`
- `ntdll!RtlIsDosDeviceName_U` at `0x180085ff0`
- `ntdll!RtlIsDosDeviceName_U` at `0x180085ff0`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x180085fb9`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x180085fb9`
- `ntdll!RtlIntegerToChar` at `0x180085fa1`
- `ntdll!RtlIntegerToChar` at `0x180085fa1`
- `ntdll!RtlInitUnicodeStringEx` at `0x180085dea`
- `ntdll!RtlInitUnicodeStringEx` at `0x180085dea`
- `KERNEL32!CreateFileW` at `0x180086057`
- `KERNEL32!CreateFileW` at `0x180086057`
- `KERNEL32!GetLastError` at `0x180086067`
- `KERNEL32!GetLastError` at `0x180086067`
- `KERNEL32!GetFileAttributesW` at `0x180085ec3`
- `KERNEL32!GetFileAttributesW` at `0x180085ef7`
- `KERNEL32!GetFileAttributesW` at `0x180085ec3`
- `KERNEL32!GetFileAttributesW` at `0x180085ef7`

## pseudocode

```c

```
