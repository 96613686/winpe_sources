# TcpTcbProcessNotificationChannelSetup

- ea: `0x14010e88c`
- end: `0x14010ea28`
- name: `TcpTcbProcessNotificationChannelSetup`
- size: `412`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14010e840`

## callees

- `0x140039b00`
- `0x1400fef24`
- `0x14010e88c`
- `0x14010ea30`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14010e9c0`
- `ntoskrnl!KeSetEvent` at `0x14010e9c0`
- `ntoskrnl!PsGetProcessId` at `0x14010e8eb`
- `ntoskrnl!PsGetProcessId` at `0x14010e8eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e8cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e9a2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e8cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e9a2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e8b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e980`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e8b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e980`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d3605`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d3605`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010e954`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010e954`

## pseudocode

```c

```
