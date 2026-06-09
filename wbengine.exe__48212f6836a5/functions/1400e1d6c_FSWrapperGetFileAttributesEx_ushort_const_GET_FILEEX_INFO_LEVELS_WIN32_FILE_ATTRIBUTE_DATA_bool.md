# FSWrapperGetFileAttributesEx(ushort const *,_GET_FILEEX_INFO_LEVELS,_WIN32_FILE_ATTRIBUTE_DATA *,bool)

- ea: `0x1400e1d6c`
- end: `0x1400e1fd2`
- name: `?FSWrapperGetFileAttributesEx@@YAJPEBGW4_GET_FILEEX_INFO_LEVELS@@PEAU_WIN32_FILE_ATTRIBUTE_DATA@@_N@Z`
- size: `614`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, enum _GET_FILEEX_INFO_LEVELS, struct _WIN32_FILE_ATTRIBUTE_DATA *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1400e22b8`

## callees

- `0x140006ca8`
- `0x1400e1d6c`
- `0x140133760`
- `0x140134d20`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x1400e1efa`
- `KERNEL32!GetFileSize` at `0x1400e1efa`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e1e8c`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e1e8c`
- `KERNEL32!CreateFileW` at `0x1400e1e12`
- `KERNEL32!CreateFileW` at `0x1400e1e12`
- `KERNEL32!CloseHandle` at `0x1400e1f81`
- `KERNEL32!CloseHandle` at `0x1400e1f81`
- `KERNEL32!RaiseException` at `0x1400e1fa7`
- `KERNEL32!RaiseException` at `0x1400e1fa7`
- `KERNEL32!GetLastError` at `0x1400e1e27`
- `KERNEL32!GetLastError` at `0x1400e1e96`
- `KERNEL32!GetLastError` at `0x1400e1f08`
- `KERNEL32!GetLastError` at `0x1400e1f8b`
- `KERNEL32!GetLastError` at `0x1400e1e27`
- `KERNEL32!GetLastError` at `0x1400e1e96`
- `KERNEL32!GetLastError` at `0x1400e1f08`
- `KERNEL32!GetLastError` at `0x1400e1f8b`

## string_xrefs

- `0x1400e1dad`: `base\stor\blb\dsm\dsmutils\dll\fsutils.cpp`
- `0x1400e1dca`: `base\stor\blb\dsm\dsmutils\dll\fsutils.cpp`
- `0x1400e1e52`: `base\stor\blb\dsm\dsmutils\dll\fsutils.cpp`
- `0x1400e1ebd`: `base\stor\blb\dsm\dsmutils\dll\fsutils.cpp`
- `0x1400e1f33`: `base\stor\blb\dsm\dsmutils\dll\fsutils.cpp`
- `0x1400e1da1`: `0 != lpstrFilePath`
- `0x1400e1e4b`: `CreateFile unsuccessful for %ws`

## pseudocode

```c

```
