# CSxFileLogger::GetLogFileCount(ushort const *,ushort const *,ushort const *,ulong *,CBsString *)

- ea: `0x1800998f8`
- end: `0x180099c1c`
- name: `?GetLogFileCount@CSxFileLogger@@QEAAJPEBG00PEAKPEAVCBsString@@@Z`
- size: `804`
- prototype: `int(CSxFileLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct CBsString *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180099690`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x1800998f8`
- `0x18009e234`
- `0x18009e3c4`
- `0x18009e904`
- `0x18009ea34`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180099af1`
- `KERNEL32!CompareFileTime` at `0x180099af1`
- `KERNEL32!GetLastError` at `0x180099b44`
- `KERNEL32!GetLastError` at `0x180099b44`
- `KERNEL32!FindFirstFileW` at `0x180099a86`
- `KERNEL32!FindFirstFileW` at `0x180099a86`
- `KERNEL32!FindNextFileW` at `0x180099b34`
- `KERNEL32!FindNextFileW` at `0x180099b34`
- `KERNEL32!FindClose` at `0x180099bb9`
- `KERNEL32!FindClose` at `0x180099bb9`

## pseudocode

```c

```
