# CWLIDFDProv::InstancePropertyStoreOpen(IFunctionInstance *,__int64,ulong,IPropertyStore * *)

- ea: `0x180007230`
- end: `0x180007246`
- name: `?InstancePropertyStoreOpen@CWLIDFDProv@@UEAAJPEAUIFunctionInstance@@_JKPEAPEAUIPropertyStore@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(CWLIDFDProv *this, struct IFunctionInstance *, __int64, __int64, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180007230`

## pseudocode

```c
__int64 __fastcall CWLIDFDProv::InstancePropertyStoreOpen(
        CWLIDFDProv *this,
        struct IFunctionInstance *a2,
        __int64 a3,
        __int64 a4,
        struct IPropertyStore **a5)
{
  __int64 result; // rax

  if ( !a5 )
    return 2147942487LL;
  result = 0;
  *a5 = 0;
  return result;
}

```

## disassembly

```asm
0x180007230  mov     rcx, [rsp+arg_20]
0x180007235  test    rcx, rcx
0x180007238  jz      short loc_180007240
0x18000723a  xor     eax, eax
0x18000723c  mov     [rcx], rax
0x18000723f  retn
0x180007240  mov     eax, 80070057h
0x180007245  retn
```
