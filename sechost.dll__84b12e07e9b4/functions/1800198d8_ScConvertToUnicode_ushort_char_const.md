# ScConvertToUnicode(ushort * *,char const *)

- ea: `0x1800198d8`
- end: `0x180019985`
- name: `?ScConvertToUnicode@@YAHPEAPEAGPEBD@Z`
- size: `173`
- prototype: `int(unsigned __int16 **, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000afb0`
- `0x180037f40`
- `0x180038180`
- `0x180038550`
- `0x18003a5a8`
- `0x18003a980`
- `0x18003a9e0`

## callees

- `0x1800198d8`

## import_xrefs

- `ntdll!RtlInitAnsiString` at `0x180019935`
- `ntdll!RtlInitAnsiString` at `0x180019935`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001995c`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001995c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001991f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001991f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019969`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019969`

## pseudocode

```c

```
