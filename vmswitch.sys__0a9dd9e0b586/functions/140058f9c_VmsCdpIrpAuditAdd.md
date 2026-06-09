# VmsCdpIrpAuditAdd

- ea: `0x140058f9c`
- end: `0x140059313`
- name: `VmsCdpIrpAuditAdd`
- size: `887`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140058c50`

## callees

- `0x14002e0f0`
- `0x140046e5c`
- `0x140058f9c`
- `0x14005931c`
- `0x140059540`
- `0x140059640`
- `0x140059714`

## import_xrefs

- `ntoskrnl!SeLocateProcessImageName` at `0x140059139`
- `ntoskrnl!SeLocateProcessImageName` at `0x140059139`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400590d0`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x1400590d0`
- `ntoskrnl!RtlxAnsiStringToUnicodeSize` at `0x140059082`
- `ntoskrnl!RtlxAnsiStringToUnicodeSize` at `0x140059082`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14005905d`
- `ntoskrnl!PsGetProcessImageFileName` at `0x14005905d`
- `ntoskrnl!IoGetRequestorProcess` at `0x140059042`
- `ntoskrnl!IoGetRequestorProcess` at `0x140059042`
- `ntoskrnl!RtlInitAnsiString` at `0x140059071`
- `ntoskrnl!RtlInitAnsiString` at `0x140059071`
- `ntoskrnl!ExAllocatePool2` at `0x140059008`
- `ntoskrnl!ExAllocatePool2` at `0x1400590a4`
- `ntoskrnl!ExAllocatePool2` at `0x140059102`
- `ntoskrnl!ExAllocatePool2` at `0x140059008`
- `ntoskrnl!ExAllocatePool2` at `0x1400590a4`
- `ntoskrnl!ExAllocatePool2` at `0x140059102`
- `NDIS!NdisReleaseRWLock` at `0x1400591c8`
- `NDIS!NdisReleaseRWLock` at `0x1400591c8`
- `NDIS!NdisAcquireRWLockWrite` at `0x140059190`
- `NDIS!NdisAcquireRWLockWrite` at `0x140059190`

## pseudocode

```c

```
