# CheckDevicePathIsWritable(ushort const *)

- ea: `0x180089648`
- end: `0x180089b1a`
- name: `?CheckDevicePathIsWritable@@YAJPEBG@Z`
- size: `1234`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18000f4a4`
- `0x18004e204`

## callees

- `0x180001f88`
- `0x180008370`
- `0x1800083a0`
- `0x180089648`
- `0x1800cf552`
- `0x1800cf55e`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `ntdll!NtClose` at `0x180089aad`
- `ntdll!NtClose` at `0x180089aad`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800898d6`
- `ntdll!RtlIsDosDeviceName_U` at `0x1800898d6`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x180089899`
- `ntdll!RtlAnsiCharToUnicodeChar` at `0x180089899`
- `ntdll!RtlIntegerToChar` at `0x18008987b`
- `ntdll!RtlIntegerToChar` at `0x18008987b`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800896b2`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800896b2`
- `KERNEL32!CreateFileW` at `0x180089943`
- `KERNEL32!CreateFileW` at `0x180089943`
- `KERNEL32!GetLastError` at `0x180089959`
- `KERNEL32!GetLastError` at `0x180089959`
- `KERNEL32!GetFileAttributesW` at `0x180089791`
- `KERNEL32!GetFileAttributesW` at `0x1800897cb`
- `KERNEL32!GetFileAttributesW` at `0x180089791`
- `KERNEL32!GetFileAttributesW` at `0x1800897cb`

## pseudocode

```c

```
