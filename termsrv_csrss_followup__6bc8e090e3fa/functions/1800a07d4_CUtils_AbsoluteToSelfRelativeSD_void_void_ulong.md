# CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)

- ea: `0x1800a07d4`
- end: `0x1800a0914`
- name: `?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z`
- size: `320`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a000`
- `0x1800bf878`

## callees

- `0x180009940`
- `0x1800a07d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0811`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a088c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0811`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a088c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a08e9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a084d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a084d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a08cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a08cc`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800a07fa`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800a0875`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800a07fa`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x1800a0875`

## pseudocode

```c

```
