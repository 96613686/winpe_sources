# CKoreanDecomposition::DecomposeKoreanForPrefixMatch(ushort const *,ushort * *)

- ea: `0x180055618`
- end: `0x18005576a`
- name: `?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEBGPEAPEAG@Z`
- size: `338`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, LPCWSTR pszText, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052b10`
- `0x180053ac4`

## callees

- `0x180055618`
- `0x180055770`
- `0x180189cce`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800556f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800556f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055750`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055750`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800556d3`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800556d3`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180055694`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180055694`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180055733`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x180055733`

## pseudocode

```c

```
