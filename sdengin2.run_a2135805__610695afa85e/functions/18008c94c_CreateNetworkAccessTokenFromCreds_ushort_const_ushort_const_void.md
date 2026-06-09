# CreateNetworkAccessTokenFromCreds(ushort const *,ushort const *,void * *)

- ea: `0x18008c94c`
- end: `0x18008cce7`
- name: `?CreateNetworkAccessTokenFromCreds@@YAJPEBG0PEAPEAX@Z`
- size: `923`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpszPassword, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002935c`
- `0x18008d150`

## callees

- `0x180009d44`
- `0x180072e08`
- `0x180072f14`
- `0x18008c94c`
- `0x180092ae0`
- `0x1800935fc`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `msvcrt!wcschr` at `0x18008ca63`
- `msvcrt!wcschr` at `0x18008ca7a`
- `msvcrt!wcschr` at `0x18008ca63`
- `msvcrt!wcschr` at `0x18008ca7a`
- `msvcrt!_wcsupr` at `0x18008cacd`
- `msvcrt!_wcsupr` at `0x18008cacd`
- `KERNEL32!CloseHandle` at `0x18008cb07`
- `KERNEL32!CloseHandle` at `0x18008cc10`
- `KERNEL32!CloseHandle` at `0x18008cc83`
- `KERNEL32!CloseHandle` at `0x18008cca3`
- `KERNEL32!CloseHandle` at `0x18008cb07`
- `KERNEL32!CloseHandle` at `0x18008cc10`
- `KERNEL32!CloseHandle` at `0x18008cc83`
- `KERNEL32!CloseHandle` at `0x18008cca3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18008cc30`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18008cc30`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18008cb52`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x18008cb52`
- `credui!CredUIParseUserNameW` at `0x18008ca46`
- `credui!CredUIParseUserNameW` at `0x18008ca46`

## string_xrefs

- `0x18008cb7c`: `SeBackupPrivilege`
- `0x18008cbaf`: `SeRestorePrivilege`
- `0x18008cbd8`: `SeSecurityPrivilege`
- `0x18008c981`: `CreateNetworkAccessTokenFromCreds`

## pseudocode

```c

```
