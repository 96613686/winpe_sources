# rimSignalReadComplete

- ea: `0x140048f34`
- end: `0x140049423`
- name: `rimSignalReadComplete`
- size: `1263`
- prototype: `void __fastcall(struct RawInputManagerObject *, LARGE_INTEGER *, struct _IO_STATUS_BLOCK *)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400e0b10`
- `0x140123a58`
- `0x1401370d0`

## callees

- `0x140048f34`
- `0x14004942c`
- `0x140049518`
- `0x140049570`
- `0x140049828`
- `0x14006862c`
- `0x1400a5ba0`
- `0x1400e23b4`
- `0x140208a2c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140049131`
- `ntoskrnl!ZwClose` at `0x140049131`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140048f9e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140048f9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048f8d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048f8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049013`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049013`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140049007`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140049007`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140049190`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140049190`
- `ntoskrnl!ZwSetEvent` at `0x14004911e`
- `ntoskrnl!ZwSetEvent` at `0x14004911e`
- `ntoskrnl!KeSetTimer` at `0x140049400`
- `ntoskrnl!KeSetTimer` at `0x140049400`
- `WIN32K!W32GetUserSessionState` at `0x140048f7d`
- `WIN32K!W32GetUserSessionState` at `0x140048fd8`
- `WIN32K!W32GetUserSessionState` at `0x140048ff1`
- `WIN32K!W32GetUserSessionState` at `0x140049079`
- `WIN32K!W32GetUserSessionState` at `0x1400491dd`
- `WIN32K!W32GetUserSessionState` at `0x140049284`
- `WIN32K!W32GetUserSessionState` at `0x140049354`
- `WIN32K!W32GetUserSessionState` at `0x1400493b7`
- `WIN32K!W32GetUserSessionState` at `0x1400493d0`
- `WIN32K!W32GetUserSessionState` at `0x1400493e3`
- `WIN32K!W32GetUserSessionState` at `0x140048f7d`
- `WIN32K!W32GetUserSessionState` at `0x140048fd8`
- `WIN32K!W32GetUserSessionState` at `0x140048ff1`
- `WIN32K!W32GetUserSessionState` at `0x140049079`
- `WIN32K!W32GetUserSessionState` at `0x1400491dd`
- `WIN32K!W32GetUserSessionState` at `0x140049284`
- `WIN32K!W32GetUserSessionState` at `0x140049354`
- `WIN32K!W32GetUserSessionState` at `0x1400493b7`
- `WIN32K!W32GetUserSessionState` at `0x1400493d0`
- `WIN32K!W32GetUserSessionState` at `0x1400493e3`
- `HAL!KeQueryPerformanceCounter` at `0x140048fb9`
- `HAL!KeQueryPerformanceCounter` at `0x1400490d7`
- `HAL!KeQueryPerformanceCounter` at `0x140048fb9`
- `HAL!KeQueryPerformanceCounter` at `0x1400490d7`

## pseudocode

```c

```
