# UdpBindEndpointInspectComplete

- ea: `0x1400121a0`
- end: `0x140012551`
- name: `UdpBindEndpointInspectComplete`
- size: `945`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b5800`

## callees

- `0x140010ac8`
- `0x1400121a0`
- `0x140012560`
- `0x14002f4a0`
- `0x140030820`
- `0x140039b00`
- `0x140039bb0`
- `0x14005f7b4`
- `0x1400601f4`
- `0x140061350`
- `0x1400b7ca0`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400123f5`
- `ntoskrnl!KfRaiseIrql` at `0x1400123f5`
- `ntoskrnl!KeLowerIrql` at `0x1400124db`
- `ntoskrnl!KeLowerIrql` at `0x1400124db`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001246c`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001246c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400121f2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400121f2`
- `ntoskrnl!PsGetProcessId` at `0x140012449`
- `ntoskrnl!PsGetProcessId` at `0x140012449`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001224e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400122cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001224e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400122cb`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001226c`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400122e9`
- `ntoskrnl!KeReleaseSemaphore` at `0x14001226c`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400122e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123c4`

## pseudocode

```c

```
