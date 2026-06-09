# CreateLDAPURLFromEntryID(ulong,ENTRYID *,ushort * *,int *)

- ea: `0x180025998`
- end: `0x180025be2`
- name: `?CreateLDAPURLFromEntryID@@YAXKPEAUENTRYID@@PEAPEAGPEAH@Z`
- size: `586`
- prototype: `void __fastcall(unsigned int, struct ENTRYID *, unsigned __int16 **, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180008344`
- `0x18004f8c4`

## callees

- `0x1800045e4`
- `0x1800189ec`
- `0x180025998`
- `0x180025f98`
- `0x1800270d4`
- `0x1800277e4`
- `0x180091eaa`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180025ac7`
- `KERNEL32!lstrcmpiW` at `0x180025ac7`
- `KERNEL32!LocalAlloc` at `0x180025a91`
- `KERNEL32!LocalAlloc` at `0x180025b23`
- `KERNEL32!LocalAlloc` at `0x180025b42`
- `KERNEL32!LocalAlloc` at `0x180025a91`
- `KERNEL32!LocalAlloc` at `0x180025b23`
- `KERNEL32!LocalAlloc` at `0x180025b42`
- `KERNEL32!LocalFree` at `0x180025bc8`
- `KERNEL32!LocalFree` at `0x180025bc8`
- `WININET!InternetCanonicalizeUrlW` at `0x180025b78`
- `WININET!InternetCanonicalizeUrlW` at `0x180025b78`

## pseudocode

```c

```
