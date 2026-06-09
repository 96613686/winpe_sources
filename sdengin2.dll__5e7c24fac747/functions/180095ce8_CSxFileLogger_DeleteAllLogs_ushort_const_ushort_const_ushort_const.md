# CSxFileLogger::_DeleteAllLogs(ushort const *,ushort const *,ushort const *)

- ea: `0x180095ce8`
- end: `0x18009616c`
- name: `?_DeleteAllLogs@CSxFileLogger@@AEAAJPEBG00@Z`
- size: `1156`
- prototype: `void __fastcall __noreturn(CSxFileLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x180095314`

## callees

- `0x180003a48`
- `0x18000b3a4`
- `0x18000b56c`
- `0x18000d984`
- `0x18000fca4`
- `0x180012914`
- `0x180012958`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180095238`
- `0x180095ce8`
- `0x180096174`
- `0x180096210`
- `0x180099bdc`
- `0x180099d58`
- `0x18009a24c`
- `0x18009a378`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180096091`
- `KERNEL32!DeleteFileW` at `0x180096091`
- `KERNEL32!GetLastError` at `0x180095fd4`
- `KERNEL32!GetLastError` at `0x180095fd4`
- `KERNEL32!FindFirstFileW` at `0x180095e45`
- `KERNEL32!FindFirstFileW` at `0x180095e45`
- `KERNEL32!FindNextFileW` at `0x180095fc6`
- `KERNEL32!FindNextFileW` at `0x180095fc6`
- `KERNEL32!FindClose` at `0x1800960f6`
- `KERNEL32!FindClose` at `0x1800960f6`

## string_xrefs

- `0x180095d21`: `CSxFileLogger::_DeleteAllLogs`

## pseudocode

```c

```
