# RegQueryHelpers::GetValue(ushort * *,HKEY__ *,ushort const *,ushort const *,ulong)

- ea: `0x180051efc`
- end: `0x18005208d`
- name: `?GetValue@RegQueryHelpers@@SAJPEAPEAGPEAUHKEY__@@PEBG2K@Z`
- size: `401`
- prototype: `__int64 __fastcall(unsigned __int16 **, HKEY, const unsigned __int16 *, const unsigned __int16 *, DWORD Type)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005138c`

## callees

- `0x18000a230`
- `0x18000e5ac`
- `0x180010130`
- `0x18001a718`
- `0x180028714`
- `0x180029c94`
- `0x180051efc`
- `0x180052094`
- `0x1800521a8`
- `0x180052280`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180051f7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180051f7a`

## string_xrefs

- `0x180051fc7`: `onecore\base\flighting\common\regvalet\regqueryhelpers.cpp`

## pseudocode

```c

```
