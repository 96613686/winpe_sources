# NtDCompositionWaitForCompositorClock

- ea: `0x140058ca0`
- end: `0x14005906f`
- name: `NtDCompositionWaitForCompositorClock`
- size: `975`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140058ca0`
- `0x140059078`
- `0x140059100`
- `0x140059220`
- `0x1400d9b0c`
- `0x1401788e0`
- `0x1401789f0`
- `0x1401c6028`
- `0x140238160`
- `0x1402382c0`
- `0x140238800`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140058dfa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140058dfa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140058d2e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140058ea8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140058d2e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140058ea8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058e7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058f64`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058e7b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058f64`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140058e5d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140058e5d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140058d9c`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140058d9c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140058dda`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140058fc2`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140058dda`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140058fc2`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140058d4e`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140058d4e`
- `ntoskrnl!ObWaitForMultipleObjects` at `0x140058f41`
- `ntoskrnl!ObWaitForMultipleObjects` at `0x140058f41`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x140058ebd`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x140058f58`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x140058ebd`
- `ext-ms-win-core-win32k-dxgk-internal-l1-1-0!DxgkModifyVSyncWaiterInternal` at `0x140058f58`

## pseudocode

```c

```
