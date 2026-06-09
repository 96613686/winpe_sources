# CSdSafeguard::_CreateTargetDirectory(ushort const *,ushort const *,_FILETIME,ushort const *,CBsString *)

- ea: `0x1800370d8`
- end: `0x1800373c1`
- name: `?_CreateTargetDirectory@CSdSafeguard@@AEAAJPEBG0U_FILETIME@@0PEAVCBsString@@@Z`
- size: `745`
- prototype: `__int64 __fastcall(CSdSafeguard *this, const unsigned __int16 *, const unsigned __int16 *, FILETIME, unsigned __int16 *, struct CBsString *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180036470`
- `0x180036730`

## callees

- `0x180008240`
- `0x1800370d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180086220`
- `0x180086ef8`
- `0x18008f5d0`
- `0x1800996f4`
- `0x180099d58`
- `0x18009a3f0`
- `0x18009ae34`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!FileTimeToLocalFileTime` at `0x1800371e4`
- `KERNEL32!FileTimeToLocalFileTime` at `0x1800371e4`
- `KERNEL32!FileTimeToSystemTime` at `0x18003721a`
- `KERNEL32!FileTimeToSystemTime` at `0x18003721a`
- `KERNEL32!GetComputerNameW` at `0x1800371b1`
- `KERNEL32!GetComputerNameW` at `0x1800371b1`

## string_xrefs

- `0x180037122`: `CSdSafeguard::_CreateTargetDirectory`

## pseudocode

```c

```
