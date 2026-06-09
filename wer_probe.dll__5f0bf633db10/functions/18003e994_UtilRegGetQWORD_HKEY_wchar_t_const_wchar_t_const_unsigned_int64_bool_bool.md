# UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)

- ea: `0x18003e994`
- end: `0x18003ea5f`
- name: `?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z`
- size: `203`
- prototype: `unsigned __int64(HKEY, const wchar_t *, const wchar_t *, unsigned __int64, bool *, bool)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180006cb0`
- `0x180017a18`
- `0x18003e74c`
- `0x180098d88`

## callees

- `0x18000716c`
- `0x18003e994`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ea16`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003ea16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ea4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ea4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e9df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e9df`

## pseudocode

```c

```
