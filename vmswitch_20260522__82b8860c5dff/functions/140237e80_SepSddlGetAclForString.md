# SepSddlGetAclForString

- ea: `0x140237e80`
- end: `0x140238234`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140237d9c`

## callees

- `0x1401bc2c0`
- `0x140237ca8`
- `0x140237e80`
- `0x14023823c`
- `0x1402382f4`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x140238044`
- `ntoskrnl!_wcsnicmp` at `0x1402380bd`
- `ntoskrnl!_wcsnicmp` at `0x140238044`
- `ntoskrnl!_wcsnicmp` at `0x1402380bd`
- `ntoskrnl!wcschr` at `0x140237eab`
- `ntoskrnl!wcschr` at `0x140237eab`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140237f62`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140237fa7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140237f62`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140237fa7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402381fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402381fc`

## pseudocode

```c

```
