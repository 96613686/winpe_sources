# LGetDevMode(HKEY__ *,ushort const *,_devicemodeW * *)

- ea: `0x14007ed18`
- end: `0x14007ee4a`
- name: `?LGetDevMode@@YAJPEAUHKEY__@@PEBGPEAPEAU_devicemodeW@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, struct _devicemodeW **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002591c`

## callees

- `0x14000645c`
- `0x14007ed18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14007ee03`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14007ee03`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14007ed86`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14007ed86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007ed58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007edb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007ed58`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14007edb5`

## string_xrefs

- `0x14007ede8`: `The size of the registry does not match the devmode's expected size`
- `0x14007ee1f`: `There were unexpected issues reading the devmode's registry`

## pseudocode

```c

```
