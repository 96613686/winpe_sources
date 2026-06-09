# CRegFolder::GetDetailsEx(_ITEMID_CHILD const *,_tagpropertykey const *,tagVARIANT *)

- ea: `0x18016b1a0`
- end: `0x18016ba6c`
- name: `?GetDetailsEx@CRegFolder@@UEAAJPEFBU_ITEMID_CHILD@@PEBU_tagpropertykey@@PEAUtagVARIANT@@@Z`
- size: `2252`
- prototype: `int(CRegFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _tagpropertykey *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180094c70`
- `0x1800c4100`
- `0x1800e1c90`
- `0x1800e4810`
- `0x18016b130`
- `0x18016b1a0`
- `0x18016ba80`
- `0x1801a1360`
- `0x1801a1560`
- `0x180232520`
- `0x18027b62c`
- `0x1802f6c48`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96d9`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18016b434`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18016b434`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016b306`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016b33a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016b306`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18016b33a`
- `OLEAUT32!__imp_SysFreeString` at `0x18016b6e8`
- `OLEAUT32!__imp_SysFreeString` at `0x18016b6e8`
- `OLEAUT32!__imp_VariantClear` at `0x18016b657`
- `OLEAUT32!__imp_VariantClear` at `0x18016ba20`
- `OLEAUT32!__imp_VariantClear` at `0x18016b657`
- `OLEAUT32!__imp_VariantClear` at `0x18016ba20`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18016b6a1`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18016b6a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016b502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18016b502`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18016b2c9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18016b2c9`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18016b6cc`
- `SHCORE!__imp_SHLoadRegUIStringW` at `0x18016b6cc`
- `PROPSYS!PSStringFromPropertyKey` at `0x18016b3a8`
- `PROPSYS!PSStringFromPropertyKey` at `0x18016b3a8`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18016b364`
- `PROPSYS!PSGetNameFromPropertyKey` at `0x18016b364`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18016b3fe`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18016b9eb`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18016b3fe`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x18016b9eb`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_CategoryIdArrayFromVariant` at `0x18016b642`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_CPL_CategoryIdArrayFromVariant` at `0x18016b642`

## string_xrefs

- `0x18016b2d3`: `CLSID\%s`

## pseudocode

```c

```
