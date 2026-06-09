# WerpReadPeb32FromProcess

- ea: `0x180050d5c`
- end: `0x180050ed1`
- name: `WerpReadPeb32FromProcess`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004f630`

## callees

- `0x180050d5c`
- `0x1800540ec`
- `0x1800552d1`
- `0x180055319`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x180050da2`
- `ntdll!NtQueryInformationProcess` at `0x180050da2`
- `ntdll!DbgPrintEx` at `0x180050dd6`
- `ntdll!DbgPrintEx` at `0x180050e15`
- `ntdll!DbgPrintEx` at `0x180050e6e`
- `ntdll!DbgPrintEx` at `0x180050eaf`
- `ntdll!DbgPrintEx` at `0x180050dd6`
- `ntdll!DbgPrintEx` at `0x180050e15`
- `ntdll!DbgPrintEx` at `0x180050e6e`
- `ntdll!DbgPrintEx` at `0x180050eaf`

## string_xrefs

- `0x180050e60`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read Peb32BaseAddress\n`

## pseudocode

```c

```
