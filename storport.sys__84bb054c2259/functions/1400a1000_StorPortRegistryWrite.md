# StorPortRegistryWrite

- ea: `0x1400a1000`
- end: `0x1400a1192`
- name: `StorPortRegistryWrite`
- size: `402`
- prototype: `__int64 __usercall@<rax>(PVOID VirtualAddress@<rcx>, PCSZ SourceString@<rdx>, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x14002be10`
- `0x14003a8ac`
- `0x140070808`
- `0x1400a1000`
- `0x140142abc`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a1156`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a116d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a1156`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400a116d`
- `ntoskrnl!RtlInitAnsiString` at `0x1400a1103`
- `ntoskrnl!RtlInitAnsiString` at `0x1400a1103`
- `ntoskrnl!MmIsAddressValid` at `0x1400a1055`
- `ntoskrnl!MmIsAddressValid` at `0x1400a1055`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400a103e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400a103e`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400a111f`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400a111f`

## pseudocode

```c

```
