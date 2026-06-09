# GetSystemDefaultTheme(ushort *,ulong)

- ea: `0x180034e50`
- end: `0x180034fa9`
- name: `?GetSystemDefaultTheme@@YAJPEAGK@Z`
- size: `345`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180017b70`
- `0x180040fcc`
- `0x180041a2c`
- `0x18004f044`

## callees

- `0x18000ab10`
- `0x18000cc2c`
- `0x180015660`
- `0x180034e50`
- `0x1800358c0`

## import_xrefs

- `SHCORE!IsOS` at `0x180034e84`
- `SHCORE!IsOS` at `0x180034e84`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034ece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034f32`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034ece`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180034f32`

## string_xrefs

- `0x180034f04`: `InstallTheme`
- `0x180034ea0`: `InstallThemeLight`

## pseudocode

```c

```
