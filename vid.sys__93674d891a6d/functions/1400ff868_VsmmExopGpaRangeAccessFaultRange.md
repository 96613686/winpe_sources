# VsmmExopGpaRangeAccessFaultRange

- ea: `0x1400ff868`
- end: `0x1400ffbeb`
- name: `VsmmExopGpaRangeAccessFaultRange`
- size: `899`
- prototype: `__int64 __fastcall(int, int, int, int, PRKPROCESS PROCESS, int, char, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400d5128`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400386a0`
- `0x1400f19cc`
- `0x1400ff868`

## import_xrefs

- `ntoskrnl!KeUnstackDetachProcess` at `0x1400ffad6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400ffad6`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ffb63`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ffb63`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ffb7b`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ffb7b`

## string_xrefs

- `0x1400ff925`: `VsmmExopGpaRangeAccessFaultRange`
- `0x1400ff95c`: `VsmmExopGpaRangeAccessFaultRange`

## pseudocode

```c

```
