# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x14004b6c8`
- end: `0x14004b719`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14004ac88`

## callees

- `0x14004b6c8`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14004b702`
- `KERNEL32!GetProcAddress` at `0x14004b702`
- `KERNEL32!GetModuleHandleW` at `0x14004b6ea`
- `KERNEL32!GetModuleHandleW` at `0x14004b6ea`

## string_xrefs

- `0x14004b6e1`: `kernelbase.dll`

## pseudocode

```c

```
