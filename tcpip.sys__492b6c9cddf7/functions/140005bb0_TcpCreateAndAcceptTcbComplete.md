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

- `0x140118898`

## callees

- `0x140005060`
- `0x140005bb0`
- `0x1400064f8`
- `0x14000726c`
- `0x1400078c0`
- `0x14000a7c0`
- `0x14001e4c0`
- `0x14002f200`
- `0x1400349f0`
- `0x1400aebd8`
- `0x1400b07b0`
- `0x1400b8080`
- `0x1400b8130`
- `0x1400b86c0`
- `0x140116d2c`
- `0x1401170cc`
- `0x140164b64`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140005e27`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140005e27`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140005dd6`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140005dd6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005e59`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400060d0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c08a5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140005e59`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400060d0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c08a5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d5f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400060b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c08e6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140005d5f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400060b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c08e6`
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
