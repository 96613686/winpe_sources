# User::UserEntry::UserEntry(bool,_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *)

- ea: `0x18001862c`
- end: `0x180018744`
- name: `??0UserEntry@User@@QEAA@_NAEBV_bstr_t@@11W4_SID_NAME_USE@@PEAX@Z`
- size: `280`
- prototype: `User::UserEntry *__fastcall(User::UserEntry *this, __int64, const struct _bstr_t *, const struct _bstr_t *, const struct _bstr_t *, enum _SID_NAME_USE, void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180018d00`
- `0x180019168`
- `0x180019a10`

## callees

- `0x18001862c`
- `0x1800188e4`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800186b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018731`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018731`

## pseudocode

```c

```
