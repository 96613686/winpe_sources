# TcpTcbKeepAliveSend

- ea: `0x14012b110`
- end: `0x14012b565`
- name: `TcpTcbKeepAliveSend`
- size: `1109`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `3`
- callee_count: `16`
- tags: ``

## callers

- `0x140035ae0`
- `0x140036f80`
- `0x14003880c`

## callees

- `0x140009470`
- `0x140009990`
- `0x14000c310`
- `0x140013140`
- `0x140013a78`
- `0x140038530`
- `0x14003b770`
- `0x1400942d4`
- `0x140094d50`
- `0x1400ae514`
- `0x1400c99d0`
- `0x1400ca060`
- `0x1400d2c00`
- `0x1400e5510`
- `0x14012b110`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14012b37e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14012b37e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b189`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b44e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b189`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b44e`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14012b2a2`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14012b2a2`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x14012b2ef`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x14012b2ef`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x14012b28a`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x14012b28a`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14012b47a`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14012b47a`

## pseudocode

```c

```
