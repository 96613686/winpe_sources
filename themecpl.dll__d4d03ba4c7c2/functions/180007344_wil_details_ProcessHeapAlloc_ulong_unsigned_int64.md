# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007344`
- end: `0x1800073fb`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180005adc`
- `0x180006710`
- `0x180007d40`
- `0x180011854`
- `0x18001eff4`

## callees

- `0x180007344`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800073b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800073b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007399`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007399`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000736f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000736f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007358`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007358`

## string_xrefs

- `0x180007392`: `ntdll.dll`

## pseudocode

```c

```
