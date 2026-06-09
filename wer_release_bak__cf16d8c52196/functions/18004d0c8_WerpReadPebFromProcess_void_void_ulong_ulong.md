# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x18004d0c8`
- end: `0x18004d21c`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `340`
- prototype: `signed int __fastcall(HANDLE hProcess, void *lpBuffer, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004d224`
- `0x180079198`

## callees

- `0x18004d0c8`
- `0x180051b7c`
- `0x180052d61`
- `0x180052da9`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18004d116`
- `ntdll!NtQueryInformationProcess` at `0x18004d116`
- `ntdll!DbgPrintEx` at `0x18004d13e`
- `ntdll!DbgPrintEx` at `0x18004d176`
- `ntdll!DbgPrintEx` at `0x18004d1c6`
- `ntdll!DbgPrintEx` at `0x18004d201`
- `ntdll!DbgPrintEx` at `0x18004d13e`
- `ntdll!DbgPrintEx` at `0x18004d176`
- `ntdll!DbgPrintEx` at `0x18004d1c6`
- `ntdll!DbgPrintEx` at `0x18004d201`

## string_xrefs

- `0x18004d1b8`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

## pseudocode

```c

```
