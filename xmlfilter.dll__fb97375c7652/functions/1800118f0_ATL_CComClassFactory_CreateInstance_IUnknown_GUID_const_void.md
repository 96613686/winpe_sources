# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800118f0`
- end: `0x180011952`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800118f0`
- `0x180017010`

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
0x1800118f0  sub     rsp, 28h
0x1800118f4  mov     r11, rcx
0x1800118f7  mov     rax, r8
0x1800118fa  xor     ecx, ecx
0x1800118fc  mov     r10, rdx
0x1800118ff  mov     r8d, 80004003h
0x180011905  test    r9, r9
0x180011908  jz      short loc_18001194A
0x18001190a  mov     [r9], rcx
0x18001190d  test    rdx, rdx
0x180011910  jz      short loc_180011935
0x180011912  cmp     [rax], ecx
0x180011914  jnz     short loc_18001192D
0x180011916  cmp     [rax+4], ecx
0x180011919  jnz     short loc_18001192D
0x18001191b  cmp     dword ptr [rax+8], 0C0h
0x180011922  jnz     short loc_18001192D
0x180011924  cmp     dword ptr [rax+0Ch], 46000000h
0x18001192b  jz      short loc_180011935
0x18001192d  mov     r8d, 80040110h
0x180011933  jmp     short loc_18001194A
0x180011935  mov     rdx, rax
0x180011938  mov     r8, r9
0x18001193b  mov     rax, [r11+40h]
0x18001193f  mov     rcx, r10
0x180011942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011947  mov     r8d, eax
0x18001194a  mov     eax, r8d
0x18001194d  add     rsp, 28h
0x180011951  retn
```
