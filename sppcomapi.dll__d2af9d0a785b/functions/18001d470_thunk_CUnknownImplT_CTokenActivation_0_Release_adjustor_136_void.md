# [thunk]:CUnknownImplT<CTokenActivation,0>::Release`adjustor{136}' (void)

- ea: `0x18001d470`
- end: `0x18001d47c`
- name: `?Release@?$CUnknownImplT@VCTokenActivation@@$0A@@@WII@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001d430`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CTokenActivation,0>::Release(__int64 a1)
{
  return CUnknownImplT<CTokenActivation,0>::Release((volatile signed __int32 *)(a1 - 136));
}

```

## disassembly

```asm
0x18001d470  sub     rcx, 88h
0x18001d477  jmp     ?Release@?$CUnknownImplT@VCTokenActivation@@$0A@@@UEAAKXZ; CUnknownImplT<CTokenActivation,0>::Release(void)
```
