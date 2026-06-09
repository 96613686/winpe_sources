# WerpGetHeaderFromProcess

- ea: `0x18004f630`
- end: `0x18004f8b1`
- name: `WerpGetHeaderFromProcess`
- size: `641`
- prototype: `__int64 __fastcall(HANDLE hProcess, LPVOID lpBuffer)`
- caller_count: `6`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180042734`
- `0x1800a8770`
- `0x1800a8848`
- `0x1800a8934`
- `0x1800a8a94`
- `0x1800a8c2c`

## callees

- `0x18004f4b4`
- `0x18004f630`
- `0x180050d5c`
- `0x1800540ec`
- `0x18005522e`
- `0x1800552d1`
- `0x180055319`
- `0x1800a8a20`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x18004f745`
- `ntdll!DbgPrintEx` at `0x18004f78a`
- `ntdll!DbgPrintEx` at `0x18004f80b`
- `ntdll!DbgPrintEx` at `0x18004f858`
- `ntdll!DbgPrintEx` at `0x18004f894`
- `ntdll!DbgPrintEx` at `0x18004f745`
- `ntdll!DbgPrintEx` at `0x18004f78a`
- `ntdll!DbgPrintEx` at `0x18004f80b`
- `ntdll!DbgPrintEx` at `0x18004f858`
- `ntdll!DbgPrintEx` at `0x18004f894`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004f670`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004f69b`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004f6bb`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004f670`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004f69b`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x18004f6bb`

## string_xrefs

- `0x18004f7fd`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read WerRegistrationData\n`
- `0x18004f77c`: `WER/CrashAPI/%u:%u: ERROR WerpNtWow64ReadVirtualMemory64 failed while trying to read PebBaseAddress\n`
- `0x18004f6fa`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`
- `0x18004f737`: `WER/CrashAPI/%u:%u: ERROR Failed to read the peb from the process\n`

## pseudocode

```c

```
