# NSInstrumentation::CReferenceTracker::CReferenceCountedType::ReferenceDereferenceCommon(NSInstrumentation::CReferenceTracker::CReferenceCountedType::SCircularBuffer *,bool)

- ea: `0x14010625c`
- end: `0x14010651e`
- name: `?ReferenceDereferenceCommon@CReferenceCountedType@CReferenceTracker@NSInstrumentation@@AEAAXPEAUSCircularBuffer@123@_N@Z`
- size: `706`
- prototype: `void __fastcall(NSInstrumentation::CReferenceTracker::CReferenceCountedType *__hidden this, struct NSInstrumentation::CReferenceTracker::CReferenceCountedType::SCircularBuffer *, bool)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140019ba8`
- `0x140019c90`
- `0x140019e78`
- `0x140031750`
- `0x140031784`
- `0x1401061f8`

## callees

- `0x14000dbf0`
- `0x14000f604`
- `0x14010625c`
- `0x140238a40`
- `0x140238f80`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1401064b1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1401064b1`
- `ntoskrnl!KeSetEvent` at `0x140106410`
- `ntoskrnl!KeSetEvent` at `0x1401064fd`
- `ntoskrnl!KeSetEvent` at `0x140106410`
- `ntoskrnl!KeSetEvent` at `0x1401064fd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401062e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010632b`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401062e2`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010632b`
- `ntoskrnl!ExAllocatePool2` at `0x14010635c`
- `ntoskrnl!ExAllocatePool2` at `0x14010635c`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140106455`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140106455`
- `ntoskrnl!KeClearEvent` at `0x14010633b`
- `ntoskrnl!KeClearEvent` at `0x14010633b`

## pseudocode

```c

```
