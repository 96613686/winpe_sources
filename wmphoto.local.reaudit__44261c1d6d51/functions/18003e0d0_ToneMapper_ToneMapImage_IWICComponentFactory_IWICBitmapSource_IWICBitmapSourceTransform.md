# ToneMapper::ToneMapImage(IWICComponentFactory *,IWICBitmapSource *,IWICBitmapSourceTransform * *)

- ea: `0x18003e0d0`
- end: `0x18003e2e2`
- name: `?ToneMapImage@ToneMapper@@QEAAJPEAUIWICComponentFactory@@PEAUIWICBitmapSource@@PEAPEAUIWICBitmapSourceTransform@@@Z`
- size: `530`
- prototype: `__int64 __fastcall(ToneMapper *__hidden this, struct IWICComponentFactory *, struct IWICBitmapSource *, struct IWICBitmapSourceTransform **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180031850`

## callees

- `0x180036420`
- `0x18003d6c0`
- `0x18003e0d0`
- `0x180043e34`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ToneMapper::ToneMapImage(
        ToneMapper *this,
        struct IWICComponentFactory *a2,
        struct IWICBitmapSource *a3,
        struct IWICBitmapSourceTransform **a4)
{
  int v7; // ebx
  __int64 v8; // rbx
  __int64 *v9; // rdi
  GUID v10; // xmm0
  HRESULT (__stdcall *QueryInterface)(IWICComponentFactory *, const IID *const, void **); // rbx
  __int64 v12; // rcx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64 *); // rdi
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // [rsp+30h] [rbp-49h] BYREF
  __int64 v20; // [rsp+38h] [rbp-41h] BYREF
  __int64 v21; // [rsp+40h] [rbp-39h] BYREF
  struct IWICComponentFactory *v22; // [rsp+48h] [rbp-31h] BYREF
  GUID v23; // [rsp+50h] [rbp-29h] BYREF
  __int128 Buf1; // [rsp+60h] [rbp-19h] BYREF
  __int128 v25; // [rsp+70h] [rbp-9h]
  __int128 v26; // [rsp+80h] [rbp+7h]
  __int64 v27; // [rsp+90h] [rbp+17h]

  v22 = a2;
  Buf1 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v23 = GUID_WICPixelFormat32bppBGR;
  v20 = 0;
  v19 = 0;
  *a4 = 0;
  v7 = ((__int64 (__fastcall *)(struct IWICBitmapSource *, __int128 *))a3->lpVtbl->GetPixelFormat)(a3, &Buf1);
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
        goto LABEL_17;
      }
    }
    Buf1 = *(_OWORD *)v9;
    v25 = *((_OWORD *)v9 + 1);
    v26 = *((_OWORD *)v9 + 2);
    v27 = v9[6];
    if ( (_mm_cvtsi128_si32((__m128i)(unsigned __int64)v27) & 0x10) != 0 )
      v10 = GUID_WICPixelFormat32bppPBGRA;
    else
      v10 = GUID_WICPixelFormat32bppBGR;
    v23 = v10;
    QueryInterface = a2->lpVtbl->QueryInterface;
    v12 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v7 = ((__int64 (__fastcall *)(struct IWICComponentFactory *, GUID *, __int64 *))QueryInterface)(
           a2,
           &GUID_489b3d8b_624a_4258_b678_7eece70f299d,
           &v20);
    if ( v7 >= 0 )
    {
      v13 = v20;
      v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 232LL);
      v15 = v19;
      if ( v19 )
      {
        v19 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v7 = v14(v13, &v19);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64, struct IWICBitmapSource *, GUID *, __int64))(*(_QWORD *)v19 + 72LL))(
               v19,
               a3,
               &v23,
               2);
        if ( v7 >= 0 )
        {
          v21 = v19;
          v7 = Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(
                 a4,
                 &v22,
                 &v21);
        }
      }
    }
  }
LABEL_17:
  v16 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003e0d0  mov     [rsp-8+arg_0], rbx
