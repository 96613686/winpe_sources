# VhdmpiWin32FilePathToNtFilePath(_UNICODE_STRING const *,_UNICODE_STRING *)

- ea: `0x1400e150c`
- end: `0x1400e1760`
- name: `?VhdmpiWin32FilePathToNtFilePath@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z`
- size: `596`
- prototype: `int(const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14009e1c0`

## callees

- `0x14005dbb0`
- `0x14005de00`
- `0x1400aadcc`
- `0x1400e150c`
- `0x1400e1768`
- `0x1400e1c34`
- `0x1400e1d0c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400e1696`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e1696`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e1724`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e1724`
- `ntoskrnl!ExAllocatePool2` at `0x1400e162e`
- `ntoskrnl!ExAllocatePool2` at `0x1400e162e`

## pseudocode

```c

```
