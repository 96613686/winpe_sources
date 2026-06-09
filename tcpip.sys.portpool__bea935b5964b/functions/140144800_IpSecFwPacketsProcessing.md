# IpSecFwPacketsProcessing

- ea: `0x140144800`
- end: `0x140144ecd`
- name: `IpSecFwPacketsProcessing`
- size: `1741`
- prototype: `__int64 __fastcall(struct _LOCK_STATE_EX LockState, char)`
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x1400ad6a0`
- `0x1401441b0`
- `0x140144800`
- `0x140152424`
- `0x140154840`
- `0x140193d68`
- `0x1401955d0`
- `0x14019938c`
- `0x140199580`
- `0x140260cd4`
- `0x140266de4`
- `0x140266f3c`
- `0x140266f5c`
- `0x140266f6c`
- `0x140266f8c`
- `0x140266fd4`
- `0x14026ecd0`
- `0x140272354`
- `0x140272398`
- `0x14027373c`
- `0x140276760`
- `0x140276c74`
- `0x14027aa68`
- `0x14027aac4`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140144874`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140144b7d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140144bd6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140144b7d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140144bd6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140144b47`
- `ntoskrnl!KeGetCurrentIrql` at `0x140144b47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140144d2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140144d2f`
- `NETIO!WfpNblInfoGet` at `0x14014485c`
- `NETIO!WfpNblInfoGet` at `0x14014485c`
- `NETIO!NetioFlowRetrieveContext` at `0x1401448d0`
- `NETIO!NetioFlowRetrieveContext` at `0x140144ad6`
- `NETIO!NetioFlowRetrieveContext` at `0x1401448d0`
- `NETIO!NetioFlowRetrieveContext` at `0x140144ad6`
- `NDIS!NdisFreeRWLock` at `0x140144d11`
- `NDIS!NdisFreeRWLock` at `0x140144d11`
- `NDIS!NdisAcquireRWLockRead` at `0x140144b61`
- `NDIS!NdisAcquireRWLockRead` at `0x140144b61`
- `NDIS!NdisReleaseRWLock` at `0x140144c02`
- `NDIS!NdisReleaseRWLock` at `0x140144c02`

## string_xrefs

- `0x140144dc5`: `IPsecFwInboundVerifyPacketAgainstCachedSA`
- `0x140144e63`: `IPsecFwInboundVerifyPacketAgainstCachedSA`

## pseudocode

```c

```
