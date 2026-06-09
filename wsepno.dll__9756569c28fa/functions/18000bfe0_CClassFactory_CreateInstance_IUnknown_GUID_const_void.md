# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000bfe0`
- end: `0x18000c019`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `57`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000bfe0`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall *v5)(const struct _GUID *, void **); // rax

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  v5 = (__int64 (__fastcall *)(const struct _GUID *, void **))*((_QWORD *)this + 2);
  if ( v5 )
    return v5(a3, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000bfe0  test    r9, r9
0x18000bfe3  jnz     short loc_18000BFEC
0x18000bfe5  mov     eax, 80004003h
0x18000bfea  jmp     short locret_18000C018
0x18000bfec  mov     qword ptr [r9], 0
0x18000bff3  test    rdx, rdx
0x18000bff6  jz      short loc_18000BFFF
0x18000bff8  mov     eax, 80040110h
0x18000bffd  jmp     short locret_18000C018
0x18000bfff  mov     rax, [rcx+10h]
0x18000c003  test    rax, rax
0x18000c006  jz      short loc_18000C013
0x18000c008  mov     rdx, r9
0x18000c00b  mov     rcx, r8
0x18000c00e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18000c013  mov     eax, 80004005h
0x18000c018  retn
```
