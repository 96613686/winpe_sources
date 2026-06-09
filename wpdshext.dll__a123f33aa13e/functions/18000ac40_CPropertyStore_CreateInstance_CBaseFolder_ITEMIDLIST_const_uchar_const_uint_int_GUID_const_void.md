# CPropertyStore::CreateInstance(CBaseFolder *,_ITEMIDLIST const *,uchar const *,uint,int,_GUID const &,void * *)

- ea: `0x18000ac40`
- end: `0x18000af5e`
- name: `?CreateInstance@CPropertyStore@@SAJPEAVCBaseFolder@@PEFBU_ITEMIDLIST@@PEBEIHAEBU_GUID@@PEAPEAX@Z`
- size: `798`
- prototype: `static int(struct CBaseFolder *, const struct _ITEMIDLIST *, const unsigned __int8 *, unsigned int, int, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180029ea0`
- `0x180045cdc`
- `0x180058784`
- `0x180066c34`

## callees

- `0x18000ac40`
- `0x18000af70`
- `0x18002ff5c`
- `0x180035590`
- `0x18003912c`
- `0x180039e80`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000acc4`
- `KERNEL32!HeapAlloc` at `0x18000acc4`
- `KERNEL32!GetProcessHeap` at `0x18000acb0`
- `KERNEL32!GetProcessHeap` at `0x18000acb0`
- `KERNEL32!EnterCriticalSection` at `0x18000ad45`
- `KERNEL32!EnterCriticalSection` at `0x18000ad45`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad59`
- `KERNEL32!LeaveCriticalSection` at `0x18000ad59`
- `SHELL32!__imp_ILCloneFirst` at `0x18000ad75`
- `SHELL32!__imp_ILCloneFirst` at `0x18000ad75`

## pseudocode

```c

```
