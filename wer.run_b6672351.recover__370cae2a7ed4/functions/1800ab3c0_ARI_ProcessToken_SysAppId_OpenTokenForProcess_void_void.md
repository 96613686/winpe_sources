# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x1800ab3c0`
- end: `0x1800ab41f`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `95`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18003f440`

## callees

- `0x1800ab3c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ab3d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab3ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800ab3ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab3fc`

## pseudocode

```c

```
