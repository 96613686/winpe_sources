# CSxFileLogger::GetLogFileCount(ushort const *,ushort const *,ushort const *,ulong *,CBsString *)

- ea: `0x180095574`
- end: `0x180095879`
- name: `?GetLogFileCount@CSxFileLogger@@QEAAJPEBG00PEAKPEAVCBsString@@@Z`
- size: `773`
- prototype: `int(CSxFileLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct CBsString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180095314`

## callees

- `0x18006fe84`
- `0x18006ff8c`
- `0x180095574`
- `0x180099bdc`
- `0x180099d58`
- `0x18009a24c`
- `0x18009a378`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180095767`
- `KERNEL32!CompareFileTime` at `0x180095767`
- `KERNEL32!GetLastError` at `0x1800957ae`
- `KERNEL32!GetLastError` at `0x1800957ae`
- `KERNEL32!FindFirstFileW` at `0x180095702`
- `KERNEL32!FindFirstFileW` at `0x180095702`
- `KERNEL32!FindNextFileW` at `0x1800957a4`
- `KERNEL32!FindNextFileW` at `0x1800957a4`
- `KERNEL32!FindClose` at `0x18009581d`
- `KERNEL32!FindClose` at `0x18009581d`

## pseudocode

```c

```
