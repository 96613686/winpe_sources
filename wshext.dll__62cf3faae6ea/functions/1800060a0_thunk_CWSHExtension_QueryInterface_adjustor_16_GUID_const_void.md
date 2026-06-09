# [thunk]:CWSHExtension::QueryInterface`adjustor{16}' (_GUID const &,void * *)

- ea: `0x1800060a0`
- end: `0x1800060a9`
- name: `?QueryInterface@CWSHExtension@@WBA@EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return CWSHExtension::QueryInterface((CWSHExtension *)(a1 - 16), a2, a3);
}

```

## disassembly

```asm
0x1800060a0  sub     rcx, 10h; this
0x1800060a4  jmp     ?QueryInterface@CWSHExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWSHExtension::QueryInterface(_GUID const &,void * *)
```
