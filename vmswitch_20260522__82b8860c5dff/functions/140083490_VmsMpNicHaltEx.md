# VmsMpNicHaltEx

- ea: `0x140083490`
- end: `0x1400836df`
- name: `VmsMpNicHaltEx`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140027a64`
- `0x140046f1c`
- `0x140066898`
- `0x14006b084`
- `0x140083490`
- `0x14008497c`
- `0x1400f92c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140083686`
- `ntoskrnl!KeReleaseMutex` at `0x1400836bf`
- `ntoskrnl!KeReleaseMutex` at `0x140083686`
- `ntoskrnl!KeReleaseMutex` at `0x1400836bf`
- `ntoskrnl!KeWaitForSingleObject` at `0x140083529`
- `ntoskrnl!KeWaitForSingleObject` at `0x140083627`
- `ntoskrnl!KeWaitForSingleObject` at `0x140083529`
- `ntoskrnl!KeWaitForSingleObject` at `0x140083627`
- `NDIS!NdisMSleep` at `0x140083699`
- `NDIS!NdisMSleep` at `0x140083699`
- `NDIS!NdisReleaseRWLock` at `0x1400835fc`
- `NDIS!NdisReleaseRWLock` at `0x1400835fc`

## string_xrefs

- `0x140083590`: `IsListEmpty(&(objNic->NicNDKInfo.NDKAdapterList)) != FALSE`

## pseudocode

```c

```
