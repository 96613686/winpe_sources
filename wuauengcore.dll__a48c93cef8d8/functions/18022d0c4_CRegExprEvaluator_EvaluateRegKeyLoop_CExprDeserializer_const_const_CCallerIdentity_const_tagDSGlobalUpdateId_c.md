# CRegExprEvaluator::EvaluateRegKeyLoop(CExprDeserializer const * const,CCallerIdentity const *,tagDSGlobalUpdateId const &,ulong,tagDSDataBlob const * const,tagSusRuleContext const &,ISusExprEvaluate *,CExpressionVariableData const * const,tagSusRuleResult *)

- ea: `0x18022d0c4`
- end: `0x18022d924`
- name: `?EvaluateRegKeyLoop@CRegExprEvaluator@@AEBAJQEBVCExprDeserializer@@PEBVCCallerIdentity@@AEBUtagDSGlobalUpdateId@@KQEBUtagDSDataBlob@@AEBUtagSusRuleContext@@PEAUISusExprEvaluate@@QEBVCExpressionVariableData@@PEAW4tagSusRuleResult@@@Z`
- size: `2144`
- prototype: `__int64 __fastcall(CRegExprEvaluator *__hidden this, const struct CExprDeserializer *const, const struct CCallerIdentity *, const struct tagDSGlobalUpdateId *, unsigned int, const struct tagDSDataBlob *const, const struct tagSusRuleContext *, struct ISusExprEvaluate *, const struct CExpressionVariableData *const, enum tagSusRuleResult *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x18022b030`

## callees

- `0x180113a10`
- `0x180113ae8`
- `0x180113b9c`
- `0x18012b618`
- `0x180137dd0`
- `0x18022d0c4`
- `0x18022de04`
- `0x180238960`
- `0x180240cc0`
- `0x180241100`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022d8e2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022d8e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022d480`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022d480`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18022d5e6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18022d5e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18022d4ef`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18022d4ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18022d805`
- `OLEAUT32!__imp_SysFreeString` at `0x18022d805`
- `OLEAUT32!__imp_SysStringLen` at `0x18022d30b`
- `OLEAUT32!__imp_SysStringLen` at `0x18022d533`
- `OLEAUT32!__imp_SysStringLen` at `0x18022d582`
- `OLEAUT32!__imp_SysStringLen` at `0x18022d30b`
- `OLEAUT32!__imp_SysStringLen` at `0x18022d533`
- `OLEAUT32!__imp_SysStringLen` at `0x18022d582`

## string_xrefs

- `0x18022d491`: `RegKeyLoop: Opened Subkey %ls successfully`

## pseudocode

```c

```
