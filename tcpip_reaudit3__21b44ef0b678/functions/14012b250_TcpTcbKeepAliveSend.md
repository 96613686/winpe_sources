# TcpTcbKeepAliveSend

- ea: `0x14012b250`
- end: `0x14012b6a5`
- name: `TcpTcbKeepAliveSend`
- size: `1109`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `3`
- callee_count: `16`
- tags: ``

## callers

- `0x140035d80`
- `0x140037220`
- `0x140038aac`

## callees

- `0x140009470`
- `0x140009990`
- `0x14000c310`
- `0x140013140`
- `0x140013a78`
- `0x1400387d0`
- `0x14003ba10`
- `0x140095184`
- `0x140095c00`
- `0x1400ae134`
- `0x1400c97b0`
- `0x1400c9e40`
- `0x1400d29e0`
- `0x1400e52f0`
- `0x14012b250`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14012b4be`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14012b4be`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b2c9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b58e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b2c9`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14012b58e`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14012b3e2`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14012b3e2`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x14012b42f`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x14012b42f`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x14012b3ca`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x14012b3ca`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14012b5ba`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14012b5ba`

## pseudocode

```c

```
