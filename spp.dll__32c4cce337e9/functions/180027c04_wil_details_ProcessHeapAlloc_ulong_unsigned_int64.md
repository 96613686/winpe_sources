# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180027c04`
- end: `0x180027ca2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002b308`
- `0x180032178`
- `0x1800322a0`
- `0x1800332f4`
- `0x180033520`

## callees

- `0x180027c04`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180027c62`
- `KERNEL32!GetProcAddress` at `0x180027c62`
- `KERNEL32!GetModuleHandleW` at `0x180027c4d`
- `KERNEL32!GetModuleHandleW` at `0x180027c4d`
- `KERNEL32!GetProcessHeap` at `0x180027c18`
- `KERNEL32!GetProcessHeap` at `0x180027c18`
- `KERNEL32!HeapAlloc` at `0x180027c29`
- `KERNEL32!HeapAlloc` at `0x180027c29`

## string_xrefs

- `0x180027c46`: `ntdll.dll`

## pseudocode

```c

```
