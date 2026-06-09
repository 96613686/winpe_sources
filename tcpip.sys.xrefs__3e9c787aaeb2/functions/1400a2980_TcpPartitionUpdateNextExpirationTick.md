# TcpPartitionUpdateNextExpirationTick

- ea: `0x1400a2980`
- end: `0x1400a2d17`
- name: `TcpPartitionUpdateNextExpirationTick`
- size: `919`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140009480`
- `0x14000e2f0`
- `0x140031340`
- `0x140033140`
- `0x1400438b0`
- `0x1400a20c0`
- `0x1400a2590`
- `0x1400a3020`
- `0x1400d1200`
- `0x1400ef1c4`
- `0x1400f74d0`
- `0x1400fd118`
- `0x14011887c`

## callees

- `0x1400198ec`
- `0x140034500`
- `0x140043548`
- `0x1400a2980`
- `0x14014eb54`

## import_xrefs

- `ntoskrnl!KeSetTimerEx` at `0x1400a2b31`
- `ntoskrnl!KeSetTimerEx` at `0x1400a2b31`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400a2c45`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1400a2c45`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a2b03`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a2b8e`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a2b03`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400a2b8e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a29fb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400a29fb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a2b70`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400a2b70`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400a29d4`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1400a29d4`

## pseudocode

```c

```
