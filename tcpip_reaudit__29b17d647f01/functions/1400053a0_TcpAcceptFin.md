# TcpAcceptFin

- ea: `0x1400053a0`
- end: `0x140005704`
- name: `TcpAcceptFin`
- size: `868`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140005314`
- `0x1400acc20`
- `0x1400ad0a8`
- `0x1400adcb4`

## callees

- `0x1400053a0`
- `0x140006384`
- `0x1400074c8`
- `0x14001d5c0`
- `0x140038aac`
- `0x140109488`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400055ad`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14000560b`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x1400055ad`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x14000560b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000554f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000554f`
- `ntoskrnl!PsGetProcessId` at `0x14000541b`
- `ntoskrnl!PsGetProcessId` at `0x14000541b`
- `NETIO!NetioInsertWorkQueue` at `0x140005501`
- `NETIO!NetioInsertWorkQueue` at `0x140005501`
- `NETIO!NetioNcmTlObjectRequest` at `0x140005481`
- `NETIO!NetioNcmTlObjectRequest` at `0x1400054c0`
- `NETIO!NetioNcmTlObjectRequest` at `0x140005481`
- `NETIO!NetioNcmTlObjectRequest` at `0x1400054c0`

## pseudocode

```c

```
