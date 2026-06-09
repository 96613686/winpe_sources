# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180013e20`
- end: `0x180013e82`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013e20`
- `0x180020010`

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
0x180013e20  sub     rsp, 28h
0x180013e24  mov     r11, rcx
0x180013e27  mov     rax, r8
0x180013e2a  xor     ecx, ecx
0x180013e2c  mov     r10, rdx
0x180013e2f  mov     r8d, 80004003h
0x180013e35  test    r9, r9
0x180013e38  jz      short loc_180013E7A
0x180013e3a  mov     [r9], rcx
0x180013e3d  test    rdx, rdx
0x180013e40  jz      short loc_180013E65
0x180013e42  cmp     [rax], ecx
0x180013e44  jnz     short loc_180013E5D
0x180013e46  cmp     [rax+4], ecx
0x180013e49  jnz     short loc_180013E5D
0x180013e4b  cmp     dword ptr [rax+8], 0C0h
0x180013e52  jnz     short loc_180013E5D
0x180013e54  cmp     dword ptr [rax+0Ch], 46000000h
0x180013e5b  jz      short loc_180013E65
0x180013e5d  mov     r8d, 80040110h
0x180013e63  jmp     short loc_180013E7A
0x180013e65  mov     rdx, rax
0x180013e68  mov     r8, r9
0x180013e6b  mov     rax, [r11+40h]
0x180013e6f  mov     rcx, r10
0x180013e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e77  mov     r8d, eax
0x180013e7a  mov     eax, r8d
0x180013e7d  add     rsp, 28h
0x180013e81  retn
```
