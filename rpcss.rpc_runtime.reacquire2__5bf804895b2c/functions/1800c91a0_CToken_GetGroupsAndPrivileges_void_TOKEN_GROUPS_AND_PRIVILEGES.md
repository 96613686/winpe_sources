# CToken::GetGroupsAndPrivileges(void *,_TOKEN_GROUPS_AND_PRIVILEGES * *)

- ea: `0x1800c91a0`
- end: `0x1800c92fd`
- name: `?GetGroupsAndPrivileges@CToken@@SAJPEAXPEAPEAU_TOKEN_GROUPS_AND_PRIVILEGES@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_GROUPS_AND_PRIVILEGES **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f7004`

## callees

- `0x180034260`
- `0x1800a7388`
- `0x1800c91a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c91df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c926f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c91df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c926f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c91d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c925f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c91d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c925f`
- `KERNELBASE!LocalAlloc` at `0x1800c9227`
- `KERNELBASE!LocalAlloc` at `0x1800c9227`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800c92df`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800c92df`

## string_xrefs

- `0x1800c92ba`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800c92a0`: `GetTokenInformation failed: %!WINERROR!`
- `0x1800c92b3`: `CToken::GetGroupsAndPrivileges`

## pseudocode

```c

```
