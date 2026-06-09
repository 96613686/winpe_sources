# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002f0ac`
- end: `0x18002f154`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `168`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180027620`
- `0x18003038c`

## callees

- `0x18002f0ac`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18002f0ff`
- `KERNEL32!GetModuleHandleW` at `0x18002f0ff`
- `KERNEL32!GetProcessHeap` at `0x18002f0ca`
- `KERNEL32!GetProcessHeap` at `0x18002f0ca`
- `KERNEL32!GetProcAddress` at `0x18002f114`
- `KERNEL32!GetProcAddress` at `0x18002f114`
- `KERNEL32!HeapAlloc` at `0x18002f0db`
- `KERNEL32!HeapAlloc` at `0x18002f0db`

## string_xrefs

- `0x18002f0f8`: `ntdll.dll`

## pseudocode

```c

```
