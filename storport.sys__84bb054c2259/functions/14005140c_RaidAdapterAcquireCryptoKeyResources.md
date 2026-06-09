# RaidAdapterAcquireCryptoKeyResources

- ea: `0x14005140c`
- end: `0x140051867`
- name: `RaidAdapterAcquireCryptoKeyResources`
- size: `1115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400097d0`

## callees

- `0x14000befc`
- `0x1400290b0`
- `0x14005140c`
- `0x140096394`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400516e3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400517d4`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400516e3`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400517d4`
- `ntoskrnl!IoFreeWorkItem` at `0x140051765`
- `ntoskrnl!IoFreeWorkItem` at `0x140051765`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051748`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051748`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x14005144e`
- `ntoskrnl!IoGetAdapterCryptoEngineExtension` at `0x14005144e`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x14005152c`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x14005183f`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x14005152c`
- `ntoskrnl!ExReleaseSpinLockSharedFromDpcLevel` at `0x14005183f`
- `ntoskrnl!ExAcquireSpinLockSharedAtDpcLevel` at `0x140051501`
- `ntoskrnl!ExAcquireSpinLockSharedAtDpcLevel` at `0x140051501`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x14005153b`
- `ntoskrnl!ExAcquireSpinLockExclusiveAtDpcLevel` at `0x14005153b`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140051708`
- `ntoskrnl!IoQueueWorkItemEx` at `0x140051708`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x1400515d8`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140051717`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140051730`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x1400515d8`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140051717`
- `ntoskrnl!ExReleaseSpinLockExclusiveFromDpcLevel` at `0x140051730`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400515ed`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400515ed`

## pseudocode

```c

```
