# LGetDevMode(HKEY__ *,ushort const *,_devicemodeW * *)

- ea: `0x1400779c4`
- end: `0x140077add`
- name: `?LGetDevMode@@YAJPEAUHKEY__@@PEBGPEAPEAU_devicemodeW@@@Z`
- size: `281`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, struct _devicemodeW **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140023974`

## callees

- `0x140005b68`
- `0x1400779c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140077a9d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140077a9d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140077a2c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140077a2c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077a04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077a55`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077a04`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140077a55`

## string_xrefs

- `0x140077a82`: `The size of the registry does not match the devmode's expected size`
- `0x140077ab3`: `There were unexpected issues reading the devmode's registry`

## pseudocode

```c

```
