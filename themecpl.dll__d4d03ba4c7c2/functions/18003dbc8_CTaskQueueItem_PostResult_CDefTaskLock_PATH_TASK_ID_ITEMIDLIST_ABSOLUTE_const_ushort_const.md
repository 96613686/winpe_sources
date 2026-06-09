# CTaskQueueItem::PostResult(CDefTaskLock *,PATH_TASK_ID,_ITEMIDLIST_ABSOLUTE const *,ushort const *)

- ea: `0x18003dbc8`
- end: `0x18003dcde`
- name: `?PostResult@CTaskQueueItem@@SAJPEAVCDefTaskLock@@W4PATH_TASK_ID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEBG@Z`
- size: `278`
- prototype: `static int __high(struct CDefTaskLock *, enum PATH_TASK_ID, const struct _ITEMIDLIST_ABSOLUTE *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180041830`
- `0x180041900`
- `0x180041b10`

## callees

- `0x18000268c`
- `0x18003dbc8`
- `0x180057010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18003dc63`
- `SHELL32!__imp_ILClone` at `0x18003dc63`
- `SHLWAPI!SHStrDupW` at `0x18003dc94`
- `SHLWAPI!SHStrDupW` at `0x18003dc94`

## pseudocode

```c

```
