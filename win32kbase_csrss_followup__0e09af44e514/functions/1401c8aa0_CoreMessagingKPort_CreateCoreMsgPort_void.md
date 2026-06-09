# CoreMessagingKPort::CreateCoreMsgPort(void)

- ea: `0x1401c8aa0`
- end: `0x1401c8cb8`
- name: `?CreateCoreMsgPort@CoreMessagingKPort@@QEAAJXZ`
- size: `536`
- prototype: `__int64 __fastcall(CoreMessagingKPort *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000bed0`
- `0x14000c970`
- `0x1400729c8`
- `0x14012cd14`
- `0x1401c8aa0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401c8ab0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401c8ab0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c8ae4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c8b03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c8ae4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c8b03`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401c8ac1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401c8ac1`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c8ad8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c8af7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c8ad8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c8af7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c8ca0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c8ca0`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1401c8b33`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1401c8b33`
- `WIN32K!W32GetUserSessionState` at `0x1401c8baf`
- `WIN32K!W32GetUserSessionState` at `0x1401c8c45`
- `WIN32K!W32GetUserSessionState` at `0x1401c8baf`
- `WIN32K!W32GetUserSessionState` at `0x1401c8c45`

## pseudocode

```c

```
