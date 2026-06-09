# VmsMpInitializeNic

- ea: `0x1400f553c`
- end: `0x1400f5bba`
- name: `VmsMpInitializeNic`
- size: `1662`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x1400f617c`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14003e9e4`
- `0x140065e70`
- `0x14006a330`
- `0x14008497c`
- `0x140087fbc`
- `0x14008a258`
- `0x1400ead08`
- `0x1400f4b08`
- `0x1400f553c`
- `0x1400fa910`
- `0x1400fe990`
- `0x1400ff28c`
- `0x1401aed84`
- `0x1401af2b0`
- `0x1401b0644`
- `0x1401bbcb0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400f5656`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400f5656`
- `ntoskrnl!KeInitializeMutex` at `0x1400f566b`
- `ntoskrnl!KeInitializeMutex` at `0x1400f566b`
- `ntoskrnl!ExAllocatePool2` at `0x1400f55e2`
- `ntoskrnl!ExAllocatePool2` at `0x1400f55e2`
- `NDIS!NdisAllocateNetBufferPool` at `0x1400f579b`
- `NDIS!NdisAllocateNetBufferPool` at `0x1400f579b`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f56ab`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f5722`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f56ab`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f5722`

## pseudocode

```c

```
