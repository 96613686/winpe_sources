# GetFileSizeAndTime(wchar_t const *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x18007b324`
- end: `0x18007b40e`
- name: `?GetFileSizeAndTime@@YAJPEB_WPEA_K1@Z`
- size: `234`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180008698`
- `0x180075690`

## callees

- `0x180007fd8`
- `0x18001c368`
- `0x18007b324`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b391`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18007b3b0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18007b3b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b374`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b374`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18007b3cd`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18007b3cd`

## pseudocode

```c

```
