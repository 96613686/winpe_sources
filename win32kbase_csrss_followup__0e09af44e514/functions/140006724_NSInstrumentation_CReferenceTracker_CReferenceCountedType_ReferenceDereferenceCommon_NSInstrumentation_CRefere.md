# NSInstrumentation::CReferenceTracker::CReferenceCountedType::ReferenceDereferenceCommon(NSInstrumentation::CReferenceTracker::CReferenceCountedType::SCircularBuffer *,bool)

- ea: `0x140006724`
- end: `0x1400069e6`
- name: `?ReferenceDereferenceCommon@CReferenceCountedType@CReferenceTracker@NSInstrumentation@@AEAAXPEAUSCircularBuffer@123@_N@Z`
- size: `706`
- prototype: `void __fastcall(NSInstrumentation::CReferenceTracker::CReferenceCountedType *__hidden this, struct NSInstrumentation::CReferenceTracker::CReferenceCountedType::SCircularBuffer *, bool)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400066c0`
- `0x140024ef0`
- `0x140024f24`
- `0x140030418`
- `0x140030500`
- `0x1400306e8`

## callees

- `0x140006724`
- `0x140007a40`
- `0x14000e0d0`
- `0x1402382c0`
- `0x140238800`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140006979`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140006979`
- `ntoskrnl!KeSetEvent` at `0x1400068d8`
- `ntoskrnl!KeSetEvent` at `0x1400069c5`
- `ntoskrnl!KeSetEvent` at `0x1400068d8`
- `ntoskrnl!KeSetEvent` at `0x1400069c5`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400067aa`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400067f3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400067aa`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400067f3`
- `ntoskrnl!ExAllocatePool2` at `0x140006824`
- `ntoskrnl!ExAllocatePool2` at `0x140006824`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14000691d`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14000691d`
- `ntoskrnl!KeClearEvent` at `0x140006803`
- `ntoskrnl!KeClearEvent` at `0x140006803`

## pseudocode

```c

```
