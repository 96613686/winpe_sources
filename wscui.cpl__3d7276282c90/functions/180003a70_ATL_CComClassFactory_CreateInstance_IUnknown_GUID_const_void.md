# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003a70`
- end: `0x180003ac4`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `int(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003a70`
- `0x180003c4c`
- `0x18000c010`

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
0x180003a70  push    rbx
0x180003a72  sub     rsp, 20h
0x180003a76  mov     r11, r8
0x180003a79  mov     r10, rdx
0x180003a7c  mov     rbx, rcx
0x180003a7f  mov     eax, 80004003h
0x180003a84  test    r9, r9
0x180003a87  jz      short loc_180003ABE
0x180003a89  mov     qword ptr [r9], 0
0x180003a90  test    rdx, rdx
0x180003a93  jz      short loc_180003AAC
0x180003a95  mov     rcx, r8; struct _GUID *
0x180003a98  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180003a9d  test    eax, eax
0x180003a9f  jnz     short loc_180003AAC
0x180003aa1  mov     eax, 80040110h
0x180003aa6  add     rsp, 20h
0x180003aaa  pop     rbx
0x180003aab  retn
0x180003aac  mov     rax, [rbx+40h]
0x180003ab0  mov     r8, r9
0x180003ab3  mov     rdx, r11
0x180003ab6  mov     rcx, r10
0x180003ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003abe  add     rsp, 20h
0x180003ac2  pop     rbx
0x180003ac3  retn
```
