# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180037e6c`
- end: `0x180037f02`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800379e8`
- `0x180037b38`
- `0x180039264`
- `0x1800394cc`
- `0x18003a940`

## callees

- `0x180034c9c`
- `0x180037e6c`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180037eb5`
- `KERNEL32!GetModuleHandleW` at `0x180037eb5`
- `KERNEL32!GetProcessHeap` at `0x180037e80`
- `KERNEL32!GetProcessHeap` at `0x180037e80`
- `KERNEL32!HeapAlloc` at `0x180037e91`
- `KERNEL32!HeapAlloc` at `0x180037e91`

## string_xrefs

- `0x180037eae`: `ntdll.dll`

## pseudocode

```c

```
