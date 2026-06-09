# UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)

- ea: `0x180040950`
- end: `0x180040a2e`
- name: `?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z`
- size: `222`
- prototype: `unsigned __int64(HKEY, const wchar_t *, const wchar_t *, unsigned __int64, bool *, bool)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013838`
- `0x18001be50`
- `0x1800406f4`
- `0x18009d330`

## callees

- `0x18001c368`
- `0x180040950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800409d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800409d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a13`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040a13`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004099b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004099b`

## pseudocode

```c

```
