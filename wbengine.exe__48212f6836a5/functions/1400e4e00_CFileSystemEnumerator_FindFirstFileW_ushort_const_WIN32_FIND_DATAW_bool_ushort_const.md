# CFileSystemEnumerator::FindFirstFileW(ushort const *,_WIN32_FIND_DATAW *,bool,ushort const *)

- ea: `0x1400e4e00`
- end: `0x1400e503c`
- name: `?FindFirstFileW@CFileSystemEnumerator@@QEAAJPEBGPEAU_WIN32_FIND_DATAW@@_N0@Z`
- size: `572`
- prototype: `__int64 __fastcall(CFileSystemEnumerator *this, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, char, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400df3bc`
- `0x1400e22b8`

## callees

- `0x140006984`
- `0x140006ca8`
- `0x1400da030`
- `0x1400dba10`
- `0x1400e4a98`
- `0x1400e4e00`
- `0x140133760`
- `0x140134d20`

## import_xrefs

- `KERNEL32!FindFirstFileW` at `0x1400e4fa8`
- `KERNEL32!FindFirstFileW` at `0x1400e4fa8`
- `KERNEL32!RaiseException` at `0x1400e4f12`
- `KERNEL32!RaiseException` at `0x1400e4f33`
- `KERNEL32!RaiseException` at `0x1400e4f7a`
- `KERNEL32!RaiseException` at `0x1400e4f9b`
- `KERNEL32!RaiseException` at `0x1400e4f12`
- `KERNEL32!RaiseException` at `0x1400e4f33`
- `KERNEL32!RaiseException` at `0x1400e4f7a`
- `KERNEL32!RaiseException` at `0x1400e4f9b`
- `KERNEL32!GetLastError` at `0x1400e4fb8`
- `KERNEL32!GetLastError` at `0x1400e4fb8`

## string_xrefs

- `0x1400e4e41`: `0 != lpstrFilePath`
- `0x1400e4e2c`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e4ec2`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e4fe6`: `base\stor\blb\dsm\dsmutils\dll\dsmfsenumerator.cpp`
- `0x1400e4ebb`: `FindFirstFileCaseSensitive(lpstrFilePath, pFindData, lpstrFileSpec)`

## pseudocode

```c

```
