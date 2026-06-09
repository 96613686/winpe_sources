# Smb2PopulateShareNormalizedNameCache

- ea: `0x140081880`
- end: `0x140081b8a`
- name: `Smb2PopulateShareNormalizedNameCache`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140081404`

## callees

- `0x140022958`
- `0x140038680`
- `0x140081880`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400818f5`
- `ntoskrnl!ExAllocatePool2` at `0x1400819a3`
- `ntoskrnl!ExAllocatePool2` at `0x1400818f5`
- `ntoskrnl!ExAllocatePool2` at `0x1400819a3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400818b5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400818b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400818da`
- `ntoskrnl!ExReleaseResourceLite` at `0x140081b53`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400818da`
- `ntoskrnl!ExReleaseResourceLite` at `0x140081b53`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140081abf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140081abf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081a3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081a3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140081b6c`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140081b05`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140081b05`
- `ntoskrnl!ZwQueryInformationFile` at `0x14008197c`
- `ntoskrnl!ZwQueryInformationFile` at `0x140081a28`
- `ntoskrnl!ZwQueryInformationFile` at `0x14008197c`
- `ntoskrnl!ZwQueryInformationFile` at `0x140081a28`

## pseudocode

```c

```
