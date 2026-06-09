# CSecurityUtils::ReProtectUnicodeString(_UNICODE_STRING *)

- ea: `0x180065aa0`
- end: `0x180065af0`
- name: `?ReProtectUnicodeString@CSecurityUtils@@SAJPEAU_UNICODE_STRING@@@Z`
- size: `80`
- prototype: `signed int __fastcall(struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180064150`
- `0x18006575c`
- `0x180065948`

## callees

- `0x180065aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065abd`
- `CRYPT32!CryptProtectMemory` at `0x180065ade`
- `CRYPT32!CryptProtectMemory` at `0x180065ade`
- `CRYPT32!CryptUnprotectMemory` at `0x180065ab3`
- `CRYPT32!CryptUnprotectMemory` at `0x180065ab3`

## pseudocode

```c

```
