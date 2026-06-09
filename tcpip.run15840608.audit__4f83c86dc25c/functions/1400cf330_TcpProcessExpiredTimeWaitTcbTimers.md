# TcpProcessExpiredTimeWaitTcbTimers

- ea: `0x1400cf330`
- end: `0x1400cf507`
- name: `TcpProcessExpiredTimeWaitTcbTimers`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400ceac0`

## callees

- `0x1400cf330`
- `0x1400d1120`
- `0x1400d12a8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cf451`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cf451`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400cf4b5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400cf4b5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf35e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf484`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf35e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf484`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf3d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf441`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf3d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf441`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400cf382`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400cf382`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1400cf3a4`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1400cf3a4`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf3bb`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf4d4`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf3bb`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf4d4`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400cf4a5`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400cf4a5`

## pseudocode

```c

```
