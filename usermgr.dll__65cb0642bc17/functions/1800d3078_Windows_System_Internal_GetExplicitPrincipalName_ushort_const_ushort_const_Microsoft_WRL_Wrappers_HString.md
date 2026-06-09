# Windows::System::Internal::_GetExplicitPrincipalName(ushort const *,ushort const *,Microsoft::WRL::Wrappers::HString &)

- ea: `0x1800d3078`
- end: `0x1800d31c1`
- name: `?_GetExplicitPrincipalName@Internal@System@Windows@@YAJPEBG0AEAVHString@Wrappers@WRL@Microsoft@@@Z`
- size: `329`
- prototype: `int(Windows::System::Internal *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Microsoft::WRL::Wrappers::HString *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180066108`

## callees

- `0x1800088e8`
- `0x18003322c`
- `0x1800d2154`
- `0x1800d3078`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d30ac`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d30ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d30bb`
- `NTDSAPI!DsCrackNamesW` at `0x1800d314d`
- `NTDSAPI!DsCrackNamesW` at `0x1800d314d`
- `NTDSAPI!DsUnBindW` at `0x1800d31a0`
- `NTDSAPI!DsUnBindW` at `0x1800d31a0`
- `NTDSAPI!DsFreeNameResultW` at `0x1800d3196`
- `NTDSAPI!DsFreeNameResultW` at `0x1800d3196`
- `NTDSAPI!DsBindW` at `0x1800d30fe`
- `NTDSAPI!DsBindW` at `0x1800d30fe`

## string_xrefs

- `0x1800d30dc`: `onecore\ds\security\umstartup\usermgr\common\lib\useraccounthelper.cpp`
- `0x1800d309d`: `ntdsapi.dll`

## pseudocode

```c

```
