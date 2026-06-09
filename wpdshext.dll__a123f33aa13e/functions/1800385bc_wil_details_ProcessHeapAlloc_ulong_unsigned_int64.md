# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800385bc`
- end: `0x180038652`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002b7d0`
- `0x18002dd24`
- `0x18003885c`
- `0x180038bf4`

## callees

- `0x180036e5c`
- `0x1800385bc`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800385e1`
- `KERNEL32!HeapAlloc` at `0x1800385e1`
- `KERNEL32!GetProcessHeap` at `0x1800385d0`
- `KERNEL32!GetProcessHeap` at `0x1800385d0`
- `KERNEL32!GetModuleHandleW` at `0x180038605`
- `KERNEL32!GetModuleHandleW` at `0x180038605`

## string_xrefs

- `0x1800385fe`: `ntdll.dll`

## pseudocode

```c

```
