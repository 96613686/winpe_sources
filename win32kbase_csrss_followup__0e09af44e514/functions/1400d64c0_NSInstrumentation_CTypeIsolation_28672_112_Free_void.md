# NSInstrumentation::CTypeIsolation<28672,112>::Free(void *)

- ea: `0x1400d64c0`
- end: `0x1400d67bb`
- name: `?Free@?$CTypeIsolation@$0HAAA@$0HA@@NSInstrumentation@@IEAAXPEAX@Z`
- size: `763`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14003804c`
- `0x1400d5ebc`

## callees

- `0x1400d64c0`
- `0x1402382c0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400d6704`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6779`
- `ntoskrnl!KeBugCheckEx` at `0x1400d67ae`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6704`
- `ntoskrnl!KeBugCheckEx` at `0x1400d6779`
- `ntoskrnl!KeBugCheckEx` at `0x1400d67ae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d65be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d6670`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d65be`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400d6670`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d64ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d65ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d665f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d64ee`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d65ad`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d665f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6624`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d664f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d66c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6756`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6624`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d664f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d66c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d6756`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d6618`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d66b8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d6618`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400d66b8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d64ff`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400d64ff`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d6643`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d674a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d6786`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d6643`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d674a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400d6786`
- `ntoskrnl!RtlTestBitNoFence` at `0x1400d6590`
- `ntoskrnl!RtlTestBitNoFence` at `0x1400d6590`
- `ntoskrnl!RtlClearBit` at `0x1400d65e6`
- `ntoskrnl!RtlClearBit` at `0x1400d65e6`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400d6730`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400d6730`

## pseudocode

```c

```
