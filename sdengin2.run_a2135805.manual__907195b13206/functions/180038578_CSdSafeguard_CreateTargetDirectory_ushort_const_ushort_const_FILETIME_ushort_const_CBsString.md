# CSdSafeguard::_CreateTargetDirectory(ushort const *,ushort const *,_FILETIME,ushort const *,CBsString *)

- ea: `0x180038578`
- end: `0x180038874`
- name: `?_CreateTargetDirectory@CSdSafeguard@@AEAAJPEBG0U_FILETIME@@0PEAVCBsString@@@Z`
- size: `764`
- prototype: `int(CSdSafeguard *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME, const unsigned __int16 *, struct CBsString *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800378e0`
- `0x180037bc0`

## callees

- `0x1800083e4`
- `0x180038578`
- `0x180072e08`
- `0x180072f14`
- `0x180089b20`
- `0x18008a874`
- `0x1800935fc`
- `0x18009dd0c`
- `0x18009e3c4`
- `0x18009eab0`
- `0x18009f560`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!FileTimeToLocalFileTime` at `0x18003868a`
- `KERNEL32!FileTimeToLocalFileTime` at `0x18003868a`
- `KERNEL32!FileTimeToSystemTime` at `0x1800386c6`
- `KERNEL32!FileTimeToSystemTime` at `0x1800386c6`
- `KERNEL32!GetComputerNameW` at `0x180038651`
- `KERNEL32!GetComputerNameW` at `0x180038651`

## string_xrefs

- `0x1800385c2`: `CSdSafeguard::_CreateTargetDirectory`

## pseudocode

```c

```
