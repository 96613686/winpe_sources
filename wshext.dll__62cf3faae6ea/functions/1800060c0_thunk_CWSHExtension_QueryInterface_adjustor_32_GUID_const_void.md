# [thunk]:CWSHExtension::QueryInterface`adjustor{32}' (_GUID const &,void * *)

- ea: `0x1800060c0`
- end: `0x1800060c9`
- name: `?QueryInterface@CWSHExtension@@WCA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return CWSHExtension::QueryInterface((CWSHExtension *)(a1 - 32), a2, a3);
}

```

## disassembly

```asm
0x1800060c0  sub     rcx, 20h ; ' '; this
0x1800060c4  jmp     ?QueryInterface@CWSHExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWSHExtension::QueryInterface(_GUID const &,void * *)
```
