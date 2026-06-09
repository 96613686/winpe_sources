# CUWFCspClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000fdd0`
- end: `0x18000fe50`
- name: `?CreateInstance@CUWFCspClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: `__int64 __fastcall(CUWFCspClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000fdd0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CUWFCspClassFactory::CreateInstance(
        CUWFCspClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  __int64 (__fastcall ***v7)(_QWORD, const struct _GUID *, void **); // rax
  __int64 (__fastcall ***v8)(_QWORD, const struct _GUID *, void **); // rsi

  if ( a2 )
  {
    v6 = -2147221232;
    if ( a4 )
      *a4 = 0;
  }
  else
  {
    v7 = (__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))(*(__int64 (**)(void))(*((_QWORD *)this + 2)
                                                                                               + 8LL))();
    v8 = v7;
    if ( v7 )
    {
      v6 = (**v7)(v7, a3, a4);
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **)))(*v8)[2])(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000fdd0  mov     [rsp+arg_0], rbx
0x18000fdd5  mov     [rsp+arg_8], rsi
0x18000fdda  push    rdi
0x18000fddb  sub     rsp, 20h
0x18000fddf  mov     rdi, r9
0x18000fde2  mov     rbx, r8
0x18000fde5  test    rdx, rdx
0x18000fde8  jz      short loc_18000FDFD
0x18000fdea  mov     ebx, 80040110h
0x18000fdef  test    r9, r9
0x18000fdf2  jz      short loc_18000FE3E
0x18000fdf4  mov     qword ptr [r9], 0
0x18000fdfb  jmp     short loc_18000FE3E
0x18000fdfd  mov     rax, [rcx+10h]
0x18000fe01  mov     rax, [rax+8]
0x18000fe05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe0a  mov     rsi, rax
0x18000fe0d  test    rax, rax
0x18000fe10  jz      short loc_18000FE39
0x18000fe12  mov     rax, [rax]
0x18000fe15  mov     r8, rdi
0x18000fe18  mov     rdx, rbx
0x18000fe1b  mov     rcx, rsi
0x18000fe1e  mov     rax, [rax]
0x18000fe21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe26  mov     rcx, [rsi]
0x18000fe29  mov     ebx, eax
0x18000fe2b  mov     rax, [rcx+10h]
0x18000fe2f  mov     rcx, rsi
0x18000fe32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe37  jmp     short loc_18000FE3E
0x18000fe39  mov     ebx, 8007000Eh
0x18000fe3e  mov     rsi, [rsp+28h+arg_8]
0x18000fe43  mov     eax, ebx
0x18000fe45  mov     rbx, [rsp+28h+arg_0]
0x18000fe4a  add     rsp, 20h
0x18000fe4e  pop     rdi
0x18000fe4f  retn
```
