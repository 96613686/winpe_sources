# VsmmExopGpaRangeAccessFaultRange

- ea: `0x1400fcd0c`
- end: `0x1400fd08f`
- name: `VsmmExopGpaRangeAccessFaultRange`
- size: `899`
- prototype: `__int64 __fastcall(int, int, int, int, PRKPROCESS PROCESS, int, char, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400d2788`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140038630`
- `0x1400ef24c`
- `0x1400fcd0c`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x1400fcf7a`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400fcf7a`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400fd007`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400fd007`
- `ntoskrnl!KeStackAttachProcess` at `0x1400fd01f`
- `ntoskrnl!KeStackAttachProcess` at `0x1400fd01f`

## string_xrefs

- `0x1400fcdc9`: `VsmmExopGpaRangeAccessFaultRange`
- `0x1400fce00`: `VsmmExopGpaRangeAccessFaultRange`

## pseudocode

```c

```
