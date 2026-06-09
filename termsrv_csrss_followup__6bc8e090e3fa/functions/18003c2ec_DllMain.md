# DllMain

- ea: `0x18003c2ec`
- end: `0x18003c378`
- name: `DllMain`
- size: `140`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180033dc4`

## callees

- `0x18003c2ec`
- `0x1800a3a20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003c30f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003c30f`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003c338`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003c359`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003c338`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003c359`

## pseudocode

```c

```
