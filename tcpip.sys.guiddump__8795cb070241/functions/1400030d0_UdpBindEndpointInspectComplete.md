# UdpBindEndpointInspectComplete

- ea: `0x1400030d0`
- end: `0x140003481`
- name: `UdpBindEndpointInspectComplete`
- size: `945`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400d7a50`

## callees

- `0x140001e18`
- `0x1400030d0`
- `0x140003490`
- `0x14001ea80`
- `0x140049760`
- `0x14004a260`
- `0x140071ac0`
- `0x140072e40`
- `0x14007cf70`
- `0x1400b5cd4`
- `0x1400b6714`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140003325`
- `ntoskrnl!KfRaiseIrql` at `0x140003325`
- `ntoskrnl!KeLowerIrql` at `0x14000340b`
- `ntoskrnl!KeLowerIrql` at `0x14000340b`
- `ntoskrnl!PsGetProcessStartKey` at `0x14000339c`
- `ntoskrnl!PsGetProcessStartKey` at `0x14000339c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003122`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140003122`
- `ntoskrnl!PsGetProcessId` at `0x140003379`
- `ntoskrnl!PsGetProcessId` at `0x140003379`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000317e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400031fb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000317e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400031fb`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000319c`
- `ntoskrnl!KeReleaseSemaphore` at `0x140003219`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000319c`
- `ntoskrnl!KeReleaseSemaphore` at `0x140003219`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400032f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400032f4`

## pseudocode

```c

```
