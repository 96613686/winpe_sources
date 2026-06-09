# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x1800588bc`
- end: `0x18005890d`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180054d68`

## callees

- `0x1800588bc`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800588de`
- `KERNEL32!GetModuleHandleW` at `0x1800588de`
- `KERNEL32!GetProcAddress` at `0x1800588f6`
- `KERNEL32!GetProcAddress` at `0x1800588f6`

## string_xrefs

- `0x1800588d5`: `kernelbase.dll`

## pseudocode

```c

```
