# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800063a0`
- end: `0x1800063f4`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800063a0`
- `0x180007200`
- `0x180012010`

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
0x1800063a0  push    rbx
0x1800063a2  sub     rsp, 20h
0x1800063a6  mov     r11, r8
0x1800063a9  mov     r10, rdx
0x1800063ac  mov     rbx, rcx
0x1800063af  mov     eax, 80004003h
0x1800063b4  test    r9, r9
0x1800063b7  jz      short loc_1800063EE
0x1800063b9  mov     qword ptr [r9], 0
0x1800063c0  test    rdx, rdx
0x1800063c3  jz      short loc_1800063DC
0x1800063c5  mov     rcx, r8; struct _GUID *
0x1800063c8  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x1800063cd  test    eax, eax
0x1800063cf  jnz     short loc_1800063DC
0x1800063d1  mov     eax, 80040110h
0x1800063d6  add     rsp, 20h
0x1800063da  pop     rbx
0x1800063db  retn
0x1800063dc  mov     rax, [rbx+40h]
0x1800063e0  mov     r8, r9
0x1800063e3  mov     rdx, r11
0x1800063e6  mov     rcx, r10
0x1800063e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ee  add     rsp, 20h
0x1800063f2  pop     rbx
0x1800063f3  retn
```
