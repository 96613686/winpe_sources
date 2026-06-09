# WerpReadPebFromProcess(void *,void *,ulong,ulong)

- ea: `0x18004f4b4`
- end: `0x18004f627`
- name: `?WerpReadPebFromProcess@@YAJPEAX0KK@Z`
- size: `371`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *lpBuffer, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004f630`
- `0x18007c77c`

## callees

- `0x18004f4b4`
- `0x1800540ec`
- `0x1800552d1`
- `0x180055319`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18004f502`
- `ntdll!NtQueryInformationProcess` at `0x18004f502`
- `ntdll!DbgPrintEx` at `0x18004f530`
- `ntdll!DbgPrintEx` at `0x18004f56e`
- `ntdll!DbgPrintEx` at `0x18004f5c4`
- `ntdll!DbgPrintEx` at `0x18004f605`
- `ntdll!DbgPrintEx` at `0x18004f530`
- `ntdll!DbgPrintEx` at `0x18004f56e`
- `ntdll!DbgPrintEx` at `0x18004f5c4`
- `ntdll!DbgPrintEx` at `0x18004f605`

## string_xrefs

- `0x18004f5b6`: `WER/CrashAPI/%u:%u: ERROR ReadProcessMemory failed while trying to read PebBaseAddress\n`

## pseudocode

```c

```
