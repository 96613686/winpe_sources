# SampLookupInternetProviderNameByGUID(_GUID *,_UNICODE_STRING *)

- ea: `0x180024fc0`
- end: `0x180025095`
- name: `?SampLookupInternetProviderNameByGUID@@YAJPEAU_GUID@@PEAU_UNICODE_STRING@@@Z`
- size: `213`
- prototype: `int(struct _GUID *, struct _UNICODE_STRING *)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180053f9c`
- `0x180054644`
- `0x180060a0c`
- `0x180060cfc`
- `0x180061124`

## callees

- `0x180024fc0`
- `0x180027e24`

## import_xrefs

- `ntdll!RtlCreateUnicodeString` at `0x180025033`
- `ntdll!RtlCreateUnicodeString` at `0x180025033`
- `ntdll!RtlFreeHeap` at `0x180025058`
- `ntdll!RtlFreeHeap` at `0x180025058`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024ffb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024ffb`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180024fe9`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18002501b`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x180024fe9`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18002501b`

## pseudocode

```c

```
