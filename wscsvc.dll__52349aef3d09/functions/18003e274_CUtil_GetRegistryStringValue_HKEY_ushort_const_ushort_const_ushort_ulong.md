# CUtil::GetRegistryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong *)

- ea: `0x18003e274`
- end: `0x18003e350`
- name: `?GetRegistryStringValue@CUtil@@SAJPEAUHKEY__@@PEBG1PEAGPEAK@Z`
- size: `220`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003bf04`
- `0x18003cbb8`

## callees

- `0x1800202e8`
- `0x18003e274`
- `0x18003e7e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e2c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e2c5`

## pseudocode

```c

```
