# kfapi::GetFolderRedirectionCapabilities(void *,_GUID const &,ulong,ulong *)

- ea: `0x1801b63f0`
- end: `0x1801b68c5`
- name: `?GetFolderRedirectionCapabilities@kfapi@@YAJPEAXAEBU_GUID@@KPEAK@Z`
- size: `1237`
- prototype: `__int64 __fastcall(kfapi *__hidden this, void *, const struct _GUID *, unsigned int, unsigned int *)`
- caller_count: `6`
- callee_count: `15`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801b6360`
- `0x180254710`
- `0x18035d5a8`
- `0x18061c378`
- `0x18061d08c`
- `0x18061d3f8`

## callees

- `0x180033dc0`
- `0x180034a40`
- `0x18003b500`
- `0x18004e06c`
- `0x180075420`
- `0x1800d9e50`
- `0x1801b63f0`
- `0x1801b68cc`
- `0x1801b68fc`
- `0x1801b6a30`
- `0x1801b7318`
- `0x1801b73d0`
- `0x1801b7444`
- `0x1801b77e4`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801b6521`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801b6521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801b6509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801b6509`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b688f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b68aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b688f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801b68aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b6613`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b6630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b6794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b67ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b6613`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b6630`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b6794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801b67ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801b65e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1801b65e9`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1801b6671`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x1801b6671`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801b64b4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1801b64b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b66bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801b66bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b663f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b6753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b67bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b6876`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b663f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b6753`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b67bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801b6876`

## pseudocode

```c

```
