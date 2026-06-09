# CScriptingEngine::QueryInterface(_GUID const &,void * *)

- ea: `0x14000dee0`
- end: `0x14000deef`
- name: `?QueryInterface@CScriptingEngine@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CScriptingEngine *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000df00`
- `0x14000df10`
- `0x14000df20`
- `0x14000df30`
- `0x14000df40`

## callees

- `0x140018010`

## pseudocode

```c
__int64 __fastcall CScriptingEngine::QueryInterface(CScriptingEngine *this, const struct _GUID *a2, void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 6))(
           *((_QWORD *)this + 6),
           a2,
           a3);
}

```

## disassembly

```asm
0x14000dee0  mov     rcx, [rcx+30h]
0x14000dee4  mov     rax, [rcx]
0x14000dee7  mov     rax, [rax]
0x14000deea  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
