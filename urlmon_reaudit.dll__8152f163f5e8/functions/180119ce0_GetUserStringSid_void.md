# GetUserStringSid(void)

- ea: `0x180119ce0`
- end: `0x180119e61`
- name: `?GetUserStringSid@@YA_NXZ`
- size: `385`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180119f00`

## callees

- `0x180119ce0`

## import_xrefs

- `iertutil!__imp_?GetCurrentUserSid@@YAKPEAPEAX@Z` at `0x180119d00`
- `iertutil!__imp_?GetCurrentUserSid@@YAKPEAPEAX@Z` at `0x180119d00`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180119d6a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180119e0b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180119d6a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180119e0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119dc2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180119dc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180119d80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180119d80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119db0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119e21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119e3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119db0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119dde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119e21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180119e3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180119d26`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180119d26`

## pseudocode

```c

```
