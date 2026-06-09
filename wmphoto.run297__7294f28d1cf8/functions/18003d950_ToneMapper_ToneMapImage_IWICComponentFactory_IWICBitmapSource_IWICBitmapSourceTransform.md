# ToneMapper::ToneMapImage(IWICComponentFactory *,IWICBitmapSource *,IWICBitmapSourceTransform * *)

- ea: `0x18003d950`
- end: `0x18003db61`
- name: `?ToneMapImage@ToneMapper@@QEAAJPEAUIWICComponentFactory@@PEAUIWICBitmapSource@@PEAPEAUIWICBitmapSourceTransform@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(ToneMapper *__hidden this, struct IWICComponentFactory *, struct IWICBitmapSource *, struct IWICBitmapSourceTransform **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800314f0`

## callees

- `0x180035e50`
- `0x18003ce80`
- `0x18003d950`
- `0x180043624`
- `0x180044010`

## pseudocode

```c
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
      v9 = &qword_18004F540[7 * v8];
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
0x18003d950  mov     [rsp-8+arg_0], rbx
0x18003d955  push    rbp
0x18003d956  push    rsi
0x18003d957  push    rdi
0x18003d958  push    r12
0x18003d95a  push    r13
0x18003d95c  push    r14
0x18003d95e  push    r15
0x18003d960  lea     rbp, [rsp-27h]
0x18003d965  sub     rsp, 0A0h
0x18003d96c  mov     rax, cs:__security_cookie
0x18003d973  xor     rax, rsp
0x18003d976  mov     [rbp+57h+var_38], rax
0x18003d97a  mov     r14, r9
0x18003d97d  mov     r15, r8
0x18003d980  mov     rsi, rdx
0x18003d983  mov     [rbp+57h+var_88], rdx
0x18003d987  xorps   xmm0, xmm0
0x18003d98a  xor     eax, eax
0x18003d98c  movups  [rbp+57h+Buf1], xmm0
0x18003d990  movups  [rbp+57h+var_60], xmm0
0x18003d994  movups  [rbp+57h+var_50], xmm0
0x18003d998  mov     [rbp+57h+var_40], rax
0x18003d99c  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGR.Data1
0x18003d9a3  movaps  [rbp+57h+var_80], xmm0
0x18003d9a7  xor     r12d, r12d
0x18003d9aa  mov     [rbp+57h+var_98], r12
0x18003d9ae  mov     [rbp+57h+var_A0], r12
0x18003d9b2  mov     [r9], r12
0x18003d9b5  mov     rax, [r8]
0x18003d9b8  lea     rdx, [rbp+57h+Buf1]
0x18003d9bc  mov     rcx, r8
0x18003d9bf  mov     rax, [rax+20h]
0x18003d9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9c8  mov     ebx, eax
0x18003d9ca  test    eax, eax
0x18003d9cc  js      loc_18003DB04
0x18003d9d2  mov     ebx, r12d
0x18003d9d5  lea     r13, qword_18004F540
0x18003d9dc  nop     dword ptr [rax+00h]
0x18003d9e0  imul    rdi, rbx, 38h ; '8'
0x18003d9e4  add     rdi, r13
0x18003d9e7  mov     r8d, 10h; Size
0x18003d9ed  mov     rdx, rdi; Buf2
0x18003d9f0  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18003d9f4  call    memcmp_0
0x18003d9f9  test    eax, eax
0x18003d9fb  jz      short loc_18003DA10
0x18003d9fd  inc     rbx
0x18003da00  cmp     rbx, 3Dh ; '='
0x18003da04  jb      short loc_18003D9E0
0x18003da06  mov     ebx, 88982F80h
0x18003da0b  jmp     loc_18003DB04
0x18003da10  movups  xmm0, xmmword ptr [rdi]
0x18003da13  movups  [rbp+57h+Buf1], xmm0
0x18003da17  movups  xmm1, xmmword ptr [rdi+10h]
0x18003da1b  movups  [rbp+57h+var_60], xmm1
0x18003da1f  movups  xmm0, xmmword ptr [rdi+20h]
0x18003da23  movups  [rbp+57h+var_50], xmm0
0x18003da27  movsd   xmm1, qword ptr [rdi+30h]
0x18003da2c  movsd   [rbp+57h+var_40], xmm1
0x18003da31  movd    eax, xmm1
0x18003da35  test    al, 10h
0x18003da37  jz      short loc_18003DA42
0x18003da39  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppPBGRA.Data1
0x18003da40  jmp     short loc_18003DA49
0x18003da42  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGR.Data1
0x18003da49  movdqa  [rbp+57h+var_80], xmm0
0x18003da4e  mov     rax, [rsi]
0x18003da51  mov     rbx, [rax]
0x18003da54  mov     rcx, [rbp+57h+var_98]
0x18003da58  test    rcx, rcx
0x18003da5b  jz      short loc_18003DA6E
0x18003da5d  mov     [rbp+57h+var_98], r12
0x18003da61  mov     rdx, [rcx]
0x18003da64  mov     rax, [rdx+10h]
0x18003da68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da6d  nop
0x18003da6e  lea     r8, [rbp+57h+var_98]
0x18003da72  lea     rdx, _GUID_489b3d8b_624a_4258_b678_7eece70f299d
0x18003da79  mov     rcx, rsi
0x18003da7c  mov     rax, rbx
0x18003da7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da84  mov     ebx, eax
0x18003da86  test    eax, eax
0x18003da88  js      short loc_18003DB04
0x18003da8a  mov     rbx, [rbp+57h+var_98]
0x18003da8e  mov     rax, [rbx]
0x18003da91  mov     rdi, [rax+0E8h]
0x18003da98  mov     rcx, [rbp+57h+var_A0]
0x18003da9c  test    rcx, rcx
0x18003da9f  jz      short loc_18003DAB2
0x18003daa1  mov     [rbp+57h+var_A0], r12
0x18003daa5  mov     rdx, [rcx]
0x18003daa8  mov     rax, [rdx+10h]
0x18003daac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dab1  nop
0x18003dab2  lea     rdx, [rbp+57h+var_A0]
0x18003dab6  mov     rcx, rbx
0x18003dab9  mov     rax, rdi
0x18003dabc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dac1  mov     ebx, eax
0x18003dac3  test    eax, eax
0x18003dac5  js      short loc_18003DB04
0x18003dac7  mov     rcx, [rbp+57h+var_A0]
0x18003dacb  mov     rax, [rcx]
0x18003dace  mov     r9d, 2
0x18003dad4  lea     r8, [rbp+57h+var_80]
0x18003dad8  mov     rdx, r15
0x18003dadb  mov     rax, [rax+48h]
0x18003dadf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dae4  mov     ebx, eax
0x18003dae6  test    eax, eax
0x18003dae8  js      short loc_18003DB04
0x18003daea  mov     rax, [rbp+57h+var_A0]
0x18003daee  mov     [rbp+57h+var_90], rax
0x18003daf2  lea     r8, [rbp+57h+var_90]
0x18003daf6  lea     rdx, [rbp+57h+var_88]
0x18003dafa  mov     rcx, r14
0x18003dafd  call    ??$MakeAndInitialize@VCBitmapSourceTransformOnBitmapSource@@UIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@PEAUIWICBitmapToneMapper@@@Details@WRL@Microsoft@@YAJPEAPEAUIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@$$QEAPEAUIWICBitmapToneMapper@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(IWICBitmapSourceTransform * *,IWICComponentFactory * &,IWICBitmapToneMapper * &&)
0x18003db02  mov     ebx, eax
0x18003db04  mov     rcx, [rbp+57h+var_A0]
0x18003db08  test    rcx, rcx
0x18003db0b  jz      short loc_18003DB1E
0x18003db0d  mov     [rbp+57h+var_A0], r12
0x18003db11  mov     rax, [rcx]
0x18003db14  mov     rax, [rax+10h]
0x18003db18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db1d  nop
0x18003db1e  mov     rcx, [rbp+57h+var_98]
0x18003db22  test    rcx, rcx
0x18003db25  jz      short loc_18003DB38
0x18003db27  mov     [rbp+57h+var_98], r12
0x18003db2b  mov     rax, [rcx]
0x18003db2e  mov     rax, [rax+10h]
0x18003db32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003db37  nop
0x18003db38  mov     eax, ebx
0x18003db3a  mov     rcx, [rbp+57h+var_38]
0x18003db3e  xor     rcx, rsp; StackCookie
0x18003db41  call    __security_check_cookie
0x18003db46  mov     rbx, [rsp+0D0h+arg_0]
0x18003db4e  add     rsp, 0A0h
0x18003db55  pop     r15
0x18003db57  pop     r14
0x18003db59  pop     r13
0x18003db5b  pop     r12
0x18003db5d  pop     rdi
0x18003db5e  pop     rsi
0x18003db5f  pop     rbp
0x18003db60  retn
```
