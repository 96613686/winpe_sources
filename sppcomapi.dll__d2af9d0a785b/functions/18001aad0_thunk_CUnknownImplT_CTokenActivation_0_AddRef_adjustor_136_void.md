# [thunk]:CUnknownImplT<CTokenActivation,0>::AddRef`adjustor{136}' (void)

- ea: `0x18001aad0`
- end: `0x18001aadc`
- name: `?AddRef@?$CUnknownImplT@VCTokenActivation@@$0A@@@WII@EAAKXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001aab0`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CTokenActivation,0>::AddRef(__int64 a1)
{
  return CUnknownImplT<CTokenActivation,0>::AddRef(a1 - 136);
}

```

## disassembly

```asm
0x18001aad0  sub     rcx, 88h
0x18001aad7  jmp     ?AddRef@?$CUnknownImplT@VCTokenActivation@@$0A@@@UEAAKXZ; CUnknownImplT<CTokenActivation,0>::AddRef(void)
```
