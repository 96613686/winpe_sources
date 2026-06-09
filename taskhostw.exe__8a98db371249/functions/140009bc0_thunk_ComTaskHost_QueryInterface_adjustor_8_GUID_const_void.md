# [thunk]:ComTaskHost::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x140009bc0`
- end: `0x140009bc9`
- name: `?QueryInterface@ComTaskHost@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, ComTaskHost **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006450`

## pseudocode

```c
__int64 __fastcall ComTaskHost::QueryInterface(__int64 a1, const struct _GUID *a2, ComTaskHost **a3)
{
  return ComTaskHost::QueryInterface((ComTaskHost *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x140009bc0  sub     rcx, 8; this
0x140009bc4  jmp     ?QueryInterface@ComTaskHost@@UEAAJAEBU_GUID@@PEAPEAX@Z; ComTaskHost::QueryInterface(_GUID const &,void * *)
```
