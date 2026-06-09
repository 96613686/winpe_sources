# LsaLookupTranslateSids

- ea: `0x18000d340`
- end: `0x18000d4d7`
- name: `LsaLookupTranslateSids`
- size: `407`
- prototype: `NTSTATUS __stdcall(LSA_LOOKUP_HANDLE PolicyHandle, ULONG Count, PSID *Sids, PLSA_REFERENCED_DOMAIN_LIST *ReferencedDomains, PLSA_TRANSLATED_NAME *Names)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000d340`
- `0x18000dcc0`
- `0x18004f902`
- `0x18004f91a`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d3c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d3c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d3eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d4c9`

## pseudocode

```c

```
