# VMX_IO_RAID5::RecycleRecoverPacket(VMX_RAID5_RECOVER_TRANSFER_PACKET *)

- ea: `0x1400110f8`
- end: `0x1400111e0`
- name: `?RecycleRecoverPacket@VMX_IO_RAID5@@QEAAXPEAVVMX_RAID5_RECOVER_TRANSFER_PACKET@@@Z`
- size: `232`
- prototype: `void __fastcall(VMX_IO_RAID5 *__hidden this, struct VMX_RAID5_RECOVER_TRANSFER_PACKET *)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x140007f70`
- `0x140008150`
- `0x140008300`
- `0x1400155a0`
- `0x1400156b0`
- `0x140015730`
- `0x1400157f0`
- `0x140015a60`
- `0x140015b70`
- `0x140015ca0`
- `0x140016020`
- `0x140016680`
- `0x140016740`
- `0x1400167f0`
- `0x1400168b0`
- `0x140016be0`

## callees

- `0x1400110f8`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011169`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011169`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011192`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011192`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400111bb`
- `ntoskrnl!MmUnmapLockedPages` at `0x140011156`
- `ntoskrnl!MmUnmapLockedPages` at `0x140011156`

## pseudocode

```c

```
