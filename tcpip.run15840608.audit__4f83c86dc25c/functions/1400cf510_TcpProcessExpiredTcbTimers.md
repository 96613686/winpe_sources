# TcpProcessExpiredTcbTimers

- ea: `0x1400cf510`
- end: `0x1400cfaeb`
- name: `TcpProcessExpiredTcbTimers`
- size: `1499`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1400ceac0`

## callees

- `0x14000de40`
- `0x14003de94`
- `0x1400ce554`
- `0x1400cf510`
- `0x1400cfaf4`
- `0x1400d0224`
- `0x1400d07d4`
- `0x1400d17c8`
- `0x14012d48c`
- `0x14012e1d0`
- `0x140161ba0`
- `0x140161d70`
- `0x140166cfc`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cf600`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cf600`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400cf710`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400cf710`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf546`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf68a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf546`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cf68a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf5cf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf701`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf7a5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf94a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf5cf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf701`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf7a5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cf94a`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400cf55d`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400cf55d`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1400cf58b`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1400cf58b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf59b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf6cd`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf59b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1400cf6cd`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400cf6bd`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400cf6bd`

## pseudocode

```c

```
