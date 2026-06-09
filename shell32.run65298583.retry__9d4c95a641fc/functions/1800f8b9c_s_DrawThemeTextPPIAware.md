# s_DrawThemeTextPPIAware

- ea: `0x1800f8b9c`
- end: `0x1800f9106`
- name: `s_DrawThemeTextPPIAware`
- size: `1386`
- prototype: `__int64 __usercall@<rax>(HTHEME hTheme@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18052a2a0`

## callees

- `0x1800208d8`
- `0x180047bb4`
- `0x1800f89a8`
- `0x1800f8b9c`
- `0x1800f910c`
- `0x18017abb0`
- `0x180233280`
- `0x1802342fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f909e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f909e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f90bc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800f90bc`
- `USER32!SystemParametersInfoW` at `0x1800f8d0b`
- `USER32!SystemParametersInfoW` at `0x1800f8d0b`
- `GDI32!DeleteObject` at `0x1800f9062`
- `GDI32!DeleteObject` at `0x1800f9062`
- `GDI32!CreateDIBSection` at `0x1800f8c85`
- `GDI32!CreateDIBSection` at `0x1800f8c85`
- `GDI32!CreateCompatibleDC` at `0x1800f8c07`
- `GDI32!CreateCompatibleDC` at `0x1800f8c07`
- `GDI32!SelectObject` at `0x1800f8cb5`
- `GDI32!SelectObject` at `0x1800f8e95`
- `GDI32!SelectObject` at `0x1800f9049`
- `GDI32!SelectObject` at `0x1800f9070`
- `GDI32!SelectObject` at `0x1800f8cb5`
- `GDI32!SelectObject` at `0x1800f8e95`
- `GDI32!SelectObject` at `0x1800f9049`
- `GDI32!SelectObject` at `0x1800f9070`
- `GDI32!DeleteDC` at `0x1800f90d3`
- `GDI32!DeleteDC` at `0x1800f90d3`
- `GDI32!GdiAlphaBlend` at `0x1800f902c`
- `GDI32!GdiAlphaBlend` at `0x1800f902c`
- `GDI32!CreateFontIndirectW` at `0x1800f8e17`
- `GDI32!CreateFontIndirectW` at `0x1800f8e17`
- `UxTheme!GetThemeFont` at `0x1800f8d6e`
- `UxTheme!GetThemeFont` at `0x1800f8d6e`

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
  int LastError; // eax
  HDC hdc; // [rsp+80h] [rbp-80h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  void **v32; // [rsp+A8h] [rbp-58h] BYREF
  HBITMAP v33; // [rsp+B0h] [rbp-50h]
  void *ppvBits; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v35; // [rsp+C0h] [rbp-40h]
  HDC v36; // [rsp+C8h] [rbp-38h]
  HDC v37; // [rsp+D0h] [rbp-30h]
  HDC v38; // [rsp+D8h] [rbp-28h]
  HGDIOBJ h; // [rsp+E0h] [rbp-20h]
  HDC v40; // [rsp+E8h] [rbp-18h]
  HGDIOBJ v41; // [rsp+F0h] [rbp-10h]
  HFONT v42; // [rsp+F8h] [rbp-8h]
  int v43; // [rsp+100h] [rbp+0h]
  int v44[19]; // [rsp+104h] [rbp+4h] BYREF
  int v45; // [rsp+150h] [rbp+50h]
  int v46; // [rsp+154h] [rbp+54h]
  int v47; // [rsp+158h] [rbp+58h]
  int v48; // [rsp+15Ch] [rbp+5Ch]
  BITMAPINFO pbmi; // [rsp+160h] [rbp+60h] BYREF
  LOGFONTW pFont; // [rsp+190h] [rbp+90h] BYREF
  int pvParam; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v52[220]; // [rsp+1F4h] [rbp+F4h] BYREF
  __int128 v53; // [rsp+2D0h] [rbp+1D0h]
  __int128 v54; // [rsp+2E0h] [rbp+1E0h]
  __int128 v55; // [rsp+2F0h] [rbp+1F0h]
  __int128 v56; // [rsp+300h] [rbp+200h]
  _OWORD v57[14]; // [rsp+310h] [rbp+210h]

  v35 = a4;
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
  v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable';
  v33 = v12;
  if ( v12 )
  {
    v13 = hdc;
    v37 = hdc;
    v40 = hdc;
    v41 = SelectObject(hdc, v12);
    v14 = *a6;
    v15 = -v11;
    v16 = -v10;
    v45 = v16 + _mm_cvtsi128_si32(*a6);
    v47 = v16 + v14.m128i_i32[2];
    v48 = v15 + v14.m128i_i32[3];
    v46 = v15 + v14.m128i_i32[1];
    memset_0(v52, 0, 0x1F4u);
    pvParam = 504;
    if ( !SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_35:
        SelectObject(v13, v41);
        v12 = v33;
        goto LABEL_37;
      }
    }
    v43 = 72;
    memset_0(v44, 0, 0x44u);
    memset_0(&pFont, 0, sizeof(pFont));
    v17 = GetThemeFont(hTheme, hdc, 27, 0, 210, &pFont) < 0;
    v18 = v44[0];
    if ( !v17 )
    {
      v18 = v44[0] | 0x40;
      v44[0] |= 0x40u;
      if ( (int)v53 <= 0 )
      {
        if ( (int)v53 >= pFont.lfHeight )
          goto LABEL_15;
      }
      else if ( (int)v53 <= pFont.lfHeight )
      {
LABEL_15:
        if ( (*(_BYTE *)(a4 + 16) & 0x20) != 0 )
        {
          pFont.lfWeight = 700;
          v44[0] = v18 | 0x40;
        }
        v19 = CreateFontIndirectW(&pFont);
        v42 = v19;
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
        v31 = v21;
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
        v36 = hdc;
        v38 = hdc;
        h = SelectObject(hdc, v19);
        if ( v23 )
        {
          Error = DPIToPPIHelpers::DrawThemeTextExPPI(a3, *(unsigned int *)(a5 + 60), a5 + 64, hTheme, hdc);
          if ( Error < 0 )
          {
LABEL_31:
            SelectObject(v36, h);
            v13 = v37;
            goto LABEL_33;
          }
          v21 = v31;
        }
        if ( v23 >= (unsigned __int64)(v21 - 1)
          || (Error = DPIToPPIHelpers::GetThemeTextExtentPPI(a3, *(unsigned int *)(a5 + 60), a5 + 64, hTheme, hdc),
              Error >= 0)
          && (v45 = v47,
              Error = DPIToPPIHelpers::DrawThemeTextExPPI(a3, *(unsigned int *)(a5 + 60), a5 + 64, hTheme, hdc),
              Error >= 0) )
        {
          if ( GdiAlphaBlend(
                 *(HDC *)(v35 + 32),
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
      pFont.lfHeight = v53;
      goto LABEL_15;
    }
    *(_OWORD *)&pFont.lfHeight = v53;
    *(_OWORD *)&pFont.lfWeight = v54;
    *(_OWORD *)&pFont.lfFaceName[2] = v55;
    *(_OWORD *)&pFont.lfFaceName[10] = v56;
    *(_OWORD *)&pFont.lfFaceName[18] = v57[0];
    *(_OWORD *)&pFont.lfFaceName[24] = *(_OWORD *)((char *)v57 + 12);
    goto LABEL_15;
  }
  Error = -2147024882;
LABEL_37:
  v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable';
  if ( v12
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::InternalClose(&v32) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
  }
  CompatibleDC = hdc;
LABEL_43:
  DeleteDC(CompatibleDC);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800f8b9c  mov     [rsp-8+arg_8], rbx
0x1800f8ba1  push    rbp
0x1800f8ba2  push    rsi
0x1800f8ba3  push    rdi
0x1800f8ba4  push    r12
0x1800f8ba6  push    r13
0x1800f8ba8  push    r14
0x1800f8baa  push    r15
0x1800f8bac  lea     rbp, [rsp-300h]
0x1800f8bb4  sub     rsp, 400h
0x1800f8bbb  mov     rax, cs:__security_cookie
0x1800f8bc2  xor     rax, rsp
0x1800f8bc5  mov     [rbp+330h+var_40], rax
0x1800f8bcc  mov     r14, r9
0x1800f8bcf  mov     [rbp+330h+var_370], r9
0x1800f8bd3  mov     [rbp+330h+var_3A0], r8
0x1800f8bd7  mov     dword ptr [rsp+430h+var_3C0.BlendOp], edx
0x1800f8bdb  mov     rsi, rcx
0x1800f8bde  mov     [rbp+330h+var_3A8], rcx
0x1800f8be2  mov     r15, [rbp+330h+arg_20]
0x1800f8be9  mov     r12, [rbp+330h+arg_28]
0x1800f8bf0  xor     r13d, r13d
0x1800f8bf3  mov     [rbp+330h+hdc], r13
0x1800f8bf7  lea     rax, ??_7CompatibleDC@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::CompatibleDC::`vftable'
0x1800f8bfe  mov     [rsp+430h+var_3B8], rax
0x1800f8c03  mov     rcx, [r9+20h]; hdc
0x1800f8c07  call    cs:__imp_CreateCompatibleDC
0x1800f8c0d  mov     rcx, rax
0x1800f8c10  mov     [rbp+330h+hdc], rax
0x1800f8c14  test    rax, rax
0x1800f8c17  jz      short loc_1800F8C1E
0x1800f8c19  mov     edi, r13d
0x1800f8c1c  jmp     short loc_1800F8C29
0x1800f8c1e  call    ResultFromKnownLastError
0x1800f8c23  mov     edi, eax
0x1800f8c25  mov     rcx, [rbp+330h+hdc]; hdc
0x1800f8c29  test    edi, edi
0x1800f8c2b  js      loc_1800F90C7
0x1800f8c31  xorps   xmm0, xmm0
0x1800f8c34  movdqu  xmmword ptr [rbp+330h+pbmi.bmiHeader.biSizeImage], xmm0
0x1800f8c39  mov     qword ptr [rbp+330h+pbmi.bmiHeader.biClrImportant], r13
0x1800f8c40  mov     [rbp+330h+pbmi.bmiHeader.biSize], 2Ch ; ','
0x1800f8c47  mov     edi, [r12]
0x1800f8c4b  mov     eax, [r12+8]
0x1800f8c50  sub     eax, edi
0x1800f8c52  mov     [rbp+330h+pbmi.bmiHeader.biWidth], eax
0x1800f8c55  mov     ebx, [r12+4]
0x1800f8c5a  mov     eax, ebx
0x1800f8c5c  sub     eax, [r12+0Ch]
0x1800f8c61  mov     [rbp+330h+pbmi.bmiHeader.biHeight], eax
0x1800f8c64  mov     qword ptr [rbp+330h+pbmi.bmiHeader.biPlanes], 200001h
0x1800f8c6c  mov     [rbp+330h+ppvBits], r13
0x1800f8c70  mov     [rsp+430h+offset], r13d; offset
0x1800f8c75  mov     [rsp+430h+hSection], r13; hSection
0x1800f8c7a  lea     r9, [rbp+330h+ppvBits]; ppvBits
0x1800f8c7e  xor     r8d, r8d; usage
0x1800f8c81  lea     rdx, [rbp+330h+pbmi]; pbmi
0x1800f8c85  call    cs:__imp_CreateDIBSection
0x1800f8c8b  lea     rcx, ??_7?$HandleT@UHBITMAPTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HBITMAPTraits>::`vftable'
0x1800f8c92  mov     [rbp+330h+var_388], rcx
0x1800f8c96  mov     [rbp+330h+var_380], rax
0x1800f8c9a  test    rax, rax
0x1800f8c9d  jz      loc_1800F9083
0x1800f8ca3  mov     r13, [rbp+330h+hdc]
0x1800f8ca7  mov     [rbp+330h+var_360], r13
0x1800f8cab  mov     [rbp+330h+var_348], r13
0x1800f8caf  mov     rdx, rax; h
0x1800f8cb2  mov     rcx, r13; hdc
0x1800f8cb5  call    cs:__imp_SelectObject
0x1800f8cbb  mov     [rbp+330h+var_340], rax
0x1800f8cbf  movaps  xmm0, xmmword ptr [r12]
0x1800f8cc4  movups  [rbp+330h+var_2E0], xmm0
0x1800f8cc8  neg     ebx
0x1800f8cca  neg     edi
0x1800f8ccc  movd    ecx, xmm0
0x1800f8cd0  add     ecx, edi
0x1800f8cd2  mov     dword ptr [rbp+330h+var_2E0], ecx
0x1800f8cd5  add     dword ptr [rbp+330h+var_2E0+8], edi
0x1800f8cd8  add     dword ptr [rbp+330h+var_2E0+0Ch], ebx
0x1800f8cdb  add     dword ptr [rbp+330h+var_2E0+4], ebx
0x1800f8cde  xor     edx, edx; Val
0x1800f8ce0  mov     r8d, 1F4h; Size
0x1800f8ce6  lea     rcx, [rbp+330h+var_23C]; void *
0x1800f8ced  call    memset_0
0x1800f8cf2  mov     edx, 1F8h; uiParam
0x1800f8cf7  mov     [rbp+330h+pvParam], edx
0x1800f8cfd  xor     r9d, r9d; fWinIni
0x1800f8d00  lea     r8, [rbp+330h+pvParam]; pvParam
0x1800f8d07  lea     ecx, [r9+29h]; uiAction
0x1800f8d0b  call    cs:__imp_SystemParametersInfoW
0x1800f8d11  test    eax, eax
0x1800f8d13  jnz     short loc_1800F8D24
0x1800f8d15  call    ResultFromKnownLastError
0x1800f8d1a  mov     edi, eax
0x1800f8d1c  test    eax, eax
0x1800f8d1e  js      loc_1800F9069
0x1800f8d24  mov     [rbp+330h+var_330], 48h ; 'H'
0x1800f8d2b  xor     edx, edx; Val
0x1800f8d2d  lea     r8d, [rdx+44h]; Size
0x1800f8d31  lea     rcx, [rbp+330h+var_32C]; void *
0x1800f8d35  call    memset_0
0x1800f8d3a  xor     edx, edx; Val
0x1800f8d3c  lea     r8d, [rdx+5Ch]; Size
0x1800f8d40  lea     rcx, [rbp+330h+pFont]; void *
0x1800f8d47  call    memset_0
0x1800f8d4c  lea     rax, [rbp+330h+pFont]
0x1800f8d53  mov     qword ptr [rsp+430h+offset], rax; pFont
0x1800f8d58  mov     dword ptr [rsp+430h+hSection], 0D2h; iPropId
0x1800f8d60  xor     r9d, r9d; iStateId
0x1800f8d63  lea     r8d, [r9+1Bh]; iPartId
0x1800f8d67  mov     rdx, [rbp+330h+hdc]; hdc
0x1800f8d6b  mov     rcx, rsi; hTheme
0x1800f8d6e  call    cs:__imp_GetThemeFont
0x1800f8d74  test    eax, eax
0x1800f8d76  mov     eax, [rbp+330h+var_32C]
0x1800f8d79  js      short loc_1800F8DA5
0x1800f8d7b  or      eax, 40h
0x1800f8d7e  mov     [rbp+330h+var_32C], eax
0x1800f8d81  mov     ecx, dword ptr [rbp+330h+var_160]
0x1800f8d87  test    ecx, ecx
0x1800f8d89  jle     short loc_1800F8D95
0x1800f8d8b  cmp     ecx, [rbp+330h+pFont.lfHeight]
0x1800f8d91  jg      short loc_1800F8D9D
0x1800f8d93  jmp     short loc_1800F8DF9
0x1800f8d95  cmp     ecx, [rbp+330h+pFont.lfHeight]
0x1800f8d9b  jge     short loc_1800F8DF9
0x1800f8d9d  mov     [rbp+330h+pFont.lfHeight], ecx
0x1800f8da3  jmp     short loc_1800F8DF9
0x1800f8da5  movaps  xmm0, [rbp+330h+var_160]
0x1800f8dac  movaps  xmmword ptr [rbp+330h+pFont.lfHeight], xmm0
0x1800f8db3  movaps  xmm1, [rbp+330h+var_150]
0x1800f8dba  movaps  xmmword ptr [rbp+330h+pFont.lfWeight], xmm1
0x1800f8dc1  movaps  xmm0, [rbp+330h+var_140]
0x1800f8dc8  movaps  xmmword ptr [rbp+330h+pFont.lfFaceName+4], xmm0
0x1800f8dcf  movaps  xmm1, [rbp+330h+var_130]
0x1800f8dd6  movaps  xmmword ptr [rbp+330h+pFont.lfFaceName+14h], xmm1
0x1800f8ddd  movaps  xmm0, [rbp+330h+var_120]
0x1800f8de4  movaps  xmmword ptr [rbp+330h+pFont.lfFaceName+24h], xmm0
0x1800f8deb  movups  xmm1, [rbp+330h+var_120+0Ch]
0x1800f8df2  movups  xmmword ptr [rbp+330h+pFont.lfFaceName+30h], xmm1
0x1800f8df9  test    byte ptr [r14+10h], 20h
0x1800f8dfe  jz      short loc_1800F8E10
0x1800f8e00  mov     [rbp+330h+pFont.lfWeight], 2BCh
0x1800f8e0a  or      eax, 40h
0x1800f8e0d  mov     [rbp+330h+var_32C], eax
0x1800f8e10  lea     rcx, [rbp+330h+pFont]; lplf
0x1800f8e17  call    cs:__imp_CreateFontIndirectW
0x1800f8e1d  mov     rbx, rax
0x1800f8e20  mov     [rbp+330h+var_338], rax
0x1800f8e24  test    rax, rax
0x1800f8e27  jz      loc_1800F9055
0x1800f8e2d  mov     esi, 24h ; '$'
0x1800f8e32  xor     r9d, r9d
0x1800f8e35  cmp     [r15+48h], r9d
0x1800f8e39  jnz     short loc_1800F8E4B
0x1800f8e3b  test    dword ptr [r14+10h], 100h
0x1800f8e43  mov     eax, 100024h
0x1800f8e48  cmovnz  esi, eax
0x1800f8e4b  mov     r13, [r15]
0x1800f8e4e  mov     rcx, r15
0x1800f8e51  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800f8e56  mov     rdi, [r15+8]
0x1800f8e5a  mov     qword ptr [rbp+330h+var_398], rdi
0x1800f8e5e  mov     r14d, r9d
0x1800f8e61  movzx   eax, word ptr [r13+0]
0x1800f8e66  test    ax, ax
0x1800f8e69  jz      short loc_1800F8E83
0x1800f8e6b  mov     rcx, r13
0x1800f8e6e  cmp     ax, 9
0x1800f8e72  jz      short loc_1800F8E83
0x1800f8e74  add     rcx, 2
0x1800f8e78  inc     r14d
0x1800f8e7b  movzx   eax, word ptr [rcx]
0x1800f8e7e  test    ax, ax
0x1800f8e81  jnz     short loc_1800F8E6E
0x1800f8e83  mov     rax, [rbp+330h+hdc]
0x1800f8e87  mov     [rbp+330h+var_368], rax
0x1800f8e8b  mov     [rbp+330h+var_358], rax
0x1800f8e8f  mov     rdx, rbx; h
0x1800f8e92  mov     rcx, rax; hdc
0x1800f8e95  call    cs:__imp_SelectObject
0x1800f8e9b  mov     [rbp+330h+h], rax
0x1800f8e9f  test    r14d, r14d
0x1800f8ea2  jz      short loc_1800F8EF8
0x1800f8ea4  lea     r8, [r15+40h]
0x1800f8ea8  lea     rax, [rbp+330h+var_330]
0x1800f8eac  mov     [rsp+430h+var_3D8], rax
0x1800f8eb1  lea     rax, [rbp+330h+var_2E0]
0x1800f8eb5  mov     qword ptr [rsp+430h+ftn.BlendOp], rax
0x1800f8eba  mov     [rsp+430h+hSrc], esi
0x1800f8ebe  mov     [rsp+430h+wSrc], r14d
0x1800f8ec3  mov     qword ptr [rsp+430h+yoriginSrc], r13
0x1800f8ec8  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x1800f8ecc  mov     [rsp+430h+xoriginSrc], eax
0x1800f8ed0  mov     rax, [rbp+330h+hdc]
0x1800f8ed4  mov     [rsp+430h+hSection], rax
0x1800f8ed9  mov     r9, [rbp+330h+var_3A8]
0x1800f8edd  mov     edx, [r15+3Ch]
0x1800f8ee1  mov     rcx, [rbp+330h+var_3A0]
0x1800f8ee5  call    ?DrawThemeTextExPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAUtagRECT@@PEAU_DTTOPTS@@@Z; DPIToPPIHelpers::DrawThemeTextExPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,tagRECT *,_DTTOPTS *)
0x1800f8eea  mov     edi, eax
0x1800f8eec  test    eax, eax
0x1800f8eee  js      loc_1800F9041
0x1800f8ef4  mov     rdi, qword ptr [rbp+330h+var_398]
0x1800f8ef8  mov     ecx, r14d
0x1800f8efb  lea     rax, [rdi-1]
0x1800f8eff  cmp     rcx, rax
0x1800f8f02  jnb     loc_1800F8FD5
0x1800f8f08  xorps   xmm0, xmm0
0x1800f8f0b  movdqu  [rbp+330h+var_398], xmm0
0x1800f8f10  sub     edi, r14d
0x1800f8f13  lea     r14d, [rdi-1]
0x1800f8f17  lea     r13, [r13+rcx*2+0]
0x1800f8f1c  add     r13, 2
0x1800f8f20  lea     r8, [r15+40h]
0x1800f8f24  lea     rax, [rbp+330h+var_398]
0x1800f8f28  mov     [rsp+430h+var_3D0], rax
0x1800f8f2d  lea     rax, [rbp+330h+var_2E0]
0x1800f8f31  mov     [rsp+430h+var_3D8], rax
0x1800f8f36  lea     rax, [rbp+330h+var_330]
0x1800f8f3a  mov     qword ptr [rsp+430h+ftn.BlendOp], rax
0x1800f8f3f  mov     [rsp+430h+hSrc], esi
0x1800f8f43  mov     [rsp+430h+wSrc], r14d
0x1800f8f48  mov     qword ptr [rsp+430h+yoriginSrc], r13
0x1800f8f4d  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x1800f8f51  mov     [rsp+430h+xoriginSrc], eax
0x1800f8f55  mov     rax, [rbp+330h+hdc]
0x1800f8f59  mov     [rsp+430h+hSection], rax
0x1800f8f5e  mov     r9, [rbp+330h+var_3A8]
0x1800f8f62  mov     edx, [r15+3Ch]
0x1800f8f66  mov     rcx, [rbp+330h+var_3A0]
0x1800f8f6a  call    ?GetThemeTextExtentPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAU_DTTOPTS@@PEAUtagRECT@@7@Z; DPIToPPIHelpers::GetThemeTextExtentPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,_DTTOPTS *,tagRECT *,tagRECT *)
0x1800f8f6f  mov     edi, eax
0x1800f8f71  test    eax, eax
0x1800f8f73  js      loc_1800F9041
0x1800f8f79  mov     eax, dword ptr [rbp+330h+var_398]
0x1800f8f7c  sub     eax, dword ptr [rbp+330h+var_398+8]
0x1800f8f7f  add     eax, dword ptr [rbp+330h+var_2E0+8]
0x1800f8f82  mov     dword ptr [rbp+330h+var_2E0], eax
0x1800f8f85  lea     rax, [rbp+330h+var_330]
0x1800f8f89  mov     [rsp+430h+var_3D8], rax
0x1800f8f8e  lea     rax, [rbp+330h+var_2E0]
0x1800f8f92  mov     qword ptr [rsp+430h+ftn.BlendOp], rax
0x1800f8f97  mov     [rsp+430h+hSrc], esi
0x1800f8f9b  mov     [rsp+430h+wSrc], r14d
0x1800f8fa0  mov     qword ptr [rsp+430h+yoriginSrc], r13
0x1800f8fa5  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x1800f8fa9  mov     [rsp+430h+xoriginSrc], eax
0x1800f8fad  mov     rax, [rbp+330h+hdc]
0x1800f8fb1  mov     [rsp+430h+hSection], rax
0x1800f8fb6  mov     r9, [rbp+330h+var_3A8]
0x1800f8fba  lea     r8, [r15+40h]
0x1800f8fbe  mov     edx, [r15+3Ch]
0x1800f8fc2  mov     rcx, [rbp+330h+var_3A0]
0x1800f8fc6  call    ?DrawThemeTextExPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAUtagRECT@@PEAU_DTTOPTS@@@Z; DPIToPPIHelpers::DrawThemeTextExPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,tagRECT *,_DTTOPTS *)
0x1800f8fcb  mov     edi, eax
0x1800f8fcd  xor     esi, esi
0x1800f8fcf  test    eax, eax
0x1800f8fd1  js      short loc_1800F9041
0x1800f8fd3  jmp     short loc_1800F8FD7
0x1800f8fd5  xor     esi, esi
0x1800f8fd7  mov     dword ptr [rsp+430h+var_3C0.BlendOp], esi
0x1800f8fdb  mov     word ptr [rsp+430h+var_3C0.SourceConstantAlpha], 1FFh
0x1800f8fe2  mov     r8d, [r12+4]; yoriginDest
0x1800f8fe7  mov     r10d, [r12+0Ch]
0x1800f8fec  sub     r10d, r8d
0x1800f8fef  mov     r9d, [r12+8]
0x1800f8ff4  sub     r9d, [r12]; wDest
0x1800f8ff8  mov     eax, dword ptr [rsp+430h+var_3C0.BlendOp]
0x1800f8ffc  mov     dword ptr [rsp+430h+ftn.BlendOp], eax; ftn
0x1800f9000  mov     [rsp+430h+hSrc], r10d; hSrc
0x1800f9005  mov     [rsp+430h+wSrc], r9d; wSrc
0x1800f900a  mov     [rsp+430h+yoriginSrc], esi; yoriginSrc
0x1800f900e  mov     [rsp+430h+xoriginSrc], esi; xoriginSrc
0x1800f9012  mov     rax, [rbp+330h+hdc]
0x1800f9016  mov     qword ptr [rsp+430h+offset], rax; hdcSrc
0x1800f901b  mov     dword ptr [rsp+430h+hSection], r10d; hDest
0x1800f9020  mov     edx, [r12]; xoriginDest
0x1800f9024  mov     rcx, [rbp+330h+var_370]
0x1800f9028  mov     rcx, [rcx+20h]; hdcDest
0x1800f902c  call    cs:__imp_GdiAlphaBlend
0x1800f9032  test    eax, eax
0x1800f9034  jz      short loc_1800F903A
0x1800f9036  mov     edi, esi
0x1800f9038  jmp     short loc_1800F9041
0x1800f903a  call    ResultFromKnownLastError
0x1800f903f  mov     edi, eax
0x1800f9041  mov     rdx, [rbp+330h+h]; h
0x1800f9045  mov     rcx, [rbp+330h+var_368]; hdc
0x1800f9049  call    cs:__imp_SelectObject
0x1800f904f  mov     r13, [rbp+330h+var_360]
0x1800f9053  jmp     short loc_1800F905A
0x1800f9055  mov     edi, 80004005h
0x1800f905a  test    rbx, rbx
0x1800f905d  jz      short loc_1800F9069
0x1800f905f  mov     rcx, rbx; ho
0x1800f9062  call    cs:__imp_DeleteObject
0x1800f9068  nop
0x1800f9069  mov     rdx, [rbp+330h+var_340]; h
0x1800f906d  mov     rcx, r13; hdc
  ... truncated ...
```
