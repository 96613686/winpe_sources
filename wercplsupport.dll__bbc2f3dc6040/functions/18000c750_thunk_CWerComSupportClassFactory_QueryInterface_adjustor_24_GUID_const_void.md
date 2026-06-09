# [thunk]:CWerComSupportClassFactory::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x18000c750`
- end: `0x18000c759`
- name: `?QueryInterface@CWerComSupportClassFactory@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c6d0`

## pseudocode

```c
__int64 __fastcall CWerComSupportClassFactory::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        CWerComSupportClassFactory **a3)
{
  return CWerComSupportClassFactory::QueryInterface((CWerComSupportClassFactory *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x18000c750  sub     rcx, 18h; this
0x18000c754  jmp     ?QueryInterface@CWerComSupportClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWerComSupportClassFactory::QueryInterface(_GUID const &,void * *)
```
