# s_DrawThemeTextPPIAware

- ea: `0x180100720`
- end: `0x180100cce`
- name: `s_DrawThemeTextPPIAware`
- size: `1454`
- prototype: `__int64 __usercall@<rax>(HTHEME hTheme@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18056856c`

## callees

- `0x180018e4c`
- `0x180043964`
- `0x180100520`
- `0x180100720`
- `0x180100cd4`
- `0x18018aff0`
- `0x1801d29a8`
- `0x180249490`
- `0x18024a53c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100c64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100c64`
- `USER32!SystemParametersInfoW` at `0x1801008a1`
- `USER32!SystemParametersInfoW` at `0x1801008a1`
- `GDI32!DeleteObject` at `0x180100c1c`
- `GDI32!DeleteObject` at `0x180100c1c`
- `GDI32!CreateDIBSection` at `0x18010080f`
- `GDI32!CreateDIBSection` at `0x18010080f`
- `GDI32!CreateCompatibleDC` at `0x18010078b`
- `GDI32!CreateCompatibleDC` at `0x18010078b`
- `GDI32!SelectObject` at `0x180100845`
- `GDI32!SelectObject` at `0x180100a3d`
- `GDI32!SelectObject` at `0x180100bfd`
- `GDI32!SelectObject` at `0x180100c30`
- `GDI32!SelectObject` at `0x180100845`
- `GDI32!SelectObject` at `0x180100a3d`
- `GDI32!SelectObject` at `0x180100bfd`
- `GDI32!SelectObject` at `0x180100c30`
- `GDI32!DeleteDC` at `0x180100c94`
- `GDI32!DeleteDC` at `0x180100c94`
- `GDI32!GdiAlphaBlend` at `0x180100bda`
- `GDI32!GdiAlphaBlend` at `0x180100bda`
- `GDI32!CreateFontIndirectW` at `0x1801009b9`
- `GDI32!CreateFontIndirectW` at `0x1801009b9`
- `UxTheme!GetThemeFont` at `0x18010090a`
- `UxTheme!GetThemeFont` at `0x18010090a`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall s_DrawThemeTextPPIAware(HTHEME hTheme, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __m128i *a6)
{
  HDC CompatibleDC; // rcx
  int Error; // edi
  __int32 v10; // edi
  __int32 v11; // ebx
  HBITMAP v12; // rax
  HDC v13; // r13
  __m128i v14; // xmm0
  int v15; // ebx
  int v16; // edi
  bool v17; // sf
  int v18; // eax
  HFONT v19; // rbx
  __int16 *v20; // r13
  __int64 v21; // rdi
  unsigned int v22; // r9d
  unsigned int v23; // r14d
  __int16 v24; // ax
  __int16 *v25; // rcx
  signed int LastError; // eax
  int v27; // edx
  unsigned int v28; // r8d
  HDC hdc; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  void **v34; // [rsp+A8h] [rbp-58h] BYREF
  HBITMAP v35; // [rsp+B0h] [rbp-50h]
  void *ppvBits; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v37; // [rsp+C0h] [rbp-40h]
  HDC v38; // [rsp+C8h] [rbp-38h]
  HDC v39; // [rsp+D0h] [rbp-30h]
  HDC v40; // [rsp+D8h] [rbp-28h]
  HGDIOBJ h; // [rsp+E0h] [rbp-20h]
  HDC v42; // [rsp+E8h] [rbp-18h]
  HGDIOBJ v43; // [rsp+F0h] [rbp-10h]
  HFONT v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+100h] [rbp+0h]
  int v46[19]; // [rsp+104h] [rbp+4h] BYREF
  int v47; // [rsp+150h] [rbp+50h]
  int v48; // [rsp+154h] [rbp+54h]
  int v49; // [rsp+158h] [rbp+58h]
  int v50; // [rsp+15Ch] [rbp+5Ch]
  BITMAPINFO pbmi; // [rsp+160h] [rbp+60h] BYREF
  LOGFONTW pFont; // [rsp+190h] [rbp+90h] BYREF
  int pvParam; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v54[220]; // [rsp+1F4h] [rbp+F4h] BYREF
  __int128 v55; // [rsp+2D0h] [rbp+1D0h]
  __int128 v56; // [rsp+2E0h] [rbp+1E0h]
  __int128 v57; // [rsp+2F0h] [rbp+1F0h]
  __int128 v58; // [rsp+300h] [rbp+200h]
  _OWORD v59[14]; // [rsp+310h] [rbp+210h]

  v37 = a4;
  CompatibleDC = CreateCompatibleDC(*(HDC *)(a4 + 32));
  hdc = CompatibleDC;
  if ( CompatibleDC )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    CompatibleDC = 0;
  }
  if ( Error < 0 )
    goto LABEL_43;
  memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
  pbmi.bmiHeader.biSize = 44;
  v10 = a6->m128i_i32[0];
  pbmi.bmiHeader.biWidth = a6->m128i_i32[2] - a6->m128i_i32[0];
  v11 = a6->m128i_i32[1];
  pbmi.bmiHeader.biHeight = v11 - a6->m128i_i32[3];
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  ppvBits = 0;
  v12 = CreateDIBSection(CompatibleDC, &pbmi, 0, &ppvBits, 0, 0);
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable';
  v35 = v12;
  if ( v12 )
  {
    v13 = hdc;
    v39 = hdc;
    v42 = hdc;
    v43 = SelectObject(hdc, v12);
    v14 = *a6;
    v15 = -v11;
    v16 = -v10;
    v47 = v16 + _mm_cvtsi128_si32(*a6);
    v49 = v16 + v14.m128i_i32[2];
    v50 = v15 + v14.m128i_i32[3];
    v48 = v15 + v14.m128i_i32[1];
    memset_0(v54, 0, 0x1F4u);
    pvParam = 504;
    if ( !SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_35:
        SelectObject(v13, v43);
        v12 = v35;
        goto LABEL_37;
      }
    }
    v45 = 72;
    memset_0(v46, 0, 0x44u);
    memset_0(&pFont, 0, sizeof(pFont));
    v17 = GetThemeFont(hTheme, hdc, 27, 0, 210, &pFont) < 0;
    v18 = v46[0];
    if ( !v17 )
    {
      v18 = v46[0] | 0x40;
      v46[0] |= 0x40u;
      if ( (int)v55 <= 0 )
      {
        if ( (int)v55 >= pFont.lfHeight )
          goto LABEL_15;
      }
      else if ( (int)v55 <= pFont.lfHeight )
      {
LABEL_15:
        if ( (*(_BYTE *)(a4 + 16) & 0x20) != 0 )
        {
          pFont.lfWeight = 700;
          v46[0] = v18 | 0x40;
        }
        v19 = CreateFontIndirectW(&pFont);
        v44 = v19;
        if ( !v19 )
        {
          Error = -2147467259;
LABEL_33:
          if ( v19 )
            DeleteObject(v19);
          goto LABEL_35;
        }
        v20 = *(__int16 **)a5;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(a5);
        v21 = *(_QWORD *)(a5 + 8);
        v33 = v21;
        v23 = v22;
        v24 = *v20;
        if ( *v20 )
        {
          v25 = v20;
          do
          {
            if ( v24 == 9 )
              break;
            ++v25;
            ++v23;
            v24 = *v25;
          }
          while ( *v25 );
        }
        v38 = hdc;
        v40 = hdc;
        h = SelectObject(hdc, v19);
        if ( v23 )
        {
          Error = DPIToPPIHelpers::DrawThemeTextExPPI(a3, *(unsigned int *)(a5 + 60), a5 + 64, hTheme, hdc);
          if ( Error < 0 )
          {
LABEL_31:
            SelectObject(v38, h);
            v13 = v39;
            goto LABEL_33;
          }
          v21 = v33;
        }
        if ( v23 >= (unsigned __int64)(v21 - 1)
          || (Error = DPIToPPIHelpers::GetThemeTextExtentPPI(a3, *(unsigned int *)(a5 + 60), a5 + 64, hTheme, hdc),
              Error >= 0)
          && (v47 = v49,
              Error = DPIToPPIHelpers::DrawThemeTextExPPI(a3, *(unsigned int *)(a5 + 60), a5 + 64, hTheme, hdc),
              Error >= 0) )
        {
          if ( GdiAlphaBlend(
                 *(HDC *)(v37 + 32),
                 a6->m128i_i32[0],
                 a6->m128i_i32[1],
                 a6->m128i_i32[2] - a6->m128i_i32[0],
                 a6->m128i_i32[3] - a6->m128i_i32[1],
                 hdc,
                 0,
                 0,
                 a6->m128i_i32[2] - a6->m128i_i32[0],
                 a6->m128i_i32[3] - a6->m128i_i32[1],
                 (BLENDFUNCTION)33488896) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
          }
        }
        goto LABEL_31;
      }
      pFont.lfHeight = v55;
      goto LABEL_15;
    }
    *(_OWORD *)&pFont.lfHeight = v55;
    *(_OWORD *)&pFont.lfWeight = v56;
    *(_OWORD *)&pFont.lfFaceName[2] = v57;
    *(_OWORD *)&pFont.lfFaceName[10] = v58;
    *(_OWORD *)&pFont.lfFaceName[18] = v59[0];
    *(_OWORD *)&pFont.lfFaceName[24] = *(_OWORD *)((char *)v59 + 12);
    goto LABEL_15;
  }
  Error = -2147024882;
