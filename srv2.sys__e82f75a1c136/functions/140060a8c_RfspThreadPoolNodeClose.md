# RfspThreadPoolNodeClose

- ea: `0x140060a8c`
- end: `0x140060b11`
- name: `RfspThreadPoolNodeClose`
- size: `133`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140060828`
- `0x140091e6c`

## callees

- `0x140060a8c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140060aa8`
- `ntoskrnl!KeSetEvent` at `0x140060aa8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060acc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140060acc`
- `ntoskrnl!ObfDereferenceObject` at `0x140060adf`
- `ntoskrnl!ObfDereferenceObject` at `0x140060adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060afe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140060afe`

## pseudocode

```c

```
