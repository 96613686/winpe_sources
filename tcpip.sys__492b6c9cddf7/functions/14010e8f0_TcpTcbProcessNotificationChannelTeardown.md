# TcpTcbProcessNotificationChannelTeardown

- ea: `0x14010e8f0`
- end: `0x14010ea6f`
- name: `TcpTcbProcessNotificationChannelTeardown`
- size: `383`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock, PVOID P)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14010e700`
- `0x14010e74c`

## callees

- `0x140006384`
- `0x14010e8f0`
- `0x1401bf390`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1401d352f`
- `ntoskrnl!KeSetEvent` at `0x1401d352f`
- `ntoskrnl!PsGetProcessId` at `0x14010e953`
- `ntoskrnl!PsGetProcessId` at `0x14010e953`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e97d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d34f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14010e97d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401d34f4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e930`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d34db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14010e930`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401d34db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d351b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401d351b`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010ea22`
- `NETIO!NetioNcmTlObjectRequest` at `0x1401d350a`
- `NETIO!NetioNcmTlObjectRequest` at `0x14010ea22`
- `NETIO!NetioNcmTlObjectRequest` at `0x1401d350a`

## pseudocode

```c

```
