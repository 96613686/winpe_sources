# TcpUnbindListenerWorkQueueRoutine

- ea: `0x14011c320`
- end: `0x14011c597`
- name: `TcpUnbindListenerWorkQueueRoutine`
- size: `631`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140081654`

## callees

- `0x14002f200`
- `0x1400349f0`
- `0x14005f514`
- `0x140060404`
- `0x1400610b0`
- `0x1400b8080`
- `0x1400b955c`
- `0x14011c320`
- `0x1401bf390`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14011c3bd`
- `ntoskrnl!KfRaiseIrql` at `0x14011c3bd`
- `ntoskrnl!KeLowerIrql` at `0x14011c479`
- `ntoskrnl!KeLowerIrql` at `0x14011c479`
- `ntoskrnl!ExRundownCompleted` at `0x14011c375`
- `ntoskrnl!ExRundownCompleted` at `0x14011c375`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14011c366`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14011c366`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14011c38a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14011c38a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c48a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c527`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c48a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14011c527`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011c559`
- `ntoskrnl!ExFreePoolWithTag` at `0x14011c559`

## pseudocode

```c

```
