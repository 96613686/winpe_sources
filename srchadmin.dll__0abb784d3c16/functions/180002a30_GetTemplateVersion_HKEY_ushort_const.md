# GetTemplateVersion(HKEY__ *,ushort const *)

- ea: `0x180002a30`
- end: `0x180002b04`
- name: `?GetTemplateVersion@@YAKPEAUHKEY__@@PEBG@Z`
- size: `212`
- prototype: `unsigned int __fastcall(HKEY hkey, PCWSTR pszIn)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021f84`

## callees

- `0x180002a30`
- `0x180005cc0`

## import_xrefs

- `SHLWAPI!UrlGetPartW` at `0x180002a99`
- `SHLWAPI!UrlGetPartW` at `0x180002a99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002ad9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002ad9`

## pseudocode

```c

```
