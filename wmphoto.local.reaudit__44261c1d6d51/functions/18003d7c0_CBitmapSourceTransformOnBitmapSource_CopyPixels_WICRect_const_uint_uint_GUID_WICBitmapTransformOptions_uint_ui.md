# CBitmapSourceTransformOnBitmapSource::CopyPixels(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)

- ea: `0x18003d7c0`
- end: `0x18003db5c`
- name: `?CopyPixels@CBitmapSourceTransformOnBitmapSource@@UEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z`
- size: `924`
- prototype: `__int64 __fastcall(CBitmapSourceTransformOnBitmapSource *__hidden this, const struct WICRect *, unsigned int, unsigned int, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180035a50`
- `0x180036420`
- `0x18003d074`
- `0x18003d0a0`
- `0x18003d7c0`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CBitmapSourceTransformOnBitmapSource::CopyPixels(
        CBitmapSourceTransformOnBitmapSource *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        struct _GUID *a5,
        enum WICBitmapTransformOptions a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int8 *a9)
{
  __int64 v9; // rdi
  __int64 v13; // rcx
  int v14; // ebx
  __int64 v15; // rbx
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  const struct WICRect *v18; // r15
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, __int64 *); // rbx
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, __int64 *); // rbx
  __int64 v23; // rsi
  __int64 (__fastcall *v24)(__int64, __int64 *); // rbx
  __int64 v25; // rbx
  __int64 v27; // [rsp+40h] [rbp-61h] BYREF
  __int64 v28; // [rsp+48h] [rbp-59h] BYREF
  __int64 v29; // [rsp+50h] [rbp-51h] BYREF
  int v30; // [rsp+58h] [rbp-49h] BYREF
  int v31; // [rsp+5Ch] [rbp-45h] BYREF
  const struct WICRect *v32; // [rsp+60h] [rbp-41h]
  unsigned __int8 *v33; // [rsp+68h] [rbp-39h]
  __int128 v34; // [rsp+70h] [rbp-31h] BYREF
  __int128 v35; // [rsp+80h] [rbp-21h] BYREF

  v9 = *((_QWORD *)this + 6);
  v33 = a9;
  v29 = v9;
  v32 = a2;
  Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(&v29);
  v13 = *((_QWORD *)this + 6);
  v35 = 0;
  v30 = 0;
  v34 = 0;
  v31 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v13 + 32LL))(v13, &v35);
  if ( v14 < 0 )
    goto LABEL_27;
  v14 = (*(__int64 (__fastcall **)(_QWORD, int *, int *))(**((_QWORD **)this + 6) + 24LL))(
          *((_QWORD *)this + 6),
          &v30,
          &v31);
  if ( v14 < 0 )
    goto LABEL_27;
  if ( a3 == v30 && a4 == v31 )
  {
    v15 = v9;
  }
  else
  {
    v27 = 0;
    v16 = *((_QWORD *)this + 7);
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 88LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v14 = v17(v16, &v27);
    if ( v14 < 0 )
      goto LABEL_17;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int))(*(_QWORD *)v27 + 64LL))(v27, v9, a3, a4, 3);
    if ( v14 < 0 )
      goto LABEL_17;
    v15 = v27;
    v28 = v27;
    Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(&v28);
    v28 = v9;
    v9 = v15;
    v29 = v15;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  }
  v18 = v32;
  if ( v32 )
  {
    v19 = *((_QWORD *)this + 7);
    v27 = 0;
    v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 96LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    v14 = v20(v19, &v27);
    if ( v14 < 0 )
      goto LABEL_17;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, const struct WICRect *))(*(_QWORD *)v27 + 64LL))(v27, v9, v18);
    if ( v14 < 0 )
      goto LABEL_17;
    v15 = v27;
    v28 = v27;
    Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(&v28);
    v28 = v9;
    v9 = v15;
    v29 = v15;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  }
  if ( a6 == WICBitmapTransformRotate0 )
    goto LABEL_20;
  v21 = *((_QWORD *)this + 7);
  v27 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v14 = v22(v21, &v27);
  if ( v14 < 0
    || (v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v27 + 64LL))(v27, v9, (unsigned int)a6),
        v14 < 0) )
  {
LABEL_17:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    goto LABEL_27;
  }
  v15 = v27;
  v28 = v27;
  Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(&v28);
  v28 = v9;
  v9 = v15;
  v29 = v15;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
