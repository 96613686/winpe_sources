# VmsPtPvtNicMuxOffloadQosEventWaitAndReset

- ea: `0x140147220`
- end: `0x140147325`
- name: `VmsPtPvtNicMuxOffloadQosEventWaitAndReset`
- size: `261`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140095f30`
- `0x140146d20`
- `0x14014732c`
- `0x1401479e8`

## callees

- `0x14002e0f0`
- `0x14006b084`
- `0x140147220`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1401472b3`
- `ntoskrnl!KeClearEvent` at `0x1401472b3`
- `ntoskrnl!KeReadStateEvent` at `0x140147286`
- `ntoskrnl!KeReadStateEvent` at `0x140147286`
- `ntoskrnl!KeWaitForSingleObject` at `0x140147261`
- `ntoskrnl!KeWaitForSingleObject` at `0x140147261`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1401472db`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1401472db`
- `NDIS!NdisReleaseRWLock` at `0x1401472a2`
- `NDIS!NdisReleaseRWLock` at `0x1401472cb`
- `NDIS!NdisReleaseRWLock` at `0x1401472a2`
- `NDIS!NdisReleaseRWLock` at `0x1401472cb`

## pseudocode

```c

```
