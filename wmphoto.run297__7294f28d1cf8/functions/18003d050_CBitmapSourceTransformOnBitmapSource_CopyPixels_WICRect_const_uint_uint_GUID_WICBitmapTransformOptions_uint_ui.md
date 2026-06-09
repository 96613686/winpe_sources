# CBitmapSourceTransformOnBitmapSource::CopyPixels(WICRect const *,uint,uint,_GUID *,WICBitmapTransformOptions,uint,uint,uchar *)

- ea: `0x18003d050`
- end: `0x18003d3eb`
- name: `?CopyPixels@CBitmapSourceTransformOnBitmapSource@@UEAAJPEBUWICRect@@IIPEAU_GUID@@W4WICBitmapTransformOptions@@IIPEAE@Z`
- size: `923`
- prototype: `__int64 __fastcall(CBitmapSourceTransformOnBitmapSource *__hidden this, const struct WICRect *, unsigned int, unsigned int, struct _GUID *, enum WICBitmapTransformOptions, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180035480`
- `0x180035e50`
- `0x18003c864`
- `0x18003c890`
- `0x18003d050`
- `0x180044010`

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
    Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v27);
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
    Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v27);
  }
  v18 = v32;
  if ( v32 )
  {
    v19 = *((_QWORD *)this + 7);
    v27 = 0;
    v20 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 96LL);
    Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v27);
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
    Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v28);
    Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v27);
  }
  if ( a6 == WICBitmapTransformRotate0 )
    goto LABEL_20;
  v21 = *((_QWORD *)this + 7);
  v27 = 0;
  v22 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 104LL);
  Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v27);
  v14 = v22(v21, &v27);
  if ( v14 < 0
    || (v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v27 + 64LL))(v27, v9, (unsigned int)a6),
        v14 < 0) )
  {
LABEL_17:
    Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v27);
    goto LABEL_27;
  }
  v15 = v27;
  v28 = v27;
  Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(&v28);
  v28 = v9;
  v9 = v15;
  v29 = v15;
  Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v27);
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
        Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v28);
        Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(&v27);
        goto LABEL_26;
      }
    }
    Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(&v27);
  }
LABEL_27:
  Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(&v29);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18003d050  push    rbp
