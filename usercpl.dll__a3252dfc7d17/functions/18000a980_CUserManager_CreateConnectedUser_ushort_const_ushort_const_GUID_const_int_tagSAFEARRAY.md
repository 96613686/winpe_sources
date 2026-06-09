# CUserManager::CreateConnectedUser(ushort const *,ushort const *,_GUID const &,int,tagSAFEARRAY *)

- ea: `0x18000a980`
- end: `0x18000aabd`
- name: `?CreateConnectedUser@CUserManager@@UEAAJPEBG0AEBU_GUID@@HPEAUtagSAFEARRAY@@@Z`
- size: `317`
- prototype: `__int64 __usercall@<rax>(CUserManager *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const struct _GUID *@<r9>, int, struct tagSAFEARRAY *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a980`
- `0x18000d560`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aa93`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000aa93`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000aa03`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000aa03`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a9e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a9ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18000aa0e`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a9e0`
- `OLEAUT32!__imp_SysAllocString` at `0x18000a9ec`
- `OLEAUT32!__imp_SysAllocString` at `0x18000aa0e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa67`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa70`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa79`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa67`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa70`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa79`

## pseudocode

```c

```
