# VMX_LOG::Release(void)

- ea: `0x140007600`
- end: `0x14000770e`
- name: `?Release@VMX_LOG@@QEAAXXZ`
- size: `270`
- prototype: `void __fastcall(VMX_LOG *__hidden this)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x14000741c`
- `0x140008a90`
- `0x14000b810`
- `0x14000b970`
- `0x14001a3f0`
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
- `0x14005384c`
- `0x140054328`

## callees

- `0x140007600`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007619`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007619`
- `ntoskrnl!ExQueueWorkItem` at `0x1400076ae`
- `ntoskrnl!ExQueueWorkItem` at `0x1400076ae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007683`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400076f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007683`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400076f1`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400076d1`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400076d1`

## pseudocode

```c

```
