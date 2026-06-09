# ToneMapper::ToneMapImageForHDRDisplay(IWICComponentFactory *,IWICBitmapSource *,float,IWICBitmapSourceTransform * *)

- ea: `0x18003e2f0`
- end: `0x18003e545`
- name: `?ToneMapImageForHDRDisplay@ToneMapper@@QEAAJPEAUIWICComponentFactory@@PEAUIWICBitmapSource@@MPEAPEAUIWICBitmapSourceTransform@@@Z`
- size: `597`
- prototype: `__int64 __fastcall(ToneMapper *__hidden this, struct IWICComponentFactory *, struct IWICBitmapSource *, float, struct IWICBitmapSourceTransform **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180031850`

## callees

- `0x180036420`
- `0x18003d6c0`
- `0x18003e2f0`
- `0x180043e34`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ToneMapper::ToneMapImageForHDRDisplay(
        ToneMapper *this,
        struct IWICComponentFactory *a2,
        struct IWICBitmapSource *a3,
        float a4,
        struct IWICBitmapSourceTransform **a5)
{
  int v7; // ebx
  __int64 v8; // rbx
  __int64 *v9; // rdi
  GUID v10; // xmm1
  __m128i v11; // xmm2
  HRESULT (__stdcall *QueryInterface)(IWICComponentFactory *, const IID *const, void **); // rbx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v20; // [rsp+40h] [rbp-61h] BYREF
  __int64 v21; // [rsp+48h] [rbp-59h] BYREF
  __int64 v22; // [rsp+50h] [rbp-51h] BYREF
  struct IWICComponentFactory *v23; // [rsp+58h] [rbp-49h] BYREF
  GUID v24; // [rsp+60h] [rbp-41h] BYREF
  GUID Buf1; // [rsp+70h] [rbp-31h] BYREF
  __int128 v26; // [rsp+80h] [rbp-21h]
  __m128i v27; // [rsp+90h] [rbp-11h]
  __int64 v28; // [rsp+A0h] [rbp-1h]

  v23 = a2;
  Buf1 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v24 = 0;
  v21 = 0;
  v20 = 0;
  *a5 = 0;
  v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, GUID *))a3->lpVtbl->GetPixelFormat)(a3, &Buf1);
  if ( v7 >= 0 )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = &qword_180050540[7 * v8];
      if ( !memcmp_0(&Buf1, v9, 0x10u) )
        break;
      if ( (unsigned __int64)++v8 >= 0x3D )
      {
        v7 = -2003292288;
        goto LABEL_19;
      }
    }
    v10 = *(GUID *)v9;
    Buf1 = *(GUID *)v9;
    v26 = *((_OWORD *)v9 + 1);
    v11 = *((__m128i *)v9 + 2);
    v27 = v11;
    v28 = v9[6];
    if ( (_mm_cvtsi128_si32((__m128i)(unsigned __int64)v28) & 0x10) != 0 )
    {
      if ( _mm_cvtsi128_si32(v11) >= 7 )
        v24 = GUID_WICPixelFormat128bppPRGBAFloat;
      else
        v24 = GUID_WICPixelFormat64bppPRGBAHalf;
    }
    else
    {
      v24 = v10;
    }
    QueryInterface = a2->lpVtbl->QueryInterface;
    v13 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v7 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, GUID *, __int64 *))QueryInterface)(
           a2,
           &GUID_489b3d8b_624a_4258_b678_7eece70f299d,
           &v21);
    if ( v7 >= 0 )
    {
      v14 = v21;
      v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 232LL);
      v16 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v7 = v15(v14, &v20);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, GUID *))(*(_QWORD *)v20 + 64LL))(
               v20,
               a3,
               &v24);
        if ( v7 >= 0 )
        {
          v22 = v20;
          v7 = Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(
                 a5,
                 &v23,
                 &v22);
        }
      }
    }
  }
