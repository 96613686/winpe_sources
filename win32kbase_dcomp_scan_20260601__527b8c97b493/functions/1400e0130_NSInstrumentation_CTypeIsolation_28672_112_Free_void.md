# NSInstrumentation::CTypeIsolation<28672,112>::Free(void *)

- ea: `0x1400e0130`
- end: `0x1400e042b`
- name: `?Free@?$CTypeIsolation@$0HAAA@$0HA@@NSInstrumentation@@IEAAXPEAX@Z`
- size: `763`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14002edcc`
- `0x1400dfb2c`

## callees

- `0x1400e0130`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400e0374`
- `ntoskrnl!KeBugCheckEx` at `0x1400e03e9`
- `ntoskrnl!KeBugCheckEx` at `0x1400e041e`
- `ntoskrnl!KeBugCheckEx` at `0x1400e0374`
- `ntoskrnl!KeBugCheckEx` at `0x1400e03e9`
- `ntoskrnl!KeBugCheckEx` at `0x1400e041e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e022e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e02e0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e022e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400e02e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e015e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e021d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e02cf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e015e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e021d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e02cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e0294`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e02bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e0334`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e03c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e0294`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e02bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e0334`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e03c6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e0288`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e0328`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e0288`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400e0328`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400e016f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400e016f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e02b3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e03ba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e03f6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e02b3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e03ba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400e03f6`
- `ntoskrnl!RtlTestBitNoFence` at `0x1400e0200`
- `ntoskrnl!RtlTestBitNoFence` at `0x1400e0200`
- `ntoskrnl!RtlClearBit` at `0x1400e0256`
- `ntoskrnl!RtlClearBit` at `0x1400e0256`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400e03a0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400e03a0`

## pseudocode

```c

```
