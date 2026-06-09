# DllMain

- ea: `0x18003a19c`
- end: `0x18003a215`
- name: `DllMain`
- size: `121`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032054`

## callees

- `0x18003a19c`
- `0x18009e620`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003a1bf`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18003a1bf`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003a1e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003a1fd`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003a1e2`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18003a1fd`

## pseudocode

```c

```
