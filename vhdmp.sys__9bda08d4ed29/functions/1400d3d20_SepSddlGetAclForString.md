# SepSddlGetAclForString

- ea: `0x1400d3d20`
- end: `0x1400d40c6`
- name: `SepSddlGetAclForString`
- size: `934`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400d3c3c`

## callees

- `0x14002947f`
- `0x14005e100`
- `0x1400d3b48`
- `0x1400d3d20`
- `0x1400d40cc`
- `0x1400d417c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400d408e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d408e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3e02`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3e47`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3e02`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400d3e47`
- `ntoskrnl!wcschr` at `0x1400d3d4b`
- `ntoskrnl!wcschr` at `0x1400d3d4b`

## pseudocode

```c

```
