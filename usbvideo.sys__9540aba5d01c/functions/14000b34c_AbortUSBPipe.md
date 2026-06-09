# AbortUSBPipe

- ea: `0x14000b34c`
- end: `0x14000b575`
- name: `AbortUSBPipe`
- size: `553`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a928`
- `0x1400149f0`
- `0x14001ca10`
- `0x14001ef60`
- `0x1400247e0`
- `0x140038e90`
- `0x140039650`

## callees

- `0x140009b9c`
- `0x14000b34c`
- `0x14001ab4c`
- `0x14001b15c`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14000b4ba`
- `ntoskrnl!KeResetEvent` at `0x14000b4ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b49b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b49b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b4ec`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000b4ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b559`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b559`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b3a0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000b3a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b500`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b4cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b500`

## pseudocode

```c

```
