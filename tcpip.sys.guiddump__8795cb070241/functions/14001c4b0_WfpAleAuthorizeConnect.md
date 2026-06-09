# WfpAleAuthorizeConnect

- ea: `0x14001c4b0`
- end: `0x14001d3a8`
- name: `WfpAleAuthorizeConnect`
- size: `3832`
- prototype: `__int64 __fastcall(volatile signed __int32 *SpinLock, __int64, unsigned __int16, unsigned int *, __int16, _DWORD *, int, __int64, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x14001bfb0`

## callees

- `0x140005ca0`
- `0x140005e20`
- `0x14000f128`
- `0x140012f00`
- `0x140014a90`
- `0x140015a70`
- `0x1400162f0`
- `0x14001c4b0`
- `0x1400611c0`
- `0x14006e3f0`
- `0x14007a580`
- `0x1400ad6a0`
- `0x1400b1140`
- `0x1400b12a0`
- `0x1400b4a50`
- `0x1400eb5a0`
- `0x1401088f0`
- `0x140126718`
- `0x14013cfa0`
- `0x140141400`
- `0x14015200c`
- `0x1401528fc`
- `0x140172b1c`
- `0x1401c0fd0`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14001d304`
- `ntoskrnl!IoQueueWorkItem` at `0x14001d304`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001d125`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001d125`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001d1ba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001d1ba`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14001c585`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x14001c585`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d1d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d32e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d345`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ca8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d1d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d32e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d345`
- `ntoskrnl!ExAllocatePool2` at `0x14001c6bf`
- `ntoskrnl!ExAllocatePool2` at `0x14001cf8b`
- `ntoskrnl!ExAllocatePool2` at `0x14001c6bf`
- `ntoskrnl!ExAllocatePool2` at `0x14001cf8b`
- `NETIO!KfdIsLayerEmpty` at `0x14001c7a3`
- `NETIO!KfdIsLayerEmpty` at `0x14001c82a`
- `NETIO!KfdIsLayerEmpty` at `0x14001c7a3`
- `NETIO!KfdIsLayerEmpty` at `0x14001c82a`
- `NETIO!KfdCheckConnectBypass` at `0x14001ca2d`
- `NETIO!KfdCheckConnectBypass` at `0x14001ca2d`
- `NETIO!NetioNrtReferenceRecord` at `0x14001c66d`
- `NETIO!NetioNrtReferenceRecord` at `0x14001c66d`

## string_xrefs

- `0x14001d053`: `WfpAleQueryPeerTokenInformation`
- `0x14001d0b9`: `StringCchCopyA`
- `0x14001d0fb`: `WfpStringCchCopyA`

## pseudocode

```c

```
