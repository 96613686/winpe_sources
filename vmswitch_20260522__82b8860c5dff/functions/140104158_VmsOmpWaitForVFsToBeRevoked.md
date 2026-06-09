# VmsOmpWaitForVFsToBeRevoked

- ea: `0x140104158`
- end: `0x1401043e3`
- name: `VmsOmpWaitForVFsToBeRevoked`
- size: `651`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400c3000`
- `0x1400ff21c`
- `0x1400ff5a8`

## callees

- `0x140027a64`
- `0x14006b084`
- `0x140073850`
- `0x14008497c`
- `0x140104158`
- `0x14012ff88`
- `0x1401bbb64`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140104241`
- `ntoskrnl!KeInitializeEvent` at `0x140104241`
- `ntoskrnl!KeReleaseMutex` at `0x140104201`
- `ntoskrnl!KeReleaseMutex` at `0x1401042cf`
- `ntoskrnl!KeReleaseMutex` at `0x140104201`
- `ntoskrnl!KeReleaseMutex` at `0x1401042cf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401041d2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401042fa`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401041d2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401042fa`
- `NDIS!NdisReleaseRWLock` at `0x14010428d`
- `NDIS!NdisReleaseRWLock` at `0x1401bce52`
- `NDIS!NdisReleaseRWLock` at `0x14010428d`
- `NDIS!NdisReleaseRWLock` at `0x1401bce52`

## string_xrefs

- `0x140104393`: `ptNicExt->VmqInfo.VFRemovalCompletedEvent == NULL`

## pseudocode

```c

```
