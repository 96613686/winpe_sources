# CoreMessagingKPort::CreateCoreMsgPort(void)

- ea: `0x1401c9870`
- end: `0x1401c9a88`
- name: `?CreateCoreMsgPort@CoreMessagingKPort@@QEAAJXZ`
- size: `536`
- prototype: `__int64 __fastcall(void **this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000b9f0`
- `0x14000c490`
- `0x140049df8`
- `0x14012ed34`
- `0x1401c9870`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401c9880`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401c9880`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c98b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c98d3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c98b4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c98d3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401c9891`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401c9891`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c98a8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c98c7`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c98a8`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c98c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c9a70`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c9a70`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1401c9903`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1401c9903`
- `WIN32K!W32GetUserSessionState` at `0x1401c997f`
- `WIN32K!W32GetUserSessionState` at `0x1401c9a15`
- `WIN32K!W32GetUserSessionState` at `0x1401c997f`
- `WIN32K!W32GetUserSessionState` at `0x1401c9a15`

## pseudocode

```c

```
