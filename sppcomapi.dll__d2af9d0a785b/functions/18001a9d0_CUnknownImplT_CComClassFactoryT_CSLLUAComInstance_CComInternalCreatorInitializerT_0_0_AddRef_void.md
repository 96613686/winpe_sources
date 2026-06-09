# CUnknownImplT<CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>,0>::AddRef(void)

- ea: `0x18001a9d0`
- end: `0x18001a9dd`
- name: `?AddRef@?$CUnknownImplT@V?$CComClassFactoryT@VCSLLUAComInstance@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@UEAAKXZ`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CComClassFactoryT<CSLLUAComInstance,CComInternalCreatorInitializerT,0>,0>::AddRef(
        __int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x18001a9d0  mov     eax, 1
0x18001a9d5  lock xadd [rcx+8], eax
0x18001a9da  inc     eax
0x18001a9dc  retn
```
