# VsmmNtSlatCreateVaGpaRange

- ea: `0x1400ec594`
- end: `0x1400ec683`
- name: `VsmmNtSlatCreateVaGpaRange`
- size: `239`
- prototype: `__int64 __fastcall(int, int, int, int, int, PRKPROCESS PROCESS, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400cb1bc`
- `0x1400ebea0`

## callees

- `0x140021650`
- `0x1400217a0`
- `0x1400ec594`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x1400ec655`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400ec655`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ec5e5`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ec5e5`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ec5fe`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ec5fe`

## pseudocode

```c

```
