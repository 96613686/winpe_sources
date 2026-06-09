# [thunk]:CWSHExtension::QueryInterface`adjustor{24}' (_GUID const &,void * *)

- ea: `0x1800060b0`
- end: `0x1800060b9`
- name: `?QueryInterface@CWSHExtension@@WBI@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006070`

## pseudocode

```c
__int64 __fastcall CWSHExtension::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return CWSHExtension::QueryInterface((CWSHExtension *)(a1 - 24), a2, a3);
}

```

## disassembly

```asm
0x1800060b0  sub     rcx, 18h; this
0x1800060b4  jmp     ?QueryInterface@CWSHExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWSHExtension::QueryInterface(_GUID const &,void * *)
```
