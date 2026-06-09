# CKoreanDecomposition::DecomposeKoreanForPrefixMatch(wchar_t const *,wchar_t * *)

- ea: `0x1800bd230`
- end: `0x1800bd382`
- name: `?DecomposeKoreanForPrefixMatch@CKoreanDecomposition@@QEAAJPEB_WPEAPEA_W@Z`
- size: `338`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, LPCWSTR pszText, wchar_t **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052b10`
- `0x1800bd1bc`

## callees

- `0x1800bd230`
- `0x1800bd388`
- `0x180189cce`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bd30d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bd30d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd368`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bd368`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800bd2eb`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x1800bd2eb`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x1800bd2ac`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x1800bd2ac`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x1800bd34b`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x1800bd34b`

## pseudocode

```c

```
