# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a310`
- end: `0x18000a3b6`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `166`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a310`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v7; // rax
  __int64 (__fastcall ***v8)(_QWORD, const struct _GUID *, void **); // rax
  __int64 (__fastcall ***v9)(_QWORD, const struct _GUID *, void **); // rsi
  unsigned int v10; // ebx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
  {
    v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v7 )
      return 2147746064LL;
  }
  v8 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))(*(__int64 (__fastcall **)(struct IUnknown *))(*((_QWORD *)this + 2) + 16LL))(a2);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v10 = (**v8)(v8, a3, a4);
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v9)[2])(v9);
  return v10;
}

```

## disassembly

```asm
0x18000a310  mov     [rsp+arg_0], rbx
0x18000a315  mov     [rsp+arg_8], rsi
0x18000a31a  push    rdi
0x18000a31b  sub     rsp, 20h
0x18000a31f  mov     rbx, r9
0x18000a322  mov     rdi, r8
0x18000a325  test    r9, r9
0x18000a328  jnz     short loc_18000A331
0x18000a32a  mov     eax, 80004003h
0x18000a32f  jmp     short loc_18000A3A6
0x18000a331  mov     qword ptr [r9], 0
0x18000a338  test    rdx, rdx
0x18000a33b  jz      short loc_18000A360
0x18000a33d  mov     rax, [r8]
0x18000a340  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18000a347  jnz     short loc_18000A354
0x18000a349  mov     rax, [r8+8]
0x18000a34d  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18000a354  test    rax, rax
0x18000a357  jz      short loc_18000A360
0x18000a359  mov     eax, 80040110h
0x18000a35e  jmp     short loc_18000A3A6
0x18000a360  mov     rax, [rcx+10h]
0x18000a364  mov     rcx, rdx
0x18000a367  mov     rax, [rax+10h]
0x18000a36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a370  mov     rsi, rax
0x18000a373  test    rax, rax
0x18000a376  jnz     short loc_18000A37F
0x18000a378  mov     eax, 8007000Eh
0x18000a37d  jmp     short loc_18000A3A6
0x18000a37f  mov     rax, [rax]
0x18000a382  mov     r8, rbx
0x18000a385  mov     rdx, rdi
0x18000a388  mov     rcx, rsi
0x18000a38b  mov     rax, [rax]
0x18000a38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a393  mov     rcx, [rsi]
0x18000a396  mov     ebx, eax
0x18000a398  mov     rax, [rcx+10h]
0x18000a39c  mov     rcx, rsi
0x18000a39f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a4  mov     eax, ebx
0x18000a3a6  mov     rbx, [rsp+28h+arg_0]
0x18000a3ab  mov     rsi, [rsp+28h+arg_8]
0x18000a3b0  add     rsp, 20h
0x18000a3b4  pop     rdi
0x18000a3b5  retn
```
