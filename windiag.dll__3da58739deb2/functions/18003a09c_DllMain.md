# DllMain

- ea: `0x18003a09c`
- end: `0x18003a259`
- name: `DllMain`
- size: `445`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180004374`

## callees

- `0x180001008`
- `0x18000113c`
- `0x180004510`
- `0x180039ff0`
- `0x18003a09c`
- `0x1800905a0`
- `0x180096038`
- `0x180096160`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003a20f`
- `msvcp_win!_Mtx_unlock` at `0x18003a20f`
- `msvcp_win!_Mtx_lock` at `0x18003a1c6`
- `msvcp_win!_Mtx_lock` at `0x18003a1c6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a1d5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a1f7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a1d5`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18003a1f7`
- `api-ms-win-crt-runtime-l1-1-0!signal` at `0x18003a0d9`
- `api-ms-win-crt-runtime-l1-1-0!signal` at `0x18003a150`
- `api-ms-win-crt-runtime-l1-1-0!signal` at `0x18003a0d9`
- `api-ms-win-crt-runtime-l1-1-0!signal` at `0x18003a150`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18003a231`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18003a231`

## pseudocode

```c

```
