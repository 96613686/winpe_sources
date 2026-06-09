# VMX_LOG::QueueLogPacket(VMX_LOG_TRANSFER_PACKET *)

- ea: `0x140003bd8`
- end: `0x140003ce9`
- name: `?QueueLogPacket@VMX_LOG@@QEAAXPEAVVMX_LOG_TRANSFER_PACKET@@@Z`
- size: `273`
- prototype: `void __fastcall(VMX_LOG *__hidden this, struct VMX_LOG_TRANSFER_PACKET *)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ea0`
- `0x140002650`
- `0x140002be0`
- `0x1400032d0`
- `0x140003a90`
- `0x140003f04`
- `0x140007bb0`
- `0x14000e85c`
- `0x14000e930`
- `0x14000ea38`
- `0x14000f068`
- `0x1400144c0`
- `0x140014d60`
- `0x1400174d0`

## callees

- `0x140003bd8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003bf4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003bf4`
- `ntoskrnl!ExQueueWorkItem` at `0x140003cb1`
- `ntoskrnl!ExQueueWorkItem` at `0x140003cb1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c86`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003cd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003c86`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003cd4`

## pseudocode

```c

```
