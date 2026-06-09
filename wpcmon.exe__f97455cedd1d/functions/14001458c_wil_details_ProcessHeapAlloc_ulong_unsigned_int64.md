# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14001458c`
- end: `0x14001462a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000fc78`
- `0x14001004c`
- `0x140011800`
- `0x140012044`
- `0x140016d58`
- `0x14001cc14`

## callees

- `0x14001458c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1400145b1`
- `KERNEL32!HeapAlloc` at `0x1400145b1`
- `KERNEL32!GetProcAddress` at `0x1400145ea`
- `KERNEL32!GetProcAddress` at `0x1400145ea`
- `KERNEL32!GetModuleHandleW` at `0x1400145d5`
- `KERNEL32!GetModuleHandleW` at `0x1400145d5`
- `KERNEL32!GetProcessHeap` at `0x1400145a0`
- `KERNEL32!GetProcessHeap` at `0x1400145a0`

## string_xrefs

- `0x1400145ce`: `ntdll.dll`

## pseudocode

```c

```
