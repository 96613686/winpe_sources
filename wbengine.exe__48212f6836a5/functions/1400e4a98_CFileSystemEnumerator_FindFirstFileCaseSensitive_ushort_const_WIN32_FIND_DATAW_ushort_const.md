# CFileSystemEnumerator::FindFirstFileCaseSensitive(ushort const *,_WIN32_FIND_DATAW *,ushort const *)

- ea: `0x1400e4a98`
- end: `0x1400e4dfa`
- name: `?FindFirstFileCaseSensitive@CFileSystemEnumerator@@AEAAJPEBGPEAU_WIN32_FIND_DATAW@@0@Z`
- size: `866`
- prototype: `__int64 __fastcall(CFileSystemEnumerator *__hidden this, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x1400e4e00`

## callees

- `0x140006ca8`
- `0x1400db9b8`
- `0x1400dba10`
- `0x1400dbebc`
- `0x1400dbf98`
- `0x1400ddd94`
- `0x1400e4a98`
- `0x1400e5100`
- `0x140133760`
- `0x140134d20`

## import_xrefs

- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e4d31`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e4d31`
- `KERNEL32!CreateFileW` at `0x1400e4cb9`
- `KERNEL32!CreateFileW` at `0x1400e4cb9`
- `KERNEL32!RaiseException` at `0x1400e4b5a`
- `KERNEL32!RaiseException` at `0x1400e4b82`
- `KERNEL32!RaiseException` at `0x1400e4bb3`
- `KERNEL32!RaiseException` at `0x1400e4c67`
- `KERNEL32!RaiseException` at `0x1400e4c89`
- `KERNEL32!RaiseException` at `0x1400e4b5a`
- `KERNEL32!RaiseException` at `0x1400e4b82`
- `KERNEL32!RaiseException` at `0x1400e4bb3`
- `KERNEL32!RaiseException` at `0x1400e4c67`
- `KERNEL32!RaiseException` at `0x1400e4c89`
- `KERNEL32!GetLastError` at `0x1400e4ccf`
- `KERNEL32!GetLastError` at `0x1400e4d3b`
- `KERNEL32!GetLastError` at `0x1400e4ccf`
- `KERNEL32!GetLastError` at `0x1400e4d3b`

## string_xrefs

- `0x1400e4ad7`: `0 != lpstrFilePath`
- `0x1400e4abf`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e4bff`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e4cfa`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e4cf3`: `CreateFile failed for %s`

## pseudocode

```c

```
