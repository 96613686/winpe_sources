# CSystemExprEvaluator::EvaluateWmiQuery(CExprDeserializer const * const,tagSusRuleResult *)

- ea: `0x180227d90`
- end: `0x180228191`
- name: `?EvaluateWmiQuery@CSystemExprEvaluator@@AEBAJQEBVCExprDeserializer@@PEAW4tagSusRuleResult@@@Z`
- size: `1025`
- prototype: `__int64 __fastcall(CSystemExprEvaluator *__hidden this, const struct CExprDeserializer *const, enum tagSusRuleResult *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180226250`

## callees

- `0x180112c1c`
- `0x18012b618`
- `0x180227d90`
- `0x180238960`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180227f4a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180227f4a`
- `OLEAUT32!__imp_SysAllocString` at `0x180227f00`
- `OLEAUT32!__imp_SysAllocString` at `0x180227f1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180227f00`
- `OLEAUT32!__imp_SysAllocString` at `0x180227f1f`
- `OLEAUT32!__imp_SysFreeString` at `0x180228158`
- `OLEAUT32!__imp_SysFreeString` at `0x180228161`
- `OLEAUT32!__imp_SysFreeString` at `0x180228158`
- `OLEAUT32!__imp_SysFreeString` at `0x180228161`
- `OLEAUT32!__imp_SysStringLen` at `0x180227eb4`
- `OLEAUT32!__imp_SysStringLen` at `0x180227eef`
- `OLEAUT32!__imp_SysStringLen` at `0x180227eb4`
- `OLEAUT32!__imp_SysStringLen` at `0x180227eef`

## string_xrefs

- `0x180227f6a`: `  EE: CoCreateInstance for CLSID_WbemLocator`
- `0x180228027`: `  EE: SetProxyBlanketImpersonationLevel`

## pseudocode

```c

```
