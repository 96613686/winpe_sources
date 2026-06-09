# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003f930`
- end: `0x18003f9c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180022990`
- `0x18003f42c`
- `0x18003f55c`
- `0x180040334`
- `0x180040598`

## callees

- `0x18003d01c`
- `0x18003f930`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003f979`
- `KERNEL32!GetModuleHandleW` at `0x18003f979`
- `KERNEL32!GetProcessHeap` at `0x18003f944`
- `KERNEL32!GetProcessHeap` at `0x18003f944`
- `KERNEL32!HeapAlloc` at `0x18003f955`
- `KERNEL32!HeapAlloc` at `0x18003f955`

## string_xrefs

- `0x18003f972`: `ntdll.dll`

## pseudocode

```c

```
