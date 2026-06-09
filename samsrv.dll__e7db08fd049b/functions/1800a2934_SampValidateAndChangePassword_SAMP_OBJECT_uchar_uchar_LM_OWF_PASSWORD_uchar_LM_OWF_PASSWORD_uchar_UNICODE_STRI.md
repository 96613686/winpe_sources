# SampValidateAndChangePassword(_SAMP_OBJECT *,uchar,uchar,_LM_OWF_PASSWORD *,uchar,_LM_OWF_PASSWORD *,uchar,_UNICODE_STRING *,_UNICODE_STRING *,_DOMAIN_PASSWORD_INFORMATION *,_USER_PWD_CHANGE_FAILURE_INFORMATION *)

- ea: `0x1800a2934`
- end: `0x1800a2dac`
- name: `?SampValidateAndChangePassword@@YAJPEAU_SAMP_OBJECT@@EEPEAU_LM_OWF_PASSWORD@@E1EPEAU_UNICODE_STRING@@2PEAU_DOMAIN_PASSWORD_INFORMATION@@PEAU_USER_PWD_CHANGE_FAILURE_INFORMATION@@@Z`
- size: `1144`
- prototype: `__int64 __usercall@<rax>(struct _SAMP_OBJECT *@<rcx>, unsigned __int8@<dl>, unsigned __int8@<r8b>, struct _LM_OWF_PASSWORD *@<r9>, unsigned __int8, struct _LM_OWF_PASSWORD *, unsigned __int8, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _DOMAIN_PASSWORD_INFORMATION *, struct _USER_PWD_CHANGE_FAILURE_INFORMATION *)`
- caller_count: `4`
- callee_count: `17`
- tags: `loader_planting, service_task`

## callers

- `0x18009b224`
- `0x18009bd34`
- `0x1800a3440`
- `0x1800a4b60`

## callees

- `0x18000e7f0`
- `0x180012a28`
- `0x180016d50`
- `0x1800198a0`
- `0x1800213d0`
- `0x1800225f0`
- `0x180027e24`
- `0x180028370`
- `0x18002cd80`
- `0x18002d720`
- `0x1800a0258`
- `0x1800a262c`
- `0x1800a2934`
- `0x1800a2f0c`
- `0x1800a46c0`
- `0x1800a4a60`
- `0x1800a5620`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x1800a2a1b`
- `ntdll!NtQuerySystemTime` at `0x1800a2a1b`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtAddLoopbackTaskForBadPasswordCount` at `0x1800a2d73`
- `ext-ms-win-ntdsaapi-l1-1-0!NtdsaExtAddLoopbackTaskForBadPasswordCount` at `0x1800a2d73`
- `CRYPTSP!SystemFunction030` at `0x1800a2bc1`
- `CRYPTSP!SystemFunction030` at `0x1800a2bc1`
- `CRYPTSP!SystemFunction031` at `0x1800a2ba8`
- `CRYPTSP!SystemFunction031` at `0x1800a2ba8`

## pseudocode

```c

```
