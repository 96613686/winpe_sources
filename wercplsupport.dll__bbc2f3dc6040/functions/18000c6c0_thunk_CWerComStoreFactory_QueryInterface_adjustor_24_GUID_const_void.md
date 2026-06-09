# [thunk]:CWerComStoreFactory::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000c6c0`
- end: `0x18000c6c9`
- name: `?QueryInterface@CWerComStoreFactory@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c640`

## pseudocode

```c
__int64 __fastcall CWerComStoreFactory::QueryInterface(__int64 a1, const struct _GUID *a2, CWerComStoreFactory **a3)
{
  return CWerComStoreFactory::QueryInterface((CWerComStoreFactory *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x18000c6c0  sub     rcx, 18h; this
0x18000c6c4  jmp     ?QueryInterface@CWerComStoreFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWerComStoreFactory::QueryInterface(_GUID const &,void * *)
```
