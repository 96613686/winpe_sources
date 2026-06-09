# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180005e90`
- end: `0x180005ecd`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `61`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005e90`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        __int64 (__fastcall **this)(const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax

  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  result = 2147549183LL;
  if ( this[2] )
    return this[2](a3, a4);
  return result;
}

```

## disassembly

```asm
0x180005e90  sub     rsp, 28h
0x180005e94  mov     qword ptr [r9], 0
0x180005e9b  mov     r10, rcx
0x180005e9e  test    rdx, rdx
0x180005ea1  jz      short loc_180005EAD
0x180005ea3  mov     eax, 80040110h
0x180005ea8  add     rsp, 28h
0x180005eac  retn
0x180005ead  cmp     qword ptr [rcx+10h], 0
0x180005eb2  mov     eax, 8000FFFFh
0x180005eb7  jz      short loc_180005EC8
0x180005eb9  mov     rax, [r10+10h]
0x180005ebd  mov     rdx, r9
0x180005ec0  mov     rcx, r8
0x180005ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec8  add     rsp, 28h
0x180005ecc  retn
```
