# WerpAddGatherBlockToReport(void *,ulong,WER_GATHER *,long (*)(void *,wchar_t const *,_WER_FILE_TYPE,ulong,wchar_t const *,wchar_t const *),long (*)(void *,ulong,void *,ulong,ulong),long (*)(void *,ulong,void *,ulong,ulong),ulong)

- ea: `0x1800a85c8`
- end: `0x1800a8769`
- name: `?WerpAddGatherBlockToReport@@YAJPEAXKPEAUWER_GATHER@@P6AJ0PEB_WW4_WER_FILE_TYPE@@K22@ZP6AJ0K0KK@Z5K@Z`
- size: `417`
- prototype: `__int64 __fastcall(void *, unsigned int, struct WER_GATHER *, int (*)(void *, const wchar_t *, enum _WER_FILE_TYPE, unsigned int, const wchar_t *, const wchar_t *), int (*)(void *, unsigned int, void *, unsigned int, unsigned int), int (*)(void *, unsigned int, void *, unsigned int, unsigned int), unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18006a100`

## callees

- `0x180025600`
- `0x1800540ec`
- `0x180069b54`
- `0x18006a040`
- `0x1800a85c8`

## import_xrefs

- `ntdll!DbgPrintEx` at `0x1800a86ca`
- `ntdll!DbgPrintEx` at `0x1800a8706`
- `ntdll!DbgPrintEx` at `0x1800a874c`
- `ntdll!DbgPrintEx` at `0x1800a86ca`
- `ntdll!DbgPrintEx` at `0x1800a8706`
- `ntdll!DbgPrintEx` at `0x1800a874c`

## string_xrefs

- `0x1800a86bc`: `WER/CrashAPI/%u:%u: ERROR StringCchCopyN failed\n`

## pseudocode

```c

```
