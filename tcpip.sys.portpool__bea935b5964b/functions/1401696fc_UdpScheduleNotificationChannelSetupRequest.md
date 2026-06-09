# UdpScheduleNotificationChannelSetupRequest

- ea: `0x1401696fc`
- end: `0x1401699ed`
- name: `UdpScheduleNotificationChannelSetupRequest`
- size: `753`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400d4fb0`

## callees

- `0x140003490`
- `0x1400599a4`
- `0x1400b4570`
- `0x14012e360`
- `0x140169238`
- `0x1401696fc`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14016974a`
- `ntoskrnl!PsGetProcessId` at `0x140169972`
- `ntoskrnl!PsGetProcessId` at `0x14016974a`
- `ntoskrnl!PsGetProcessId` at `0x140169972`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14016983f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401699c4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14016983f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401699c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401698f3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401698f3`
- `ntoskrnl!KeInitializeEvent` at `0x1401697ff`
- `ntoskrnl!KeInitializeEvent` at `0x1401697ff`
- `ntoskrnl!ExAllocatePool2` at `0x1401697d8`
- `ntoskrnl!ExAllocatePool2` at `0x1401697d8`
- `NETIO!NetioInsertWorkQueue` at `0x1401698d2`
- `NETIO!NetioInsertWorkQueue` at `0x1401698d2`

## pseudocode

```c

```
