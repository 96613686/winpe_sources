# RegGetPackageFamilyName(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18007e134`
- end: `0x18007e244`
- name: `?RegGetPackageFamilyName@@YA?AUhstring@winrt@@PEAUHKEY__@@PEB_W11@Z`
- size: `272`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180025364`
- `0x18002589c`

## callees

- `0x1800260c0`
- `0x18007e134`
- `0x18015cb00`
- `0x18015d500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e18b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007e18b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007e20e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007e20e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e1ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e1ae`

## string_xrefs

- `0x18007e17d`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Packages`

## pseudocode

```c

```
