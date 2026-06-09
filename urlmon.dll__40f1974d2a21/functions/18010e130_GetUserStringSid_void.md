# GetUserStringSid(void)

- ea: `0x18010e130`
- end: `0x18010e26b`
- name: `?GetUserStringSid@@YA_NXZ`
- size: `315`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18010e274`

## callees

- `0x18010e130`

## import_xrefs

- `iertutil!__imp_?GetCurrentUserSid@@YAKPEAPEAX@Z` at `0x18010e150`
- `iertutil!__imp_?GetCurrentUserSid@@YAKPEAPEAX@Z` at `0x18010e150`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010e1ae`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010e22b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010e1ae`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18010e22b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010e1cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010e1ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010e1cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010e1ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010e1be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010e1be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e1e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e23b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e24e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e1e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e23b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010e24e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18010e170`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18010e170`

## pseudocode

```c

```
