# UdpScheduleNotificationChannelSetupRequest

- ea: `0x140167b3c`
- end: `0x140167e2d`
- name: `UdpScheduleNotificationChannelSetupRequest`
- size: `753`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400b62a0`

## callees

- `0x140006384`
- `0x140012560`
- `0x14005e920`
- `0x140124628`
- `0x140167678`
- `0x140167b3c`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140167b8a`
- `ntoskrnl!PsGetProcessId` at `0x140167db2`
- `ntoskrnl!PsGetProcessId` at `0x140167b8a`
- `ntoskrnl!PsGetProcessId` at `0x140167db2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140167c7f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140167e04`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140167c7f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140167e04`
- `ntoskrnl!KeWaitForSingleObject` at `0x140167d33`
- `ntoskrnl!KeWaitForSingleObject` at `0x140167d33`
- `ntoskrnl!KeInitializeEvent` at `0x140167c3f`
- `ntoskrnl!KeInitializeEvent` at `0x140167c3f`
- `ntoskrnl!ExAllocatePool2` at `0x140167c18`
- `ntoskrnl!ExAllocatePool2` at `0x140167c18`
- `NETIO!NetioInsertWorkQueue` at `0x140167d12`
- `NETIO!NetioInsertWorkQueue` at `0x140167d12`

## pseudocode

```c

```
