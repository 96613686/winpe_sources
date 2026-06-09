# VhdmpiPrefetchThisBlock(_VHD_PREFETCH_BLOCK *)

- ea: `0x1400b8e10`
- end: `0x1400b9073`
- name: `?VhdmpiPrefetchThisBlock@@YAXPEAU_VHD_PREFETCH_BLOCK@@@Z`
- size: `611`
- prototype: `void __fastcall(struct _VHD_PREFETCH_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400b8d34`

## callees

- `0x140016cc0`
- `0x140023980`
- `0x140036284`
- `0x14005dac2`
- `0x14005dbb0`
- `0x14005e100`
- `0x1400b8824`
- `0x1400b8e10`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b8f86`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b902f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b8f86`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b902f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9043`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9043`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8eaa`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8f41`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8eaa`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8f41`

## string_xrefs

- `0x1400b8feb`: `Prefetch read failed: Filename = %wZ, Offset = %I64u, Length = %u, Status = 0x%08x`

## pseudocode

```c

```
