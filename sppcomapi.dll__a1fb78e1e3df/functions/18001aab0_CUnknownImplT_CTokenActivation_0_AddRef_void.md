# CUnknownImplT<CTokenActivation,0>::AddRef(void)

- ea: `0x18001aab0`
- end: `0x18001aac0`
- name: `?AddRef@?$CUnknownImplT@VCTokenActivation@@$0A@@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001aad0`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CTokenActivation,0>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 280));
}

```

## disassembly

```asm
0x18001aab0  mov     eax, 1
0x18001aab5  lock xadd [rcx+118h], eax
0x18001aabd  inc     eax
0x18001aabf  retn
```
