# CSxRefTraceList::CaptureStackTrace(ulong)

- ea: `0x180009cd0`
- end: `0x180009d71`
- name: `?CaptureStackTrace@CSxRefTraceList@@QEAAXK@Z`
- size: `161`
- prototype: `void __fastcall(union _SLIST_HEADER *this, int)`
- caller_count: `14`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009040`
- `0x1800090a0`
- `0x1800090f0`
- `0x180009160`
- `0x18000a308`
- `0x18000a460`
- `0x18000a7a8`
- `0x18000a8fc`
- `0x18000ae88`
- `0x18000af28`
- `0x18000ca90`
- `0x18000cb90`
- `0x18000cc80`
- `0x18000cd90`

## callees

- `0x180009cd0`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180009d5b`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180009d5b`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180009d4a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180009d4a`
- `ntdll!RtlAllocateHeap` at `0x180009cfc`
- `ntdll!RtlAllocateHeap` at `0x180009d20`
- `ntdll!RtlAllocateHeap` at `0x180009cfc`
- `ntdll!RtlAllocateHeap` at `0x180009d20`

## pseudocode

```c

```
