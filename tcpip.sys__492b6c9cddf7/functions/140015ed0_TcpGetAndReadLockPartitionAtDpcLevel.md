# TcpGetAndReadLockPartitionAtDpcLevel

- ea: `0x140015ed0`
- end: `0x140016083`
- name: `TcpGetAndReadLockPartitionAtDpcLevel`
- size: `435`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140016890`
- `0x1400ac9e0`
- `0x14011546c`
- `0x140160e8c`

## callees

- `0x140015ed0`
- `0x14014c878`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140015f44`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140015fee`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140015f44`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140015fee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140015f59`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016003`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140015f59`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140016003`
- `ntoskrnl!KeTestSpinLock` at `0x140015f28`
- `ntoskrnl!KeTestSpinLock` at `0x140015fd2`
- `ntoskrnl!KeTestSpinLock` at `0x140015f28`
- `ntoskrnl!KeTestSpinLock` at `0x140015fd2`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140016021`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140016052`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140016021`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140016052`

## pseudocode

```c

```
