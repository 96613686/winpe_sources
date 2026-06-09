# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800082a0`
- end: `0x180008302`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800082a0`
- `0x180016010`

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
0x1800082a0  sub     rsp, 28h
0x1800082a4  mov     r11, rcx
0x1800082a7  mov     rax, r8
0x1800082aa  xor     ecx, ecx
0x1800082ac  mov     r10, rdx
0x1800082af  mov     r8d, 80004003h
0x1800082b5  test    r9, r9
0x1800082b8  jz      short loc_1800082FA
0x1800082ba  mov     [r9], rcx
0x1800082bd  test    rdx, rdx
0x1800082c0  jz      short loc_1800082E5
0x1800082c2  cmp     [rax], ecx
0x1800082c4  jnz     short loc_1800082DD
0x1800082c6  cmp     [rax+4], ecx
0x1800082c9  jnz     short loc_1800082DD
0x1800082cb  cmp     dword ptr [rax+8], 0C0h
0x1800082d2  jnz     short loc_1800082DD
0x1800082d4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800082db  jz      short loc_1800082E5
0x1800082dd  mov     r8d, 80040110h
0x1800082e3  jmp     short loc_1800082FA
0x1800082e5  mov     rdx, rax
0x1800082e8  mov     r8, r9
0x1800082eb  mov     rax, [r11+40h]
0x1800082ef  mov     rcx, r10
0x1800082f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f7  mov     r8d, eax
0x1800082fa  mov     eax, r8d
0x1800082fd  add     rsp, 28h
0x180008301  retn
```
