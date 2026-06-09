# DeviceIdStore::AddCertificatesToPersistentStore(PPCRLUserType,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1801019a0`
- end: `0x180101ec7`
- name: `?AddCertificatesToPersistentStore@DeviceIdStore@@SAJW4PPCRLUserType@@PEBG111K@Z`
- size: `1319`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800dd340`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x180012f64`
- `0x180013fb4`
- `0x1800151c4`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180039d60`
- `0x180039ee8`
- `0x18003c814`
- `0x1800406a8`
- `0x180044408`
- `0x180087a84`
- `0x1801019a0`
- `0x180102f10`
- `0x180105adc`
- `0x1801067c4`
- `0x180107348`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180101bc2`
- `OLEAUT32!__imp_SysFreeString` at `0x180101dcf`
- `OLEAUT32!__imp_SysFreeString` at `0x180101bc2`
- `OLEAUT32!__imp_SysFreeString` at `0x180101dcf`
- `OLEAUT32!__imp_VariantInit` at `0x180101c07`
- `OLEAUT32!__imp_VariantInit` at `0x180101c07`
- `OLEAUT32!__imp_VariantClear` at `0x180101c3c`
- `OLEAUT32!__imp_VariantClear` at `0x180101c93`
- `OLEAUT32!__imp_VariantClear` at `0x180101cea`
- `OLEAUT32!__imp_VariantClear` at `0x180101d01`
- `OLEAUT32!__imp_VariantClear` at `0x180101d7e`
- `OLEAUT32!__imp_VariantClear` at `0x180101ea5`
- `OLEAUT32!__imp_VariantClear` at `0x180101c3c`
- `OLEAUT32!__imp_VariantClear` at `0x180101c93`
- `OLEAUT32!__imp_VariantClear` at `0x180101cea`
- `OLEAUT32!__imp_VariantClear` at `0x180101d01`
- `OLEAUT32!__imp_VariantClear` at `0x180101d7e`
- `OLEAUT32!__imp_VariantClear` at `0x180101ea5`

## string_xrefs

- `0x180101a4d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidstore.cpp`
- `0x180101ab4`: `hr = DeviceIdStore::LoadPersistedDOM(wstrRegPath, false, pDOM)`
- `0x180101a86`: `hr = GetRegistryPath(eUserType, wszUserName, wstrRegPath)`
- `0x180101dee`: `hr = DeviceIdStore::SaveDOM(wstrRegPath, pDOM)`
- `0x180101bcc`: `hr = pDOM->selectSingleNode(CComBSTR(wstrXPath), &pCertNode)`

## pseudocode

```c

```
