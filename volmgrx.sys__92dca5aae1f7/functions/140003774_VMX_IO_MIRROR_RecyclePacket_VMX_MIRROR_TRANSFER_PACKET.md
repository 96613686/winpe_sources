# VMX_IO_MIRROR::RecyclePacket(VMX_MIRROR_TRANSFER_PACKET *)

- ea: `0x140003774`
- end: `0x140003a7e`
- name: `?RecyclePacket@VMX_IO_MIRROR@@QEAAXPEAVVMX_MIRROR_TRANSFER_PACKET@@@Z`
- size: `778`
- prototype: `void __fastcall(VMX_IO_MIRROR *__hidden this, struct VMX_MIRROR_TRANSFER_PACKET *)`
- caller_count: `11`
- callee_count: `7`
- tags: ``

## callers

- `0x140001ab0`
- `0x140002be0`
- `0x1400032d0`
- `0x140012d50`
- `0x140012f80`
- `0x140013280`
- `0x140013360`
- `0x1400135d0`
- `0x1400136b0`
- `0x140013898`
- `0x140013a90`

## callees

- `0x140001948`
- `0x140001ea0`
- `0x140002470`
- `0x140002650`
- `0x140003774`
- `0x140003cf0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003824`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400038a1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003824`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400038a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000384c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003880`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400038dc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000384c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003880`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400038dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400039e0`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000394a`
- `ntoskrnl!MmUnmapLockedPages` at `0x14000394a`

## pseudocode

```c

```
