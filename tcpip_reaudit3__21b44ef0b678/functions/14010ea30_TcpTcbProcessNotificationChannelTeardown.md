# TcpTcbProcessNotificationChannelTeardown

- ea: `0x14010ea30`
- end: `0x14010ebaf`
- name: `TcpTcbProcessNotificationChannelTeardown`
- size: `383`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PVOID P)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14010e840`
- `0x14010e88c`

## callees

- `0x140006384`
- `0x14010ea30`
- `0x1401bf4d0`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d366f`
- `ntoskrnl!KeSetEvent` at `0x1401d366f`
- `ntoskrnl!PsGetProcessId` at `0x14010ea93`
- `ntoskrnl!PsGetProcessId` at `0x14010ea93`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010eabd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d3634`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010eabd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d3634`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010ea70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d361b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010ea70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d361b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d365b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d365b`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010eb62`
- `NETIO!NetioNcmTlObjectRequest` at `0x1401d364a`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010eb62`
- `NETIO!NetioNcmTlObjectRequest` at `0x1401d364a`

## pseudocode

```c

```
