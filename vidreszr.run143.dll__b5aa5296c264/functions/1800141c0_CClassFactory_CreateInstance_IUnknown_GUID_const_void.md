# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800141c0`
- end: `0x1800142ab`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `235`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014410`

## callees

- `0x1800141c0`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax
  __int64 v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // rcx
  __int64 v11; // rax
  int v12; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2
    && (*(_QWORD *)&a3->Data1 != *(_QWORD *)&IID_IUnknown.Data1 || *(_QWORD *)a3->Data4 != *(_QWORD *)IID_IUnknown.Data4) )
  {
    return 2147500034LL;
  }
  v7 = *((_QWORD *)this + 1);
  v12 = 0;
  v8 = (_QWORD *)(*(__int64 (__fastcall **)(struct IUnknown *, int *))(v7 + 8))(a2, &v12);
  v9 = v8;
  if ( v8 )
  {
    v10 = v8;
    v11 = *v8;
    if ( v12 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(v11 + 8))(v10);
      v12 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v9)(v9, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(v11 + 24))(v10, 1);
    }
    return (unsigned int)v12;
  }
  else
  {
    result = (unsigned int)v12;
    if ( v12 >= 0 )
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800141c0  mov     [rsp+arg_0], rbx
0x1800141c5  mov     [rsp+arg_8], rsi
0x1800141ca  push    rdi
0x1800141cb  sub     rsp, 20h
0x1800141cf  mov     rsi, r8
0x1800141d2  mov     r8, rdx
0x1800141d5  mov     rdi, r9
0x1800141d8  test    r9, r9
0x1800141db  jnz     short loc_1800141E7
0x1800141dd  mov     eax, 80004003h
0x1800141e2  jmp     loc_18001429B
0x1800141e7  mov     qword ptr [r9], 0
0x1800141ee  test    r8, r8
0x1800141f1  jz      short loc_180014216
0x1800141f3  mov     rax, [rsi]
0x1800141f6  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800141fd  jnz     short loc_18001420C
0x1800141ff  mov     rax, [rsi+8]
0x180014203  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x18001420a  jz      short loc_180014216
0x18001420c  mov     eax, 80004002h
0x180014211  jmp     loc_18001429B
0x180014216  mov     rax, [rcx+8]
0x18001421a  lea     rdx, [rsp+28h+arg_18]
0x18001421f  mov     [rsp+28h+arg_18], 0
0x180014227  mov     rcx, r8
0x18001422a  mov     rax, [rax+8]
0x18001422e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014233  mov     rbx, rax
0x180014236  test    rax, rax
0x180014239  jnz     short loc_18001424A
0x18001423b  mov     eax, [rsp+28h+arg_18]
0x18001423f  test    eax, eax
0x180014241  js      short loc_18001429B
0x180014243  mov     eax, 8007000Eh
0x180014248  jmp     short loc_18001429B
0x18001424a  cmp     [rsp+28h+arg_18], 0
0x18001424f  mov     rcx, rbx
0x180014252  mov     rax, [rax]
0x180014255  jge     short loc_180014267
0x180014257  mov     rax, [rax+18h]
0x18001425b  mov     edx, 1
0x180014260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014265  jmp     short loc_180014297
0x180014267  mov     rax, [rax+8]
0x18001426b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014270  mov     rax, [rbx]
0x180014273  mov     r8, rdi
0x180014276  mov     rdx, rsi
0x180014279  mov     rcx, rbx
0x18001427c  mov     rax, [rax]
0x18001427f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014284  mov     [rsp+28h+arg_18], eax
0x180014288  mov     rcx, rbx
0x18001428b  mov     rax, [rbx]
0x18001428e  mov     rax, [rax+10h]
0x180014292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014297  mov     eax, [rsp+28h+arg_18]
0x18001429b  mov     rbx, [rsp+28h+arg_0]
0x1800142a0  mov     rsi, [rsp+28h+arg_8]
0x1800142a5  add     rsp, 20h
0x1800142a9  pop     rdi
0x1800142aa  retn
```
