# TcpTcbHeaderSend

- ea: `0x14003880c`
- end: `0x1400392e9`
- name: `TcpTcbHeaderSend`
- size: `2781`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `6`
- callee_count: `23`
- tags: ``

## callers

- `0x1400053a0`
- `0x1400064f8`
- `0x140035ae0`
- `0x140036f80`
- `0x1400ae268`
- `0x14012dc94`

## callees

- `0x14000c310`
- `0x140013140`
- `0x140013a78`
- `0x14002f200`
- `0x14003880c`
- `0x14003b770`
- `0x14008efb0`
- `0x140094d50`
- `0x1400ae514`
- `0x1400b8080`
- `0x1400b8130`
- `0x1400c99d0`
- `0x1400ca060`
- `0x1400d2c00`
- `0x1400d404c`
- `0x1400e3580`
- `0x1400e5510`
- `0x1400f6280`
- `0x1400f7278`
- `0x14012b110`
- `0x140150adc`
- `0x140150b58`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140038d2c`
- `ntoskrnl!KeLowerIrql` at `0x140038d2c`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038e4e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140038e4e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038890`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038d43`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400391ca`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038890`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038d43`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400391ca`
- `NETIO!NetioAllocateMdl` at `0x140038d79`
- `NETIO!NetioAllocateMdl` at `0x140038d79`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140038ef8`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x140038ef8`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140038f2b`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x140038f2b`
- `NETIO!NetioExtendNetBuffer` at `0x140038d9a`
- `NETIO!NetioExtendNetBuffer` at `0x140038d9a`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x140038de1`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x140038de1`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140038cfb`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x140038cfb`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400391fe`
- `NDIS!NdisNblTrackerTransferOwnership` at `0x1400391fe`

## pseudocode

```c

```
