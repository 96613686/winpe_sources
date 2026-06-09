# TcpProcessExpiredSynTcbTimers

- ea: `0x14000a3c4`
- end: `0x14000a589`
- name: `TcpProcessExpiredSynTcbTimers`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140008fd0`

## callees

- `0x14000a3c4`
- `0x14000ad00`
- `0x14007b044`
- `0x1400b0778`
- `0x1400b1cc8`
- `0x14012416c`
- `0x140161f84`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a487`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c0d5b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000a487`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c0d5b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a52a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c0d3f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000a52a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c0d3f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a3f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000a3f2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a42b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a46b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a51b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a558`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a42b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a46b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a51b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000a558`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000a412`
- `NETIO!RtlIsTimerWheelSuspended` at `0x14000a412`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401c0c70`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x1401c0c70`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0c83`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0d8e`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0c83`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x1401c0d8e`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1401c0d7b`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1401c0d7b`

## pseudocode

```c

```
