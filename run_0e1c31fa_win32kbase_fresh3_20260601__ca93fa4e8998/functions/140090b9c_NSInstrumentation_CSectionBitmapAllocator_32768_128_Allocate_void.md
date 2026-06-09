# NSInstrumentation::CSectionBitmapAllocator<32768,128>::Allocate(void)

- ea: `0x140090b9c`
- end: `0x140090d0b`
- name: `?Allocate@?$CSectionBitmapAllocator@$0IAAA@$0IA@@NSInstrumentation@@QEAAPEAXXZ`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140018450`

## callees

- `0x14005c610`
- `0x140090b9c`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140090bc0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140090bc0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090baf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140090baf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090c71`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090ca8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090c71`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140090ca8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140090c65`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140090c9c`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140090c65`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140090c9c`
- `ntoskrnl!MmCommitSessionMappedView` at `0x140090cd9`
- `ntoskrnl!MmCommitSessionMappedView` at `0x140090cd9`
- `ntoskrnl!RtlTestBit` at `0x140090c1b`
- `ntoskrnl!RtlTestBit` at `0x140090c1b`
- `ntoskrnl!RtlSetBit` at `0x140090c2c`
- `ntoskrnl!RtlSetBit` at `0x140090c2c`
- `ntoskrnl!RtlFindClearBits` at `0x140090bea`
- `ntoskrnl!RtlFindClearBits` at `0x140090bea`

## pseudocode

```c

```
