# VhdmpiCleanupMirrorAsyncCopyContext(_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *)

- ea: `0x1400b3110`
- end: `0x1400b3201`
- name: `?VhdmpiCleanupMirrorAsyncCopyContext@@YAXPEAU_VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT@@@Z`
- size: `241`
- prototype: `void __fastcall(struct _VHD_INTERNAL_ASYNC_MIRROR_COPY_CONTEXT *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400b2ee0`
- `0x1400b5ebc`

## callees

- `0x140033598`
- `0x1400b3110`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b319e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b319e`
- `ntoskrnl!ZwClose` at `0x1400b317e`
- `ntoskrnl!ZwClose` at `0x1400b317e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b31e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b31e0`
- `ntoskrnl!KeSetEvent` at `0x1400b316d`
- `ntoskrnl!KeSetEvent` at `0x1400b316d`

## pseudocode

```c

```
