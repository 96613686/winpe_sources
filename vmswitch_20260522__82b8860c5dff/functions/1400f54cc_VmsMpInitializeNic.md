# VmsMpInitializeNic

- ea: `0x1400f54cc`
- end: `0x1400f5b4a`
- name: `VmsMpInitializeNic`
- size: `1662`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, PCUNICODE_STRING@<rdx>, PCUNICODE_STRING, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x1400f610c`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14003e9e4`
- `0x140065e70`
- `0x14006a330`
- `0x14008497c`
- `0x140087fbc`
- `0x14008a258`
- `0x1400eac98`
- `0x1400f4a98`
- `0x1400f54cc`
- `0x1400fa8a0`
- `0x1400fe920`
- `0x1400ff21c`
- `0x1401aed14`
- `0x1401af240`
- `0x1401b05d4`
- `0x1401bbc40`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400f55e6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400f55e6`
- `ntoskrnl!KeInitializeMutex` at `0x1400f55fb`
- `ntoskrnl!KeInitializeMutex` at `0x1400f55fb`
- `ntoskrnl!ExAllocatePool2` at `0x1400f5572`
- `ntoskrnl!ExAllocatePool2` at `0x1400f5572`
- `NDIS!NdisAllocateNetBufferPool` at `0x1400f572b`
- `NDIS!NdisAllocateNetBufferPool` at `0x1400f572b`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f563b`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f56b2`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f563b`
- `NDIS!NdisAllocateNetBufferListPool` at `0x1400f56b2`

## pseudocode

```c

```
