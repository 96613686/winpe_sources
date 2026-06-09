# CLogonUser::changePassword(tagVARIANT,tagVARIANT,short *)

- ea: `0x18002df70`
- end: `0x18002e178`
- name: `?changePassword@CLogonUser@@UEAAJUtagVARIANT@@0PEAF@Z`
- size: `520`
- prototype: `__int64 __fastcall(CLogonUser *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *__struct_ptr, __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18002d54c`
- `0x18002df70`
- `0x1800772c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e06a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002e06a`
- `samcli!NetUserChangePassword` at `0x18002e08d`
- `samcli!NetUserChangePassword` at `0x18002e08d`
- `samcli!NetUserModalsGet` at `0x18002dfe2`
- `samcli!NetUserModalsGet` at `0x18002dfe2`
- `samcli!NetUserGetInfo` at `0x18002e0d7`
- `samcli!NetUserGetInfo` at `0x18002e0d7`
- `samcli!NetUserSetInfo` at `0x18002e0b3`
- `samcli!NetUserSetInfo` at `0x18002e103`
- `samcli!NetUserSetInfo` at `0x18002e0b3`
- `samcli!NetUserSetInfo` at `0x18002e103`
- `netutils!NetApiBufferFree` at `0x18002e014`
- `netutils!NetApiBufferFree` at `0x18002e10e`
- `netutils!NetApiBufferFree` at `0x18002e014`
- `netutils!NetApiBufferFree` at `0x18002e10e`
- `SspiCli!GetUserNameExW` at `0x18002e039`
- `SspiCli!GetUserNameExW` at `0x18002e039`

## pseudocode

```c

```
