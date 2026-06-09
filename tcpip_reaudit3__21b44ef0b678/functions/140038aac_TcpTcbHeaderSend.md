# TcpTcbHeaderSend

- ea: `0x140038aac`
- end: `0x140039589`
- name: `TcpTcbHeaderSend`
- size: `2781`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `6`
- callee_count: `23`
- tags: ``

## callers

- `0x1400053a0`
- `0x1400064f8`
- `0x140035d80`
- `0x140037220`
- `0x1400ade88`
- `0x14012ddd4`

## callees

- `0x14000c310`
- `0x140013140`
- `0x140013a78`
- `0x14002f4a0`
- `0x140038aac`
- `0x14003ba10`
- `0x14008fe60`
- `0x140095c00`
- `0x1400ae134`
- `0x1400b7ca0`
- `0x1400b7d50`
- `0x1400c97b0`
- `0x1400c9e40`
- `0x1400d29e0`
- `0x1400d3e2c`
- `0x1400e3360`
- `0x1400e52f0`
- `0x1400f6170`
- `0x1400f7168`
- `0x14012b250`
- `0x140150c1c`
- `0x140150c98`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140038fcc`
- `ntoskrnl!KeLowerIrql` at `0x140038fcc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400390ee`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400390ee`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038b30`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038fe3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003946a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038b30`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038fe3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003946a`
- `NETIO!NetioAllocateMdl` at `0x140039019`
- `NETIO!NetioAllocateMdl` at `0x140039019`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140039198`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140039198`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x1400391cb`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x1400391cb`
- `NETIO!NetioExtendNetBuffer` at `0x14003903a`
- `NETIO!NetioExtendNetBuffer` at `0x14003903a`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x140039081`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x140039081`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140038f9b`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140038f9b`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14003949e`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x14003949e`

## pseudocode

```c

```
