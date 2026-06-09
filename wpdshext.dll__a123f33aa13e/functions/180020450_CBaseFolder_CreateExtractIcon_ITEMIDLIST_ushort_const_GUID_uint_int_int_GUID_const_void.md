# CBaseFolder::_CreateExtractIcon(_ITEMIDLIST *,ushort const *,_GUID,uint,int,int,_GUID const &,void * *)

- ea: `0x180020450`
- end: `0x1800206df`
- name: `?_CreateExtractIcon@CBaseFolder@@MEAAJPEFAU_ITEMIDLIST@@PEBGU_GUID@@IHHAEBU3@PEAPEAX@Z`
- size: `655`
- prototype: `int(CBaseFolder *__hidden this, struct _ITEMIDLIST *, const unsigned __int16 *, struct _GUID *__struct_ptr, unsigned int, int, int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180020450`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x18003912c`
- `0x180039e80`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1800204b1`
- `KERNEL32!HeapAlloc` at `0x1800204b1`
- `KERNEL32!GetProcessHeap` at `0x18002049e`
- `KERNEL32!GetProcessHeap` at `0x18002049e`
- `KERNEL32!EnterCriticalSection` at `0x180020517`
- `KERNEL32!EnterCriticalSection` at `0x180020517`
- `KERNEL32!LeaveCriticalSection` at `0x18002052b`
- `KERNEL32!LeaveCriticalSection` at `0x18002052b`
- `SHELL32!__imp_ILClone` at `0x18002053d`
- `SHELL32!__imp_ILClone` at `0x18002053d`

## pseudocode

```c

```
