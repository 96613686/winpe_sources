# VmxpRaid5ConsolidationCompletionRoutine(void *,long)

- ea: `0x1400144c0`
- end: `0x140014623`
- name: `?VmxpRaid5ConsolidationCompletionRoutine@@YAXPEAXJ@Z`
- size: `355`
- prototype: `void(void *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003bd8`
- `0x140007828`
- `0x14000d0dc`
- `0x1400144c0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400144e5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400144e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014591`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014591`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001451b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001451b`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400144fe`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1400144fe`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001455c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001455c`

## pseudocode

```c

```
