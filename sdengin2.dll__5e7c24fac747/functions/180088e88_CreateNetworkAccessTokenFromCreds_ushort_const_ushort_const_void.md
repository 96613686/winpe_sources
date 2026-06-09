# CreateNetworkAccessTokenFromCreds(ushort const *,ushort const *,void * *)

- ea: `0x180088e88`
- end: `0x1800891e6`
- name: `?CreateNetworkAccessTokenFromCreds@@YAJPEBG0PEAPEAX@Z`
- size: `862`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpszPassword, void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028300`
- `0x18008960c`

## callees

- `0x180009ac8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088e88`
- `0x18008eb48`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `msvcrt!wcschr` at `0x180088f99`
- `msvcrt!wcschr` at `0x180088faa`
- `msvcrt!wcschr` at `0x180088f99`
- `msvcrt!wcschr` at `0x180088faa`
- `msvcrt!_wcsupr` at `0x180088ff7`
- `msvcrt!_wcsupr` at `0x180088ff7`
- `KERNEL32!CloseHandle` at `0x18008902b`
- `KERNEL32!CloseHandle` at `0x180089128`
- `KERNEL32!CloseHandle` at `0x18008918f`
- `KERNEL32!CloseHandle` at `0x1800891a9`
- `KERNEL32!CloseHandle` at `0x18008902b`
- `KERNEL32!CloseHandle` at `0x180089128`
- `KERNEL32!CloseHandle` at `0x18008918f`
- `KERNEL32!CloseHandle` at `0x1800891a9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180089142`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180089142`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180089070`
- `api-ms-win-security-logon-l1-1-0!LogonUserExW` at `0x180089070`
- `credui!CredUIParseUserNameW` at `0x180088f82`
- `credui!CredUIParseUserNameW` at `0x180088f82`

## string_xrefs

- `0x180089094`: `SeBackupPrivilege`
- `0x1800890c7`: `SeRestorePrivilege`
- `0x1800890f0`: `SeSecurityPrivilege`
- `0x180088ebd`: `CreateNetworkAccessTokenFromCreds`

## pseudocode

```c

```
