# SdGetFindData(ushort const *,_SX_FIND_DATA *)

- ea: `0x18008c5e8`
- end: `0x18008c8fa`
- name: `?SdGetFindData@@YAJPEBGPEAU_SX_FIND_DATA@@@Z`
- size: `786`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _SX_FIND_DATA *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180019028`
- `0x1800350b0`

## callees

- `0x180014c30`
- `0x180072e08`
- `0x180072f14`
- `0x18008c4a8`
- `0x18008c5e8`
- `0x1800935fc`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18008c73d`
- `KERNEL32!CreateFileW` at `0x18008c73d`
- `KERNEL32!CloseHandle` at `0x18008c8a2`
- `KERNEL32!CloseHandle` at `0x18008c8a2`
- `KERNEL32!FindFirstFileW` at `0x18008c6be`
- `KERNEL32!FindFirstFileW` at `0x18008c6be`
- `KERNEL32!FindClose` at `0x18008c8bb`
- `KERNEL32!FindClose` at `0x18008c8bb`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18008c77e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18008c77e`

## pseudocode

```c

```
