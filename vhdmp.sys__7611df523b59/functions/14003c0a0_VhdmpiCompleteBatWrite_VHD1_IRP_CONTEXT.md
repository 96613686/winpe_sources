# VhdmpiCompleteBatWrite(_VHD1_IRP_CONTEXT *)

- ea: `0x14003c0a0`
- end: `0x14003c21d`
- name: `?VhdmpiCompleteBatWrite@@YAXPEAU_VHD1_IRP_CONTEXT@@@Z`
- size: `381`
- prototype: `void __fastcall(struct _VHD1_IRP_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14003b970`

## callees

- `0x140020184`
- `0x140020cd0`
- `0x140020d0c`
- `0x140020e8c`
- `0x140023560`
- `0x140035e94`
- `0x14003c0a0`
- `0x14003e60c`
- `0x14003e648`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x14003c1bb`
- `ntoskrnl!MmUnlockPages` at `0x14003c1bb`
- `ntoskrnl!KeSetEvent` at `0x14003c0c1`
- `ntoskrnl!KeSetEvent` at `0x14003c0c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c142`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14003c142`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c179`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003c179`

## string_xrefs

- `0x14003c126`: `VhdmpiCompleteBatWrite: IrpContext=0x%p SrbPart=0x%p`
- `0x14003c12d`: `VhdmpiCompleteBatWrite`

## pseudocode

```c

```
