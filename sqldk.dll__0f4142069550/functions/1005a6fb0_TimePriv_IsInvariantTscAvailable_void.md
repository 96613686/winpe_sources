# TimePriv::IsInvariantTscAvailable(void)

- ea: `0x1005a6fb0`
- end: `0x1005a7102`
- name: `?IsInvariantTscAvailable@TimePriv@@CAHXZ`
- size: `338`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1004b7e20`

## callees

- `0x100403070`
- `0x1004b5fa0`
- `0x1005a6fb0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1005a70a1`
- `KERNEL32!QueryPerformanceCounter` at `0x1005a70a1`
- `KERNEL32!GetModuleHandleW` at `0x1005a6ff7`
- `KERNEL32!GetModuleHandleW` at `0x1005a6ff7`
- `KERNEL32!GetProcAddress` at `0x1005a700c`
- `KERNEL32!GetProcAddress` at `0x1005a700c`

## string_xrefs

- `0x1005a6ff0`: `ntdll.dll`

## pseudocode

```c

```
