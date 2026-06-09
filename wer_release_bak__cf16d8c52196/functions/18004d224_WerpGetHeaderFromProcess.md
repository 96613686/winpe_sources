# WerpGetHeaderFromProcess

- ea: `0x18004d224`
- end: `0x18004d470`
- name: `WerpGetHeaderFromProcess`
- size: `588`
- prototype: `signed int __fastcall(HANDLE hProcess, _WORD *lpBuffer)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180040c34`
- `0x1800a3ac4`
- `0x1800a3b98`
- `0x1800a3c80`
- `0x1800a3dd8`
- `0x1800a3f64`

## callees

- `0x18004d0c8`
- `0x18004d224`
- `0x18004e974`
- `0x180051b7c`
- `0x180052cbe`
- `0x180052d61`
- `0x180052da9`
- `0x1800a3d68`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18004d327`
- `ntdll!DbgPrintEx` at `0x18004d366`
- `ntdll!DbgPrintEx` at `0x18004d3e1`
- `ntdll!DbgPrintEx` at `0x18004d424`
- `ntdll!DbgPrintEx` at `0x18004d45a`
- `ntdll!DbgPrintEx` at `0x18004d327`
- `ntdll!DbgPrintEx` at `0x18004d366`
- `ntdll!DbgPrintEx` at `0x18004d3e1`
- `ntdll!DbgPrintEx` at `0x18004d424`
- `ntdll!DbgPrintEx` at `0x18004d45a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004d264`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004d289`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004d2a3`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004d264`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004d289`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004d2a3`

## string_xrefs

- `0x18004d3d3`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`
- `0x18004d2dc`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18004d319`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18004d358`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`

## pseudocode

```c

```
