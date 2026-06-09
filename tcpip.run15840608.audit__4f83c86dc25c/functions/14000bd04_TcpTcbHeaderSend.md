# TcpTcbHeaderSend

- ea: `0x14000bd04`
- end: `0x14000c7f7`
- name: `TcpTcbHeaderSend`
- size: `2803`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `6`
- callee_count: `22`
- tags: ``

## callers

- `0x14000c800`
- `0x14001a158`
- `0x1400438b0`
- `0x14005881c`
- `0x140059e00`
- `0x140134d40`

## callees

- `0x140004070`
- `0x140004ac8`
- `0x140008f10`
- `0x140009190`
- `0x1400092a0`
- `0x140009370`
- `0x14000a3c8`
- `0x14000bd04`
- `0x140018e5c`
- `0x14001ea80`
- `0x14001eb30`
- `0x14003b570`
- `0x14003f8f0`
- `0x140044e10`
- `0x140047b80`
- `0x140071ac0`
- `0x1400fe270`
- `0x1400ff318`
- `0x140111204`
- `0x1401529c8`
- `0x140152a44`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14000c788`
- `ntoskrnl!KeLowerIrql` at `0x14000c788`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c713`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000c713`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c164`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c265e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c26e3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c164`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c265e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401c26e3`
- `NETIO!NetioAllocateMdl` at `0x14000c6b4`
- `NETIO!NetioAllocateMdl` at `0x14000c6b4`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14000c079`
- `NETIO!NetioNcmFastCheckIsAoAcCapable` at `0x14000c079`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x14000c617`
- `NETIO!NetioNcmFastActiveReferenceRequest` at `0x14000c617`
- `NETIO!NetioExtendNetBuffer` at `0x14000c6d9`
- `NETIO!NetioExtendNetBuffer` at `0x14000c6d9`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x14000c66e`
- `NETIO!NetioNrtIsPktTaggingEnabled` at `0x14000c66e`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x14000bf69`
- `NETIO!NetioAllocateAndReferenceNetBufferListNetBufferMdlAndData` at `0x14000bf69`

## pseudocode

```c

```