LABEL_37:
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable';
  if ( v12
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::InternalClose(&v34) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v27, v28);
  }
  CompatibleDC = hdc;
LABEL_43:
  DeleteDC(CompatibleDC);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180100720  mov     [rsp-8+arg_8], rbx
0x180100725  push    rbp
0x180100726  push    rsi
0x180100727  push    rdi
0x180100728  push    r12
0x18010072a  push    r13
0x18010072c  push    r14
0x18010072e  push    r15
0x180100730  lea     rbp, [rsp-300h]
0x180100738  sub     rsp, 400h
0x18010073f  mov     rax, cs:__security_cookie
0x180100746  xor     rax, rsp
0x180100749  mov     [rbp+330h+var_40], rax
0x180100750  mov     r14, r9
0x180100753  mov     [rbp+330h+var_370], r9
0x180100757  mov     [rbp+330h+var_3A0], r8
0x18010075b  mov     dword ptr [rsp+430h+var_3C0.BlendOp], edx
0x18010075f  mov     rsi, rcx
0x180100762  mov     [rbp+330h+var_3A8], rcx
0x180100766  mov     r15, [rbp+330h+arg_20]
0x18010076d  mov     r12, [rbp+330h+arg_28]
0x180100774  xor     r13d, r13d
0x180100777  mov     [rbp+330h+hdc], r13
0x18010077b  lea     rax, ??_7CompatibleDC@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::CompatibleDC::`vftable'
0x180100782  mov     [rsp+430h+var_3B8], rax
0x180100787  mov     rcx, [r9+20h]; hdc
0x18010078b  call    cs:__imp_CreateCompatibleDC
0x180100792  nop     dword ptr [rax+rax+00h]
0x180100797  mov     rcx, rax
0x18010079a  mov     [rbp+330h+hdc], rax
0x18010079e  test    rax, rax
0x1801007a1  jz      short loc_1801007A8
0x1801007a3  mov     edi, r13d
0x1801007a6  jmp     short loc_1801007B3
0x1801007a8  call    ResultFromKnownLastError
0x1801007ad  mov     edi, eax
0x1801007af  mov     rcx, [rbp+330h+hdc]; hdc
0x1801007b3  test    edi, edi
0x1801007b5  js      loc_180100C88
0x1801007bb  xorps   xmm0, xmm0
0x1801007be  movdqu  xmmword ptr [rbp+330h+pbmi.bmiHeader.biSizeImage], xmm0
0x1801007c3  mov     qword ptr [rbp+330h+pbmi.bmiHeader.biClrImportant], r13
0x1801007ca  mov     [rbp+330h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x1801007d1  mov     edi, [r12]
0x1801007d5  mov     eax, [r12+8]
0x1801007da  sub     eax, edi
0x1801007dc  mov     [rbp+330h+pbmi.bmiHeader.biWidth], eax
0x1801007df  mov     ebx, [r12+4]
0x1801007e4  mov     eax, ebx
0x1801007e6  sub     eax, [r12+0Ch]
0x1801007eb  mov     [rbp+330h+pbmi.bmiHeader.biHeight], eax
0x1801007ee  mov     qword ptr [rbp+330h+pbmi.bmiHeader.biPlanes], 200001h
0x1801007f6  mov     [rbp+330h+ppvBits], r13
0x1801007fa  mov     [rsp+430h+offset], r13d; offset
0x1801007ff  mov     [rsp+430h+hSection], r13; hSection
0x180100804  lea     r9, [rbp+330h+ppvBits]; ppvBits
0x180100808  xor     r8d, r8d; usage
0x18010080b  lea     rdx, [rbp+330h+pbmi]; pbmi
0x18010080f  call    cs:__imp_CreateDIBSection
0x180100816  nop     dword ptr [rax+rax+00h]
0x18010081b  lea     rcx, ??_7?$HandleT@UHBITMAPTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable'
0x180100822  mov     [rbp+330h+var_388], rcx
0x180100826  mov     [rbp+330h+var_380], rax
0x18010082a  test    rax, rax
0x18010082d  jz      loc_180100C49
0x180100833  mov     r13, [rbp+330h+hdc]
0x180100837  mov     [rbp+330h+var_360], r13
0x18010083b  mov     [rbp+330h+var_348], r13
0x18010083f  mov     rdx, rax; h
0x180100842  mov     rcx, r13; hdc
0x180100845  call    cs:__imp_SelectObject
0x18010084c  nop     dword ptr [rax+rax+00h]
0x180100851  mov     [rbp+330h+var_340], rax
0x180100855  movaps  xmm0, xmmword ptr [r12]
0x18010085a  movups  [rbp+330h+var_2E0], xmm0
0x18010085e  neg     ebx
0x180100860  neg     edi
0x180100862  movd    ecx, xmm0
0x180100866  add     ecx, edi
0x180100868  mov     dword ptr [rbp+330h+var_2E0], ecx
0x18010086b  add     dword ptr [rbp+330h+var_2E0+8], edi
0x18010086e  add     dword ptr [rbp+330h+var_2E0+0Ch], ebx
0x180100871  add     dword ptr [rbp+330h+var_2E0+4], ebx
0x180100874  xor     edx, edx; Val
0x180100876  mov     r8d, 1F4h; Size
0x18010087c  lea     rcx, [rbp+330h+var_23C]; void *
0x180100883  call    memset_0
0x180100888  mov     edx, 1F8h; uiParam
0x18010088d  mov     [rbp+330h+pvParam], edx
0x180100893  xor     r9d, r9d; fWinIni
0x180100896  lea     r8, [rbp+330h+pvParam]; pvParam
0x18010089d  lea     ecx, [r9+29h]; uiAction
0x1801008a1  call    cs:__imp_SystemParametersInfoW
0x1801008a8  nop     dword ptr [rax+rax+00h]
0x1801008ad  test    eax, eax
0x1801008af  jnz     short loc_1801008C0
0x1801008b1  call    ResultFromKnownLastError
0x1801008b6  mov     edi, eax
0x1801008b8  test    eax, eax
0x1801008ba  js      loc_180100C29
0x1801008c0  mov     [rbp+330h+var_330], 48h ; 'H'
0x1801008c7  xor     edx, edx; Val
0x1801008c9  lea     r8d, [rdx+44h]; Size
0x1801008cd  lea     rcx, [rbp+330h+var_32C]; void *
0x1801008d1  call    memset_0
0x1801008d6  xor     edx, edx; Val
0x1801008d8  lea     r8d, [rdx+5Ch]; Size
0x1801008dc  lea     rcx, [rbp+330h+pFont]; void *
0x1801008e3  call    memset_0
0x1801008e8  lea     rax, [rbp+330h+pFont]
0x1801008ef  mov     qword ptr [rsp+430h+offset], rax; pFont
0x1801008f4  mov     dword ptr [rsp+430h+hSection], 0D2h; iPropId
0x1801008fc  xor     r9d, r9d; iStateId
0x1801008ff  lea     r8d, [r9+1Bh]; iPartId
0x180100903  mov     rdx, [rbp+330h+hdc]; hdc
0x180100907  mov     rcx, rsi; hTheme
0x18010090a  call    cs:__imp_GetThemeFont
0x180100911  nop     dword ptr [rax+rax+00h]
0x180100916  test    eax, eax
0x180100918  mov     eax, [rbp+330h+var_32C]
0x18010091b  js      short loc_180100947
0x18010091d  or      eax, 40h
0x180100920  mov     [rbp+330h+var_32C], eax
0x180100923  mov     ecx, dword ptr [rbp+330h+var_160]
0x180100929  test    ecx, ecx
0x18010092b  jle     short loc_180100937
0x18010092d  cmp     ecx, [rbp+330h+pFont.lfHeight]
0x180100933  jg      short loc_18010093F
0x180100935  jmp     short loc_18010099B
0x180100937  cmp     ecx, [rbp+330h+pFont.lfHeight]
0x18010093d  jge     short loc_18010099B
0x18010093f  mov     [rbp+330h+pFont.lfHeight], ecx
0x180100945  jmp     short loc_18010099B
0x180100947  movaps  xmm0, [rbp+330h+var_160]
0x18010094e  movaps  xmmword ptr [rbp+330h+pFont.lfHeight], xmm0
0x180100955  movaps  xmm1, [rbp+330h+var_150]
0x18010095c  movaps  xmmword ptr [rbp+330h+pFont.lfWeight], xmm1
0x180100963  movaps  xmm0, [rbp+330h+var_140]
0x18010096a  movaps  xmmword ptr [rbp+330h+pFont.lfFaceName+4], xmm0
0x180100971  movaps  xmm1, [rbp+330h+var_130]
0x180100978  movaps  xmmword ptr [rbp+330h+pFont.lfFaceName+14h], xmm1
0x18010097f  movaps  xmm0, [rbp+330h+var_120]
0x180100986  movaps  xmmword ptr [rbp+330h+pFont.lfFaceName+24h], xmm0
0x18010098d  movups  xmm1, [rbp+330h+var_120+0Ch]
0x180100994  movups  xmmword ptr [rbp+330h+pFont.lfFaceName+30h], xmm1
0x18010099b  test    byte ptr [r14+10h], 20h
0x1801009a0  jz      short loc_1801009B2
0x1801009a2  mov     [rbp+330h+pFont.lfWeight], 2BCh
0x1801009ac  or      eax, 40h
0x1801009af  mov     [rbp+330h+var_32C], eax
0x1801009b2  lea     rcx, [rbp+330h+pFont]; lplf
0x1801009b9  call    cs:__imp_CreateFontIndirectW
0x1801009c0  nop     dword ptr [rax+rax+00h]
0x1801009c5  mov     rbx, rax
0x1801009c8  mov     [rbp+330h+var_338], rax
0x1801009cc  test    rax, rax
0x1801009cf  jz      loc_180100C0F
0x1801009d5  mov     esi, 24h ; '$'
0x1801009da  xor     r9d, r9d
0x1801009dd  cmp     [r15+48h], r9d
0x1801009e1  jnz     short loc_1801009F3
0x1801009e3  test    dword ptr [r14+10h], 100h
0x1801009eb  mov     eax, 100024h
0x1801009f0  cmovnz  esi, eax
0x1801009f3  mov     r13, [r15]
0x1801009f6  mov     rcx, r15
0x1801009f9  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1801009fe  mov     rdi, [r15+8]
0x180100a02  mov     qword ptr [rbp+330h+var_398], rdi
0x180100a06  mov     r14d, r9d
0x180100a09  movzx   eax, word ptr [r13+0]
0x180100a0e  test    ax, ax
0x180100a11  jz      short loc_180100A2B
0x180100a13  mov     rcx, r13
0x180100a16  cmp     ax, 9
0x180100a1a  jz      short loc_180100A2B
0x180100a1c  add     rcx, 2
0x180100a20  inc     r14d
0x180100a23  movzx   eax, word ptr [rcx]
0x180100a26  test    ax, ax
0x180100a29  jnz     short loc_180100A16
0x180100a2b  mov     rax, [rbp+330h+hdc]
0x180100a2f  mov     [rbp+330h+var_368], rax
0x180100a33  mov     [rbp+330h+var_358], rax
0x180100a37  mov     rdx, rbx; h
0x180100a3a  mov     rcx, rax; hdc
0x180100a3d  call    cs:__imp_SelectObject
0x180100a44  nop     dword ptr [rax+rax+00h]
0x180100a49  mov     [rbp+330h+h], rax
0x180100a4d  test    r14d, r14d
0x180100a50  jz      short loc_180100AA6
0x180100a52  lea     r8, [r15+40h]
0x180100a56  lea     rax, [rbp+330h+var_330]
0x180100a5a  mov     [rsp+430h+var_3D8], rax
0x180100a5f  lea     rax, [rbp+330h+var_2E0]
0x180100a63  mov     qword ptr [rsp+430h+ftn.BlendOp], rax
0x180100a68  mov     [rsp+430h+hSrc], esi
0x180100a6c  mov     [rsp+430h+wSrc], r14d
0x180100a71  mov     qword ptr [rsp+430h+yoriginSrc], r13
0x180100a76  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x180100a7a  mov     [rsp+430h+xoriginSrc], eax
0x180100a7e  mov     rax, [rbp+330h+hdc]
0x180100a82  mov     [rsp+430h+hSection], rax
0x180100a87  mov     r9, [rbp+330h+var_3A8]
0x180100a8b  mov     edx, [r15+3Ch]
0x180100a8f  mov     rcx, [rbp+330h+var_3A0]
0x180100a93  call    ?DrawThemeTextExPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAUtagRECT@@PEAU_DTTOPTS@@@Z; DPIToPPIHelpers::DrawThemeTextExPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,tagRECT *,_DTTOPTS *)
0x180100a98  mov     edi, eax
0x180100a9a  test    eax, eax
0x180100a9c  js      loc_180100BF5
0x180100aa2  mov     rdi, qword ptr [rbp+330h+var_398]
0x180100aa6  mov     ecx, r14d
0x180100aa9  lea     rax, [rdi-1]
0x180100aad  cmp     rcx, rax
0x180100ab0  jnb     loc_180100B83
0x180100ab6  xorps   xmm0, xmm0
0x180100ab9  movdqu  [rbp+330h+var_398], xmm0
0x180100abe  sub     edi, r14d
0x180100ac1  lea     r14d, [rdi-1]
0x180100ac5  lea     r13, [r13+rcx*2+0]
0x180100aca  add     r13, 2
0x180100ace  lea     r8, [r15+40h]
0x180100ad2  lea     rax, [rbp+330h+var_398]
0x180100ad6  mov     [rsp+430h+var_3D0], rax
0x180100adb  lea     rax, [rbp+330h+var_2E0]
0x180100adf  mov     [rsp+430h+var_3D8], rax
0x180100ae4  lea     rax, [rbp+330h+var_330]
0x180100ae8  mov     qword ptr [rsp+430h+ftn.BlendOp], rax
0x180100aed  mov     [rsp+430h+hSrc], esi
0x180100af1  mov     [rsp+430h+wSrc], r14d
0x180100af6  mov     qword ptr [rsp+430h+yoriginSrc], r13
0x180100afb  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x180100aff  mov     [rsp+430h+xoriginSrc], eax
0x180100b03  mov     rax, [rbp+330h+hdc]
0x180100b07  mov     [rsp+430h+hSection], rax
0x180100b0c  mov     r9, [rbp+330h+var_3A8]
0x180100b10  mov     edx, [r15+3Ch]
0x180100b14  mov     rcx, [rbp+330h+var_3A0]
0x180100b18  call    ?GetThemeTextExtentPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAU_DTTOPTS@@PEAUtagRECT@@7@Z; DPIToPPIHelpers::GetThemeTextExtentPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,_DTTOPTS *,tagRECT *,tagRECT *)
0x180100b1d  mov     edi, eax
0x180100b1f  test    eax, eax
0x180100b21  js      loc_180100BF5
0x180100b27  mov     eax, dword ptr [rbp+330h+var_398]
0x180100b2a  sub     eax, dword ptr [rbp+330h+var_398+8]
0x180100b2d  add     eax, dword ptr [rbp+330h+var_2E0+8]
0x180100b30  mov     dword ptr [rbp+330h+var_2E0], eax
0x180100b33  lea     rax, [rbp+330h+var_330]
0x180100b37  mov     [rsp+430h+var_3D8], rax
0x180100b3c  lea     rax, [rbp+330h+var_2E0]
0x180100b40  mov     qword ptr [rsp+430h+ftn.BlendOp], rax
0x180100b45  mov     [rsp+430h+hSrc], esi
0x180100b49  mov     [rsp+430h+wSrc], r14d
0x180100b4e  mov     qword ptr [rsp+430h+yoriginSrc], r13
0x180100b53  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x180100b57  mov     [rsp+430h+xoriginSrc], eax
0x180100b5b  mov     rax, [rbp+330h+hdc]
0x180100b5f  mov     [rsp+430h+hSection], rax
0x180100b64  mov     r9, [rbp+330h+var_3A8]
0x180100b68  lea     r8, [r15+40h]
0x180100b6c  mov     edx, [r15+3Ch]
0x180100b70  mov     rcx, [rbp+330h+var_3A0]
0x180100b74  call    ?DrawThemeTextExPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAUtagRECT@@PEAU_DTTOPTS@@@Z; DPIToPPIHelpers::DrawThemeTextExPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,tagRECT *,_DTTOPTS *)
0x180100b79  mov     edi, eax
0x180100b7b  xor     esi, esi
0x180100b7d  test    eax, eax
0x180100b7f  js      short loc_180100BF5
0x180100b81  jmp     short loc_180100B85
0x180100b83  xor     esi, esi
0x180100b85  mov     dword ptr [rsp+430h+var_3C0.BlendOp], esi
0x180100b89  mov     word ptr [rsp+430h+var_3C0.SourceConstantAlpha], 1FFh
0x180100b90  mov     r8d, [r12+4]; yoriginDest
0x180100b95  mov     r10d, [r12+0Ch]
0x180100b9a  sub     r10d, r8d
0x180100b9d  mov     r9d, [r12+8]
0x180100ba2  sub     r9d, [r12]; wDest
0x180100ba6  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x180100baa  mov     dword ptr [rsp+430h+ftn.BlendOp], eax; ftn
0x180100bae  mov     [rsp+430h+hSrc], r10d; hSrc
0x180100bb3  mov     [rsp+430h+wSrc], r9d; wSrc
0x180100bb8  mov     [rsp+430h+yoriginSrc], esi; yoriginSrc
0x180100bbc  mov     [rsp+430h+xoriginSrc], esi; xoriginSrc
0x180100bc0  mov     rax, [rbp+330h+hdc]
0x180100bc4  mov     qword ptr [rsp+430h+offset], rax; hdcSrc
0x180100bc9  mov     dword ptr [rsp+430h+hSection], r10d; hDest
0x180100bce  mov     edx, [r12]; xoriginDest
0x180100bd2  mov     rcx, [rbp+330h+var_370]
0x180100bd6  mov     rcx, [rcx+20h]; hdcDest
0x180100bda  call    cs:__imp_GdiAlphaBlend
0x180100be1  nop     dword ptr [rax+rax+00h]
0x180100be6  test    eax, eax
0x180100be8  jz      short loc_180100BEE
0x180100bea  mov     edi, esi
0x180100bec  jmp     short loc_180100BF5
0x180100bee  call    ResultFromKnownLastError
0x180100bf3  mov     edi, eax
0x180100bf5  mov     rdx, [rbp+330h+h]; h
0x180100bf9  mov     rcx, [rbp+330h+var_368]; hdc
0x180100bfd  call    cs:__imp_SelectObject
0x180100c04  nop     dword ptr [rax+rax+00h]
0x180100c09  mov     r13, [rbp+330h+var_360]
  ... truncated ...
```
