# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800098c0`
- end: `0x1800098f3`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `51`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800098c0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  __int64 (__fastcall *v6)(const struct _GUID *, void **); // r8

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v6 = (__int64 (__fastcall *)(const struct _GUID *, void **))*((_QWORD *)this + 2);
  result = 2147549183LL;
  if ( v6 )
    return v6(a3, a4);
  return result;
}

```

## disassembly

```asm
0x1800098c0  mov     qword ptr [r9], 0
0x1800098c7  mov     r10, r8
0x1800098ca  test    rdx, rdx
0x1800098cd  jz      short loc_1800098D6
0x1800098cf  mov     eax, 80040110h
0x1800098d4  jmp     short locret_1800098F2
0x1800098d6  mov     r8, [rcx+10h]
0x1800098da  mov     eax, 8000FFFFh
0x1800098df  test    r8, r8
0x1800098e2  jz      short locret_1800098F2
0x1800098e4  mov     rdx, r9
0x1800098e7  mov     rcx, r10
0x1800098ea  mov     rax, r8
0x1800098ed  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1800098f2  retn
```
