# DloadGetSRWLockFunctionPointers(void)

- ea: `0x100451184`
- end: `0x10045121f`
- name: `?DloadGetSRWLockFunctionPointers@@YAEXZ`
- size: `155`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1004510d4`
- `0x100451400`

## callees

- `0x100451184`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1004511c8`
- `KERNEL32!GetProcAddress` at `0x1004511e4`
- `KERNEL32!GetProcAddress` at `0x1004511c8`
- `KERNEL32!GetProcAddress` at `0x1004511e4`
- `KERNEL32!GetModuleHandleW` at `0x1004511ab`
- `KERNEL32!GetModuleHandleW` at `0x1004511ab`

## string_xrefs

- `0x1004511a4`: `KERNEL32.DLL`

## pseudocode

```c

```
