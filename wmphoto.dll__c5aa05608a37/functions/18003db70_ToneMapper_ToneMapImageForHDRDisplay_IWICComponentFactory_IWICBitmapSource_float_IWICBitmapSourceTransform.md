# ToneMapper::ToneMapImageForHDRDisplay(IWICComponentFactory *,IWICBitmapSource *,float,IWICBitmapSourceTransform * *)

- ea: `0x18003db70`
- end: `0x18003ddc4`
- name: `?ToneMapImageForHDRDisplay@ToneMapper@@QEAAJPEAUIWICComponentFactory@@PEAUIWICBitmapSource@@MPEAPEAUIWICBitmapSourceTransform@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(ToneMapper *__hidden this, struct IWICComponentFactory *, struct IWICBitmapSource *, float, struct IWICBitmapSourceTransform **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800314f0`

## callees

- `0x180035e50`
- `0x18003ce80`
- `0x18003db70`
- `0x180043624`
- `0x180044010`

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
  __m128i *v9; // rdi
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
  __m128i Buf1; // [rsp+70h] [rbp-31h] BYREF
  __m128i v26; // [rsp+80h] [rbp-21h]
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
  v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __m128i *))a3->lpVtbl->GetPixelFormat)(a3, &Buf1);
  if ( v7 >= 0 )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = (__m128i *)((char *)&unk_18004F540 + 56 * v8);
      if ( !memcmp_0(&Buf1, v9, 0x10u) )
        break;
      if ( (unsigned __int64)++v8 >= 0x3D )
      {
        v7 = -2003292288;
        goto LABEL_19;
      }
    }
    v10 = (GUID)*v9;
    Buf1 = *v9;
    v26 = v9[1];
    v11 = v9[2];
    v27 = v11;
    v28 = v9[3].m128i_i64[0];
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
0x18003db70  mov     [rsp-8+arg_0], rbx
0x18003db75  push    rbp
0x18003db76  push    rsi
0x18003db77  push    rdi
0x18003db78  push    r12
0x18003db7a  push    r13
0x18003db7c  push    r14
0x18003db7e  push    r15
0x18003db80  lea     rbp, [rsp-1Fh]
0x18003db85  sub     rsp, 0C0h
0x18003db8c  movaps  [rsp+0F0h+var_40], xmm6
0x18003db94  mov     rax, cs:__security_cookie
0x18003db9b  xor     rax, rsp
0x18003db9e  mov     [rbp+4Fh+var_48], rax
0x18003dba2  movaps  xmm6, xmm3
0x18003dba5  mov     r15, r8
0x18003dba8  mov     rsi, rdx
0x18003dbab  mov     [rbp+4Fh+var_98], rdx
0x18003dbaf  mov     r14, [rbp+4Fh+arg_20]
0x18003dbb3  xorps   xmm0, xmm0
0x18003dbb6  xor     eax, eax
0x18003dbb8  movups  [rbp+4Fh+Buf1], xmm0
0x18003dbbc  movups  [rbp+4Fh+var_70], xmm0
0x18003dbc0  movups  [rbp+4Fh+var_60], xmm0
0x18003dbc4  mov     [rbp+4Fh+var_50], rax
0x18003dbc8  movups  [rbp+4Fh+var_90], xmm0
0x18003dbcc  xor     r12d, r12d
0x18003dbcf  mov     [rbp+4Fh+var_A8], r12
0x18003dbd3  mov     [rbp+4Fh+var_B0], r12
0x18003dbd7  mov     [r14], r12
0x18003dbda  mov     rax, [r8]
0x18003dbdd  lea     rdx, [rbp+4Fh+Buf1]
0x18003dbe1  mov     rcx, r8
0x18003dbe4  mov     rax, [rax+20h]
0x18003dbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbed  mov     ebx, eax
0x18003dbef  test    eax, eax
0x18003dbf1  js      loc_18003DD5F
0x18003dbf7  mov     ebx, r12d
0x18003dbfa  lea     r13, unk_18004F540
0x18003dc01  nop     dword ptr [rax+00h]
0x18003dc05  nop     word ptr [rax+rax+00000000h]
0x18003dc10  imul    rdi, rbx, 38h ; '8'
0x18003dc14  add     rdi, r13
0x18003dc17  mov     r8d, 10h; Size
0x18003dc1d  mov     rdx, rdi; Buf2
0x18003dc20  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18003dc24  call    memcmp_0
0x18003dc29  test    eax, eax
0x18003dc2b  jz      short loc_18003DC40
0x18003dc2d  inc     rbx
0x18003dc30  cmp     rbx, 3Dh ; '='
0x18003dc34  jb      short loc_18003DC10
0x18003dc36  mov     ebx, 88982F80h
0x18003dc3b  jmp     loc_18003DD5F
0x18003dc40  movups  xmm1, xmmword ptr [rdi]
0x18003dc43  movups  [rbp+4Fh+Buf1], xmm1
0x18003dc47  movups  xmm0, xmmword ptr [rdi+10h]
0x18003dc4b  movups  [rbp+4Fh+var_70], xmm0
0x18003dc4f  movups  xmm2, xmmword ptr [rdi+20h]
0x18003dc53  movups  [rbp+4Fh+var_60], xmm2
0x18003dc57  movsd   xmm0, qword ptr [rdi+30h]
0x18003dc5c  movsd   [rbp+4Fh+var_50], xmm0
0x18003dc61  movd    eax, xmm0
0x18003dc65  test    al, 10h
0x18003dc67  jz      short loc_18003DC8E
0x18003dc69  movd    eax, xmm2
0x18003dc6d  cmp     eax, 7
0x18003dc70  jge     short loc_18003DC80
0x18003dc72  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat64bppPRGBAHalf.Data1
0x18003dc79  movdqa  [rbp+4Fh+var_90], xmm0
0x18003dc7e  jmp     short loc_18003DC92
0x18003dc80  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat128bppPRGBAFloat.Data1
0x18003dc87  movdqa  [rbp+4Fh+var_90], xmm0
0x18003dc8c  jmp     short loc_18003DC92
0x18003dc8e  movups  [rbp+4Fh+var_90], xmm1
0x18003dc92  mov     rax, [rsi]
0x18003dc95  mov     rbx, [rax]
0x18003dc98  mov     rcx, [rbp+4Fh+var_A8]
0x18003dc9c  test    rcx, rcx
0x18003dc9f  jz      short loc_18003DCB2
0x18003dca1  mov     [rbp+4Fh+var_A8], r12
0x18003dca5  mov     rdx, [rcx]
0x18003dca8  mov     rax, [rdx+10h]
0x18003dcac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcb1  nop
0x18003dcb2  lea     r8, [rbp+4Fh+var_A8]
0x18003dcb6  lea     rdx, _GUID_489b3d8b_624a_4258_b678_7eece70f299d
0x18003dcbd  mov     rcx, rsi
0x18003dcc0  mov     rax, rbx
0x18003dcc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcc8  mov     ebx, eax
0x18003dcca  test    eax, eax
0x18003dccc  js      loc_18003DD5F
0x18003dcd2  mov     rbx, [rbp+4Fh+var_A8]
0x18003dcd6  mov     rax, [rbx]
0x18003dcd9  mov     rdi, [rax+0E8h]
0x18003dce0  mov     rcx, [rbp+4Fh+var_B0]
0x18003dce4  test    rcx, rcx
0x18003dce7  jz      short loc_18003DCFA
0x18003dce9  mov     [rbp+4Fh+var_B0], r12
0x18003dced  mov     rdx, [rcx]
0x18003dcf0  mov     rax, [rdx+10h]
0x18003dcf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcf9  nop
0x18003dcfa  lea     rdx, [rbp+4Fh+var_B0]
0x18003dcfe  mov     rcx, rbx
0x18003dd01  mov     rax, rdi
0x18003dd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd09  mov     ebx, eax
0x18003dd0b  test    eax, eax
0x18003dd0d  js      short loc_18003DD5F
0x18003dd0f  mov     rcx, [rbp+4Fh+var_B0]
0x18003dd13  mov     rax, [rcx]
0x18003dd16  mov     [rsp+0F0h+var_C8], 2
0x18003dd1e  movss   xmm0, cs:__real@434b0000
0x18003dd26  movss   [rsp+0F0h+var_D0], xmm0
0x18003dd2c  movaps  xmm3, xmm6
0x18003dd2f  lea     r8, [rbp+4Fh+var_90]
0x18003dd33  mov     rdx, r15
0x18003dd36  mov     rax, [rax+40h]
0x18003dd3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd3f  mov     ebx, eax
0x18003dd41  test    eax, eax
0x18003dd43  js      short loc_18003DD5F
0x18003dd45  mov     rax, [rbp+4Fh+var_B0]
0x18003dd49  mov     [rbp+4Fh+var_A0], rax
0x18003dd4d  lea     r8, [rbp+4Fh+var_A0]
0x18003dd51  lea     rdx, [rbp+4Fh+var_98]
0x18003dd55  mov     rcx, r14
0x18003dd58  call    ??$MakeAndInitialize@VCBitmapSourceTransformOnBitmapSource@@UIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@PEAUIWICBitmapToneMapper@@@Details@WRL@Microsoft@@YAJPEAPEAUIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@$$QEAPEAUIWICBitmapToneMapper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(IWICBitmapSourceTransform * *,IWICComponentFactory * &,IWICBitmapToneMapper * &&)
0x18003dd5d  mov     ebx, eax
0x18003dd5f  mov     rcx, [rbp+4Fh+var_B0]
0x18003dd63  test    rcx, rcx
0x18003dd66  jz      short loc_18003DD79
0x18003dd68  mov     [rbp+4Fh+var_B0], r12
0x18003dd6c  mov     rax, [rcx]
0x18003dd6f  mov     rax, [rax+10h]
0x18003dd73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd78  nop
0x18003dd79  mov     rcx, [rbp+4Fh+var_A8]
0x18003dd7d  test    rcx, rcx
0x18003dd80  jz      short loc_18003DD93
0x18003dd82  mov     [rbp+4Fh+var_A8], r12
0x18003dd86  mov     rax, [rcx]
0x18003dd89  mov     rax, [rax+10h]
0x18003dd8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd92  nop
0x18003dd93  mov     eax, ebx
0x18003dd95  mov     rcx, [rbp+4Fh+var_48]
0x18003dd99  xor     rcx, rsp; StackCookie
0x18003dd9c  call    __security_check_cookie
0x18003dda1  mov     rbx, [rsp+0F0h+arg_0]
0x18003dda9  movaps  xmm6, [rsp+0F0h+var_40]
0x18003ddb1  add     rsp, 0C0h
0x18003ddb8  pop     r15
0x18003ddba  pop     r14
0x18003ddbc  pop     r13
0x18003ddbe  pop     r12
0x18003ddc0  pop     rdi
0x18003ddc1  pop     rsi
0x18003ddc2  pop     rbp
0x18003ddc3  retn
```
