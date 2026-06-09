# CDetectISAPIConfigModuleFactory::GetHttpModule(CHttpModule * *,IModuleAllocator *)

- ea: `0x1800014f0`
- end: `0x180001505`
- name: `?GetHttpModule@CDetectISAPIConfigModuleFactory@@UEAAJPEAPEAVCHttpModule@@PEAVIModuleAllocator@@@Z`
- size: `21`
- prototype: `__int64 __fastcall(CDetectISAPIConfigModuleFactory *__hidden this, struct CHttpModule **, struct IModuleAllocator *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800014f0`

## pseudocode

```c
__int64 __fastcall CDetectISAPIConfigModuleFactory::GetHttpModule(
        CDetectISAPIConfigModuleFactory *this,
        struct CHttpModule **a2,
        struct IModuleAllocator *a3)
{
  struct CHttpModule *v3; // rax

  v3 = (struct CHttpModule *)*((_QWORD *)this + 1);
  if ( !v3 )
    return 2147943568LL;
  *a2 = v3;
  return 0;
}

```

## disassembly

```asm
0x1800014f0  mov     rax, [rcx+8]
0x1800014f4  test    rax, rax
0x1800014f7  jnz     short loc_1800014FF
0x1800014f9  mov     eax, 80070490h
0x1800014fe  retn
0x1800014ff  mov     [rdx], rax
0x180001502  xor     eax, eax
0x180001504  retn
```