LABEL_19:
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e2f0  mov     [rsp-8+arg_0], rbx
0x18003e2f5  push    rbp
0x18003e2f6  push    rsi
0x18003e2f7  push    rdi
0x18003e2f8  push    r12
0x18003e2fa  push    r13
0x18003e2fc  push    r14
0x18003e2fe  push    r15
0x18003e300  lea     rbp, [rsp-1Fh]
0x18003e305  sub     rsp, 0C0h
0x18003e30c  movaps  [rsp+0F0h+var_40], xmm6
0x18003e314  mov     rax, cs:__security_cookie
0x18003e31b  xor     rax, rsp
0x18003e31e  mov     [rbp+4Fh+var_48], rax
0x18003e322  movaps  xmm6, xmm3
0x18003e325  mov     r15, r8
0x18003e328  mov     rsi, rdx
0x18003e32b  mov     [rbp+4Fh+var_98], rdx
0x18003e32f  mov     r14, [rbp+4Fh+arg_20]
0x18003e333  xorps   xmm0, xmm0
0x18003e336  xor     eax, eax
0x18003e338  movups  [rbp+4Fh+Buf1], xmm0
0x18003e33c  movups  [rbp+4Fh+var_70], xmm0
0x18003e340  movups  [rbp+4Fh+var_60], xmm0
0x18003e344  mov     [rbp+4Fh+var_50], rax
0x18003e348  movups  [rbp+4Fh+var_90], xmm0
0x18003e34c  xor     r12d, r12d
0x18003e34f  mov     [rbp+4Fh+var_A8], r12
0x18003e353  mov     [rbp+4Fh+var_B0], r12
0x18003e357  mov     [r14], r12
0x18003e35a  mov     rax, [r8]
0x18003e35d  lea     rdx, [rbp+4Fh+Buf1]
0x18003e361  mov     rcx, r8
0x18003e364  mov     rax, [rax+20h]
0x18003e368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e36d  mov     ebx, eax
0x18003e36f  test    eax, eax
0x18003e371  js      loc_18003E4DF
0x18003e377  mov     ebx, r12d
0x18003e37a  lea     r13, qword_180050540
0x18003e381  nop     dword ptr [rax+00h]
0x18003e385  nop     word ptr [rax+rax+00000000h]
0x18003e390  imul    rdi, rbx, 38h ; '8'
0x18003e394  add     rdi, r13
0x18003e397  mov     r8d, 10h; Size
0x18003e39d  mov     rdx, rdi; Buf2
0x18003e3a0  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18003e3a4  call    memcmp_0
0x18003e3a9  test    eax, eax
0x18003e3ab  jz      short loc_18003E3C0
0x18003e3ad  inc     rbx
0x18003e3b0  cmp     rbx, 3Dh ; '='
0x18003e3b4  jb      short loc_18003E390
0x18003e3b6  mov     ebx, 88982F80h
0x18003e3bb  jmp     loc_18003E4DF
0x18003e3c0  movups  xmm1, xmmword ptr [rdi]
0x18003e3c3  movups  [rbp+4Fh+Buf1], xmm1
0x18003e3c7  movups  xmm0, xmmword ptr [rdi+10h]
0x18003e3cb  movups  [rbp+4Fh+var_70], xmm0
0x18003e3cf  movups  xmm2, xmmword ptr [rdi+20h]
0x18003e3d3  movups  [rbp+4Fh+var_60], xmm2
0x18003e3d7  movsd   xmm0, qword ptr [rdi+30h]
0x18003e3dc  movsd   [rbp+4Fh+var_50], xmm0
0x18003e3e1  movd    eax, xmm0
0x18003e3e5  test    al, 10h
0x18003e3e7  jz      short loc_18003E40E
0x18003e3e9  movd    eax, xmm2
0x18003e3ed  cmp     eax, 7
0x18003e3f0  jge     short loc_18003E400
0x18003e3f2  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat64bppPRGBAHalf.Data1
0x18003e3f9  movdqa  [rbp+4Fh+var_90], xmm0
0x18003e3fe  jmp     short loc_18003E412
0x18003e400  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat128bppPRGBAFloat.Data1
0x18003e407  movdqa  [rbp+4Fh+var_90], xmm0
0x18003e40c  jmp     short loc_18003E412
0x18003e40e  movups  [rbp+4Fh+var_90], xmm1
0x18003e412  mov     rax, [rsi]
0x18003e415  mov     rbx, [rax]
0x18003e418  mov     rcx, [rbp+4Fh+var_A8]
0x18003e41c  test    rcx, rcx
0x18003e41f  jz      short loc_18003E432
0x18003e421  mov     [rbp+4Fh+var_A8], r12
0x18003e425  mov     rdx, [rcx]
0x18003e428  mov     rax, [rdx+10h]
0x18003e42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e431  nop
0x18003e432  lea     r8, [rbp+4Fh+var_A8]
0x18003e436  lea     rdx, _GUID_489b3d8b_624a_4258_b678_7eece70f299d
0x18003e43d  mov     rcx, rsi
0x18003e440  mov     rax, rbx
0x18003e443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e448  mov     ebx, eax
0x18003e44a  test    eax, eax
0x18003e44c  js      loc_18003E4DF
0x18003e452  mov     rbx, [rbp+4Fh+var_A8]
0x18003e456  mov     rax, [rbx]
0x18003e459  mov     rdi, [rax+0E8h]
0x18003e460  mov     rcx, [rbp+4Fh+var_B0]
0x18003e464  test    rcx, rcx
0x18003e467  jz      short loc_18003E47A
0x18003e469  mov     [rbp+4Fh+var_B0], r12
0x18003e46d  mov     rdx, [rcx]
0x18003e470  mov     rax, [rdx+10h]
0x18003e474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e479  nop
0x18003e47a  lea     rdx, [rbp+4Fh+var_B0]
0x18003e47e  mov     rcx, rbx
0x18003e481  mov     rax, rdi
0x18003e484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e489  mov     ebx, eax
0x18003e48b  test    eax, eax
0x18003e48d  js      short loc_18003E4DF
0x18003e48f  mov     rcx, [rbp+4Fh+var_B0]
0x18003e493  mov     rax, [rcx]
0x18003e496  mov     [rsp+0F0h+var_C8], 2
0x18003e49e  movss   xmm0, cs:__real@434b0000
0x18003e4a6  movss   [rsp+0F0h+var_D0], xmm0
0x18003e4ac  movaps  xmm3, xmm6
0x18003e4af  lea     r8, [rbp+4Fh+var_90]
0x18003e4b3  mov     rdx, r15
0x18003e4b6  mov     rax, [rax+40h]
0x18003e4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4bf  mov     ebx, eax
0x18003e4c1  test    eax, eax
0x18003e4c3  js      short loc_18003E4DF
0x18003e4c5  mov     rax, [rbp+4Fh+var_B0]
0x18003e4c9  mov     [rbp+4Fh+var_A0], rax
0x18003e4cd  lea     r8, [rbp+4Fh+var_A0]
0x18003e4d1  lea     rdx, [rbp+4Fh+var_98]
0x18003e4d5  mov     rcx, r14
0x18003e4d8  call    ??$MakeAndInitialize@VCBitmapSourceTransformOnBitmapSource@@UIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@PEAUIWICBitmapToneMapper@@@Details@WRL@Microsoft@@YAJPEAPEAUIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@$$QEAPEAUIWICBitmapToneMapper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(IWICBitmapSourceTransform * *,IWICComponentFactory * &,IWICBitmapToneMapper * &&)
0x18003e4dd  mov     ebx, eax
0x18003e4df  mov     rcx, [rbp+4Fh+var_B0]
0x18003e4e3  test    rcx, rcx
0x18003e4e6  jz      short loc_18003E4F9
0x18003e4e8  mov     [rbp+4Fh+var_B0], r12
0x18003e4ec  mov     rax, [rcx]
0x18003e4ef  mov     rax, [rax+10h]
0x18003e4f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e4f8  nop
0x18003e4f9  mov     rcx, [rbp+4Fh+var_A8]
0x18003e4fd  test    rcx, rcx
0x18003e500  jz      short loc_18003E513
0x18003e502  mov     [rbp+4Fh+var_A8], r12
0x18003e506  mov     rax, [rcx]
0x18003e509  mov     rax, [rax+10h]
0x18003e50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e512  nop
0x18003e513  mov     eax, ebx
0x18003e515  mov     rcx, [rbp+4Fh+var_48]
0x18003e519  xor     rcx, rsp; StackCookie
0x18003e51c  call    __security_check_cookie
0x18003e521  mov     rbx, [rsp+0F0h+arg_0]
0x18003e529  movaps  xmm6, [rsp+0F0h+var_40]
0x18003e531  add     rsp, 0C0h
0x18003e538  pop     r15
0x18003e53a  pop     r14
0x18003e53c  pop     r13
0x18003e53e  pop     r12
0x18003e540  pop     rdi
0x18003e541  pop     rsi
0x18003e542  pop     rbp
0x18003e543  retn
```
