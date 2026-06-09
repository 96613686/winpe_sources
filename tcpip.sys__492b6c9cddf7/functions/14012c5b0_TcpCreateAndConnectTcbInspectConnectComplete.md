# TcpCreateAndConnectTcbInspectConnectComplete

- ea: `0x14012c5b0`
- end: `0x14012cfbe`
- name: `TcpCreateAndConnectTcbInspectConnectComplete`
- size: `2574`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `28`
- tags: `broker_com_uri`

## callers

- `0x1400ecfa0`

## callees

- `0x1400064f8`
- `0x14000726c`
- `0x14000890c`
- `0x140009470`
- `0x140009990`
- `0x140012d30`
- `0x140014290`
- `0x140015d10`
- `0x14001bed0`
- `0x14002f200`
- `0x140035ae0`
- `0x140038530`
- `0x1400739b0`
- `0x14008d7c0`
- `0x1400942d4`
- `0x1400afcb0`
- `0x1400b8080`
- `0x1400b8130`
- `0x1400b86c0`
- `0x1400d33f0`
- `0x1400f1670`
- `0x1400f20f0`
- `0x1400f81b0`
- `0x1400ff4c0`
- `0x140107bf8`
- `0x14012c5b0`
- `0x14015aaac`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14012c85f`
- `ntoskrnl!KfRaiseIrql` at `0x14012c85f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14012c8c5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14012c98f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14012cb6f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14012c8c5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14012c98f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14012cb6f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cabf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cade`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cbdb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cbff`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cabf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cade`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cbdb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012cbff`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14012cc41`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14012cc41`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14012cc14`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14012cc14`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012c668`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012cf68`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012c668`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012cf68`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012c640`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012c96b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012cf40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012c640`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012c96b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012cf40`

## string_xrefs

- `0x14012c79a`: `Updating Template Connect Inspect completed.`

## pseudocode

```c

```
