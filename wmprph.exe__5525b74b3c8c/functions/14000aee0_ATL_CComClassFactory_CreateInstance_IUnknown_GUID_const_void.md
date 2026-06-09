# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x14000aee0`
- end: `0x14000af42`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000aee0`
- `0x14000f010`

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
      return this[7](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14000aee0  sub     rsp, 28h
0x14000aee4  mov     r11, rcx
0x14000aee7  mov     rax, r8
0x14000aeea  xor     ecx, ecx
0x14000aeec  mov     r10, rdx
0x14000aeef  mov     r8d, 80004003h
0x14000aef5  test    r9, r9
0x14000aef8  jz      short loc_14000AF3A
0x14000aefa  mov     [r9], rcx
0x14000aefd  test    rdx, rdx
0x14000af00  jz      short loc_14000AF25
0x14000af02  cmp     [rax], ecx
0x14000af04  jnz     short loc_14000AF1D
0x14000af06  cmp     [rax+4], ecx
0x14000af09  jnz     short loc_14000AF1D
0x14000af0b  cmp     dword ptr [rax+8], 0C0h
0x14000af12  jnz     short loc_14000AF1D
0x14000af14  cmp     dword ptr [rax+0Ch], 46000000h
0x14000af1b  jz      short loc_14000AF25
0x14000af1d  mov     r8d, 80040110h
0x14000af23  jmp     short loc_14000AF3A
0x14000af25  mov     rdx, rax
0x14000af28  mov     r8, r9
0x14000af2b  mov     rax, [r11+38h]
0x14000af2f  mov     rcx, r10
0x14000af32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000af37  mov     r8d, eax
0x14000af3a  mov     eax, r8d
0x14000af3d  add     rsp, 28h
0x14000af41  retn
```