0x18003d052  push    rbx
0x18003d053  push    rsi
0x18003d054  push    rdi
0x18003d055  push    r12
0x18003d057  push    r13
0x18003d059  push    r14
0x18003d05b  push    r15
0x18003d05d  lea     rbp, [rsp-7]
0x18003d062  sub     rsp, 0A8h
0x18003d069  mov     rax, cs:__security_cookie
0x18003d070  xor     rax, rsp
0x18003d073  mov     [rbp+3Fh+var_50], rax
0x18003d077  mov     rdi, [rcx+30h]
0x18003d07b  mov     r14, rcx
0x18003d07e  mov     rax, [rbp+3Fh+arg_40]
0x18003d085  lea     rcx, [rbp+3Fh+var_90]
0x18003d089  mov     r12, [rbp+3Fh+arg_20]
0x18003d08d  mov     r13d, r9d
0x18003d090  mov     [rbp+3Fh+var_78], rax
0x18003d094  mov     r15d, r8d
0x18003d097  mov     [rbp+3Fh+var_90], rdi
0x18003d09b  mov     [rbp+3Fh+var_80], rdx
0x18003d09f  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d0a4  mov     rcx, [r14+30h]
0x18003d0a8  lea     rdx, [rbp+3Fh+var_60]
0x18003d0ac  xorps   xmm0, xmm0
0x18003d0af  xorps   xmm1, xmm1
0x18003d0b2  xor     esi, esi
0x18003d0b4  movups  [rbp+3Fh+var_60], xmm0
0x18003d0b8  mov     [rbp+3Fh+var_88], esi
0x18003d0bb  movups  [rbp+3Fh+var_70], xmm1
0x18003d0bf  mov     [rbp+3Fh+var_84], esi
0x18003d0c2  mov     rax, [rcx]
0x18003d0c5  mov     rax, [rax+20h]
0x18003d0c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0ce  mov     ebx, eax
0x18003d0d0  test    eax, eax
0x18003d0d2  js      loc_18003D3C0
0x18003d0d8  mov     rcx, [r14+30h]
0x18003d0dc  lea     r8, [rbp+3Fh+var_84]
0x18003d0e0  lea     rdx, [rbp+3Fh+var_88]
0x18003d0e4  mov     rax, [rcx]
0x18003d0e7  mov     rax, [rax+18h]
0x18003d0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0f0  mov     ebx, eax
0x18003d0f2  test    eax, eax
0x18003d0f4  js      loc_18003D3C0
0x18003d0fa  cmp     r15d, [rbp+3Fh+var_88]
0x18003d0fe  jnz     short loc_18003D111
0x18003d100  cmp     r13d, [rbp+3Fh+var_84]
0x18003d104  jnz     short loc_18003D111
0x18003d106  mov     rbx, rdi
0x18003d109  xor     r13d, r13d
0x18003d10c  jmp     loc_18003D1A4
0x18003d111  mov     [rbp+3Fh+var_A0], rsi
0x18003d115  lea     rcx, [rbp+3Fh+var_A0]
0x18003d119  mov     rsi, [r14+38h]
0x18003d11d  mov     rax, [rsi]
0x18003d120  mov     rbx, [rax+58h]
0x18003d124  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d129  lea     rdx, [rbp+3Fh+var_A0]
0x18003d12d  mov     rcx, rsi
0x18003d130  mov     rax, rbx
0x18003d133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d138  mov     ebx, eax
0x18003d13a  test    eax, eax
0x18003d13c  jns     short loc_18003D14C
0x18003d13e  lea     rcx, [rbp+3Fh+var_A0]
0x18003d142  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d147  jmp     loc_18003D3C0
0x18003d14c  mov     rcx, [rbp+3Fh+var_A0]
0x18003d150  mov     r9d, r13d
0x18003d153  mov     r8d, r15d
0x18003d156  mov     dword ptr [rsp+0E0h+var_C0], 3
0x18003d15e  mov     rdx, rdi
0x18003d161  mov     rax, [rcx]
0x18003d164  mov     rax, [rax+40h]
0x18003d168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d16d  xor     r13d, r13d
0x18003d170  mov     ebx, eax
0x18003d172  test    eax, eax
0x18003d174  js      short loc_18003D13E
0x18003d176  mov     rbx, [rbp+3Fh+var_A0]
0x18003d17a  lea     rcx, [rbp+3Fh+var_98]
0x18003d17e  mov     [rbp+3Fh+var_98], rbx
0x18003d182  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d187  mov     [rbp+3Fh+var_98], rdi
0x18003d18b  lea     rcx, [rbp+3Fh+var_98]
0x18003d18f  mov     rdi, rbx
0x18003d192  mov     [rbp+3Fh+var_90], rbx
0x18003d196  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d19b  lea     rcx, [rbp+3Fh+var_A0]
0x18003d19f  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d1a4  mov     r15, [rbp+3Fh+var_80]
0x18003d1a8  test    r15, r15
0x18003d1ab  jz      loc_18003D236
0x18003d1b1  mov     rsi, [r14+38h]
0x18003d1b5  lea     rcx, [rbp+3Fh+var_A0]
0x18003d1b9  mov     [rbp+3Fh+var_A0], r13
0x18003d1bd  mov     rax, [rsi]
0x18003d1c0  mov     rbx, [rax+60h]
0x18003d1c4  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d1c9  lea     rdx, [rbp+3Fh+var_A0]
0x18003d1cd  mov     rcx, rsi
0x18003d1d0  mov     rax, rbx
0x18003d1d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1d8  mov     ebx, eax
0x18003d1da  test    eax, eax
0x18003d1dc  jns     short loc_18003D1EC
0x18003d1de  lea     rcx, [rbp+3Fh+var_A0]
0x18003d1e2  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d1e7  jmp     loc_18003D3C0
0x18003d1ec  mov     rcx, [rbp+3Fh+var_A0]
0x18003d1f0  mov     r8, r15
0x18003d1f3  mov     rdx, rdi
0x18003d1f6  mov     rax, [rcx]
0x18003d1f9  mov     rax, [rax+40h]
0x18003d1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d202  mov     ebx, eax
0x18003d204  test    eax, eax
0x18003d206  js      short loc_18003D1DE
0x18003d208  mov     rbx, [rbp+3Fh+var_A0]
0x18003d20c  lea     rcx, [rbp+3Fh+var_98]
0x18003d210  mov     [rbp+3Fh+var_98], rbx
0x18003d214  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d219  mov     [rbp+3Fh+var_98], rdi
0x18003d21d  lea     rcx, [rbp+3Fh+var_98]
0x18003d221  mov     rdi, rbx
0x18003d224  mov     [rbp+3Fh+var_90], rbx
0x18003d228  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d22d  lea     rcx, [rbp+3Fh+var_A0]
0x18003d231  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d236  mov     r15d, [rbp+3Fh+arg_28]
0x18003d23a  test    r15d, r15d
0x18003d23d  jz      loc_18003D2C8
0x18003d243  mov     rsi, [r14+38h]
0x18003d247  lea     rcx, [rbp+3Fh+var_A0]
0x18003d24b  mov     [rbp+3Fh+var_A0], r13
0x18003d24f  mov     rax, [rsi]
0x18003d252  mov     rbx, [rax+68h]
0x18003d256  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d25b  lea     rdx, [rbp+3Fh+var_A0]
0x18003d25f  mov     rcx, rsi
0x18003d262  mov     rax, rbx
0x18003d265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d26a  mov     ebx, eax
0x18003d26c  test    eax, eax
0x18003d26e  jns     short loc_18003D27E
0x18003d270  lea     rcx, [rbp+3Fh+var_A0]
0x18003d274  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d279  jmp     loc_18003D3C0
0x18003d27e  mov     rcx, [rbp+3Fh+var_A0]
0x18003d282  mov     r8d, r15d
0x18003d285  mov     rdx, rdi
0x18003d288  mov     rax, [rcx]
0x18003d28b  mov     rax, [rax+40h]
0x18003d28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d294  mov     ebx, eax
0x18003d296  test    eax, eax
0x18003d298  js      short loc_18003D270
0x18003d29a  mov     rbx, [rbp+3Fh+var_A0]
0x18003d29e  lea     rcx, [rbp+3Fh+var_98]
0x18003d2a2  mov     [rbp+3Fh+var_98], rbx
0x18003d2a6  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d2ab  mov     [rbp+3Fh+var_98], rdi
0x18003d2af  lea     rcx, [rbp+3Fh+var_98]
0x18003d2b3  mov     rdi, rbx
0x18003d2b6  mov     [rbp+3Fh+var_90], rbx
0x18003d2ba  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d2bf  lea     rcx, [rbp+3Fh+var_A0]
0x18003d2c3  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d2c8  mov     rax, [rbx]
0x18003d2cb  lea     rdx, [rbp+3Fh+var_70]
0x18003d2cf  mov     rcx, rbx
0x18003d2d2  mov     rax, [rax+20h]
0x18003d2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2db  mov     ebx, eax
0x18003d2dd  test    eax, eax
0x18003d2df  js      loc_18003D3C0
0x18003d2e5  mov     rax, qword ptr [rbp+3Fh+var_70]
0x18003d2e9  cmp     rax, [r12]
0x18003d2ed  jnz     short loc_18003D2FE
0x18003d2ef  mov     rax, qword ptr [rbp+3Fh+var_70+8]
0x18003d2f3  cmp     rax, [r12+8]
0x18003d2f8  jz      loc_18003D399
0x18003d2fe  mov     rsi, [r14+38h]
0x18003d302  lea     rcx, [rbp+3Fh+var_A0]
0x18003d306  mov     [rbp+3Fh+var_A0], r13
0x18003d30a  mov     rax, [rsi]
0x18003d30d  mov     rbx, [rax+50h]
0x18003d311  call    ?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)
0x18003d316  lea     rdx, [rbp+3Fh+var_A0]
0x18003d31a  mov     rcx, rsi
0x18003d31d  mov     rax, rbx
0x18003d320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d325  mov     ebx, eax
0x18003d327  test    eax, eax
0x18003d329  jns     short loc_18003D339
0x18003d32b  lea     rcx, [rbp+3Fh+var_A0]
0x18003d32f  call    ?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)
0x18003d334  jmp     loc_18003D3C0
0x18003d339  mov     rcx, [rbp+3Fh+var_A0]
0x18003d33d  xorps   xmm0, xmm0
0x18003d340  mov     [rsp+0E0h+var_B0], r13d
0x18003d345  xor     r9d, r9d
0x18003d348  movsd   [rsp+0E0h+var_B8], xmm0
0x18003d34e  mov     r8, r12
0x18003d351  mov     rdx, rdi
0x18003d354  mov     [rsp+0E0h+var_C0], r13
0x18003d359  mov     rax, [rcx]
0x18003d35c  mov     rax, [rax+40h]
0x18003d360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d365  mov     ebx, eax
0x18003d367  test    eax, eax
0x18003d369  js      short loc_18003D32B
0x18003d36b  mov     rbx, [rbp+3Fh+var_A0]
0x18003d36f  lea     rcx, [rbp+3Fh+var_98]
0x18003d373  mov     [rbp+3Fh+var_98], rbx
0x18003d377  call    ?InternalAddRef@?$ComPtr@UIWICBitmapSource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWICBitmapSource>::InternalAddRef(void)
0x18003d37c  mov     [rbp+3Fh+var_98], rdi
0x18003d380  lea     rcx, [rbp+3Fh+var_98]
0x18003d384  mov     rdi, rbx
0x18003d387  mov     [rbp+3Fh+var_90], rbx
0x18003d38b  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d390  lea     rcx, [rbp+3Fh+var_A0]
0x18003d394  call    ?InternalRelease@?$ComPtr@UIWICFormatConverter@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICFormatConverter>::InternalRelease(void)
0x18003d399  mov     rax, [rdi]
0x18003d39c  xor     edx, edx
0x18003d39e  mov     rcx, [rbp+3Fh+var_78]
0x18003d3a2  mov     r9d, [rbp+3Fh+arg_38]
0x18003d3a9  mov     r8d, [rbp+3Fh+arg_30]
0x18003d3ad  mov     rax, [rax+38h]
0x18003d3b1  mov     [rsp+0E0h+var_C0], rcx
0x18003d3b6  mov     rcx, rdi
0x18003d3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3be  mov     ebx, eax
0x18003d3c0  lea     rcx, [rbp+3Fh+var_90]
0x18003d3c4  call    ?InternalRelease@?$ComPtr@UID2D1ColorContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID2D1ColorContext>::InternalRelease(void)
0x18003d3c9  mov     eax, ebx
0x18003d3cb  mov     rcx, [rbp+3Fh+var_50]
0x18003d3cf  xor     rcx, rsp; StackCookie
0x18003d3d2  call    __security_check_cookie
0x18003d3d7  add     rsp, 0A8h
0x18003d3de  pop     r15
0x18003d3e0  pop     r14
0x18003d3e2  pop     r13
0x18003d3e4  pop     r12
0x18003d3e6  pop     rdi
0x18003d3e7  pop     rsi
0x18003d3e8  pop     rbx
0x18003d3e9  pop     rbp
0x18003d3ea  retn
```
