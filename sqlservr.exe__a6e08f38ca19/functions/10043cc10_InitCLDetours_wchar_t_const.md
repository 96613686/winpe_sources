# InitCLDetours(wchar_t const *)

- ea: `0x10043cc10`
- end: `0x10043ce51`
- name: `?InitCLDetours@@YAJPEB_W@Z`
- size: `577`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x10043c440`
- `0x10043cc10`
- `0x10043ddb0`
- `0x10043de70`
- `0x10043dfb0`
- `0x10043e2c0`
- `0x10043e700`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x10043cc24`
- `KERNEL32!GetModuleHandleW` at `0x10043cc24`
- `KERNEL32!GetDynamicTimeZoneInformation` at `0x10043cc9a`
- `KERNEL32!GetTimeZoneInformation` at `0x10043ccb6`
- `KERNEL32!FileTimeToLocalFileTime` at `0x10043ccd8`
- `KERNEL32!GetLocalTime` at `0x10043ccca`
- `sqlmin!GetXdbServerGlobals` at `0x10043cc58`
- `sqlmin!GetXdbServerGlobals` at `0x10043cc65`
- `sqlmin!GetXdbServerGlobals` at `0x10043cc83`
- `sqlmin!GetXdbServerGlobals` at `0x10043cd71`
- `sqlmin!GetXdbServerGlobals` at `0x10043cdd7`
- `sqlmin!GetXdbServerGlobals` at `0x10043cc58`
- `sqlmin!GetXdbServerGlobals` at `0x10043cc65`
- `sqlmin!GetXdbServerGlobals` at `0x10043cc83`
- `sqlmin!GetXdbServerGlobals` at `0x10043cd71`
- `sqlmin!GetXdbServerGlobals` at `0x10043cdd7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043cc4d`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10043cc4d`

## string_xrefs

- `0x10043cc1d`: `KERNEL32.DLL`

## pseudocode

```c

```
