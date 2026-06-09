# CallerIdentity::IsProcessAppContainer(void *,bool *)

- ea: `0x18003f00c`
- end: `0x18003f0ed`
- name: `?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `225`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, void *, bool *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a6d0`
- `0x1800a3cc0`
- `0x180102cc0`

## callees

- `0x18003f00c`
- `0x1800ea2d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f028`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003f028`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f040`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003f040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f04a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f04a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0d9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f09e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003f09e`

## pseudocode

```c

```
