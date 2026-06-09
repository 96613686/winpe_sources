# StorPortRegistryRead

- ea: `0x14003a4b0`
- end: `0x14003a674`
- name: `StorPortRegistryRead`
- size: `452`
- prototype: `__int64 __usercall@<rax>(PVOID VirtualAddress@<rcx>, PCSZ SourceString@<rdx>, __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x14003a4b0`
- `0x14003a67c`
- `0x14003a8ac`
- `0x140070808`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14003a604`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003a666`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003a604`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14003a666`
- `ntoskrnl!RtlInitAnsiString` at `0x14003a5b2`
- `ntoskrnl!RtlInitAnsiString` at `0x14003a5b2`
- `ntoskrnl!MmIsAddressValid` at `0x14003a4f6`
- `ntoskrnl!MmIsAddressValid` at `0x14003a4f6`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a4df`
- `ntoskrnl!KeGetCurrentIrql` at `0x14003a4df`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14003a5c9`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14003a5c9`

## pseudocode

```c

```
