# UtilGetCurrentProcessIntegrityLevel(ulong *)

- ea: `0x18009b978`
- end: `0x18009ba69`
- name: `?UtilGetCurrentProcessIntegrityLevel@@YAJPEAK@Z`
- size: `241`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003fb04`

## callees

- `0x180007fd8`
- `0x18001c368`
- `0x180020680`
- `0x18002e0b0`
- `0x18004b454`
- `0x18004cc30`
- `0x18009b978`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009b9a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009b9a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009b9bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009b9bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b9d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009b9d8`

## pseudocode

```c

```
