# CWSHExtension::QueryInterface(_GUID const &,void * *)

- ea: `0x180006070`
- end: `0x18000607f`
- name: `?QueryInterface@CWSHExtension@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CWSHExtension *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180006090`
- `0x1800060a0`
- `0x1800060b0`
- `0x1800060c0`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CWSHExtension::QueryInterface(CWSHExtension *this, const struct _GUID *a2, void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 6))(
           *((_QWORD *)this + 6),
           a2,
           a3);
}

```

## disassembly

```asm
0x180006070  mov     rcx, [rcx+30h]
0x180006074  mov     rax, [rcx]
0x180006077  mov     rax, [rax]
0x18000607a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
