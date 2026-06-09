# IsRuleGroupEnabled(INetFwPolicy2 *,ushort const *,int *)

- ea: `0x14003104c`
- end: `0x14003114e`
- name: `?IsRuleGroupEnabled@@YAJPEAUINetFwPolicy2@@PEBGPEAH@Z`
- size: `258`
- prototype: `__int64 __fastcall(struct INetFwPolicy2 *, const unsigned __int16 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140030cec`
- `0x14004f094`

## callees

- `0x14003104c`
- `0x14004a834`
- `0x1400549e0`
- `0x14009e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1400310ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1400310ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1400310fa`
- `OLEAUT32!__imp_SysFreeString` at `0x1400310fa`

## string_xrefs

- `0x14003106d`: `@FirewallAPI.dll,-31252`

## pseudocode

```c

```
