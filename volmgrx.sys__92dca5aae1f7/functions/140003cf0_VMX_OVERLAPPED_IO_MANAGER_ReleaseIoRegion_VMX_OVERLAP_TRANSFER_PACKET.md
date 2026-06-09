# VMX_OVERLAPPED_IO_MANAGER::ReleaseIoRegion(VMX_OVERLAP_TRANSFER_PACKET *)

- ea: `0x140003cf0`
- end: `0x140003efb`
- name: `?ReleaseIoRegion@VMX_OVERLAPPED_IO_MANAGER@@QEAAXPEAVVMX_OVERLAP_TRANSFER_PACKET@@@Z`
- size: `523`
- prototype: `void __fastcall(VMX_OVERLAPPED_IO_MANAGER *__hidden this, struct VMX_OVERLAP_TRANSFER_PACKET *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140003774`
- `0x140012d50`
- `0x140012f80`
- `0x140013280`
- `0x140013360`
- `0x1400135d0`
- `0x1400136b0`
- `0x140013898`
- `0x140013be0`
- `0x140016d40`
- `0x1400174d0`
- `0x1400178c0`

## callees

- `0x140003cf0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d4e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003d4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003da0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003da0`

## pseudocode

```c

```
