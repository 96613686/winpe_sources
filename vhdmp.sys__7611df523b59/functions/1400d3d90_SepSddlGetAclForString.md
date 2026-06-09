# SepSddlGetAclForString

- ea: `0x1400d3d90`
- end: `0x1400d4136`
- name: `SepSddlGetAclForString`
- size: `934`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400d3cac`

## callees

- `0x140028f5f`
- `0x14005dd00`
- `0x1400d3bb8`
- `0x1400d3d90`
- `0x1400d413c`
- `0x1400d41ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d40fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d40fe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3e72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3eb7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3e72`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3eb7`
- `ntoskrnl!wcschr` at `0x1400d3dbb`
- `ntoskrnl!wcschr` at `0x1400d3dbb`

## pseudocode

```c

```
