# CRegFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x1800953e0`
- end: `0x180095d0d`
- name: `?GetDetailsEx@CRegFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `2349`
- prototype: `int(CRegFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180045bd0`
- `0x180063050`
- `0x18008ecb0`
- `0x180092a70`
- `0x180095130`
- `0x1800953e0`
- `0x180095d20`
- `0x18014e070`
- `0x1801c0ae0`
- `0x1801c0cf0`
- `0x180244240`
- `0x180289388`
- `0x180307738`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69b9`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800956a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009554c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095586`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009554c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095586`
- `OLEAUT32!__imp_SysFreeString` at `0x180095977`
- `OLEAUT32!__imp_SysFreeString` at `0x180095977`
- `OLEAUT32!__imp_VariantClear` at `0x1800958d4`
- `OLEAUT32!__imp_VariantClear` at `0x180095cbb`
- `OLEAUT32!__imp_VariantClear` at `0x1800958d4`
- `OLEAUT32!__imp_VariantClear` at `0x180095cbb`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180095924`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180095924`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095773`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180095509`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180095509`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x180095955`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x180095955`
- `PROPSYS!PSStringFromPropertyKey` at `0x180095608`
- `PROPSYS!PSStringFromPropertyKey` at `0x180095608`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1800955be`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x1800955be`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180095664`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180095c80`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180095664`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x180095c80`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_CategoryIdArrayFromVariant` at `0x1800958b9`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_CategoryIdArrayFromVariant` at `0x1800958b9`

## string_xrefs

- `0x180095519`: `CLSID\%s`

## pseudocode

```c

```
