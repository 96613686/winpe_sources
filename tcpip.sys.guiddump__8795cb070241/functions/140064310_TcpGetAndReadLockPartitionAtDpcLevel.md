# TcpGetAndReadLockPartitionAtDpcLevel

- ea: `0x140064310`
- end: `0x1400644c3`
- name: `TcpGetAndReadLockPartitionAtDpcLevel`
- size: `435`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400641dc`
- `0x140064690`
- `0x1400653e0`
- `0x140162c4c`

## callees

- `0x140064310`
- `0x14014e558`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140064384`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006442e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140064384`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14006442e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140064399`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140064443`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140064399`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140064443`
- `ntoskrnl!KeTestSpinLock` at `0x140064368`
- `ntoskrnl!KeTestSpinLock` at `0x140064412`
- `ntoskrnl!KeTestSpinLock` at `0x140064368`
- `ntoskrnl!KeTestSpinLock` at `0x140064412`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140064461`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140064492`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140064461`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140064492`

## pseudocode

```c

```
