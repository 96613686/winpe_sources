# [thunk]:CUnknownImplT<CTokenActivation,0>::QueryInterface`adjustor{136}' (_GUID const &,void * *)

- ea: `0x18001d1e0`
- end: `0x18001d1ec`
- name: `?QueryInterface@?$CUnknownImplT@VCTokenActivation@@$0A@@@WII@EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001d160`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CTokenActivation,0>::QueryInterface(__int64 a1, _QWORD *a2, __int64 **a3)
{
  return CUnknownImplT<CTokenActivation,0>::QueryInterface((__int64 *)(a1 - 136), a2, a3);
}

```

## disassembly

```asm
0x18001d1e0  sub     rcx, 88h
0x18001d1e7  jmp     ?QueryInterface@?$CUnknownImplT@VCTokenActivation@@$0A@@@UEAAJAEBU_GUID@@PEAPEAX@Z; CUnknownImplT<CTokenActivation,0>::QueryInterface(_GUID const &,void * *)
```
