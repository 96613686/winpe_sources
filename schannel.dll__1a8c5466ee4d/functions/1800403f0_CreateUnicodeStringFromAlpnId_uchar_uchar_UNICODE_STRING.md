# CreateUnicodeStringFromAlpnId(uchar *,uchar,_UNICODE_STRING *)

- ea: `0x1800403f0`
- end: `0x180040449`
- name: `?CreateUnicodeStringFromAlpnId@@YAKPEAEEPEAU_UNICODE_STRING@@@Z`
- size: `89`
- prototype: `ULONG __fastcall(CHAR *, unsigned __int8, struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007168`
- `0x180019ad0`
- `0x1800527b8`

## callees

- `0x1800403f0`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004042f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18004042f`
- `ntdll!RtlNtStatusToDosError` at `0x180040437`
- `ntdll!RtlNtStatusToDosError` at `0x180040437`

## pseudocode

```c

```
