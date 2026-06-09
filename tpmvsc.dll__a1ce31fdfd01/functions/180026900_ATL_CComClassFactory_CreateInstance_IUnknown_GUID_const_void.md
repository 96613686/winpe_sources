# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180026900`
- end: `0x180026954`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180026900`
- `0x18002698c`
- `0x180037010`

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
0x180026900  push    rbx
0x180026902  sub     rsp, 20h
0x180026906  mov     r11, r8
0x180026909  mov     r10, rdx
0x18002690c  mov     rbx, rcx
0x18002690f  mov     eax, 80004003h
0x180026914  test    r9, r9
0x180026917  jz      short loc_18002694E
0x180026919  mov     qword ptr [r9], 0
0x180026920  test    rdx, rdx
0x180026923  jz      short loc_18002693C
0x180026925  mov     rcx, r8; struct _GUID *
0x180026928  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18002692d  test    eax, eax
0x18002692f  jnz     short loc_18002693C
0x180026931  mov     eax, 80040110h
0x180026936  add     rsp, 20h
0x18002693a  pop     rbx
0x18002693b  retn
0x18002693c  mov     rax, [rbx+40h]
0x180026940  mov     r8, r9
0x180026943  mov     rdx, r11
0x180026946  mov     rcx, r10
0x180026949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002694e  add     rsp, 20h
0x180026952  pop     rbx
0x180026953  retn
```
