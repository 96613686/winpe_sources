# CFileSystemEnumerator::GetNextFile(_WIN32_FIND_DATAW *)

- ea: `0x1400e51fc`
- end: `0x1400e56f9`
- name: `?GetNextFile@CFileSystemEnumerator@@AEAAJPEAU_WIN32_FIND_DATAW@@@Z`
- size: `1277`
- prototype: `__int64 __fastcall(CFileSystemEnumerator *__hidden this, struct _WIN32_FIND_DATAW *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting`

## callers

- `0x1400e5044`

## callees

- `0x140006000`
- `0x140006984`
- `0x140006ca8`
- `0x140006dd4`
- `0x1400db940`
- `0x1400db9b8`
- `0x1400e3dcc`
- `0x1400e51fc`
- `0x140133760`
- `0x140134cf6`
- `0x140134d20`

## import_xrefs

- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e52f9`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e5597`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e52f9`
- `KERNEL32!GetFileInformationByHandleEx` at `0x1400e5597`
- `KERNEL32!CreateFileW` at `0x1400e5507`
- `KERNEL32!CreateFileW` at `0x1400e5507`
- `KERNEL32!CloseHandle` at `0x1400e56a2`
- `KERNEL32!CloseHandle` at `0x1400e56a2`
- `KERNEL32!RaiseException` at `0x1400e54b0`
- `KERNEL32!RaiseException` at `0x1400e54df`
- `KERNEL32!RaiseException` at `0x1400e56ca`
- `KERNEL32!RaiseException` at `0x1400e54b0`
- `KERNEL32!RaiseException` at `0x1400e54df`
- `KERNEL32!RaiseException` at `0x1400e56ca`
- `KERNEL32!GetLastError` at `0x1400e5307`
- `KERNEL32!GetLastError` at `0x1400e5516`
- `KERNEL32!GetLastError` at `0x1400e55a1`
- `KERNEL32!GetLastError` at `0x1400e56ac`
- `KERNEL32!GetLastError` at `0x1400e5307`
- `KERNEL32!GetLastError` at `0x1400e5516`
- `KERNEL32!GetLastError` at `0x1400e55a1`
- `KERNEL32!GetLastError` at `0x1400e56ac`
- `msvcrt!wcsncpy_s` at `0x1400e5675`
- `msvcrt!wcsncpy_s` at `0x1400e5693`
- `msvcrt!wcsncpy_s` at `0x1400e5675`
- `msvcrt!wcsncpy_s` at `0x1400e5693`

## string_xrefs

- `0x1400e5229`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e533b`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e5546`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e55cd`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e553f`: `CreateFile failed for %s`

## pseudocode

```c

```
