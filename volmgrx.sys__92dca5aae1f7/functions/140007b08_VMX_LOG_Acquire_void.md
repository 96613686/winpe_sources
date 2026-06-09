# VMX_LOG::Acquire(void)

- ea: `0x140007b08`
- end: `0x140007b9e`
- name: `?Acquire@VMX_LOG@@QEAAXXZ`
- size: `150`
- prototype: `void __fastcall(VMX_LOG *__hidden this)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x14000741c`
- `0x14000b810`
- `0x14000b970`
- `0x14002a3f4`
- `0x14002a920`
- `0x14002eaf4`
- `0x14002f1e4`
- `0x1400316d4`
- `0x140033278`
- `0x140039028`
- `0x1400397a0`
- `0x14004a6b0`
- `0x14004b3dc`
- `0x14004bbe4`
- `0x14004e3ac`
- `0x1400532d4`
- `0x14005343c`
- `0x14005384c`
- `0x140054328`

## callees

- `0x140007b08`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b63`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b1b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b88`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007b88`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007b52`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007b52`

## pseudocode

```c

```
