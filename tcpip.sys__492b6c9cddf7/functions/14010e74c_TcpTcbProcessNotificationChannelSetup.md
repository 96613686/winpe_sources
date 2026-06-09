# TcpTcbProcessNotificationChannelSetup

- ea: `0x14010e74c`
- end: `0x14010e8e8`
- name: `TcpTcbProcessNotificationChannelSetup`
- size: `412`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14010e700`

## callees

- `0x140039860`
- `0x1400fede4`
- `0x14010e74c`
- `0x14010e8f0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14010e880`
- `ntoskrnl!KeSetEvent` at `0x14010e880`
- `ntoskrnl!PsGetProcessId` at `0x14010e7ab`
- `ntoskrnl!PsGetProcessId` at `0x14010e7ab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e78d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e862`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e78d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e862`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e770`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e840`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e770`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e840`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d34c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d34c5`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010e814`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010e814`

## pseudocode

```c

```
