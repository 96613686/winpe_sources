# GetMachineNameFromUNC(ushort const *,ushort * *)

- ea: `0x180086874`
- end: `0x180086ad6`
- name: `?GetMachineNameFromUNC@@YAJPEBGPEAPEAG@Z`
- size: `610`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18008960c`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180086874`
- `0x180086ef8`
- `0x18008f5d0`
- `0x18008f660`
- `0x180099bb0`
- `0x18009a24c`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `msvcrt!wcschr` at `0x180086a22`
- `msvcrt!wcschr` at `0x180086a22`
- `ntdll!NtQueryInformationFile` at `0x1800869c9`
- `ntdll!NtQueryInformationFile` at `0x1800869c9`
- `KERNEL32!CreateFileW` at `0x180086975`
- `KERNEL32!CreateFileW` at `0x180086975`
- `KERNEL32!CloseHandle` at `0x180086aa2`
- `KERNEL32!CloseHandle` at `0x180086aa2`

## pseudocode

```c

```
