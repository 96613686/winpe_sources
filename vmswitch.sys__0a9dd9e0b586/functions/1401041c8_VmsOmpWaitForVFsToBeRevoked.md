# VmsOmpWaitForVFsToBeRevoked

- ea: `0x1401041c8`
- end: `0x140104453`
- name: `VmsOmpWaitForVFsToBeRevoked`
- size: `651`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400c3070`
- `0x1400ff28c`
- `0x1400ff618`

## callees

- `0x140027a64`
- `0x14006b084`
- `0x140073850`
- `0x14008497c`
- `0x1401041c8`
- `0x14012fff8`
- `0x1401bbbd4`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1401042b1`
- `ntoskrnl!KeInitializeEvent` at `0x1401042b1`
- `ntoskrnl!KeReleaseMutex` at `0x140104271`
- `ntoskrnl!KeReleaseMutex` at `0x14010433f`
- `ntoskrnl!KeReleaseMutex` at `0x140104271`
- `ntoskrnl!KeReleaseMutex` at `0x14010433f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140104242`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010436a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140104242`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010436a`
- `NDIS!NdisReleaseRWLock` at `0x1401042fd`
- `NDIS!NdisReleaseRWLock` at `0x1401bced2`
- `NDIS!NdisReleaseRWLock` at `0x1401042fd`
- `NDIS!NdisReleaseRWLock` at `0x1401bced2`

## string_xrefs

- `0x140104403`: `ptNicExt->VmqInfo.VFRemovalCompletedEvent == NULL`

## pseudocode

```c

```
