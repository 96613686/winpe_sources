# VmxpConsolidationCompletionRoutine(void *,long)

- ea: `0x140006140`
- end: `0x1400061c1`
- name: `?VmxpConsolidationCompletionRoutine@@YAXPEAXJ@Z`
- size: `129`
- prototype: `void __fastcall(PVOID P, NTSTATUS Status)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140006140`
- `0x140007828`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006152`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006152`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006173`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006173`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006198`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006198`

## pseudocode

```c

```
