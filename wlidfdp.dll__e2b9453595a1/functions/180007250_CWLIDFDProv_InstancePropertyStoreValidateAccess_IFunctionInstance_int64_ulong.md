# CWLIDFDProv::InstancePropertyStoreValidateAccess(IFunctionInstance *,__int64,ulong)

- ea: `0x180007250`
- end: `0x18000725f`
- name: `?InstancePropertyStoreValidateAccess@CWLIDFDProv@@UEAAJPEAUIFunctionInstance@@_JK@Z`
- size: `15`
- prototype: `__int64 __fastcall(CWLIDFDProv *this, struct IFunctionInstance *, __int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CWLIDFDProv::InstancePropertyStoreValidateAccess(
        CWLIDFDProv *this,
        struct IFunctionInstance *a2,
        __int64 a3,
        int a4)
{
  return a4 != 0 ? 0x80030005 : 0;
}

```

## disassembly

```asm
0x180007250  xor     eax, eax
0x180007252  sub     eax, r9d
0x180007255  neg     eax
0x180007257  sbb     eax, eax
0x180007259  and     eax, 80030005h
0x18000725e  retn
```
