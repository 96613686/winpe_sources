# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000fe88`
- end: `0x18000ff26`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f9d8`
- `0x18000fb3c`
- `0x180012cfc`
- `0x180012f24`
- `0x180014020`

## callees

- `0x18000fe88`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000fee6`
- `KERNEL32!GetProcAddress` at `0x18000fee6`
- `KERNEL32!GetModuleHandleW` at `0x18000fed1`
- `KERNEL32!GetModuleHandleW` at `0x18000fed1`
- `KERNEL32!HeapAlloc` at `0x18000fead`
- `KERNEL32!HeapAlloc` at `0x18000fead`
- `KERNEL32!GetProcessHeap` at `0x18000fe9c`
- `KERNEL32!GetProcessHeap` at `0x18000fe9c`

## string_xrefs

- `0x18000feca`: `ntdll.dll`

## pseudocode

```c

```
