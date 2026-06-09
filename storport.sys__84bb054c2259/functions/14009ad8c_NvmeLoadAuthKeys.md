# NvmeLoadAuthKeys

- ea: `0x14009ad8c`
- end: `0x14009af1d`
- name: `NvmeLoadAuthKeys`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400cda60`

## callees

- `0x1400290b0`
- `0x14009ad8c`
- `0x14009cfa4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14009adc5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009adc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009aee9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009aee9`
- `ntoskrnl!ZwClose` at `0x14009aefe`
- `ntoskrnl!ZwClose` at `0x14009aefe`
- `ntoskrnl!ZwOpenKey` at `0x14009ae04`
- `ntoskrnl!ZwOpenKey` at `0x14009ae04`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14009aecd`
- `ntoskrnl!ZwEnumerateValueKey` at `0x14009aecd`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14009ae68`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x14009ae68`

## string_xrefs

- `0x14009ada1`: `\Registry\Machine\System\CurrentControlSet\Control\StorPort\NVMeAuthKeys`

## pseudocode

```c

```
