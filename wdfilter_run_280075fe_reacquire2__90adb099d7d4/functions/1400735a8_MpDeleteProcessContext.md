# MpDeleteProcessContext

- ea: `0x1400735a8`
- end: `0x140073682`
- name: `MpDeleteProcessContext`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140036780`

## callees

- `0x14000572c`
- `0x140030060`
- `0x1400735a8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007366f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073659`
- `ntoskrnl!ExReleaseResourceLite` at `0x140073659`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400735ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400735ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400735bc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400735bc`

## string_xrefs

- `0x140073635`: `delete`

## pseudocode

```c

```
