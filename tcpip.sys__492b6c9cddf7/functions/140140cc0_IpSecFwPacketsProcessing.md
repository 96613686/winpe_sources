# IpSecFwPacketsProcessing

- ea: `0x140140cc0`
- end: `0x14014138d`
- name: `IpSecFwPacketsProcessing`
- size: `1741`
- prototype: `__int64 __fastcall(struct _LOCK_STATE_EX LockState, char)`
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x14008a370`
- `0x140140670`
- `0x140140cc0`
- `0x1401506e4`
- `0x140152820`
- `0x140191f88`
- `0x1401937f0`
- `0x1401975c0`
- `0x1401977b4`
- `0x14025ccd4`
- `0x140262de4`
- `0x140262f3c`
- `0x140262f5c`
- `0x140262f6c`
- `0x140262f8c`
- `0x140262fd4`
- `0x14026a670`
- `0x14026dfb4`
- `0x14026dff8`
- `0x14026f39c`
- `0x1402723d0`
- `0x1402728e4`
- `0x140276c48`
- `0x140276ca4`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x140140d34`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14014103d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140141096`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14014103d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140141096`
- `ntoskrnl!KeGetCurrentIrql` at `0x140141007`
- `ntoskrnl!KeGetCurrentIrql` at `0x140141007`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401411ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401411ef`
- `NETIO!WfpNblInfoGet` at `0x140140d1c`
- `NETIO!WfpNblInfoGet` at `0x140140d1c`
- `NETIO!NetioFlowRetrieveContext` at `0x140140d90`
- `NETIO!NetioFlowRetrieveContext` at `0x140140f96`
- `NETIO!NetioFlowRetrieveContext` at `0x140140d90`
- `NETIO!NetioFlowRetrieveContext` at `0x140140f96`
- `NDIS!NdisFreeRWLock` at `0x1401411d1`
- `NDIS!NdisFreeRWLock` at `0x1401411d1`
- `NDIS!NdisAcquireRWLockRead` at `0x140141021`
- `NDIS!NdisAcquireRWLockRead` at `0x140141021`
- `NDIS!NdisReleaseRWLock` at `0x1401410c2`
- `NDIS!NdisReleaseRWLock` at `0x1401410c2`

## string_xrefs

- `0x140141285`: `IPsecFwInboundVerifyPacketAgainstCachedSA`
- `0x140141323`: `IPsecFwInboundVerifyPacketAgainstCachedSA`

## pseudocode

```c

```
