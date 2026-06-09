# CopyClientString(ushort *,ulong,uchar,_UNICODE_STRING *)

- ea: `0x18005c3e0`
- end: `0x18005c522`
- name: `?CopyClientString@@YAJPEAGKEPEAU_UNICODE_STRING@@@Z`
- size: `322`
- prototype: `int(unsigned __int16 *, unsigned int, unsigned __int8, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18005ca90`

## callees

- `0x18005c3e0`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c50b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c50b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c422`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c479`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c422`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18005c479`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005c4e1`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18005c4e1`

## pseudocode

```c

```
