# CToken::GetTokenGroups(void *)

- ea: `0x180066838`
- end: `0x180066997`
- name: `?GetTokenGroups@CToken@@SAPEAU_TOKEN_GROUPS@@PEAX@Z`
- size: `351`
- prototype: `struct _TOKEN_GROUPS *__fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800667a4`

## callees

- `0x180034260`
- `0x180066838`
- `0x1800a7388`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006686d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006686d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066920`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066861`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066910`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066861`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066910`
- `KERNELBASE!LocalAlloc` at `0x1800668de`
- `KERNELBASE!LocalAlloc` at `0x1800668de`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006697a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18006697a`

## string_xrefs

- `0x1800668c7`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18006696b`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x1800668c0`: `CToken::GetTokenGroups`
- `0x180066964`: `CToken::GetTokenGroups`

## pseudocode

```c

```
