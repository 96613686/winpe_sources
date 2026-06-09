# BlbutilLogonUser(ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x140094a18`
- end: `0x140094caf`
- name: `?BlbutilLogonUser@@YAJPEBG00PEAPEAX@Z`
- size: `663`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400502e0`
- `0x140055ae0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140094a18`
- `0x140094ff8`

## import_xrefs

- `ADVAPI32!LogonUserExExW` at `0x140094af4`
- `ADVAPI32!LogonUserExExW` at `0x140094ba0`
- `ADVAPI32!LogonUserExExW` at `0x140094af4`
- `ADVAPI32!LogonUserExExW` at `0x140094ba0`
- `KERNEL32!CloseHandle` at `0x140094c42`
- `KERNEL32!CloseHandle` at `0x140094c42`
- `KERNEL32!GetLastError` at `0x140094b02`
- `KERNEL32!GetLastError` at `0x140094baa`
- `KERNEL32!GetLastError` at `0x140094b02`
- `KERNEL32!GetLastError` at `0x140094baa`
- `ole32!CoTaskMemFree` at `0x140094c54`
- `ole32!CoTaskMemFree` at `0x140094c5e`
- `ole32!CoTaskMemFree` at `0x140094c54`
- `ole32!CoTaskMemFree` at `0x140094c5e`

## string_xrefs

- `0x140094a8f`: `base\stor\blb\util\securityutils.cpp`
- `0x140094a83`: `phToken`

## pseudocode

```c

```
