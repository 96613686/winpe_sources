# TcpTcbProcessNotificationChannelTeardown

- ea: `0x140118160`
- end: `0x1401182df`
- name: `TcpTcbProcessNotificationChannelTeardown`
- size: `383`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PVOID P)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140117f70`
- `0x140117fbc`

## callees

- `0x1400599a4`
- `0x140118160`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d739d`
- `ntoskrnl!KeSetEvent` at `0x1401d739d`
- `ntoskrnl!PsGetProcessId` at `0x1401181c3`
- `ntoskrnl!PsGetProcessId` at `0x1401181c3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401181ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d7362`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401181ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d7362`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401181a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d7349`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401181a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d7349`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d7389`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d7389`
- `NETIO!NetioNcmTlObjectRequest` at `0x140118292`
- `NETIO!NetioNcmTlObjectRequest` at `0x1401d7378`
- `NETIO!NetioNcmTlObjectRequest` at `0x140118292`
- `NETIO!NetioNcmTlObjectRequest` at `0x1401d7378`

## pseudocode

```c

```
