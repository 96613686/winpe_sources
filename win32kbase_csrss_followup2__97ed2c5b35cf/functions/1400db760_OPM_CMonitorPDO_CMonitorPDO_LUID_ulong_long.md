# OPM::CMonitorPDO::CMonitorPDO(_LUID &,ulong,long *)

- ea: `0x1400db760`
- end: `0x1400db9ce`
- name: `??0CMonitorPDO@OPM@@QEAA@AEAU_LUID@@KPEAJ@Z`
- size: `622`
- prototype: `__int64 __fastcall(OPM::CMonitorPDO *__hidden this, struct _LUID *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400db690`

## callees

- `0x1400db3f0`
- `0x1400db530`
- `0x1400db5a0`
- `0x1400db760`
- `0x1400db9e0`
- `0x1400dbadc`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400db953`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400db953`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400db9ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400db9ae`
- `ntoskrnl!ObfReferenceObject` at `0x1400db858`
- `ntoskrnl!ObfReferenceObject` at `0x1400db858`
- `ntoskrnl!ExAllocatePool2` at `0x1400db7de`
- `ntoskrnl!ExAllocatePool2` at `0x1400db7de`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400db88a`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400db8e1`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400db88a`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x1400db8e1`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400db904`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x1400db904`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400db929`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400db929`
- `ntoskrnl!ObfDereferenceObject` at `0x1400db89c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400db89c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400db826`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400db826`

## pseudocode

```c

```
