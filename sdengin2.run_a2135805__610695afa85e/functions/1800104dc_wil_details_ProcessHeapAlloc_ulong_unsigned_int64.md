# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800104dc`
- end: `0x180010593`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180010010`
- `0x180010174`
- `0x18001356c`
- `0x1800137a4`
- `0x1800148ac`

## callees

- `0x1800104dc`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18001054c`
- `KERNEL32!GetProcAddress` at `0x18001054c`
- `KERNEL32!GetModuleHandleW` at `0x180010531`
- `KERNEL32!GetModuleHandleW` at `0x180010531`
- `KERNEL32!HeapAlloc` at `0x180010507`
- `KERNEL32!HeapAlloc` at `0x180010507`
- `KERNEL32!GetProcessHeap` at `0x1800104f0`
- `KERNEL32!GetProcessHeap` at `0x1800104f0`

## string_xrefs

- `0x18001052a`: `ntdll.dll`

## pseudocode

```c

```
