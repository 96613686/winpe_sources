# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140003ed0`
- end: `0x140003f32`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003ed0`
- `0x140016010`

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
0x140003ed0  sub     rsp, 28h
0x140003ed4  mov     r11, rcx
0x140003ed7  mov     rax, r8
0x140003eda  xor     ecx, ecx
0x140003edc  mov     r10, rdx
0x140003edf  mov     r8d, 80004003h
0x140003ee5  test    r9, r9
0x140003ee8  jz      short loc_140003F2A
0x140003eea  mov     [r9], rcx
0x140003eed  test    rdx, rdx
0x140003ef0  jz      short loc_140003F15
0x140003ef2  cmp     [rax], ecx
0x140003ef4  jnz     short loc_140003F0D
0x140003ef6  cmp     [rax+4], ecx
0x140003ef9  jnz     short loc_140003F0D
0x140003efb  cmp     dword ptr [rax+8], 0C0h
0x140003f02  jnz     short loc_140003F0D
0x140003f04  cmp     dword ptr [rax+0Ch], 46000000h
0x140003f0b  jz      short loc_140003F15
0x140003f0d  mov     r8d, 80040110h
0x140003f13  jmp     short loc_140003F2A
0x140003f15  mov     rdx, rax
0x140003f18  mov     r8, r9
0x140003f1b  mov     rax, [r11+40h]
0x140003f1f  mov     rcx, r10
0x140003f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f27  mov     r8d, eax
0x140003f2a  mov     eax, r8d
0x140003f2d  add     rsp, 28h
0x140003f31  retn
```
