# wil_details_GetKernelBaseProcAddress(char const *)

- ea: `0x18003aae4`
- end: `0x18003ab35`
- name: `?wil_details_GetKernelBaseProcAddress@@YAP6A_JXZPEBD@Z`
- size: `81`
- prototype: `__int64 (*__fastcall(LPCSTR lpProcName))(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18003a568`
- `0x18003b120`

## callees

- `0x18003aae4`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18003ab06`
- `KERNEL32!GetModuleHandleW` at `0x18003ab06`
- `KERNEL32!GetProcAddress` at `0x18003ab1e`
- `KERNEL32!GetProcAddress` at `0x18003ab1e`

## string_xrefs

- `0x18003aafd`: `kernelbase.dll`

## pseudocode

```c

```
