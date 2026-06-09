# CRegAccount::GetTempDir(ushort *,int,int *)

- ea: `0x180024a54`
- end: `0x180024b5d`
- name: `?GetTempDir@CRegAccount@@CAJPEAGHPEAH@Z`
- size: `265`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800214a4`
- `0x180023044`

## callees

- `0x180002584`
- `0x180007824`
- `0x180024a54`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180024a99`
- `KERNEL32!lstrlenW` at `0x180024ad3`
- `KERNEL32!lstrlenW` at `0x180024a99`
- `KERNEL32!lstrlenW` at `0x180024ad3`
- `KERNEL32!GetFileAttributesW` at `0x180024b0b`
- `KERNEL32!GetFileAttributesW` at `0x180024b0b`

## string_xrefs

- `0x180024af0`: `Temporary ASP.NET Files`

## pseudocode

```c

```
