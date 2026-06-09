# SampQueryRegistryStringValue(HKEY__ *,ushort *,ushort * *)

- ea: `0x1800ad05c`
- end: `0x1800ad174`
- name: `?SampQueryRegistryStringValue@@YAJPEAUHKEY__@@PEAGPEAPEAG@Z`
- size: `280`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180092ca8`

## callees

- `0x180027e24`
- `0x18002d720`
- `0x1800ad05c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad09d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad11c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad09d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ad11c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ad0de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ad0de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ad130`

## string_xrefs

- `0x1800ad08b`: `ShadowAccountSid`
- `0x1800ad10d`: `ShadowAccountSid`

## pseudocode

```c

```
