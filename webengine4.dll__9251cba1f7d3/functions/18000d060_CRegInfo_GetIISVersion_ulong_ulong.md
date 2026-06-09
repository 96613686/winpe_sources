# CRegInfo::GetIISVersion(ulong *,ulong *)

- ea: `0x18000d060`
- end: `0x18000d155`
- name: `?GetIISVersion@CRegInfo@@SAJPEAK0@Z`
- size: `245`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180040408`

## callees

- `0x18000d060`
- `0x180040fa0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000d140`
- `ADVAPI32!RegCloseKey` at `0x18000d140`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d0b9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d0b9`
- `ADVAPI32!RegQueryValueExW` at `0x18000d0f6`
- `ADVAPI32!RegQueryValueExW` at `0x18000d128`
- `ADVAPI32!RegQueryValueExW` at `0x18000d0f6`
- `ADVAPI32!RegQueryValueExW` at `0x18000d128`

## pseudocode

```c

```
