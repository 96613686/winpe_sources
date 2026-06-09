# FusionpvDbgPrintExNoNTDLL(ulong,ulong,char *,char *)

- ea: `0x18006810c`
- end: `0x1800681c5`
- name: `?FusionpvDbgPrintExNoNTDLL@@YAKKKPEAD0@Z`
- size: `185`
- prototype: `unsigned int(unsigned int, unsigned int, char *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180068088`

## callees

- `0x18006810c`
- `0x18006a110`

## import_xrefs

- `ntdll!vsprintf_s` at `0x180068194`
- `ntdll!vsprintf_s` at `0x180068194`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800681a7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800681a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068176`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681b5`

## pseudocode

```c

```
