# WfpAleAuthorizeSend

- ea: `0x1400aed00`
- end: `0x1400afb56`
- name: `WfpAleAuthorizeSend`
- size: `3670`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, unsigned __int16, int, __int64, __int16, __int64, __int16, __int64, void *, int, char, __int64, int, int, void *, __int64, __int64, _DWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x1400adc20`

## callees

- `0x140005e20`
- `0x1400066f0`
- `0x1400162f0`
- `0x1400605b4`
- `0x140060adc`
- `0x14006e3f0`
- `0x1400ad6a0`
- `0x1400aed00`
- `0x140130b40`
- `0x14013fc30`
- `0x140141400`
- `0x14014e980`
- `0x140152424`
- `0x140172540`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1400afada`
- `ntoskrnl!IoQueueWorkItem` at `0x1400afada`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400af4b2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400af4b2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400af350`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400af350`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400af431`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400af4de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400af431`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400af4de`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400aee35`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400af5c2`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400aee35`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400af5c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af450`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af450`
- `ntoskrnl!ExAllocatePool2` at `0x1400af1ca`
- `ntoskrnl!ExAllocatePool2` at `0x1400af1ca`
- `NETIO!NetioInsertWorkQueue` at `0x1400af624`
- `NETIO!NetioInsertWorkQueue` at `0x1400af624`

## string_xrefs

- `0x1400af2ee`: `StringCchCopyA`
- `0x1400af329`: `WfpStringCchCopyA`

## pseudocode

```c

```
