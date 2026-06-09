# [thunk]:CWSHExtension::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180006090`
- end: `0x180006099`
- name: `?QueryInterface@CWSHExtension@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
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
  return CWSHExtension::QueryInterface((CWSHExtension *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180006090  sub     rcx, 8; this
0x180006094  jmp     ?QueryInterface@CWSHExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z; CWSHExtension::QueryInterface(_GUID const &,void * *)
```
