# User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x18002b690`
- end: `0x18002b8f1`
- name: `?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z`
- size: `609`
- prototype: `void __usercall(User *__hidden this@<rcx>, const struct _bstr_t *@<rdx>, const struct _bstr_t *@<r8>, const struct _bstr_t *@<r9>, enum _SID_NAME_USE, void *, bool)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180029508`
- `0x18002af2c`
- `0x18002b1d0`
- `0x18004cfb0`
- `0x1800515c0`

## callees

- `0x18000dc30`
- `0x180019130`
- `0x18002a320`
- `0x18002a3c8`
- `0x18002a9e0`
- `0x18002ae80`
- `0x18002b690`
- `0x1800322a0`
- `0x1800339c0`
- `0x1800440ec`
- `0x1800679e0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002b726`
- `msvcrt!_wcsicmp` at `0x18002b754`
- `msvcrt!_wcsicmp` at `0x18002b726`
- `msvcrt!_wcsicmp` at `0x18002b754`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b8c3`
- `OLEAUT32!__imp_SysFreeString` at `0x18002b8c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b8de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b8de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b6c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b6c2`

## pseudocode

```c

```
