# GetTokenInformationHelper(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x180086aec`
- end: `0x180086c22`
- name: `?GetTokenInformationHelper@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `310`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18005a09c`
- `0x180080410`

## callees

- `0x18000d60c`
- `0x180010c04`
- `0x180066ed8`
- `0x180067258`
- `0x180086aec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086b2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180086b2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086b42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180086b42`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086b1f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086b8d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086b1f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180086b8d`

## string_xrefs

- `0x180086b5a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180086b9c`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180086bdc`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180086bf7`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c

```
