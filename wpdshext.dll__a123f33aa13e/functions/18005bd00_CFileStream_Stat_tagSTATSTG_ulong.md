# CFileStream::Stat(tagSTATSTG *,ulong)

- ea: `0x18005bd00`
- end: `0x18005be72`
- name: `?Stat@CFileStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `370`
- prototype: `int(CFileStream *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18005bd00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005bd73`
- `KERNEL32!GetLastError` at `0x18005bd73`
- `KERNEL32!GetFileInformationByHandle` at `0x18005bd69`
- `KERNEL32!GetFileInformationByHandle` at `0x18005bd69`
- `SHLWAPI!SHStrDupW` at `0x18005bdef`
- `SHLWAPI!SHStrDupW` at `0x18005bdef`
- `SHLWAPI!PathFindFileNameW` at `0x18005bde3`
- `SHLWAPI!PathFindFileNameW` at `0x18005bde3`

## pseudocode

```c

```
