# CAddUserAccountWizard::_CommitDomainAccount(void)

- ea: `0x180009874`
- end: `0x180009a47`
- name: `?_CommitDomainAccount@CAddUserAccountWizard@@AEAAJXZ`
- size: `467`
- prototype: `__int64 __fastcall(CAddUserAccountWizard *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007a10`

## callees

- `0x180006f2c`
- `0x180007554`
- `0x180007730`
- `0x180007a4c`
- `0x180008cb0`
- `0x180008f74`
- `0x180009874`
- `0x18000ad0c`
- `0x18000d200`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `samcli!NetUserGetLocalGroups` at `0x180009953`
- `samcli!NetUserGetLocalGroups` at `0x180009953`
- `netutils!NetApiBufferFree` at `0x180009962`
- `netutils!NetApiBufferFree` at `0x180009962`
- `ntdll!WinSqmIncrementDWORD` at `0x1800099d0`
- `ntdll!WinSqmIncrementDWORD` at `0x1800099d0`

## string_xrefs

- `0x1800098ae`: `CreateDomainUser`

## pseudocode

```c

```
