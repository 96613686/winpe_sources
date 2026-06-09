# SampRegConstructAttributeValue(_SAMP_OBJECT *,ulong,_ATTRSIMPLE *)

- ea: `0x18001b230`
- end: `0x18001b4d0`
- name: `?SampRegConstructAttributeValue@@YAJPEAU_SAMP_OBJECT@@KPEAU_ATTRSIMPLE@@@Z`
- size: `672`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, unsigned int, struct _ATTRSIMPLE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bae0`

## callees

- `0x18001b230`
- `0x18001ba70`
- `0x18001bae0`
- `0x180021eec`
- `0x180027e24`
- `0x18002cd80`
- `0x1800bb77c`

## import_xrefs

- `ntdll!RtlCreateUnicodeString` at `0x18001b375`
- `ntdll!RtlCreateUnicodeString` at `0x18001b375`
- `ntdll!RtlFreeHeap` at `0x18001b39a`
- `ntdll!RtlFreeHeap` at `0x18001b39a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b33c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b3d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b33c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001b3d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b42a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b42a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b437`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18001b32b`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18001b35c`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18001b32b`
- `api-ms-win-security-lsalookup-l1-1-1!GetIdentityProviderInfoByGUID` at `0x18001b35c`

## pseudocode

```c

```
