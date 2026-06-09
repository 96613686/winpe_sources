# SrvNetFindEndpointByName

- ea: `0x140053830`
- end: `0x14005392f`
- name: `SrvNetFindEndpointByName`
- size: `255`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING String1@<rcx>, PCUNICODE_STRING@<rdx>, char)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a000`
- `0x14000a090`
- `0x14000a1f0`
- `0x14000a9c0`
- `0x1400237a4`
- `0x140042524`

## callees

- `0x14000ec20`
- `0x140053830`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x1400538ae`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005391a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400538ae`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14005391a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005386e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005386e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400538df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400538df`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053852`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140053852`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400538d3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400538d3`

## pseudocode

```c

```
