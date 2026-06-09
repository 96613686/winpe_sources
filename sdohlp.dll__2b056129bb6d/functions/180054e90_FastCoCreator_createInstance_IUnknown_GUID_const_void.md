# FastCoCreator::createInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180054e90`
- end: `0x180054f56`
- name: `?createInstance@FastCoCreator@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `198`
- prototype: `__int64 __fastcall(FastCoCreator *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180054e70`

## callees

- `0x180054e90`
- `0x180058010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180054ea6`
- `KERNEL32!EnterCriticalSection` at `0x180054ea6`
- `KERNEL32!LeaveCriticalSection` at `0x180054f43`
- `KERNEL32!LeaveCriticalSection` at `0x180054f43`
- `ole32!CoGetClassObject` at `0x180054edb`
- `ole32!CoGetClassObject` at `0x180054edb`

## pseudocode

```c

```
