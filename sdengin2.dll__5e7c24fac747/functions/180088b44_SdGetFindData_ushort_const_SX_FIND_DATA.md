# SdGetFindData(ushort const *,_SX_FIND_DATA *)

- ea: `0x180088b44`
- end: `0x180088e37`
- name: `?SdGetFindData@@YAJPEBGPEAU_SX_FIND_DATA@@@Z`
- size: `755`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, struct _SX_FIND_DATA *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180018614`
- `0x180033d20`

## callees

- `0x180014394`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088a04`
- `0x180088b44`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180088c93`
- `KERNEL32!CreateFileW` at `0x180088c93`
- `KERNEL32!CloseHandle` at `0x180088dec`
- `KERNEL32!CloseHandle` at `0x180088dec`
- `KERNEL32!FindFirstFileW` at `0x180088c1a`
- `KERNEL32!FindFirstFileW` at `0x180088c1a`
- `KERNEL32!FindClose` at `0x180088dff`
- `KERNEL32!FindClose` at `0x180088dff`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180088cce`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180088cce`

## pseudocode

```c

```
