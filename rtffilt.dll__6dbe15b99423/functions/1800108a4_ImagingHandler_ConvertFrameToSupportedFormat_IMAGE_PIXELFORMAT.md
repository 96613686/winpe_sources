# ImagingHandler::ConvertFrameToSupportedFormat(IMAGE_PIXELFORMAT *)

- ea: `0x1800108a4`
- end: `0x180010b7a`
- name: `?ConvertFrameToSupportedFormat@ImagingHandler@@AEAAJPEAW4IMAGE_PIXELFORMAT@@@Z`
- size: `726`
- prototype: `__int64 __fastcall(ImagingHandler *__hidden this, enum IMAGE_PIXELFORMAT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013b90`

## callees

- `0x180001e40`
- `0x18000a844`
- `0x1800108a4`
- `0x180011384`
- `0x180018f38`
- `0x1800198a4`
- `0x18001b010`

## string_xrefs

- `0x180010a47`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x1800108f8`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`
- `0x180010979`: `onecoreuap\base\appmodel\Search\filters\common\imageprocessing\imagingHandler.h`

## pseudocode

```c
__int64 __fastcall ImagingHandler::ConvertFrameToSupportedFormat(ImagingHandler *this, enum IMAGE_PIXELFORMAT *a2)
{
  int v4; // eax
  int v5; // edi
  __int64 v7; // rdx
  GUID v8; // xmm0
  int v9; // eax
  const wchar_t *v10; // r9
  _QWORD *v11; // rdi
  __int64 (__fastcall *v12)(_QWORD *, __int64, __int64, char *); // rsi
  unsigned int v13; // ebx
  _QWORD *v14; // rsi
  unsigned int (__fastcall *v15)(_QWORD *, _QWORD, __int64, char *); // r14
  int v16; // [rsp+20h] [rbp-60h]
  __int64 v17; // [rsp+40h] [rbp-40h] BYREF
  int v18; // [rsp+48h] [rbp-38h] BYREF
  __int128 Buf1; // [rsp+50h] [rbp-30h] BYREF
  GUID v20; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  Buf1 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2), &Buf1);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
      (const char *)(unsigned int)v4,
      v16);
    return (unsigned int)v5;
  }
  if ( !memcmp_0(&Buf1, &GUID_WICPixelFormat24bppBGR, 0x10u) || !memcmp_0(&Buf1, &GUID_WICPixelFormat32bppBGRA, 0x10u) )
  {
    *(_DWORD *)a2 = memcmp_0(&Buf1, &GUID_WICPixelFormat24bppBGR, 0x10u) == 0 ? 2 : 0;
    v14 = *(_QWORD **)this;
    v15 = *(unsigned int (__fastcall **)(_QWORD *, _QWORD, __int64, char *))(**(_QWORD **)this + 144LL);
    if ( *((_QWORD *)this + 3) )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref((char *)this + 24);
    return v15(v14, *((_QWORD *)this + 2), 1, (char *)this + 24);
  }
  v17 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)this + 80LL))(*(_QWORD *)this, &v17);
  if ( v5 < 0 )
  {
    v7 = 244;
    goto LABEL_8;
  }
  v18 = 0;
  if ( !memcmp_0(&Buf1, &GUID_WICPixelFormat24bppRGB, 0x10u)
    || !memcmp_0(&Buf1, &GUID_WICPixelFormat48bppRGB, 0x10u)
    || !memcmp_0(&Buf1, &GUID_WICPixelFormat48bppBGR, 0x10u) )
  {
    v8 = GUID_WICPixelFormat24bppBGR;
    v9 = 2;
  }
  else
  {
    v8 = GUID_WICPixelFormat32bppBGRA;
    v9 = 0;
  }
  v20 = v8;
  *(_DWORD *)a2 = v9;
  v5 = (*(__int64 (__fastcall **)(__int64, __int128 *, GUID *, int *))(*(_QWORD *)v17 + 72LL))(v17, &Buf1, &v20, &v18);
  if ( v5 < 0 )
  {
    v7 = 262;
    goto LABEL_8;
  }
  if ( v18 )
  {
    v16 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD))(*(_QWORD *)v17 + 64LL))(
           v17,
           *((_QWORD *)this + 2),
           &v20,
           0);
    if ( v5 < 0 )
    {
      v7 = 277;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
        (const char *)(unsigned int)v5,
        v16);
      if ( v17 )
        winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v17);
      return (unsigned int)v5;
    }
    v11 = *(_QWORD **)this;
    v12 = *(__int64 (__fastcall **)(_QWORD *, __int64, __int64, char *))(**(_QWORD **)this + 144LL);
    if ( *((_QWORD *)this + 3) )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref((char *)this + 24);
    v13 = v12(v11, v17, 1, (char *)this + 24);
    if ( v17 )
      winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v17);
    return v13;
  }
  SearchIndexerTrace::Error(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\filters\\common\\imageprocessing\\imagingHandler.h",
    (const wchar_t *)0x10B,
    (unsigned int)L"ImagingHandler::ConvertFrameToSupportedFormat : Unable to convert from source format to premultiplied Bgra8",
    v10);
  if ( v17 )
    winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(&v17);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800108a4  mov     [rsp-18h+arg_10], rbx
0x1800108a9  mov     [rsp-18h+arg_18], rsi
0x1800108ae  push    rbp
0x1800108af  push    rdi
0x1800108b0  push    r14
0x1800108b2  mov     rbp, rsp
0x1800108b5  sub     rsp, 80h
0x1800108bc  mov     rax, cs:__security_cookie
0x1800108c3  xor     rax, rsp
0x1800108c6  mov     [rbp+var_10], rax
0x1800108ca  mov     rsi, rdx
0x1800108cd  mov     rbx, rcx
0x1800108d0  xorps   xmm0, xmm0
0x1800108d3  movups  [rbp+Buf1], xmm0
0x1800108d7  mov     rcx, [rcx+10h]
0x1800108db  mov     rax, [rcx]
0x1800108de  lea     rdx, [rbp+Buf1]
0x1800108e2  mov     rax, [rax+20h]
0x1800108e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108eb  mov     edi, eax
0x1800108ed  test    eax, eax
0x1800108ef  jns     short loc_180010910
0x1800108f1  mov     rcx, [rbp+18h]; this
0x1800108f5  mov     r9d, eax; char *
0x1800108f8  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x1800108ff  mov     edx, 0E7h; void *
0x180010904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010909  mov     eax, edi
0x18001090b  jmp     loc_180010B56
0x180010910  mov     r14d, 10h
0x180010916  mov     r8d, r14d; Size
0x180010919  lea     rdx, GUID_WICPixelFormat24bppBGR; Buf2
0x180010920  lea     rcx, [rbp+Buf1]; Buf1
0x180010924  call    memcmp_0
0x180010929  test    eax, eax
0x18001092b  jz      loc_180010AFD
0x180010931  mov     r8d, r14d; Size
0x180010934  lea     rdx, GUID_WICPixelFormat32bppBGRA; Buf2
0x18001093b  lea     rcx, [rbp+Buf1]; Buf1
0x18001093f  call    memcmp_0
0x180010944  test    eax, eax
0x180010946  jz      loc_180010AFD
0x18001094c  mov     [rbp+var_40], 0
0x180010954  mov     rcx, [rbx]
0x180010957  mov     rax, [rcx]
0x18001095a  lea     rdx, [rbp+var_40]
0x18001095e  mov     rax, [rax+50h]
0x180010962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010967  mov     edi, eax
0x180010969  test    eax, eax
0x18001096b  jns     short loc_18001099F
0x18001096d  mov     edx, 0F4h; void *
0x180010972  mov     rcx, [rbp+18h]; this
0x180010976  mov     r9d, edi; char *
0x180010979  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180010980  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010985  nop
0x180010986  cmp     [rbp+var_40], 0
0x18001098b  jz      loc_180010909
0x180010991  lea     rcx, [rbp+var_40]
0x180010995  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x18001099a  jmp     loc_180010909
0x18001099f  mov     [rbp+var_38], 0
0x1800109a6  mov     r8, r14; Size
0x1800109a9  lea     rdx, GUID_WICPixelFormat24bppRGB; Buf2
0x1800109b0  lea     rcx, [rbp+Buf1]; Buf1
0x1800109b4  call    memcmp_0
0x1800109b9  test    eax, eax
0x1800109bb  jz      short loc_1800109F6
0x1800109bd  mov     r8, r14; Size
0x1800109c0  lea     rdx, GUID_WICPixelFormat48bppRGB; Buf2
0x1800109c7  lea     rcx, [rbp+Buf1]; Buf1
0x1800109cb  call    memcmp_0
0x1800109d0  test    eax, eax
0x1800109d2  jz      short loc_1800109F6
0x1800109d4  mov     r8, r14; Size
0x1800109d7  lea     rdx, GUID_WICPixelFormat48bppBGR; Buf2
0x1800109de  lea     rcx, [rbp+Buf1]; Buf1
0x1800109e2  call    memcmp_0
0x1800109e7  test    eax, eax
0x1800109e9  jz      short loc_1800109F6
0x1800109eb  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x1800109f2  xor     eax, eax
0x1800109f4  jmp     short loc_180010A02
0x1800109f6  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat24bppBGR.Data1
0x1800109fd  mov     eax, 2
0x180010a02  movdqu  [rbp+var_20], xmm0
0x180010a07  mov     [rsi], eax
0x180010a09  mov     rcx, [rbp+var_40]
0x180010a0d  mov     rax, [rcx]
0x180010a10  lea     r9, [rbp+var_38]
0x180010a14  lea     r8, [rbp+var_20]
0x180010a18  lea     rdx, [rbp+Buf1]
0x180010a1c  mov     rax, [rax+48h]
0x180010a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a25  mov     edi, eax
0x180010a27  test    eax, eax
0x180010a29  jns     short loc_180010A35
0x180010a2b  mov     edx, 106h
0x180010a30  jmp     loc_180010972
0x180010a35  cmp     [rbp+var_38], 0
0x180010a39  jnz     short loc_180010A6E
0x180010a3b  lea     r8, aImaginghandler_3; "ImagingHandler::ConvertFrameToSupported"...
0x180010a42  mov     edx, 10Bh; wchar_t *
0x180010a47  lea     rcx, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\Search\\fil"...
0x180010a4e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180010a53  nop
0x180010a54  cmp     [rbp+var_40], 0
0x180010a59  jz      short loc_180010A64
0x180010a5b  lea     rcx, [rbp+var_40]
0x180010a5f  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180010a64  mov     eax, 80004005h
0x180010a69  jmp     loc_180010B56
0x180010a6e  mov     rcx, [rbp+var_40]
0x180010a72  mov     rax, [rcx]
0x180010a75  mov     [rsp+80h+var_50], 1
0x180010a7d  xorps   xmm0, xmm0
0x180010a80  movsd   [rsp+80h+var_58], xmm0
0x180010a86  mov     [rsp+80h+var_60], 0
0x180010a8f  xor     r9d, r9d
0x180010a92  lea     r8, [rbp+var_20]
0x180010a96  mov     rdx, [rbx+10h]
0x180010a9a  mov     rax, [rax+40h]
0x180010a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa3  mov     edi, eax
0x180010aa5  test    eax, eax
0x180010aa7  jns     short loc_180010AB3
0x180010aa9  mov     edx, 115h
0x180010aae  jmp     loc_180010972
0x180010ab3  mov     rdi, [rbx]
0x180010ab6  mov     rax, [rdi]
0x180010ab9  mov     rsi, [rax+90h]
0x180010ac0  cmp     qword ptr [rbx+18h], 0
0x180010ac5  jz      short loc_180010AD0
0x180010ac7  lea     rcx, [rbx+18h]
0x180010acb  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180010ad0  lea     r9, [rbx+18h]
0x180010ad4  mov     r8d, 1
0x180010ada  mov     rdx, [rbp+var_40]
0x180010ade  mov     rcx, rdi
0x180010ae1  mov     rax, rsi
0x180010ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ae9  mov     ebx, eax
0x180010aeb  cmp     [rbp+var_40], 0
0x180010af0  jz      short loc_180010B54
0x180010af2  lea     rcx, [rbp+var_40]
0x180010af6  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180010afb  jmp     short loc_180010B54
0x180010afd  mov     r8, r14; Size
0x180010b00  lea     rdx, GUID_WICPixelFormat24bppBGR; Buf2
0x180010b07  lea     rcx, [rbp+Buf1]; Buf1
0x180010b0b  call    memcmp_0
0x180010b10  neg     eax
0x180010b12  sbb     ecx, ecx
0x180010b14  not     ecx
0x180010b16  and     ecx, 2
0x180010b19  mov     [rsi], ecx
0x180010b1b  mov     rsi, [rbx]
0x180010b1e  mov     rax, [rsi]
0x180010b21  mov     r14, [rax+90h]
0x180010b28  lea     rdi, [rbx+18h]
0x180010b2c  cmp     qword ptr [rdi], 0
0x180010b30  jz      short loc_180010B3A
0x180010b32  mov     rcx, rdi
0x180010b35  call    ?unconditional_release_ref@?$com_ptr@UIWICBitmapFrameDecode@@@winrt@@AEAAXXZ; winrt::com_ptr<IWICBitmapFrameDecode>::unconditional_release_ref(void)
0x180010b3a  mov     r9, rdi
0x180010b3d  mov     r8d, 1
0x180010b43  mov     rdx, [rbx+10h]
0x180010b47  mov     rcx, rsi
0x180010b4a  mov     rax, r14
0x180010b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b52  mov     ebx, eax
0x180010b54  mov     eax, ebx
0x180010b56  mov     rcx, [rbp+var_10]
0x180010b5a  xor     rcx, rsp; StackCookie
0x180010b5d  call    __security_check_cookie
0x180010b62  lea     r11, [rsp+80h+var_s0]
0x180010b6a  mov     rbx, [r11+30h]
0x180010b6e  mov     rsi, [r11+38h]
0x180010b72  mov     rsp, r11
0x180010b75  pop     r14
0x180010b77  pop     rdi
0x180010b78  pop     rbp
0x180010b79  retn
```
