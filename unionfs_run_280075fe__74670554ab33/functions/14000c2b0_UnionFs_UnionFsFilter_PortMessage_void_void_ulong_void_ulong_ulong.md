# UnionFs::UnionFsFilter::PortMessage(void *,void *,ulong,void *,ulong,ulong *)

- ea: `0x14000c2b0`
- end: `0x14000c971`
- name: `?PortMessage@UnionFsFilter@UnionFs@@SAJPEAX0K0KPEAK@Z`
- size: `1729`
- prototype: `NTSTATUS __stdcall(PVOID PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config`

## callees

- `0x1400047d4`
- `0x140005504`
- `0x1400055d0`
- `0x140006168`
- `0x140009120`
- `0x14000c2b0`
- `0x14000deb4`
- `0x14000e56c`
- `0x14000e86c`
- `0x14000eae0`
- `0x1400567f4`
- `0x140056ac4`
- `0x140056afc`
- `0x140069890`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b900`
- `0x1400a7008`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c601`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c654`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c729`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c816`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c847`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c85d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c601`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c654`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c729`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c7fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c816`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c847`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c85d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c8f6`

## string_xrefs

- `0x14000c753`: `PUSH: Message Response: CreateConfigureUnion`
- `0x14000c69d`: `PUSH: Message Response: ProcessRemoveUnionMsg`
- `0x14000c6e3`: `usedRemoveResponseSize <= OutputBufferSize - FIELD_OFFSET(UFS_MESSAGE, Buffer)`
- `0x14000c7c9`: `ORIGIN: Copying to user output buffer`

## pseudocode

```c

```
