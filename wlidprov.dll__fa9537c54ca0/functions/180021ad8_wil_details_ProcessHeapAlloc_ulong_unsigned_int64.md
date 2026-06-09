# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180021ad8`
- end: `0x180021b6e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001648c`
- `0x1800165f0`
- `0x18002119c`
- `0x180021ef0`
- `0x180022288`
- `0x180035224`

## callees

- `0x18001fd24`
- `0x180021ad8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180021b21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021aec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021aec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021afd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021afd`

## string_xrefs

- `0x180021b1a`: `ntdll.dll`

## pseudocode

```c

```
