# TcpProcessExpiredSynTcbTimers

- ea: `0x1400cfd04`
- end: `0x1400cfec9`
- name: `TcpProcessExpiredSynTcbTimers`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400ceac0`

## callees

- `0x1400cfd04`
- `0x1400ef100`
- `0x1400fc2ac`
- `0x1400fd22c`
- `0x14011887c`
- `0x14012e1d0`
- `0x140163d44`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cfdc7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401d0de9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400cfdc7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401d0de9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400cfe6a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401d0dcd`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400cfe6a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401d0dcd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cfd32`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400cfd32`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfd6b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfdab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfe5b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfe98`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfd6b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfdab`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfe5b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400cfe98`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400cfd52`
- `NETIO!RtlIsTimerWheelSuspended` at `0x1400cfd52`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401d0cfe`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401d0cfe`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401d0d11`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401d0e1c`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401d0d11`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401d0e1c`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1401d0e09`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1401d0e09`

## pseudocode

```c

```
