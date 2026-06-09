# User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x180002790`
- end: `0x180002a10`
- name: `?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z`
- size: `640`
- prototype: `void __usercall(User *__hidden this@<rcx>, const struct _bstr_t *@<rdx>, const struct _bstr_t *@<r8>, const struct _bstr_t *@<r9>, enum _SID_NAME_USE, void *, bool)`
- caller_count: `5`
- callee_count: `11`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180001f8c`
- `0x180002260`
- `0x18003c1f8`
- `0x18004f2b0`
- `0x180053b68`

## callees

- `0x180001d10`
- `0x180001dbc`
- `0x180001e10`
- `0x180002790`
- `0x180011e40`
- `0x18001d130`
- `0x1800301f0`
- `0x180030620`
- `0x180032c30`
- `0x180046208`
- `0x18006acbc`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000282c`
- `msvcrt!_wcsicmp` at `0x180002860`
- `msvcrt!_wcsicmp` at `0x18000282c`
- `msvcrt!_wcsicmp` at `0x180002860`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800029d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800029f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800027c2`

## pseudocode

```c

```
