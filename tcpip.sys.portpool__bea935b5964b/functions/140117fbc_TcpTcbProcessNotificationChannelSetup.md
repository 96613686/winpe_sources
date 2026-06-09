# TcpTcbProcessNotificationChannelSetup

- ea: `0x140117fbc`
- end: `0x140118158`
- name: `TcpTcbProcessNotificationChannelSetup`
- size: `412`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PVOID P)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140117f70`

## callees

- `0x140049760`
- `0x14010a2a4`
- `0x140117fbc`
- `0x140118160`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401180f0`
- `ntoskrnl!KeSetEvent` at `0x1401180f0`
- `ntoskrnl!PsGetProcessId` at `0x14011801b`
- `ntoskrnl!PsGetProcessId` at `0x14011801b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140117ffd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401180d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140117ffd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401180d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140117fe0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401180b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140117fe0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401180b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d7333`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d7333`
- `NETIO!NetioNcmTlObjectRequest` at `0x140118084`
- `NETIO!NetioNcmTlObjectRequest` at `0x140118084`

## pseudocode

```c

```
