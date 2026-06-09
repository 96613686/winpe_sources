# CWMResizeDMO::QueryInterface(_GUID const &,void * *)

- ea: `0x1800083b0`
- end: `0x1800083c2`
- name: `?QueryInterface@CWMResizeDMO@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(CWMResizeDMO *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083d0`
- `0x1800083f0`
- `0x180008410`
- `0x180008430`

## callees

- `0x180016010`

## pseudocode

```c
__int64 __fastcall CWMResizeDMO::QueryInterface(CWMResizeDMO *this, const struct _GUID *a2, void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 53))(
           *((_QWORD *)this + 53),
           a2,
           a3);
}

```

## disassembly

```asm
0x1800083b0  mov     rcx, [rcx+1A8h]
0x1800083b7  mov     rax, [rcx]
0x1800083ba  mov     rax, [rax]
0x1800083bd  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