0x18003e0d5  push    rbp
0x18003e0d6  push    rsi
0x18003e0d7  push    rdi
0x18003e0d8  push    r12
0x18003e0da  push    r13
0x18003e0dc  push    r14
0x18003e0de  push    r15
0x18003e0e0  lea     rbp, [rsp-27h]
0x18003e0e5  sub     rsp, 0A0h
0x18003e0ec  mov     rax, cs:__security_cookie
0x18003e0f3  xor     rax, rsp
0x18003e0f6  mov     [rbp+57h+var_38], rax
0x18003e0fa  mov     r14, r9
0x18003e0fd  mov     r15, r8
0x18003e100  mov     rsi, rdx
0x18003e103  mov     [rbp+57h+var_88], rdx
0x18003e107  xorps   xmm0, xmm0
0x18003e10a  xor     eax, eax
0x18003e10c  movups  [rbp+57h+Buf1], xmm0
0x18003e110  movups  [rbp+57h+var_60], xmm0
0x18003e114  movups  [rbp+57h+var_50], xmm0
0x18003e118  mov     [rbp+57h+var_40], rax
0x18003e11c  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGR.Data1
0x18003e123  movaps  [rbp+57h+var_80], xmm0
0x18003e127  xor     r12d, r12d
0x18003e12a  mov     [rbp+57h+var_98], r12
0x18003e12e  mov     [rbp+57h+var_A0], r12
0x18003e132  mov     [r9], r12
0x18003e135  mov     rax, [r8]
0x18003e138  lea     rdx, [rbp+57h+Buf1]
0x18003e13c  mov     rcx, r8
0x18003e13f  mov     rax, [rax+20h]
0x18003e143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e148  mov     ebx, eax
0x18003e14a  test    eax, eax
0x18003e14c  js      loc_18003E284
0x18003e152  mov     ebx, r12d
0x18003e155  lea     r13, qword_180050540
0x18003e15c  nop     dword ptr [rax+00h]
0x18003e160  imul    rdi, rbx, 38h ; '8'
0x18003e164  add     rdi, r13
0x18003e167  mov     r8d, 10h; Size
0x18003e16d  mov     rdx, rdi; Buf2
0x18003e170  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003e174  call    memcmp_0
0x18003e179  test    eax, eax
0x18003e17b  jz      short loc_18003E190
0x18003e17d  inc     rbx
0x18003e180  cmp     rbx, 3Dh ; '='
0x18003e184  jb      short loc_18003E160
0x18003e186  mov     ebx, 88982F80h
0x18003e18b  jmp     loc_18003E284
0x18003e190  movups  xmm0, xmmword ptr [rdi]
0x18003e193  movups  [rbp+57h+Buf1], xmm0
0x18003e197  movups  xmm1, xmmword ptr [rdi+10h]
0x18003e19b  movups  [rbp+57h+var_60], xmm1
0x18003e19f  movups  xmm0, xmmword ptr [rdi+20h]
0x18003e1a3  movups  [rbp+57h+var_50], xmm0
0x18003e1a7  movsd   xmm1, qword ptr [rdi+30h]
0x18003e1ac  movsd   [rbp+57h+var_40], xmm1
0x18003e1b1  movd    eax, xmm1
0x18003e1b5  test    al, 10h
0x18003e1b7  jz      short loc_18003E1C2
0x18003e1b9  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppPBGRA.Data1
0x18003e1c0  jmp     short loc_18003E1C9
0x18003e1c2  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGR.Data1
0x18003e1c9  movdqa  [rbp+57h+var_80], xmm0
0x18003e1ce  mov     rax, [rsi]
0x18003e1d1  mov     rbx, [rax]
0x18003e1d4  mov     rcx, [rbp+57h+var_98]
0x18003e1d8  test    rcx, rcx
0x18003e1db  jz      short loc_18003E1EE
0x18003e1dd  mov     [rbp+57h+var_98], r12
0x18003e1e1  mov     rdx, [rcx]
0x18003e1e4  mov     rax, [rdx+10h]
0x18003e1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e1ed  nop
0x18003e1ee  lea     r8, [rbp+57h+var_98]
0x18003e1f2  lea     rdx, _GUID_489b3d8b_624a_4258_b678_7eece70f299d
0x18003e1f9  mov     rcx, rsi
0x18003e1fc  mov     rax, rbx
0x18003e1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e204  mov     ebx, eax
0x18003e206  test    eax, eax
0x18003e208  js      short loc_18003E284
0x18003e20a  mov     rbx, [rbp+57h+var_98]
0x18003e20e  mov     rax, [rbx]
0x18003e211  mov     rdi, [rax+0E8h]
0x18003e218  mov     rcx, [rbp+57h+var_A0]
0x18003e21c  test    rcx, rcx
0x18003e21f  jz      short loc_18003E232
0x18003e221  mov     [rbp+57h+var_A0], r12
0x18003e225  mov     rdx, [rcx]
0x18003e228  mov     rax, [rdx+10h]
0x18003e22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e231  nop
0x18003e232  lea     rdx, [rbp+57h+var_A0]
0x18003e236  mov     rcx, rbx
0x18003e239  mov     rax, rdi
0x18003e23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e241  mov     ebx, eax
0x18003e243  test    eax, eax
0x18003e245  js      short loc_18003E284
0x18003e247  mov     rcx, [rbp+57h+var_A0]
0x18003e24b  mov     rax, [rcx]
0x18003e24e  mov     r9d, 2
0x18003e254  lea     r8, [rbp+57h+var_80]
0x18003e258  mov     rdx, r15
0x18003e25b  mov     rax, [rax+48h]
0x18003e25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e264  mov     ebx, eax
0x18003e266  test    eax, eax
0x18003e268  js      short loc_18003E284
0x18003e26a  mov     rax, [rbp+57h+var_A0]
0x18003e26e  mov     [rbp+57h+var_90], rax
0x18003e272  lea     r8, [rbp+57h+var_90]
0x18003e276  lea     rdx, [rbp+57h+var_88]
0x18003e27a  mov     rcx, r14
0x18003e27d  call    ??$MakeAndInitialize@VCBitmapSourceTransformOnBitmapSource@@UIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@PEAUIWICBitmapToneMapper@@@Details@WRL@Microsoft@@YAJPEAPEAUIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@$$QEAPEAUIWICBitmapToneMapper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(IWICBitmapSourceTransform * *,IWICComponentFactory * &,IWICBitmapToneMapper * &&)
0x18003e282  mov     ebx, eax
0x18003e284  mov     rcx, [rbp+57h+var_A0]
0x18003e288  test    rcx, rcx
0x18003e28b  jz      short loc_18003E29E
0x18003e28d  mov     [rbp+57h+var_A0], r12
0x18003e291  mov     rax, [rcx]
0x18003e294  mov     rax, [rax+10h]
0x18003e298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e29d  nop
0x18003e29e  mov     rcx, [rbp+57h+var_98]
0x18003e2a2  test    rcx, rcx
0x18003e2a5  jz      short loc_18003E2B8
0x18003e2a7  mov     [rbp+57h+var_98], r12
0x18003e2ab  mov     rax, [rcx]
0x18003e2ae  mov     rax, [rax+10h]
0x18003e2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e2b7  nop
0x18003e2b8  mov     eax, ebx
0x18003e2ba  mov     rcx, [rbp+57h+var_38]
0x18003e2be  xor     rcx, rsp; StackCookie
0x18003e2c1  call    __security_check_cookie
0x18003e2c6  mov     rbx, [rsp+0D0h+arg_0]
0x18003e2ce  add     rsp, 0A0h
0x18003e2d5  pop     r15
0x18003e2d7  pop     r14
0x18003e2d9  pop     r13
0x18003e2db  pop     r12
0x18003e2dd  pop     rdi
0x18003e2de  pop     rsi
0x18003e2df  pop     rbp
0x18003e2e0  retn
```
