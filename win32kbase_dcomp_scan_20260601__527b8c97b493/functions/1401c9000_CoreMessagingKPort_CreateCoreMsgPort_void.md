# CoreMessagingKPort::CreateCoreMsgPort(void)

- ea: `0x1401c9000`
- end: `0x1401c9218`
- name: `?CreateCoreMsgPort@CoreMessagingKPort@@QEAAJXZ`
- size: `536`
- prototype: `__int64 __fastcall(CoreMessagingKPort *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14005c5d0`
- `0x14005c610`
- `0x140071828`
- `0x14012c734`
- `0x1401c9000`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401c9010`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401c9010`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c9044`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c9063`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c9044`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401c9063`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401c9021`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401c9021`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c9038`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c9057`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c9038`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1401c9057`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c9200`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401c9200`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1401c9093`
- `ntoskrnl!SeConvertStringSecurityDescriptorToSecurityDescriptor` at `0x1401c9093`
- `WIN32K!W32GetUserSessionState` at `0x1401c910f`
- `WIN32K!W32GetUserSessionState` at `0x1401c91a5`
- `WIN32K!W32GetUserSessionState` at `0x1401c910f`
- `WIN32K!W32GetUserSessionState` at `0x1401c91a5`

## pseudocode

```c

```
