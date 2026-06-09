# SepSddlGetAclForString

- ea: `0x140237ee0`
- end: `0x140238294`
- name: `SepSddlGetAclForString`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *Str1, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140237dfc`

## callees

- `0x1401bc340`
- `0x140237d08`
- `0x140237ee0`
- `0x14023829c`
- `0x140238354`

## import_xrefs

- `ntoskrnl!_wcsnicmp` at `0x1402380a4`
- `ntoskrnl!_wcsnicmp` at `0x14023811d`
- `ntoskrnl!_wcsnicmp` at `0x1402380a4`
- `ntoskrnl!_wcsnicmp` at `0x14023811d`
- `ntoskrnl!wcschr` at `0x140237f0b`
- `ntoskrnl!wcschr` at `0x140237f0b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140237fc2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140238007`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140237fc2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140238007`
- `ntoskrnl!ExFreePoolWithTag` at `0x14023825c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14023825c`

## pseudocode

```c

```
