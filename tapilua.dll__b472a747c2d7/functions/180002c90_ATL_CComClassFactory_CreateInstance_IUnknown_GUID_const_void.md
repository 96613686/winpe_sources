# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002c90`
- end: `0x180002cf2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002c90`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // r8d

  v5 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2
      && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002c90  sub     rsp, 28h
0x180002c94  mov     r11, rcx
0x180002c97  mov     rax, r8
0x180002c9a  xor     ecx, ecx
0x180002c9c  mov     r10, rdx
0x180002c9f  mov     r8d, 80004003h
0x180002ca5  test    r9, r9
0x180002ca8  jz      short loc_180002CEA
0x180002caa  mov     [r9], rcx
0x180002cad  test    rdx, rdx
0x180002cb0  jz      short loc_180002CD5
0x180002cb2  cmp     [rax], ecx
0x180002cb4  jnz     short loc_180002CCD
0x180002cb6  cmp     [rax+4], ecx
0x180002cb9  jnz     short loc_180002CCD
0x180002cbb  cmp     dword ptr [rax+8], 0C0h
0x180002cc2  jnz     short loc_180002CCD
0x180002cc4  cmp     dword ptr [rax+0Ch], 46000000h
0x180002ccb  jz      short loc_180002CD5
0x180002ccd  mov     r8d, 80040110h
0x180002cd3  jmp     short loc_180002CEA
0x180002cd5  mov     rdx, rax
0x180002cd8  mov     r8, r9
0x180002cdb  mov     rax, [r11+40h]
0x180002cdf  mov     rcx, r10
0x180002ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ce7  mov     r8d, eax
0x180002cea  mov     eax, r8d
0x180002ced  add     rsp, 28h
0x180002cf1  retn
```
