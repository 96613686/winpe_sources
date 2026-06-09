# VhdmpiShutdownThreadPool

- ea: `0x1400bcfa8`
- end: `0x1400bd09d`
- name: `VhdmpiShutdownThreadPool`
- size: `245`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400cab70`
- `0x1400ee1f0`

## callees

- `0x1400bcfa8`

## import_xrefs

- `ntoskrnl!KeRundownQueue` at `0x1400bcfe6`
- `ntoskrnl!KeRundownQueue` at `0x1400bcfe6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd017`
- `ntoskrnl!ObfDereferenceObject` at `0x1400bd017`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bd007`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bd007`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd03c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd06f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd03c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bd06f`

## pseudocode

```c

```
