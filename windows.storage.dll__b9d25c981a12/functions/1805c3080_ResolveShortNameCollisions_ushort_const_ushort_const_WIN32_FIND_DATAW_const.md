# ResolveShortNameCollisions(ushort const *,ushort const *,_WIN32_FIND_DATAW const *)

- ea: `0x1805c3080`
- end: `0x1805c32f3`
- name: `?ResolveShortNameCollisions@@YAHPEBG0PEBU_WIN32_FIND_DATAW@@@Z`
- size: `627`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, LPCWSTR lpString1, const struct _WIN32_FIND_DATAW *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x18036de3c`

## callees

- `0x1800c5204`
- `0x1801720d0`
- `0x1801720f0`
- `0x1803b1f60`
- `0x1805c2178`
- `0x1805c3080`
- `0x1805e5908`
- `0x1805e599c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1805c32a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1805c32a6`
- `ntdll!RtlGetLastNtStatus` at `0x1805c322b`
- `ntdll!RtlGetLastNtStatus` at `0x1805c328d`
- `ntdll!RtlGetLastNtStatus` at `0x1805c322b`
- `ntdll!RtlGetLastNtStatus` at `0x1805c328d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1805c30c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1805c30dd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1805c30c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1805c30dd`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1805c326c`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1805c326c`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1805c3148`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x1805c3148`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1805c324e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1805c324e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1805c3217`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1805c327f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1805c3217`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1805c327f`
- `SHCORE!__imp_IsNotifySuspended` at `0x1805c32b4`
- `SHCORE!__imp_IsNotifySuspended` at `0x1805c32b4`

## pseudocode

```c

```
