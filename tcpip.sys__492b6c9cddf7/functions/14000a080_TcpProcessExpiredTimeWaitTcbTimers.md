# TcpProcessExpiredTimeWaitTcbTimers

- ea: `0x14000a080`
- end: `0x14000a257`
- name: `TcpProcessExpiredTimeWaitTcbTimers`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140008fd0`

## callees

- `0x14000a080`
- `0x14000ad30`
- `0x1400f152c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a1a1`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a1a1`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a205`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a205`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a0ae`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a1d4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a0ae`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a1d4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a124`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a191`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a124`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a191`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000a0d2`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000a0d2`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14000a0f4`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x14000a0f4`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000a10b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000a224`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000a10b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000a224`
- `NETIO!RtlReturnTimerWheelEntry` at `0x14000a1f5`
- `NETIO!RtlReturnTimerWheelEntry` at `0x14000a1f5`

## pseudocode

```c

```
