# CUnknownImplT<CElevationConfig,0>::AddRef(void)

- ea: `0x18001a9f0`
- end: `0x18001aa00`
- name: `?AddRef@?$CUnknownImplT@VCElevationConfig@@$0A@@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CElevationConfig,0>::AddRef(__int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 160));
}

```

## disassembly

```asm
0x18001a9f0  mov     eax, 1
0x18001a9f5  lock xadd [rcx+0A0h], eax
0x18001a9fd  inc     eax
0x18001a9ff  retn
```
