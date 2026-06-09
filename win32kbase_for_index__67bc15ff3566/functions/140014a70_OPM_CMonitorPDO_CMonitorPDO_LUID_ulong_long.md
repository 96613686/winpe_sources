# OPM::CMonitorPDO::CMonitorPDO(_LUID &,ulong,long *)

- ea: `0x140014a70`
- end: `0x140014cde`
- name: `??0CMonitorPDO@OPM@@QEAA@AEAU_LUID@@KPEAJ@Z`
- size: `622`
- prototype: `__int64 __fastcall(OPM::CMonitorPDO *__hidden this, struct _LUID *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400149a4`

## callees

- `0x140014740`
- `0x140014880`
- `0x1400148f0`
- `0x140014a70`
- `0x140014cf0`
- `0x140014dec`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140014c63`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140014c63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014cbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014cbe`
- `ntoskrnl!ObfReferenceObject` at `0x140014b68`
- `ntoskrnl!ObfReferenceObject` at `0x140014b68`
- `ntoskrnl!ExAllocatePool2` at `0x140014aee`
- `ntoskrnl!ExAllocatePool2` at `0x140014aee`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140014b9a`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140014bf1`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140014b9a`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140014bf1`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x140014c14`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x140014c14`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014c39`
- `ntoskrnl!RtlInitUnicodeString` at `0x140014c39`
- `ntoskrnl!ObfDereferenceObject` at `0x140014bac`
- `ntoskrnl!ObfDereferenceObject` at `0x140014bac`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140014b36`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140014b36`

## pseudocode

```c

```
