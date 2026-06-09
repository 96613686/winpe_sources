# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004600`
- end: `0x180004654`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `int(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004600`
- `0x180004ab4`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        __int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v4; // r11
  struct IUnknown *v5; // r10
  __int64 result; // rax

  v4 = a3;
  v5 = a2;
  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( !a2 || (unsigned int)ATL::InlineIsEqualUnknown(a3) )
      return this[8](v5, v4, a4);
    else
      return 2147746064LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004600  push    rbx
0x180004602  sub     rsp, 20h
0x180004606  mov     r11, r8
0x180004609  mov     r10, rdx
0x18000460c  mov     rbx, rcx
0x18000460f  mov     eax, 80004003h
0x180004614  test    r9, r9
0x180004617  jz      short loc_18000464E
0x180004619  mov     qword ptr [r9], 0
0x180004620  test    rdx, rdx
0x180004623  jz      short loc_18000463C
0x180004625  mov     rcx, r8; struct _GUID *
0x180004628  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000462d  test    eax, eax
0x18000462f  jnz     short loc_18000463C
0x180004631  mov     eax, 80040110h
0x180004636  add     rsp, 20h
0x18000463a  pop     rbx
0x18000463b  retn
0x18000463c  mov     rax, [rbx+40h]
0x180004640  mov     r8, r9
0x180004643  mov     rdx, r11
0x180004646  mov     rcx, r10
0x180004649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000464e  add     rsp, 20h
0x180004652  pop     rbx
0x180004653  retn
```
