# SearchSettings::SearchSettingsHelper::GetSearchSettingAsBool(wchar_t const * const,bool)

- ea: `0x180046e34`
- end: `0x180046ef4`
- name: `?GetSearchSettingAsBool@SearchSettingsHelper@SearchSettings@@CA_NQEB_W_N@Z`
- size: `192`
- prototype: `bool __fastcall(LPCWSTR lpValue, bool)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800352a0`
- `0x1800353b0`
- `0x180046dc0`
- `0x1800e333c`
- `0x1803490c4`
- `0x18034b050`

## callees

- `0x180046e34`
- `0x180046efc`
- `0x1800e488c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046e9e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180046e9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046eec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046eec`

## string_xrefs

- `0x180046ecc`: `shellcommon\internal\shell\inc\search\SearchSettingsHelper.h`

## pseudocode

```c

```
