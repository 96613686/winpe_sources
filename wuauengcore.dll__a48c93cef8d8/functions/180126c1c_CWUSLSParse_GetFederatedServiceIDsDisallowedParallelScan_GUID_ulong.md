# CWUSLSParse::GetFederatedServiceIDsDisallowedParallelScan(_GUID * *,ulong *)

- ea: `0x180126c1c`
- end: `0x180126ff0`
- name: `?GetFederatedServiceIDsDisallowedParallelScan@CWUSLSParse@@QEBAJPEAPEAU_GUID@@PEAK@Z`
- size: `980`
- prototype: `__int64 __fastcall(CWUSLSParse *__hidden this, struct _GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1801cf4a0`

## callees

- `0x18000def4`
- `0x180015b10`
- `0x180015ba0`
- `0x18001a7f0`
- `0x180126c1c`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180126e09`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180126e09`
- `RPCRT4!UuidFromStringW` at `0x180126e5c`
- `RPCRT4!UuidFromStringW` at `0x180126e5c`
- `OLEAUT32!__imp_SysFreeString` at `0x180126dc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180126e2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180126e88`
- `OLEAUT32!__imp_SysFreeString` at `0x180126e96`
- `OLEAUT32!__imp_SysFreeString` at `0x180126f7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180126faa`
- `OLEAUT32!__imp_SysFreeString` at `0x180126dc1`
- `OLEAUT32!__imp_SysFreeString` at `0x180126e2c`
- `OLEAUT32!__imp_SysFreeString` at `0x180126e88`
- `OLEAUT32!__imp_SysFreeString` at `0x180126e96`
- `OLEAUT32!__imp_SysFreeString` at `0x180126f7c`
- `OLEAUT32!__imp_SysFreeString` at `0x180126faa`

## string_xrefs

- `0x180126d87`: `ServiceId`
- `0x180126cb0`: `/ServiceEnvironment/WUClientData/FederatedServicesDisallowedParallelScan`

## pseudocode

```c

```
