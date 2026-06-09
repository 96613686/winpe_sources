# CConnectionPoint::OnCompleted(long,IDispatch *,IDispatch *,IDispatch *)

- ea: `0x180027d08`
- end: `0x180027ef5`
- name: `?OnCompleted@CConnectionPoint@@QEAAXJPEAUIDispatch@@00@Z`
- size: `493`
- prototype: `void __fastcall(CConnectionPoint *__hidden this, int, struct IDispatch *, struct IDispatch *, struct IDispatch *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180027f00`

## callees

- `0x180027d08`
- `0x180034090`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180027dae`
- `OLEAUT32!__imp_VariantInit` at `0x180027dc5`
- `OLEAUT32!__imp_VariantInit` at `0x180027e35`
- `OLEAUT32!__imp_VariantInit` at `0x180027e4c`
- `OLEAUT32!__imp_VariantInit` at `0x180027e63`
- `OLEAUT32!__imp_VariantInit` at `0x180027dae`
- `OLEAUT32!__imp_VariantInit` at `0x180027dc5`
- `OLEAUT32!__imp_VariantInit` at `0x180027e35`
- `OLEAUT32!__imp_VariantInit` at `0x180027e4c`
- `OLEAUT32!__imp_VariantInit` at `0x180027e63`

## pseudocode

```c
void __fastcall CConnectionPoint::OnCompleted(
        CConnectionPoint *this,
        LONG a2,
        struct IDispatch *a3,
        struct IDispatch *a4,
        struct IDispatch *a5)
{
  int i; // ebx
  int (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // [rsp+20h] [rbp-E0h]
  __int64 v12; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v13[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v14[3]; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v16; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v17; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v18; // [rsp+D8h] [rbp-28h] BYREF
  VARIANTARG v19; // [rsp+F0h] [rbp-10h] BYREF

  v12 = 0;
  for ( i = 0; i < *((_DWORD *)this + 12); ++i )
  {
    v10 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 8) + 8LL * i);
    if ( v10 && (**v10)(v10, &IID_IDispatch, &v12) >= 0 )
    {
      if ( a3 )
      {
        v13[1] = 0;
        v13[0] = &pvarg;
        v13[2] = 2;
        VariantInit(&pvarg);
        pvarg.llVal = (LONGLONG)a5;
        pvarg.vt = 9;
        VariantInit(&v16);
        v16.vt = 9;
        v16.llVal = (LONGLONG)a3;
        LOWORD(v11) = 1;
        (*(void (__fastcall **)(__int64, __int64, GUID *, __int64, int, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
          v12,
          4,
          &GUID_NULL,
          2048,
          v11,
          v13,
          0,
          0,
          0);
      }
      v14[1] = 0;
      v14[0] = &v17;
      v14[2] = 3;
      VariantInit(&v17);
      v17.llVal = (LONGLONG)a5;
      v17.vt = 9;
      VariantInit(&v18);
      v18.llVal = (LONGLONG)a4;
      v18.vt = 9;
      VariantInit(&v19);
      v19.vt = 3;
      v19.lVal = a2;
      LOWORD(v11) = 1;
      (*(void (__fastcall **)(__int64, __int64, GUID *, __int64, int, _QWORD *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
        v12,
        2,
        &GUID_NULL,
        2048,
        v11,
        v14,
        0,
        0,
        0);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
}

```

## disassembly

```asm
0x180027d08  push    rbp
0x180027d0a  push    rbx
0x180027d0b  push    rsi
0x180027d0c  push    rdi
0x180027d0d  push    r12
0x180027d0f  push    r13
0x180027d11  push    r14
0x180027d13  push    r15
0x180027d15  lea     rbp, [rsp-28h]
0x180027d1a  sub     rsp, 128h
0x180027d21  mov     rax, cs:__security_cookie
0x180027d28  xor     rax, rsp
0x180027d2b  mov     [rbp+60h+var_50], rax
0x180027d2f  xor     r13d, r13d
0x180027d32  mov     r15, r9
0x180027d35  mov     rsi, r8
0x180027d38  mov     r12d, edx
0x180027d3b  mov     rdi, rcx
0x180027d3e  mov     [rsp+160h+var_110], r13
0x180027d43  mov     ebx, r13d
0x180027d46  cmp     [rcx+30h], r13d
0x180027d4a  jle     loc_180027ED5
0x180027d50  mov     r14, [rbp+60h+arg_20]
0x180027d57  mov     rax, [rdi+40h]
0x180027d5b  movsxd  rcx, ebx
0x180027d5e  mov     rcx, [rax+rcx*8]
0x180027d62  test    rcx, rcx
0x180027d65  jz      loc_180027ECA
0x180027d6b  mov     rax, [rcx]
0x180027d6e  lea     r8, [rsp+160h+var_110]
0x180027d73  lea     rdx, IID_IDispatch
0x180027d7a  mov     rax, [rax]
0x180027d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d82  test    eax, eax
0x180027d84  js      loc_180027ECA
0x180027d8a  test    rsi, rsi
0x180027d8d  jz      loc_180027E1B
0x180027d93  lea     rax, [rbp+60h+pvarg]
0x180027d97  mov     [rsp+160h+var_100], r13
0x180027d9c  lea     rcx, [rbp+60h+pvarg]; pvarg
0x180027da0  mov     [rsp+160h+var_108], rax
0x180027da5  mov     [rsp+160h+var_F8], 2
0x180027dae  call    cs:__imp_VariantInit
0x180027db4  mov     eax, 9
0x180027db9  mov     qword ptr [rbp+60h+pvarg+8], r14
0x180027dbd  lea     rcx, [rbp+60h+var_C0]; pvarg
0x180027dc1  mov     word ptr [rbp+60h+pvarg], ax
0x180027dc5  call    cs:__imp_VariantInit
0x180027dcb  mov     rcx, [rsp+160h+var_110]
0x180027dd0  lea     rdx, [rsp+160h+var_108]
0x180027dd5  mov     [rsp+160h+var_120], r13
0x180027dda  lea     r8, GUID_NULL
0x180027de1  mov     [rsp+160h+var_128], r13
0x180027de6  mov     eax, 9
0x180027deb  mov     word ptr [rbp+60h+var_C0], ax
0x180027def  mov     r9d, 800h
0x180027df5  mov     qword ptr [rbp+60h+var_C0+8], rsi
0x180027df9  mov     rax, [rcx]
0x180027dfc  mov     [rsp+160h+var_130], r13
0x180027e01  mov     [rsp+160h+var_138], rdx
0x180027e06  mov     edx, 4
0x180027e0b  mov     [rsp+160h+var_140], 1
0x180027e12  mov     rax, [rax+30h]
0x180027e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e1b  lea     rax, [rbp+60h+var_A0]
0x180027e1f  mov     [rsp+160h+var_E8], r13
0x180027e24  lea     rcx, [rbp+60h+var_A0]; pvarg
0x180027e28  mov     [rsp+160h+var_F0], rax
0x180027e2d  mov     [rbp+60h+var_E0], 3
0x180027e35  call    cs:__imp_VariantInit
0x180027e3b  mov     eax, 9
0x180027e40  mov     qword ptr [rbp+60h+var_A0+8], r14
0x180027e44  lea     rcx, [rbp+60h+var_88]; pvarg
0x180027e48  mov     word ptr [rbp+60h+var_A0], ax
0x180027e4c  call    cs:__imp_VariantInit
0x180027e52  mov     eax, 9
0x180027e57  mov     qword ptr [rbp+60h+var_88+8], r15
0x180027e5b  lea     rcx, [rbp+60h+var_70]; pvarg
0x180027e5f  mov     word ptr [rbp+60h+var_88], ax
0x180027e63  call    cs:__imp_VariantInit
0x180027e69  mov     rcx, [rsp+160h+var_110]
0x180027e6e  lea     rdx, [rsp+160h+var_F0]
0x180027e73  mov     [rsp+160h+var_120], r13
0x180027e78  lea     r8, GUID_NULL
0x180027e7f  mov     [rsp+160h+var_128], r13
0x180027e84  mov     eax, 3
0x180027e89  mov     word ptr [rbp+60h+var_70], ax
0x180027e8d  mov     r9d, 800h
0x180027e93  mov     dword ptr [rbp+60h+var_70+8], r12d
0x180027e97  mov     rax, [rcx]
0x180027e9a  mov     [rsp+160h+var_130], r13
0x180027e9f  mov     [rsp+160h+var_138], rdx
0x180027ea4  mov     edx, 2
0x180027ea9  mov     [rsp+160h+var_140], 1
0x180027eb0  mov     rax, [rax+30h]
0x180027eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eb9  mov     rcx, [rsp+160h+var_110]
0x180027ebe  mov     rax, [rcx]
0x180027ec1  mov     rax, [rax+10h]
0x180027ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eca  inc     ebx
0x180027ecc  cmp     ebx, [rdi+30h]
0x180027ecf  jl      loc_180027D57
0x180027ed5  mov     rcx, [rbp+60h+var_50]
0x180027ed9  xor     rcx, rsp; StackCookie
0x180027edc  call    __security_check_cookie
0x180027ee1  add     rsp, 128h
0x180027ee8  pop     r15
0x180027eea  pop     r14
0x180027eec  pop     r13
0x180027eee  pop     r12
0x180027ef0  pop     rdi
0x180027ef1  pop     rsi
0x180027ef2  pop     rbx
0x180027ef3  pop     rbp
0x180027ef4  retn
```
