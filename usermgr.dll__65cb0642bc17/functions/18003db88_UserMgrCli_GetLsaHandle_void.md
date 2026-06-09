# UserMgrCli::GetLsaHandle(void * *)

- ea: `0x18003db88`
- end: `0x18003dc5a`
- name: `?GetLsaHandle@UserMgrCli@@AEAAJPEAPEAX@Z`
- size: `210`
- prototype: `__int64 __fastcall(UserMgrCli *__hidden this, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180041048`

## callees

- `0x18003db88`
- `0x18003dc60`
- `0x18004e4e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dc40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003dc40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dba4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003dba4`
- `ntdll!RtlInitString` at `0x18003dbf9`
- `ntdll!RtlInitString` at `0x18003dbf9`
- `SspiCli!LsaRegisterLogonProcess` at `0x18003dc10`
- `SspiCli!LsaRegisterLogonProcess` at `0x18003dc10`

## string_xrefs

- `0x18003dbdc`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`
- `0x18003dc22`: `onecore\ds\security\umstartup\usermgr\lib\usermgrcli.cpp`

## pseudocode

```c

```
