# NSInstrumentation::CSectionBitmapAllocator<32768,128>::Allocate(void)

- ea: `0x14000c29c`
- end: `0x14000c40b`
- name: `?Allocate@?$CSectionBitmapAllocator@$0IAAA@$0IA@@NSInstrumentation@@QEAAPEAXXZ`
- size: `367`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002dcd0`

## callees

- `0x14000b9f0`
- `0x14000c29c`
- `0x140238a40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c2c0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c2c0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c2af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c2af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c371`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c3a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c371`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c3a8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c365`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c39c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c365`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c39c`
- `ntoskrnl!MmCommitSessionMappedView` at `0x14000c3d9`
- `ntoskrnl!MmCommitSessionMappedView` at `0x14000c3d9`
- `ntoskrnl!RtlTestBit` at `0x14000c31b`
- `ntoskrnl!RtlTestBit` at `0x14000c31b`
- `ntoskrnl!RtlSetBit` at `0x14000c32c`
- `ntoskrnl!RtlSetBit` at `0x14000c32c`
- `ntoskrnl!RtlFindClearBits` at `0x14000c2ea`
- `ntoskrnl!RtlFindClearBits` at `0x14000c2ea`

## pseudocode

```c

```
