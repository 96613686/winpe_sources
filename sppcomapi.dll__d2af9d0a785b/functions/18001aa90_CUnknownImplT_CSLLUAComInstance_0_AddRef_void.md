# CUnknownImplT<CSLLUAComInstance,0>::AddRef(void)

- ea: `0x18001aa90`
- end: `0x18001aa9d`
- name: `?AddRef@?$CUnknownImplT@VCSLLUAComInstance@@$0A@@@UEAAKXZ`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CSLLUAComInstance,0>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
}

```

## disassembly

```asm
0x18001aa90  mov     eax, 1
0x18001aa95  lock xadd [rcx+10h], eax
0x18001aa9a  inc     eax
0x18001aa9c  retn
```
