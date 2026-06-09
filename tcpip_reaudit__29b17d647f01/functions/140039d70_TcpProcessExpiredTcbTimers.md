# TcpProcessExpiredTcbTimers

- ea: `0x140039d70`
- end: `0x14003a34b`
- name: `TcpProcessExpiredTcbTimers`
- size: `1499`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x140008fd0`

## callees

- `0x14000ebcc`
- `0x1400387d0`
- `0x140039d70`
- `0x140095184`
- `0x1400aca54`
- `0x1400f6420`
- `0x140102760`
- `0x1401221e0`
- `0x14012331c`
- `0x1401242ac`
- `0x14015ff20`
- `0x1401600f0`
- `0x14016507c`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140039e60`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140039e60`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140039f70`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140039f70`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039da6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039eea`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039da6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039eea`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039e2f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039f61`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003a005`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003a1aa`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039e2f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039f61`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003a005`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003a1aa`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140039dbd`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140039dbd`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140039deb`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140039deb`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039dfb`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039f2d`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039dfb`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039f2d`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140039f1d`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140039f1d`

## pseudocode

```c

```
