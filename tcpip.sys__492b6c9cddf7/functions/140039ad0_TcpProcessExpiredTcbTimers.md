# TcpProcessExpiredTcbTimers

- ea: `0x140039ad0`
- end: `0x14003a0ab`
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
- `0x140038530`
- `0x140039ad0`
- `0x1400942d4`
- `0x1400ace34`
- `0x1400f6530`
- `0x140102740`
- `0x1401220a0`
- `0x1401231dc`
- `0x14012416c`
- `0x14015fde0`
- `0x14015ffb0`
- `0x140164f3c`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140039bc0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140039bc0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140039cd0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140039cd0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039b06`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039c4a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039b06`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140039c4a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039b8f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039cc1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039d65`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039f0a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039b8f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039cc1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039d65`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140039f0a`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140039b1d`
- `NETIO!RtlIsTimerWheelSuspended` at `0x140039b1d`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140039b4b`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140039b4b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039b5b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039c8d`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039b5b`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140039c8d`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140039c7d`
- `NETIO!RtlReturnTimerWheelEntry` at `0x140039c7d`

## pseudocode

```c

```
