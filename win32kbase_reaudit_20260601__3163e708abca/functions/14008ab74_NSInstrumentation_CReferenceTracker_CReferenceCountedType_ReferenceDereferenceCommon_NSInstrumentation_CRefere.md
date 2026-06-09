# NSInstrumentation::CReferenceTracker::CReferenceCountedType::ReferenceDereferenceCommon(NSInstrumentation::CReferenceTracker::CReferenceCountedType::SCircularBuffer *,bool)

- ea: `0x14008ab74`
- end: `0x14008ae36`
- name: `?ReferenceDereferenceCommon@CReferenceCountedType@CReferenceTracker@NSInstrumentation@@AEAAXPEAUSCircularBuffer@123@_N@Z`
- size: `706`
- prototype: `void __fastcall(NSInstrumentation::CReferenceTracker::CReferenceCountedType *__hidden this, struct NSInstrumentation::CReferenceTracker::CReferenceCountedType::SCircularBuffer *, bool)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001bed0`
- `0x14001bf04`
- `0x140027198`
- `0x140027280`
- `0x140027468`
- `0x14008ab10`

## callees

- `0x14008ab74`
- `0x14008be90`
- `0x1400924b0`
- `0x140238c40`
- `0x140239180`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14008adc9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14008adc9`
- `ntoskrnl!KeSetEvent` at `0x14008ad28`
- `ntoskrnl!KeSetEvent` at `0x14008ae15`
- `ntoskrnl!KeSetEvent` at `0x14008ad28`
- `ntoskrnl!KeSetEvent` at `0x14008ae15`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008abfa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008ac43`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008abfa`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008ac43`
- `ntoskrnl!ExAllocatePool2` at `0x14008ac74`
- `ntoskrnl!ExAllocatePool2` at `0x14008ac74`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14008ad6d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14008ad6d`
- `ntoskrnl!KeClearEvent` at `0x14008ac53`
- `ntoskrnl!KeClearEvent` at `0x14008ac53`

## pseudocode

```c

```
