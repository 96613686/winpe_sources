# CreateACLedUserTileFolderandRegKey(ushort const *)

- ea: `0x18005021c`
- end: `0x18005038f`
- name: `?CreateACLedUserTileFolderandRegKey@@YAJPEBG@Z`
- size: `371`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d0d10`

## callees

- `0x18002e93c`
- `0x18003d244`
- `0x18005021c`
- `0x180054130`
- `0x1800ca1e0`
- `0x1800dba30`
- `0x1800dbe00`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050344`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050344`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180050304`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x180050304`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x1800502be`
- `SHCORE!__imp_SHCreateDirectoryExW` at `0x1800502be`
- `SHELL32!SHSetLocalizedName` at `0x1800502e0`
- `SHELL32!SHSetLocalizedName` at `0x180050331`
- `SHELL32!SHSetLocalizedName` at `0x1800502e0`
- `SHELL32!SHSetLocalizedName` at `0x180050331`

## string_xrefs

- `0x1800502fd`: `%ProgramData%\Microsoft\User Account Pictures`
- `0x1800502d4`: `Windows.UI.Immersive.dll`
- `0x180050325`: `Windows.UI.Immersive.dll`

## pseudocode

```c

```
