# TcpCreateAndAcceptTcbComplete

- ea: `0x140009820`
- end: `0x140009da9`
- name: `TcpCreateAndAcceptTcbComplete`
- size: `1417`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140122b18`

## callees

- `0x140009410`
- `0x140009590`
- `0x140009680`
- `0x140009820`
- `0x140009db0`
- `0x14000a8f0`
- `0x14000b6ac`
- `0x14000f330`
- `0x140018578`
- `0x14001ea80`
- `0x14001eb30`
- `0x1400579c0`
- `0x14005881c`
- `0x14005c160`
- `0x140071ac0`
- `0x1401215ac`
- `0x140166924`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140009a97`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140009a97`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140009a46`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140009a46`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009ac9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009d40`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c2415`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009ac9`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140009d40`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1401c2415`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400099cf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140009d27`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c2456`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400099cf`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140009d27`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401c2456`
- `ntoskrnl!PsGetProcessStartKey` at `0x140009bef`
- `ntoskrnl!PsGetProcessStartKey` at `0x140009bef`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009ca3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009ca3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400099a7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400099a7`
- `ntoskrnl!PsGetProcessId` at `0x140009b8d`
- `ntoskrnl!PsGetProcessId` at `0x140009b8d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ccd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ccd`

## pseudocode

```c

```
