# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002090`
- end: `0x180002148`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `184`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002090`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 (__fastcall ***v6)(_QWORD, const struct _GUID *, void **); // rax
  __int64 (__fastcall ***v7)(_QWORD, const struct _GUID *, void **); // rdi
  unsigned int v8; // ebx
  __int64 v10; // rax

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
  {
    v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v10 )
      return 2147746064LL;
  }
  v6 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))(*(__int64 (__fastcall **)(struct IUnknown *))(*((_QWORD *)this + 2) + 16LL))(a2);
  v7 = v6;
  if ( !v6 )
    return 2147942414LL;
  v8 = (**v6)(v6, a3, a4);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v7)[2])(v7);
  return v8;
}

```

## disassembly

```asm
0x180002090  mov     [rsp+arg_8], rbx
0x180002095  push    rsi
0x180002096  sub     rsp, 20h
0x18000209a  mov     rbx, r9
0x18000209d  mov     rsi, r8
0x1800020a0  test    r9, r9
0x1800020a3  jz      short loc_180002105
0x1800020a5  mov     qword ptr [r9], 0
0x1800020ac  test    rdx, rdx
0x1800020af  jnz     short loc_180002115
0x1800020b1  mov     rax, [rcx+10h]
0x1800020b5  mov     rcx, rdx
0x1800020b8  mov     [rsp+28h+arg_0], rdi
0x1800020bd  mov     rax, [rax+10h]
0x1800020c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c6  mov     rdi, rax
0x1800020c9  test    rax, rax
0x1800020cc  jz      short loc_180002141
0x1800020ce  mov     rax, [rax]
0x1800020d1  mov     r8, rbx
0x1800020d4  mov     rdx, rsi
0x1800020d7  mov     rcx, rdi
0x1800020da  mov     rax, [rax]
0x1800020dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e2  mov     rcx, [rdi]
0x1800020e5  mov     ebx, eax
0x1800020e7  mov     rax, [rcx+10h]
0x1800020eb  mov     rcx, rdi
0x1800020ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f3  mov     eax, ebx
0x1800020f5  mov     rdi, [rsp+28h+arg_0]
0x1800020fa  mov     rbx, [rsp+28h+arg_8]
0x1800020ff  add     rsp, 20h
0x180002103  pop     rsi
0x180002104  retn
0x180002105  mov     eax, 80004003h
0x18000210a  mov     rbx, [rsp+28h+arg_8]
0x18000210f  add     rsp, 20h
0x180002113  pop     rsi
0x180002114  retn
0x180002115  mov     rax, [r8]
0x180002118  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000211f  jnz     short loc_18000212C
0x180002121  mov     rax, [r8+8]
0x180002125  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000212c  test    rax, rax
0x18000212f  jz      short loc_1800020B1
0x180002131  mov     rbx, [rsp+28h+arg_8]
0x180002136  mov     eax, 80040110h
0x18000213b  add     rsp, 20h
0x18000213f  pop     rsi
0x180002140  retn
0x180002141  mov     eax, 8007000Eh
0x180002146  jmp     short loc_1800020F5
```
