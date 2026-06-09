# OPM::CMonitorPDO::CMonitorPDO(_LUID &,ulong,long *)

- ea: `0x140032470`
- end: `0x1400326de`
- name: `??0CMonitorPDO@OPM@@QEAA@AEAU_LUID@@KPEAJ@Z`
- size: `622`
- prototype: `__int64 __fastcall(OPM::CMonitorPDO *__hidden this, struct _LUID *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400323a0`

## callees

- `0x140032100`
- `0x140032240`
- `0x1400322b0`
- `0x140032470`
- `0x1400326f0`
- `0x1400327ec`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140032663`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140032663`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400326be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400326be`
- `ntoskrnl!ObfReferenceObject` at `0x140032568`
- `ntoskrnl!ObfReferenceObject` at `0x140032568`
- `ntoskrnl!ExAllocatePool2` at `0x1400324ee`
- `ntoskrnl!ExAllocatePool2` at `0x1400324ee`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14003259a`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400325f1`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14003259a`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400325f1`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x140032614`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x140032614`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032639`
- `ntoskrnl!RtlInitUnicodeString` at `0x140032639`
- `ntoskrnl!ObfDereferenceObject` at `0x1400325ac`
- `ntoskrnl!ObfDereferenceObject` at `0x1400325ac`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140032536`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140032536`

## pseudocode

```c

```
