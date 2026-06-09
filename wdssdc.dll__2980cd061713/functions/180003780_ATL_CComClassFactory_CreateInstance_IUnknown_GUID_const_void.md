# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003780`
- end: `0x1800037e3`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003780`
- `0x18000d010`

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
0x180003780  sub     rsp, 28h
0x180003784  mov     r11, rcx
0x180003787  mov     rax, r8
0x18000378a  xor     ecx, ecx
0x18000378c  mov     r10, rdx
0x18000378f  mov     r8d, 80004003h
0x180003795  test    r9, r9
0x180003798  jz      short loc_1800037DA
0x18000379a  mov     [r9], rcx
0x18000379d  test    rdx, rdx
0x1800037a0  jz      short loc_1800037C5
0x1800037a2  cmp     [rax], ecx
0x1800037a4  jnz     short loc_1800037BD
0x1800037a6  cmp     [rax+4], ecx
0x1800037a9  jnz     short loc_1800037BD
0x1800037ab  cmp     dword ptr [rax+8], 0C0h
0x1800037b2  jnz     short loc_1800037BD
0x1800037b4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800037bb  jz      short loc_1800037C5
0x1800037bd  mov     r8d, 80040110h
0x1800037c3  jmp     short loc_1800037DA
0x1800037c5  mov     rdx, rax
0x1800037c8  mov     r8, r9
0x1800037cb  mov     rax, [r11+40h]
0x1800037cf  mov     rcx, r10
0x1800037d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d7  mov     r8d, eax
0x1800037da  mov     eax, r8d
0x1800037dd  add     rsp, 28h
0x1800037e1  retn
```
