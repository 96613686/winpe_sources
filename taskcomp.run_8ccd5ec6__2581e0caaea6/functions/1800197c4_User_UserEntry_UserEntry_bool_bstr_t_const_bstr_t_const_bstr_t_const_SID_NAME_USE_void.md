# User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)

- ea: `0x1800197c4`
- end: `0x1800198e9`
- name: `??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z`
- size: `293`
- prototype: `__int64 __usercall@<rax>(User::UserEntry *__hidden this@<rcx>, bool@<dl>, const struct _bstr_t *@<r8>, const struct _bstr_t *@<r9>, const struct _bstr_t *, enum _SID_NAME_USE, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180019f10`
- `0x18001a394`
- `0x18001acc4`

## callees

- `0x1800197c4`
- `0x180019ac0`
- `0x18001ca54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001984f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001984f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800198cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800198cf`

## pseudocode

```c

```
