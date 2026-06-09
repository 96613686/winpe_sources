# VhdmpiCompleteBatWrite(_VHD1_IRP_CONTEXT *)

- ea: `0x14003c490`
- end: `0x14003c60d`
- name: `?VhdmpiCompleteBatWrite@@YAXPEAU_VHD1_IRP_CONTEXT@@@Z`
- size: `381`
- prototype: `void __fastcall(struct _VHD1_IRP_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14003bd60`

## callees

- `0x1400205a4`
- `0x1400210f0`
- `0x14002112c`
- `0x1400212ac`
- `0x140023980`
- `0x140036284`
- `0x14003c490`
- `0x14003e9fc`
- `0x14003ea38`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14003c5ab`
- `ntoskrnl!MmUnlockPages` at `0x14003c5ab`
- `ntoskrnl!KeSetEvent` at `0x14003c4b1`
- `ntoskrnl!KeSetEvent` at `0x14003c4b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c532`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c532`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c569`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c569`

## string_xrefs

- `0x14003c51d`: `VhdmpiCompleteBatWrite`
- `0x14003c516`: `VhdmpiCompleteBatWrite: IrpContext=0x%p SrbPart=0x%p`

## pseudocode

```c

```
