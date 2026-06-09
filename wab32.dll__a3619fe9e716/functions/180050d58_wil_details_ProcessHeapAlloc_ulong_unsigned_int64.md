# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180050d58`
- end: `0x180050dee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180050890`
- `0x1800509e4`
- `0x18005201c`
- `0x18005334c`
- `0x180058718`

## callees

- `0x180049738`
- `0x180050d58`
- `0x180093010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180050da1`
- `KERNEL32!GetModuleHandleW` at `0x180050da1`
- `KERNEL32!GetProcessHeap` at `0x180050d6c`
- `KERNEL32!GetProcessHeap` at `0x180050d6c`
- `KERNEL32!HeapAlloc` at `0x180050d7d`
- `KERNEL32!HeapAlloc` at `0x180050d7d`

## string_xrefs

- `0x180050d9a`: `ntdll.dll`

## pseudocode

```c

```
