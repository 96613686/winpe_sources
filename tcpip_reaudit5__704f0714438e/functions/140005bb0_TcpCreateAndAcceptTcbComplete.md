# TcpCreateAndAcceptTcbComplete

- ea: `0x140005bb0`
- end: `0x140006139`
- name: `TcpCreateAndAcceptTcbComplete`
- size: `1417`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401189d8`

## callees

- `0x140005060`
- `0x140005bb0`
- `0x1400064f8`
- `0x14000726c`
- `0x1400078c0`
- `0x14000a7c0`
- `0x14001e760`
- `0x14002f4a0`
- `0x140034c90`
- `0x1400ae7f8`
- `0x1400b03d0`
- `0x1400b7ca0`
- `0x1400b7d50`
- `0x1400b82e0`
- `0x140116e6c`
- `0x14011720c`
- `0x140164ca4`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140005e27`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005e27`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140005dd6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140005dd6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005e59`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400060d0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c09e5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005e59`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400060d0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c09e5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d5f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400060b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c0a26`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d5f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400060b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c0a26`
- `ntoskrnl!PsGetProcessStartKey` at `0x140005f7f`
- `ntoskrnl!PsGetProcessStartKey` at `0x140005f7f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006033`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140006033`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140005d37`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140005d37`
- `ntoskrnl!PsGetProcessId` at `0x140005f1d`
- `ntoskrnl!PsGetProcessId` at `0x140005f1d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000605d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000605d`

## pseudocode

```c

```
