# IpSecFwPacketsProcessing

- ea: `0x140140e50`
- end: `0x14014151d`
- name: `IpSecFwPacketsProcessing`
- size: `1741`
- prototype: `__int64 __fastcall(struct _LOCK_STATE_EX LockState, char)`
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x14008b220`
- `0x140140800`
- `0x140140e50`
- `0x140150824`
- `0x140152960`
- `0x1401920c8`
- `0x140193930`
- `0x140197700`
- `0x1401978f4`
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

- `ntoskrnl!MmBadPointer` at `0x140140ec4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401411cd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140141226`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1401411cd`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140141226`
- `ntoskrnl!KeGetCurrentIrql` at `0x140141197`
- `ntoskrnl!KeGetCurrentIrql` at `0x140141197`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014137f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014137f`
- `NETIO!WfpNblInfoGet` at `0x140140eac`
- `NETIO!WfpNblInfoGet` at `0x140140eac`
- `NETIO!NetioFlowRetrieveContext` at `0x140140f20`
- `NETIO!NetioFlowRetrieveContext` at `0x140141126`
- `NETIO!NetioFlowRetrieveContext` at `0x140140f20`
- `NETIO!NetioFlowRetrieveContext` at `0x140141126`
- `NDIS!NdisFreeRWLock` at `0x140141361`
- `NDIS!NdisFreeRWLock` at `0x140141361`
- `NDIS!NdisAcquireRWLockRead` at `0x1401411b1`
- `NDIS!NdisAcquireRWLockRead` at `0x1401411b1`
- `NDIS!NdisReleaseRWLock` at `0x140141252`
- `NDIS!NdisReleaseRWLock` at `0x140141252`

## string_xrefs

- `0x140141415`: `IPsecFwInboundVerifyPacketAgainstCachedSA`
- `0x1401414b3`: `IPsecFwInboundVerifyPacketAgainstCachedSA`

## pseudocode

```c

```
