# TcpUnbindListenerWorkQueueRoutine

- ea: `0x14011c460`
- end: `0x14011c6d7`
- name: `TcpUnbindListenerWorkQueueRoutine`
- size: `631`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140082504`

## callees

- `0x14002f4a0`
- `0x140034c90`
- `0x14005f7b4`
- `0x1400606a4`
- `0x140061350`
- `0x1400b7ca0`
- `0x1400b917c`
- `0x14011c460`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14011c4fd`
- `ntoskrnl!KfRaiseIrql` at `0x14011c4fd`
- `ntoskrnl!KeLowerIrql` at `0x14011c5b9`
- `ntoskrnl!KeLowerIrql` at `0x14011c5b9`
- `ntoskrnl!ExRundownCompleted` at `0x14011c4b5`
- `ntoskrnl!ExRundownCompleted` at `0x14011c4b5`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14011c4a6`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14011c4a6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14011c4ca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14011c4ca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c5ca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c667`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c5ca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c667`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011c699`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011c699`

## pseudocode

```c

```