LABEL_20:
  v14 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v15 + 32LL))(v15, &v34);
  if ( v14 >= 0 )
  {
    if ( v34 == *(_OWORD *)a5 )
    {
LABEL_26:
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, unsigned __int8 *))(*(_QWORD *)v9 + 56LL))(
              v9,
              0,
              a7,
              a8,
              v33);
      goto LABEL_27;
    }
    v23 = *((_QWORD *)this + 7);
    v27 = 0;
    v24 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 80LL);
    Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(&v27);
    v14 = v24(v23, &v27);
    if ( v14 >= 0 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64, __int64, struct _GUID *, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v27 + 64LL))(
              v27,
              v9,
              a5,
              0,
              0,
              0,
              0);
      if ( v14 >= 0 )
      {
        v25 = v27;
        v28 = v27;
        Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(&v28);
        v28 = v9;
        v9 = v25;
        v29 = v25;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
        Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(&v27);
        goto LABEL_26;
      }
    }
    Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(&v27);
  }
LABEL_27:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003d7c0  push    rbp
0x18003d7c2  push    rbx
0x18003d7c3  push    rsi
0x18003d7c4  push    rdi
0x18003d7c5  push    r12
0x18003d7c7  push    r13
0x18003d7c9  push    r14
0x18003d7cb  push    r15
0x18003d7cd  lea     rbp, [rsp-7]
0x18003d7d2  sub     rsp, 0A8h
0x18003d7d9  mov     rax, cs:__security_cookie
0x18003d7e0  xor     rax, rsp
0x18003d7e3  mov     [rbp+3Fh+var_50], rax
0x18003d7e7  mov     rdi, [rcx+30h]
0x18003d7eb  mov     r14, rcx
0x18003d7ee  mov     rax, [rbp+3Fh+arg_40]
0x18003d7f5  lea     rcx, [rbp+3Fh+var_90]
0x18003d7f9  mov     r12, [rbp+3Fh+arg_20]
0x18003d7fd  mov     r13d, r9d
0x18003d800  mov     [rbp+3Fh+var_78], rax
0x18003d804  mov     r15d, r8d
0x18003d807  mov     [rbp+3Fh+var_90], rdi
0x18003d80b  mov     [rbp+3Fh+var_80], rdx
0x18003d80f  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d814  mov     rcx, [r14+30h]
0x18003d818  lea     rdx, [rbp+3Fh+var_60]
0x18003d81c  xorps   xmm0, xmm0
0x18003d81f  xorps   xmm1, xmm1
0x18003d822  xor     esi, esi
0x18003d824  movups  [rbp+3Fh+var_60], xmm0
0x18003d828  mov     [rbp+3Fh+var_88], esi
0x18003d82b  movups  [rbp+3Fh+var_70], xmm1
0x18003d82f  mov     [rbp+3Fh+var_84], esi
0x18003d832  mov     rax, [rcx]
0x18003d835  mov     rax, [rax+20h]
0x18003d839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d83e  mov     ebx, eax
0x18003d840  test    eax, eax
0x18003d842  js      loc_18003DB30
0x18003d848  mov     rcx, [r14+30h]
0x18003d84c  lea     r8, [rbp+3Fh+var_84]
0x18003d850  lea     rdx, [rbp+3Fh+var_88]
0x18003d854  mov     rax, [rcx]
0x18003d857  mov     rax, [rax+18h]
0x18003d85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d860  mov     ebx, eax
0x18003d862  test    eax, eax
0x18003d864  js      loc_18003DB30
0x18003d86a  cmp     r15d, [rbp+3Fh+var_88]
0x18003d86e  jnz     short loc_18003D881
0x18003d870  cmp     r13d, [rbp+3Fh+var_84]
0x18003d874  jnz     short loc_18003D881
0x18003d876  mov     rbx, rdi
0x18003d879  xor     r13d, r13d
0x18003d87c  jmp     loc_18003D914
0x18003d881  mov     [rbp+3Fh+var_A0], rsi
0x18003d885  lea     rcx, [rbp+3Fh+var_A0]
0x18003d889  mov     rsi, [r14+38h]
0x18003d88d  mov     rax, [rsi]
0x18003d890  mov     rbx, [rax+58h]
0x18003d894  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d899  lea     rdx, [rbp+3Fh+var_A0]
0x18003d89d  mov     rcx, rsi
0x18003d8a0  mov     rax, rbx
0x18003d8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8a8  mov     ebx, eax
0x18003d8aa  test    eax, eax
0x18003d8ac  jns     short loc_18003D8BC
0x18003d8ae  lea     rcx, [rbp+3Fh+var_A0]
0x18003d8b2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d8b7  jmp     loc_18003DB30
0x18003d8bc  mov     rcx, [rbp+3Fh+var_A0]
0x18003d8c0  mov     r9d, r13d
0x18003d8c3  mov     r8d, r15d
0x18003d8c6  mov     dword ptr [rsp+0E0h+var_C0], 3
0x18003d8ce  mov     rdx, rdi
0x18003d8d1  mov     rax, [rcx]
0x18003d8d4  mov     rax, [rax+40h]
0x18003d8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8dd  xor     r13d, r13d
0x18003d8e0  mov     ebx, eax
0x18003d8e2  test    eax, eax
0x18003d8e4  js      short loc_18003D8AE
0x18003d8e6  mov     rbx, [rbp+3Fh+var_A0]
0x18003d8ea  lea     rcx, [rbp+3Fh+var_98]
0x18003d8ee  mov     [rbp+3Fh+var_98], rbx
0x18003d8f2  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d8f7  mov     [rbp+3Fh+var_98], rdi
0x18003d8fb  lea     rcx, [rbp+3Fh+var_98]
0x18003d8ff  mov     rdi, rbx
0x18003d902  mov     [rbp+3Fh+var_90], rbx
0x18003d906  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d90b  lea     rcx, [rbp+3Fh+var_A0]
0x18003d90f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d914  mov     r15, [rbp+3Fh+var_80]
0x18003d918  test    r15, r15
0x18003d91b  jz      loc_18003D9A6
0x18003d921  mov     rsi, [r14+38h]
0x18003d925  lea     rcx, [rbp+3Fh+var_A0]
0x18003d929  mov     [rbp+3Fh+var_A0], r13
0x18003d92d  mov     rax, [rsi]
0x18003d930  mov     rbx, [rax+60h]
0x18003d934  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d939  lea     rdx, [rbp+3Fh+var_A0]
0x18003d93d  mov     rcx, rsi
0x18003d940  mov     rax, rbx
0x18003d943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d948  mov     ebx, eax
0x18003d94a  test    eax, eax
0x18003d94c  jns     short loc_18003D95C
0x18003d94e  lea     rcx, [rbp+3Fh+var_A0]
0x18003d952  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d957  jmp     loc_18003DB30
0x18003d95c  mov     rcx, [rbp+3Fh+var_A0]
0x18003d960  mov     r8, r15
0x18003d963  mov     rdx, rdi
0x18003d966  mov     rax, [rcx]
0x18003d969  mov     rax, [rax+40h]
0x18003d96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d972  mov     ebx, eax
0x18003d974  test    eax, eax
0x18003d976  js      short loc_18003D94E
0x18003d978  mov     rbx, [rbp+3Fh+var_A0]
0x18003d97c  lea     rcx, [rbp+3Fh+var_98]
0x18003d980  mov     [rbp+3Fh+var_98], rbx
0x18003d984  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d989  mov     [rbp+3Fh+var_98], rdi
0x18003d98d  lea     rcx, [rbp+3Fh+var_98]
0x18003d991  mov     rdi, rbx
0x18003d994  mov     [rbp+3Fh+var_90], rbx
0x18003d998  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d99d  lea     rcx, [rbp+3Fh+var_A0]
0x18003d9a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d9a6  mov     r15d, [rbp+3Fh+arg_28]
0x18003d9aa  test    r15d, r15d
0x18003d9ad  jz      loc_18003DA38
0x18003d9b3  mov     rsi, [r14+38h]
0x18003d9b7  lea     rcx, [rbp+3Fh+var_A0]
0x18003d9bb  mov     [rbp+3Fh+var_A0], r13
0x18003d9bf  mov     rax, [rsi]
0x18003d9c2  mov     rbx, [rax+68h]
0x18003d9c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d9cb  lea     rdx, [rbp+3Fh+var_A0]
0x18003d9cf  mov     rcx, rsi
0x18003d9d2  mov     rax, rbx
0x18003d9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9da  mov     ebx, eax
0x18003d9dc  test    eax, eax
0x18003d9de  jns     short loc_18003D9EE
0x18003d9e0  lea     rcx, [rbp+3Fh+var_A0]
0x18003d9e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003d9e9  jmp     loc_18003DB30
0x18003d9ee  mov     rcx, [rbp+3Fh+var_A0]
0x18003d9f2  mov     r8d, r15d
0x18003d9f5  mov     rdx, rdi
0x18003d9f8  mov     rax, [rcx]
0x18003d9fb  mov     rax, [rax+40h]
0x18003d9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da04  mov     ebx, eax
0x18003da06  test    eax, eax
0x18003da08  js      short loc_18003D9E0
0x18003da0a  mov     rbx, [rbp+3Fh+var_A0]
0x18003da0e  lea     rcx, [rbp+3Fh+var_98]
0x18003da12  mov     [rbp+3Fh+var_98], rbx
0x18003da16  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003da1b  mov     [rbp+3Fh+var_98], rdi
0x18003da1f  lea     rcx, [rbp+3Fh+var_98]
0x18003da23  mov     rdi, rbx
0x18003da26  mov     [rbp+3Fh+var_90], rbx
0x18003da2a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003da2f  lea     rcx, [rbp+3Fh+var_A0]
0x18003da33  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003da38  mov     rax, [rbx]
0x18003da3b  lea     rdx, [rbp+3Fh+var_70]
0x18003da3f  mov     rcx, rbx
0x18003da42  mov     rax, [rax+20h]
0x18003da46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da4b  mov     ebx, eax
0x18003da4d  test    eax, eax
0x18003da4f  js      loc_18003DB30
0x18003da55  mov     rax, qword ptr [rbp+3Fh+var_70]
0x18003da59  cmp     rax, [r12]
0x18003da5d  jnz     short loc_18003DA6E
0x18003da5f  mov     rax, qword ptr [rbp+3Fh+var_70+8]
0x18003da63  cmp     rax, [r12+8]
0x18003da68  jz      loc_18003DB09
0x18003da6e  mov     rsi, [r14+38h]
0x18003da72  lea     rcx, [rbp+3Fh+var_A0]
0x18003da76  mov     [rbp+3Fh+var_A0], r13
0x18003da7a  mov     rax, [rsi]
0x18003da7d  mov     rbx, [rax+50h]
0x18003da81  call    ?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)
0x18003da86  lea     rdx, [rbp+3Fh+var_A0]
0x18003da8a  mov     rcx, rsi
0x18003da8d  mov     rax, rbx
0x18003da90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da95  mov     ebx, eax
0x18003da97  test    eax, eax
0x18003da99  jns     short loc_18003DAA9
0x18003da9b  lea     rcx, [rbp+3Fh+var_A0]
0x18003da9f  call    ?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)
0x18003daa4  jmp     loc_18003DB30
0x18003daa9  mov     rcx, [rbp+3Fh+var_A0]
0x18003daad  xorps   xmm0, xmm0
0x18003dab0  mov     [rsp+0E0h+var_B0], r13d
0x18003dab5  xor     r9d, r9d
0x18003dab8  movsd   [rsp+0E0h+var_B8], xmm0
0x18003dabe  mov     r8, r12
0x18003dac1  mov     rdx, rdi
0x18003dac4  mov     [rsp+0E0h+var_C0], r13
0x18003dac9  mov     rax, [rcx]
0x18003dacc  mov     rax, [rax+40h]
0x18003dad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dad5  mov     ebx, eax
0x18003dad7  test    eax, eax
0x18003dad9  js      short loc_18003DA9B
0x18003dadb  mov     rbx, [rbp+3Fh+var_A0]
0x18003dadf  lea     rcx, [rbp+3Fh+var_98]
0x18003dae3  mov     [rbp+3Fh+var_98], rbx
0x18003dae7  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003daec  mov     [rbp+3Fh+var_98], rdi
0x18003daf0  lea     rcx, [rbp+3Fh+var_98]
0x18003daf4  mov     rdi, rbx
0x18003daf7  mov     [rbp+3Fh+var_90], rbx
0x18003dafb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db00  lea     rcx, [rbp+3Fh+var_A0]
0x18003db04  call    ?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)
0x18003db09  mov     rax, [rdi]
0x18003db0c  xor     edx, edx
0x18003db0e  mov     rcx, [rbp+3Fh+var_78]
0x18003db12  mov     r9d, [rbp+3Fh+arg_38]
0x18003db19  mov     r8d, [rbp+3Fh+arg_30]
0x18003db1d  mov     rax, [rax+38h]
0x18003db21  mov     [rsp+0E0h+var_C0], rcx
0x18003db26  mov     rcx, rdi
0x18003db29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db2e  mov     ebx, eax
0x18003db30  lea     rcx, [rbp+3Fh+var_90]
0x18003db34  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003db39  mov     eax, ebx
0x18003db3b  mov     rcx, [rbp+3Fh+var_50]
0x18003db3f  xor     rcx, rsp; StackCookie
0x18003db42  call    __security_check_cookie
0x18003db47  add     rsp, 0A8h
0x18003db4e  pop     r15
0x18003db50  pop     r14
0x18003db52  pop     r13
0x18003db54  pop     r12
0x18003db56  pop     rdi
0x18003db57  pop     rsi
0x18003db58  pop     rbx
0x18003db59  pop     rbp
0x18003db5a  retn
```
