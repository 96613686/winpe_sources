# _ApplyDefaultVisualEffect(HKEY__ *,HKEY__ *)

- ea: `0x18029cf2c`
- end: `0x18029d2d0`
- name: `?_ApplyDefaultVisualEffect@@YAXPEAUHKEY__@@0@Z`
- size: `932`
- prototype: `void __fastcall(HKEY hKey, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18021181c`

## callees

- `0x18011611c`
- `0x180249490`
- `0x18029a2d4`
- `0x18029bf1c`
- `0x18029cf2c`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18029d09f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18029d2a0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18029d09f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18029d2a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029cf99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029cfee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d023`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d074`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d0b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d0f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d1b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d1ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d23b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029cf99`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029cfee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d023`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d074`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d0b4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d0f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d1b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d1ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18029d23b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029d149`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18029d149`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18029d26d`
- `api-ms-win-shcore-registry-l1-1-0!SHSetValueW` at `0x18029d26d`
- `SHCORE!__imp_GUIDFromStringW` at `0x18029d118`
- `SHCORE!__imp_GUIDFromStringW` at `0x18029d118`

## string_xrefs

- `0x18029d0d2`: `CLSID`
- `0x18029d1e6`: `RegPath`

## pseudocode

```c

```
