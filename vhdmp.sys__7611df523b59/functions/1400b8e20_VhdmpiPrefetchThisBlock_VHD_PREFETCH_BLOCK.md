# VhdmpiPrefetchThisBlock(_VHD_PREFETCH_BLOCK *)

- ea: `0x1400b8e20`
- end: `0x1400b9083`
- name: `?VhdmpiPrefetchThisBlock@@YAXPEAU_VHD_PREFETCH_BLOCK@@@Z`
- size: `611`
- prototype: `void __fastcall(struct _VHD_PREFETCH_BLOCK *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400b8d44`

## callees

- `0x140016820`
- `0x140023560`
- `0x140035e94`
- `0x14005d6d2`
- `0x14005d7c0`
- `0x14005dd00`
- `0x1400b8834`
- `0x1400b8e20`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b8f96`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b903f`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b8f96`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400b903f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9053`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b9053`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8eba`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8f51`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8eba`
- `ntoskrnl!KeInitializeEvent` at `0x1400b8f51`

## string_xrefs

- `0x1400b8ffb`: `Prefetch read failed: Filename = %wZ, Offset = %I64u, Length = %u, Status = 0x%08x`

## pseudocode

```c

```
