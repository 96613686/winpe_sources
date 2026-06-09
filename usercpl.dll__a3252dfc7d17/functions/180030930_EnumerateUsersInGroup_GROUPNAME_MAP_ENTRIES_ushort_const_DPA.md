# EnumerateUsersInGroup(GROUPNAME_MAP_ENTRIES,ushort const *,_DPA *)

- ea: `0x180030930`
- end: `0x180030b9f`
- name: `?EnumerateUsersInGroup@@YAJW4GROUPNAME_MAP_ENTRIES@@PEBGPEAU_DPA@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180032dd4`

## callees

- `0x1800252d0`
- `0x18002c814`
- `0x180030930`
- `0x1800332b0`
- `0x180063b30`
- `0x180078010`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180030ab4`
- `SHLWAPI!StrChrW` at `0x180030ab4`
- `OLEAUT32!__imp_VariantClear` at `0x180030a64`
- `OLEAUT32!__imp_VariantClear` at `0x180030a64`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030a57`
- `samcli!NetLocalGroupGetMembers` at `0x1800309cb`
- `samcli!NetLocalGroupGetMembers` at `0x1800309cb`
- `netutils!NetApiBufferFree` at `0x180030b73`
- `netutils!NetApiBufferFree` at `0x180030b73`
- `KERNEL32!lstrcmpiW` at `0x180030ada`
- `KERNEL32!lstrcmpiW` at `0x180030ada`

## pseudocode

```c

```
