# UtilGetCurrentProcessIntegrityLevel(ulong *)

- ea: `0x1800975e8`
- end: `0x1800976c6`
- name: `?UtilGetCurrentProcessIntegrityLevel@@YAJPEAK@Z`
- size: `222`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003daec`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x18001fe24`
- `0x18002c570`
- `0x180049310`
- `0x18004acbc`
- `0x1800975e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180097615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180097615`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180097626`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180097626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009763c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009763c`

## pseudocode

```c

```
