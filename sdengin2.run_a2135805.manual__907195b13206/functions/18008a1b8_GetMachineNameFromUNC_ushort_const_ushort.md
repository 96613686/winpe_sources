# GetMachineNameFromUNC(ushort const *,ushort * *)

- ea: `0x18008a1b8`
- end: `0x18008a437`
- name: `?GetMachineNameFromUNC@@YAJPEBGPEAPEAG@Z`
- size: `639`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x18008d150`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008a1b8`
- `0x18008a874`
- `0x1800935fc`
- `0x180093698`
- `0x18009e208`
- `0x18009e904`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!wcschr` at `0x18008a376`
- `msvcrt!wcschr` at `0x18008a376`
- `ntdll!NtQueryInformationFile` at `0x18008a313`
- `ntdll!NtQueryInformationFile` at `0x18008a313`
- `KERNEL32!CreateFileW` at `0x18008a2b9`
- `KERNEL32!CreateFileW` at `0x18008a2b9`
- `KERNEL32!CloseHandle` at `0x18008a3fc`
- `KERNEL32!CloseHandle` at `0x18008a3fc`

## pseudocode

```c

```
