# SxSetFileAttributes(ushort const *,ulong)

- ea: `0x18009b7c8`
- end: `0x18009ba10`
- name: `?SxSetFileAttributes@@YAJPEBGK@Z`
- size: `584`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18009af48`
- `0x18009b1dc`
- `0x18009c17c`

## callees

- `0x180008370`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180093698`
- `0x18009b7c8`
- `0x1800cf5c0`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18009b9a7`
- `ntdll!NtSetInformationFile` at `0x18009b9a7`
- `ntdll!NtQueryInformationFile` at `0x18009b967`
- `ntdll!NtQueryInformationFile` at `0x18009b967`
- `KERNEL32!CreateFileW` at `0x18009b8ab`
- `KERNEL32!CreateFileW` at `0x18009b8ab`
- `KERNEL32!CloseHandle` at `0x18009b9d5`
- `KERNEL32!CloseHandle` at `0x18009b9d5`

## string_xrefs

- `0x18009b82b`: `SxSetFileAttributes`

## pseudocode

```c

```
