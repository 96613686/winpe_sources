# VmsUninitializePD

- ea: `0x1400a4300`
- end: `0x1400a4615`
- name: `VmsUninitializePD`
- size: `789`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400a41e8`

## callees

- `0x14001484c`
- `0x140014988`
- `0x140027a64`
- `0x14003a450`
- `0x140046e5c`
- `0x14006e100`
- `0x14008497c`
- `0x1400a4300`
- `0x1401bbe10`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400a45f4`
- `ntoskrnl!KeReleaseMutex` at `0x1400a45f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a436b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400a436b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a45c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400a45c9`
- `ntoskrnl!ExAllocatePool2` at `0x1400a43b1`
- `ntoskrnl!ExAllocatePool2` at `0x1400a43b1`
- `NDIS!NdisReleaseRWLock` at `0x1400a4460`
- `NDIS!NdisReleaseRWLock` at `0x1400a4460`

## string_xrefs

- `0x1400a4424`: `!"Out of memory during VmsUninitializePD."`
- `0x1400a44f7`: `!"PtNic not NULL or traffic is flowing during VmsUninitializePD."`

## pseudocode

```c

```
