# NtDCompositionWaitForCompositorClock

- ea: `0x14004fee0`
- end: `0x1400502af`
- name: `NtDCompositionWaitForCompositorClock`
- size: `975`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x14004fee0`
- `0x1400502b8`
- `0x140050340`
- `0x140050460`
- `0x1400e377c`
- `0x140177d70`
- `0x140177e80`
- `0x1401c6588`
- `0x140238b10`
- `0x140238c40`
- `0x140239180`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005003a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005003a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004ff6e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400500e8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004ff6e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400500e8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400500bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400501a4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400500bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400501a4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005009d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14005009d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14004ffdc`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14004ffdc`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14005001a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140050202`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14005001a`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140050202`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14004ff8e`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14004ff8e`
- `ntoskrnl!ObWaitForMultipleObjects` at `0x140050181`
- `ntoskrnl!ObWaitForMultipleObjects` at `0x140050181`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x1400500fd`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x140050198`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x1400500fd`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x140050198`

## pseudocode

```c

```
