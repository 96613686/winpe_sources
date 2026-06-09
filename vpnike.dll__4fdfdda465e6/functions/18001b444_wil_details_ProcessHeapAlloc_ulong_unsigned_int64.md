# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18001b444`
- end: `0x18001b4e2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001a314`
- `0x18001a43c`
- `0x18001e4d0`
- `0x18001e958`
- `0x180020560`

## callees

- `0x18001b444`
- `0x18007a010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b469`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b469`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b458`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b458`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b4a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b4a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b48d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001b48d`

## string_xrefs

- `0x18001b486`: `ntdll.dll`

## pseudocode

```c

```
