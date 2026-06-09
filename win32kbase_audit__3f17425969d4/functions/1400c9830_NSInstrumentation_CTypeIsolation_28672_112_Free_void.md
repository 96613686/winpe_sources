# NSInstrumentation::CTypeIsolation<28672,112>::Free(void *)

- ea: `0x1400c9830`
- end: `0x1400c9b2b`
- name: `?Free@?$CTypeIsolation@$0HAAA@$0HA@@NSInstrumentation@@IEAAXPEAX@Z`
- size: `763`
- prototype: `void __fastcall(__int64 *, ULONG_PTR)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400c922c`
- `0x1400d98bc`

## callees

- `0x1400c9830`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x1400c9a74`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9ae9`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9b1e`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9a74`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9ae9`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9b1e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c992e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c99e0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c992e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c99e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c985e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c991d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c99cf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c985e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c991d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c99cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9994`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c99bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9a34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9ac6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9994`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c99bf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9a34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c9ac6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c9988`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c9a28`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c9988`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c9a28`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400c986f`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400c986f`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400c99b3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400c9aba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400c9af6`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400c99b3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400c9aba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400c9af6`
- `ntoskrnl!RtlTestBitNoFence` at `0x1400c9900`
- `ntoskrnl!RtlTestBitNoFence` at `0x1400c9900`
- `ntoskrnl!RtlClearBit` at `0x1400c9956`
- `ntoskrnl!RtlClearBit` at `0x1400c9956`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400c9aa0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400c9aa0`

## pseudocode

```c

```
