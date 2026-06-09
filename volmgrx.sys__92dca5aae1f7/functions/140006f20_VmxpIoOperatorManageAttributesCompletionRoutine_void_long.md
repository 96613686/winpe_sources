# VmxpIoOperatorManageAttributesCompletionRoutine(void *,long)

- ea: `0x140006f20`
- end: `0x140006fb0`
- name: `?VmxpIoOperatorManageAttributesCompletionRoutine@@YAXPEAXJ@Z`
- size: `144`
- prototype: `void __fastcall(void *, NTSTATUS Status)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006c80`

## callees

- `0x140005fb0`
- `0x140006f20`
- `0x140007828`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006f32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006f32`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006f52`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006f52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006f9a`

## pseudocode

```c

```
