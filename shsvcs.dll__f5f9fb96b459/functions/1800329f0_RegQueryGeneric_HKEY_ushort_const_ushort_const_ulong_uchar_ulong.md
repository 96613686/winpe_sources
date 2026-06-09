# _RegQueryGeneric(HKEY__ *,ushort const *,ushort const *,ulong *,uchar *,ulong *)

- ea: `0x1800329f0`
- end: `0x180032a72`
- name: `?_RegQueryGeneric@@YAJPEAUHKEY__@@PEBG1PEAKPEAE2@Z`
- size: `130`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, unsigned __int8 *lpData, unsigned int *lpcbData)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004de0`
- `0x180006578`
- `0x1800157b0`
- `0x1800189dc`
- `0x18002433c`
- `0x180032a78`

## callees

- `0x180016580`
- `0x1800329cc`
- `0x1800329f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032a44`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180032a44`

## pseudocode

```c

```
