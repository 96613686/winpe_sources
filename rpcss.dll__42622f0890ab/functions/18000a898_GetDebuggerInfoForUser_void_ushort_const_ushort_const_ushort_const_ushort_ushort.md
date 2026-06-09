# GetDebuggerInfoForUser(void *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *)

- ea: `0x18000a898`
- end: `0x18000aca5`
- name: `?GetDebuggerInfoForUser@@YAJPEAXPEBG11PEAPEAG2@Z`
- size: `1037`
- prototype: `__int64 __fastcall(PSID Sid, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a480`

## callees

- `0x18000a898`
- `0x18000bbe8`
- `0x18001ec28`
- `0x18002ba28`
- `0x18002f058`
- `0x18006b5a4`
- `0x18006c5c0`
- `0x18006ca54`
- `0x1800731b0`
- `0x18008e98c`
- `0x180098b54`
- `0x1800b27e0`
- `0x1800c6748`
- `0x1800c6898`
- `0x1800f95ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa81`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aa96`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a900`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000a900`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000a9ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000a9de`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000aa0a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000a9ce`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000a9de`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000aa0a`

## string_xrefs

- `0x18000a913`: `\REGISTRY\User\%s\Software\Classes\PackagesDebug`
- `0x18000a9ed`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000aa3c`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000aaf4`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000abc2`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000ac46`: `onecore\com\combase\rpcss\olescm\launch.cxx`
- `0x18000ab98`: `DebugPath`

## pseudocode

```c

```
