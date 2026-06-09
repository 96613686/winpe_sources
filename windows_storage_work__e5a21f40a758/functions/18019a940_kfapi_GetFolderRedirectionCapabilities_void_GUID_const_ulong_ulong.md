# kfapi::GetFolderRedirectionCapabilities(void *,_GUID const &,ulong,ulong *)

- ea: `0x18019a940`
- end: `0x18019ae17`
- name: `?GetFolderRedirectionCapabilities@kfapi@@YAJPEAXAEBU_GUID@@KPEAK@Z`
- size: `1239`
- prototype: `__int64 __fastcall(kfapi *__hidden this, void *, const struct _GUID *, unsigned int, unsigned int *)`
- caller_count: `6`
- callee_count: `14`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18019a8b0`
- `0x180245f90`
- `0x18034c0a0`
- `0x1805fc068`
- `0x1805fcd1c`
- `0x1805fd084`

## callees

- `0x18003e3b0`
- `0x18003eff0`
- `0x180045990`
- `0x18009d164`
- `0x1800ef3d0`
- `0x18019a940`
- `0x18019ae20`
- `0x18019ae48`
- `0x18019af40`
- `0x18019b7b4`
- `0x18019b8c0`
- `0x18019bc28`
- `0x180227514`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019aa5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019aa5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019aa37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18019aa37`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019aa8c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18019aa8c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019aa7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18019aa7a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019aa4f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18019aa4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ad1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019adeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019ad1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019adeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019ab72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019ab89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019acdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019acef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019ab72`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019ab89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019acdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019acef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019ab4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019ab4e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18019abbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18019abbd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18019aa04`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18019aa04`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18019ac03`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18019ac03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ab92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ac93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019acb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019acf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ad5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019adce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ab92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ac93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019acb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019acf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019ad5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019adce`

## pseudocode

```c

```
