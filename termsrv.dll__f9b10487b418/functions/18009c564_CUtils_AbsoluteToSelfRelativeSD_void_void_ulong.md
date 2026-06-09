# CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)

- ea: `0x18009c564`
- end: `0x18009c66d`
- name: `?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z`
- size: `265`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028a64`
- `0x1800b8f58`

## callees

- `0x18000a210`
- `0x18009c564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c59b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c5fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c59b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c5fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c5b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c5b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c649`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c5cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18009c5cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c632`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c632`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009c58a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009c5ed`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009c58a`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18009c5ed`

## pseudocode

```c

```
