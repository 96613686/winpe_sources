# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x1800a6464`
- end: `0x1800a64b0`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `DWORD __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003d38c`

## callees

- `0x1800a6464`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a6474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800a6474`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a648a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800a648a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6494`

## pseudocode

```c

```
