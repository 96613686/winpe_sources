# CSecurityUtils::ReProtectUnicodeString(_UNICODE_STRING *)

- ea: `0x180068c90`
- end: `0x180068cf3`
- name: `?ReProtectUnicodeString@CSecurityUtils@@SAJPEAU_UNICODE_STRING@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180067310`
- `0x18006894c`
- `0x180068b38`

## callees

- `0x180068c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068cb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068cb3`
- `CRYPT32!CryptProtectMemory` at `0x180068cda`
- `CRYPT32!CryptProtectMemory` at `0x180068cda`
- `CRYPT32!CryptUnprotectMemory` at `0x180068ca3`
- `CRYPT32!CryptUnprotectMemory` at `0x180068ca3`

## pseudocode

```c

```
