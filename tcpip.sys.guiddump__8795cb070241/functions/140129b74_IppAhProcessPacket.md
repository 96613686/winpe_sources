# IppAhProcessPacket

- ea: `0x140129b74`
- end: `0x140129e98`
- name: `IppAhProcessPacket`
- size: `804`
- prototype: `__int64 __fastcall(__int64, __int64, struct _NET_BUFFER *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140129abc`
- `0x140192fdc`

## callees

- `0x14007ef10`
- `0x140129b74`
- `0x140129ea0`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1402658d0`
- `0x14026595c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140129dc6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140129e3d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140129dc6`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140129e3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129cf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140129cf0`
- `NDIS!NdisGetDataBuffer` at `0x140129be9`
- `NDIS!NdisGetDataBuffer` at `0x140129c37`
- `NDIS!NdisGetDataBuffer` at `0x140129c6c`
- `NDIS!NdisGetDataBuffer` at `0x140129d4e`
- `NDIS!NdisGetDataBuffer` at `0x140129be9`
- `NDIS!NdisGetDataBuffer` at `0x140129c37`
- `NDIS!NdisGetDataBuffer` at `0x140129c6c`
- `NDIS!NdisGetDataBuffer` at `0x140129d4e`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140129c21`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140129c21`

## pseudocode

```c

```
