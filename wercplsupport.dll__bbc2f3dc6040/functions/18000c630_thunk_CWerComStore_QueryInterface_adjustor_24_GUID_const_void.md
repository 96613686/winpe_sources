# [thunk]:CWerComStore::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000c630`
- end: `0x18000c639`
- name: `?QueryInterface@CWerComStore@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c5b0`

## pseudocode

```c
__int64 __fastcall CWerComStore::QueryInterface(__int64 a1, const struct _GUID *a2, CWerComStore **a3)
{
  return CWerComStore::QueryInterface((CWerComStore *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x18000c630  sub     rcx, 18h; this
0x18000c634  jmp     ?QueryInterface@CWerComStore@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWerComStore::QueryInterface(_GUID const &,void * *)
```
