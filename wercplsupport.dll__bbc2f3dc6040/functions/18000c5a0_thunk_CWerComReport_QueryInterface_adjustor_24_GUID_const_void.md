# [thunk]:CWerComReport::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000c5a0`
- end: `0x18000c5a9`
- name: `?QueryInterface@CWerComReport@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c520`

## pseudocode

```c
__int64 __fastcall CWerComReport::QueryInterface(__int64 a1, const struct _GUID *a2, CWerComReport **a3)
{
  return CWerComReport::QueryInterface((CWerComReport *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x18000c5a0  sub     rcx, 18h; this
0x18000c5a4  jmp     ?QueryInterface@CWerComReport@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWerComReport::QueryInterface(_GUID const &,void * *)
```
