# VhdmpiWin32FilePathToNtFilePath(_UNICODE_STRING const *,_UNICODE_STRING *)

- ea: `0x1400e157c`
- end: `0x1400e17d0`
- name: `?VhdmpiWin32FilePathToNtFilePath@@YAJPEBU_UNICODE_STRING@@PEAU1@@Z`
- size: `596`
- prototype: `int(const struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14009e1c0`

## callees

- `0x14005d7c0`
- `0x14005da00`
- `0x1400aadcc`
- `0x1400e157c`
- `0x1400e17d8`
- `0x1400e1ca4`
- `0x1400e1d7c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400e1706`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e1706`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e1794`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e1794`
- `ntoskrnl!ExAllocatePool2` at `0x1400e169e`
- `ntoskrnl!ExAllocatePool2` at `0x1400e169e`

## pseudocode

```c

```
