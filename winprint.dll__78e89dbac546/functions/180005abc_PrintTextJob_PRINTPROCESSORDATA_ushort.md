# PrintTextJob(_PRINTPROCESSORDATA *,ushort *)

- ea: `0x180005abc`
- end: `0x1800060f8`
- name: `?PrintTextJob@@YAHPEAU_PRINTPROCESSORDATA@@PEAG@Z`
- size: `1596`
- prototype: `__int64 __fastcall(struct _PRINTPROCESSORDATA *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800061f0`

## callees

- `0x180004c80`
- `0x1800054fa`
- `0x180005830`
- `0x180005abc`
- `0x1800077b5`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180005b76`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x180005b76`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180005c77`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180005cac`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180005c77`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180005cac`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006098`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800060c6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180006098`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800060c6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005efe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005efe`
- `GDI32!EndDoc` at `0x18000604b`
- `GDI32!EndDoc` at `0x18000604b`
- `GDI32!TranslateCharsetInfo` at `0x180005b93`
- `GDI32!TranslateCharsetInfo` at `0x180005b93`
- `GDI32!AbortDoc` at `0x18000608a`
- `GDI32!AbortDoc` at `0x18000608a`
- `GDI32!EndPage` at `0x180005f20`
- `GDI32!EndPage` at `0x180005fe5`
- `GDI32!EndPage` at `0x180005f20`
- `GDI32!EndPage` at `0x180005fe5`
- `GDI32!StartDocW` at `0x180005c96`
- `GDI32!StartDocW` at `0x180005c96`
- `GDI32!CreateFontIndirectW` at `0x180005bc9`
- `GDI32!CreateFontIndirectW` at `0x180005bc9`
- `GDI32!DeleteObject` at `0x1800060b8`
- `GDI32!DeleteObject` at `0x1800060b8`
- `GDI32!SetBkMode` at `0x180005dc7`
- `GDI32!SetBkMode` at `0x18000606b`
- `GDI32!SetBkMode` at `0x180005dc7`
- `GDI32!SetBkMode` at `0x18000606b`
- `GDI32!TextOutA` at `0x180005f63`
- `GDI32!TextOutA` at `0x180005f63`
- `GDI32!GetTextMetricsW` at `0x180005bf6`
- `GDI32!GetTextMetricsW` at `0x180005bf6`
- `GDI32!StartPage` at `0x180005ddf`
- `GDI32!StartPage` at `0x180005f33`
- `GDI32!StartPage` at `0x180005ddf`
- `GDI32!StartPage` at `0x180005f33`
- `GDI32!SelectObject` at `0x180005bda`
- `GDI32!SelectObject` at `0x1800060ae`
- `GDI32!SelectObject` at `0x180005bda`
- `GDI32!SelectObject` at `0x1800060ae`
- `GDI32!GetDeviceCaps` at `0x180005c30`
- `GDI32!GetDeviceCaps` at `0x180005c4a`
- `GDI32!GetDeviceCaps` at `0x180005c30`
- `GDI32!GetDeviceCaps` at `0x180005c4a`
- `WINSPOOL!ClosePrinter` at `0x180005ffd`
- `WINSPOOL!ClosePrinter` at `0x18000607b`
- `WINSPOOL!ClosePrinter` at `0x180005ffd`
- `WINSPOOL!ClosePrinter` at `0x18000607b`
- `WINSPOOL!OpenPrinterW` at `0x180005cf9`
- `WINSPOOL!OpenPrinterW` at `0x180005cf9`
- `WINSPOOL!GetPrinterDataW` at `0x180005d31`
- `WINSPOOL!GetPrinterDataW` at `0x180005d71`
- `WINSPOOL!GetPrinterDataW` at `0x180005db0`
- `WINSPOOL!GetPrinterDataW` at `0x180005d31`
- `WINSPOOL!GetPrinterDataW` at `0x180005d71`
- `WINSPOOL!GetPrinterDataW` at `0x180005db0`
- `WINSPOOL!ReadPrinter` at `0x180005e45`
- `WINSPOOL!ReadPrinter` at `0x180005e45`

## pseudocode

```c
__int64 __fastcall PrintTextJob(struct _PRINTPROCESSORDATA *a1, unsigned __int16 *a2)
{
  int v3; // r13d
  unsigned int v4; // esi
  unsigned __int8 *v5; // r15
  CHAR *v6; // rdi
  int v7; // r14d
  HFONT v8; // rax
  HDC v9; // rcx
  unsigned int tmAveCharWidth; // r13d
  unsigned int v11; // r12d
  unsigned int DeviceCaps; // eax
  HDC v13; // rcx
  int v14; // r13d
  unsigned int v15; // eax
  int v16; // edi
  unsigned int v17; // r12d
  unsigned int v18; // edi
  int v19; // esi
  void *v20; // r10
  unsigned int v21; // r13d
  unsigned int v22; // esi
  __int64 v23; // r15
  DWORD v24; // r8d
  unsigned __int8 *v25; // rsi
  int v26; // eax
  int v27; // ecx
  int v28; // esi
  unsigned __int8 *TabbedLineFromBuffer; // rax
  unsigned int v30; // eax
  HDC v31; // rcx
  int v33; // [rsp+50h] [rbp-B0h]
  unsigned int v34; // [rsp+54h] [rbp-ACh] BYREF
  int v35; // [rsp+58h] [rbp-A8h]
  unsigned int v36; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h]
  int v38; // [rsp+64h] [rbp-9Ch]
  LPCSTR lpString; // [rsp+68h] [rbp-98h]
  HANDLE phPrinter; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbNeeded; // [rsp+78h] [rbp-88h] BYREF
  int v42; // [rsp+7Ch] [rbp-84h]
  BYTE v43[4]; // [rsp+80h] [rbp-80h] BYREF
  BYTE pData[4]; // [rsp+84h] [rbp-7Ch] BYREF
  BYTE v45[4]; // [rsp+88h] [rbp-78h] BYREF
  DWORD pNoBytesRead; // [rsp+8Ch] [rbp-74h] BYREF
  int v47; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h]
  unsigned __int8 *v49; // [rsp+A0h] [rbp-60h]
  int v50; // [rsp+A8h] [rbp-58h]
  unsigned int v51; // [rsp+ACh] [rbp-54h] BYREF
  UINT CodePage; // [rsp+B0h] [rbp-50h]
  int v53; // [rsp+B4h] [rbp-4Ch]
  LONG v54; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v55; // [rsp+C0h] [rbp-40h]
  HGDIOBJ h; // [rsp+C8h] [rbp-38h]
  HGDIOBJ ho; // [rsp+D0h] [rbp-30h]
  LPWSTR pPrinterName; // [rsp+D8h] [rbp-28h]
  DOCINFOW v59; // [rsp+E0h] [rbp-20h] BYREF
  tagCHARSETINFO v60; // [rsp+108h] [rbp+8h] BYREF
  tagTEXTMETRICW tm; // [rsp+128h] [rbp+28h] BYREF
  LOGFONTW lf; // [rsp+170h] [rbp+70h] BYREF

  pPrinterName = a2;
  *(_QWORD *)&v59.cbSize = 40;
  memset_0(&lf, 0, sizeof(lf));
  pNoBytesRead = 0;
  phPrinter = 0;
  pcbNeeded = 0;
  v3 = 2;
  *(_DWORD *)pData = 0;
  v4 = 0;
  *(_DWORD *)v45 = 0;
  v5 = 0;
  *(_DWORD *)v43 = 0;
  v6 = 0;
  v7 = 0;
  v59.lpszDocName = (LPCWSTR)*((_QWORD *)a1 + 7);
  v37 = 0;
  v33 = 2;
  memset(&tm, 0, sizeof(tm));
  memset(&v59.lpszOutput, 0, 24);
  CodePage = GetACP();
  memset(&v60, 0, sizeof(v60));
  if ( TranslateCharsetInfo((DWORD *)CodePage, &v60, 2u) )
  {
    memset_0(&lf, 0, sizeof(lf));
    lf.lfCharSet = v60.ciCharset;
    lf.lfWeight = 400;
    lf.lfPitchAndFamily = 1;
    v8 = CreateFontIndirectW(&lf);
    v9 = (HDC)*((_QWORD *)a1 + 13);
    ho = v8;
    h = SelectObject(v9, v8);
  }
  else
  {
    h = 0;
    ho = 0;
  }
  if ( GetTextMetricsW(*((HDC *)a1 + 13), &tm) )
  {
    tmAveCharWidth = tm.tmAveCharWidth;
    v54 = tm.tmAveCharWidth;
    if ( !tm.tmAveCharWidth )
      goto LABEL_68;
    v11 = tm.tmHeight + tm.tmExternalLeading;
    v53 = tm.tmHeight + tm.tmExternalLeading;
    if ( !(tm.tmHeight + tm.tmExternalLeading) )
      goto LABEL_68;
    DeviceCaps = GetDeviceCaps(*((HDC *)a1 + 13), 118);
    v13 = (HDC)*((_QWORD *)a1 + 13);
    v14 = DeviceCaps / tmAveCharWidth;
    v50 = v14;
    v15 = GetDeviceCaps(v13, 117);
    if ( !v14 )
      goto LABEL_68;
    v42 = v15 / v11;
    if ( v15 / v11
      && (lpString = (LPCSTR)LocalAlloc(0x40u, (unsigned int)(v14 + 5)), (v6 = (CHAR *)lpString) != 0)
      && StartDocW(*((HDC *)a1 + 13), &v59)
      && (v55 = (unsigned __int8 *)LocalAlloc(0x40u, 0x40000u), (v5 = v55) != 0) )
    {
      v16 = *((_DWORD *)a1 + 23);
      v47 = v16;
      Src = 0;
      v49 = 0;
      while ( 2 )
      {
        if ( v16 )
        {
          v17 = 0;
          v51 = 0;
          v18 = 384;
          v36 = 0;
          v34 = 384;
          if ( OpenPrinterW(pPrinterName, &phPrinter, 0) )
          {
            v19 = 384;
            if ( !GetPrinterDataW(phPrinter, (LPWSTR)L"Winprint_TextNoTranslation", 0, pData, 4u, &pcbNeeded)
              && *(_DWORD *)pData )
            {
              v18 = 0;
              v34 = 0;
              v19 = 0;
            }
            if ( GetPrinterDataW(phPrinter, (LPWSTR)L"Winprint_TextNoCRTranslation", 0, v45, 4u, &pcbNeeded)
              || !*(_DWORD *)v45
              || (v18 = v19 & 0xFFFFFEFF,
                  v34 = v19 & 0xFFFFFEFF,
                  GetPrinterDataW(phPrinter, (LPWSTR)L"Transparency", 0, v43, 4u, &pcbNeeded))
              || !*(_DWORD *)v43 )
            {
              v3 = v33;
            }
            else
            {
              v3 = SetBkMode(*((HDC *)a1 + 13), 1);
              v33 = v3;
            }
            if ( StartPage(*((HDC *)a1 + 13)) == -1 )
            {
              v6 = (CHAR *)lpString;
              v7 = 1;
              v4 = 0;
              goto LABEL_69;
            }
            v20 = Src;
            v21 = 0;
            v35 = 0;
            v38 = 0;
LABEL_26:
            while ( 2 )
            {
              if ( (v18 & 8) != 0 )
              {
LABEL_27:
                v22 = (_DWORD)v49 - (_DWORD)v20;
                memcpy_0(v5, v20, (unsigned int)((_DWORD)v49 - (_DWORD)v20));
                v18 &= ~8u;
                v34 = v18;
              }
              else
              {
                v22 = 0;
              }
              v23 = v22;
              v24 = 0x40000 - v22;
              v25 = v55;
              if ( ReadPrinter(phPrinter, &v55[v23], v24, &pNoBytesRead) && pNoBytesRead )
              {
                Src = v25;
                v26 = v38;
                v27 = (_DWORD)v25 + v23 + pNoBytesRead;
                v49 = &v25[v23 + pNoBytesRead];
                v20 = v25;
              }
              else
              {
                v27 = (int)v49;
                v26 = 1;
                v20 = Src;
                v38 = 1;
              }
              v5 = v25;
              while ( 1 )
              {
                v28 = v35;
                if ( !v26 )
                {
                  TabbedLineFromBuffer = GetTabbedLineFromBuffer(
                                           (unsigned __int8 *)v20,
                                           v27 - (int)v20,
                                           (unsigned __int8 *)lpString,
                                           v50 - v35,
                                           *((_DWORD *)a1 + 24),
                                           CodePage,
                                           &v36,
                                           &v51,
                                           &v34);
                  v18 = v34;
                  v20 = TabbedLineFromBuffer;
                  v17 = v36;
                  Src = TabbedLineFromBuffer;
                  if ( !TabbedLineFromBuffer )
                    goto LABEL_26;
                  if ( (v34 & 8) != 0 )
                    goto LABEL_27;
                }
                if ( (*((_BYTE *)a1 + 16) & 8) != 0 )
                  WaitForSingleObject(*((HANDLE *)a1 + 3), 0xFFFFFFFF);
                if ( (*((_BYTE *)a1 + 16) & 1) != 0 )
                {
                  v4 = 1;
                  v7 = 1;
                  goto LABEL_66;
                }
                if ( v17 )
                {
                  v30 = v42;
                  while ( 1 )
                  {
                    v31 = (HDC)*((_QWORD *)a1 + 13);
                    if ( v21 < v30 )
                      break;
                    if ( EndPage(v31) == -1 || StartPage(*((HDC *)a1 + 13)) == -1 )
                      goto LABEL_60;
                    v30 = v42;
                    v21 -= v42;
                  }
                  if ( TextOutA(v31, v28 * v54, v21 * v53, lpString, v17) )
                  {
                    v35 = v17 + v28;
                    goto LABEL_48;
                  }
LABEL_60:
                  v4 = v37;
                  goto LABEL_65;
                }
LABEL_48:
                if ( (v18 & 0x40) != 0 )
                {
                  v18 &= ~0x40u;
                  v35 = 0;
                  v34 = v18;
                }
                if ( (v18 & 0x20) != 0 )
                {
                  ++v21;
                  v18 &= ~0x20u;
                  v34 = v18;
                }
                if ( (v18 & 0x10) != 0 )
                {
                  v21 = v42;
                  v18 &= ~0x10u;
                  v35 = 0;
                  v34 = v18;
                }
                v20 = Src;
                v17 = 0;
                v36 = 0;
                if ( !Src )
                  break;
                v27 = (int)v49;
                if ( Src == v49 )
                  break;
                v26 = v38;
              }
              if ( !v38 )
                continue;
              break;
            }
            if ( EndPage(*((HDC *)a1 + 13)) != -1 )
            {
              v16 = --v47;
              ClosePrinter(phPrinter);
              phPrinter = 0;
              continue;
            }
          }
          else
          {
            phPrinter = 0;
          }
          v4 = 0;
LABEL_65:
          v7 = 1;
        }
        else
        {
          EndDoc(*((HDC *)a1 + 13));
          v4 = 1;
        }
        break;
      }
LABEL_66:
      v6 = (CHAR *)lpString;
      v3 = v33;
    }
    else
    {
LABEL_68:
      v3 = 2;
    }
  }
LABEL_69:
  if ( *(_DWORD *)v43 )
    SetBkMode(*((HDC *)a1 + 13), v3);
  if ( phPrinter )
    ClosePrinter(phPrinter);
  if ( v7 )
    AbortDoc(*((HDC *)a1 + 13));
  if ( v6 )
    LocalFree(v6);
  if ( h )
  {
    SelectObject(*((HDC *)a1 + 13), h);
    DeleteObject(ho);
  }
  if ( v5 )
    LocalFree(v5);
  return v4;
}

```

## disassembly

```asm
0x180005abc  mov     [rsp-8+arg_10], rbx
0x180005ac1  push    rbp
0x180005ac2  push    rsi
0x180005ac3  push    rdi
0x180005ac4  push    r12
0x180005ac6  push    r13
0x180005ac8  push    r14
0x180005aca  push    r15
0x180005acc  lea     rbp, [rsp-0E0h]
0x180005ad4  sub     rsp, 1E0h
0x180005adb  mov     rax, cs:__security_cookie
0x180005ae2  xor     rax, rsp
0x180005ae5  mov     [rbp+110h+var_40], rax
0x180005aec  mov     [rbp+110h+pPrinterName], rdx
0x180005af0  mov     rbx, rcx
0x180005af3  mov     r12d, 5Ch ; '\'
0x180005af9  mov     qword ptr [rbp+110h+var_130.cbSize], 28h ; '('
0x180005b01  mov     r8d, r12d; Size
0x180005b04  mov     qword ptr [rbp+110h+var_130.fwType], 0
0x180005b0c  xor     edx, edx; Val
0x180005b0e  lea     rcx, [rbp+110h+lf]; void *
0x180005b12  call    memset_0
0x180005b17  xorps   xmm0, xmm0
0x180005b1a  mov     [rbp+110h+pNoBytesRead], 0
0x180005b21  xor     eax, eax
0x180005b23  mov     [rsp+210h+phPrinter], 0
0x180005b2c  mov     [rsp+210h+var_198], eax
0x180005b30  lea     r13d, [r12-5Ah]
0x180005b35  mov     dword ptr [rbp+110h+pData], eax
0x180005b38  xor     esi, esi
0x180005b3a  mov     dword ptr [rbp+110h+var_188], eax
0x180005b3d  xor     r15d, r15d
0x180005b40  mov     dword ptr [rbp+110h+var_190], eax
0x180005b43  xor     edi, edi
0x180005b45  mov     rax, [rbx+38h]
0x180005b49  xor     r14d, r14d
0x180005b4c  movups  xmmword ptr [rbp+110h+tm.tmOverhang], xmm0
0x180005b50  mov     [rbp+110h+var_130.lpszDocName], rax
0x180005b54  movups  xmmword ptr [rbp+110h+var_108.ciCharset], xmm0
0x180005b58  mov     [rsp+210h+var_1B0], esi
0x180005b5c  movups  xmmword ptr [rbp+110h+var_108.fs.fsUsb+8], xmm0
0x180005b60  mov     [rsp+210h+var_1C0], r13d
0x180005b65  movups  xmmword ptr [rbp+110h+tm.tmHeight], xmm0
0x180005b69  movups  xmmword ptr [rbp+110h+tm.tmExternalLeading], xmm0
0x180005b6d  movups  xmmword ptr [rbp+110h+tm.tmFirstChar], xmm0
0x180005b71  movdqu  xmmword ptr [rbp+110h+var_130.lpszOutput], xmm0
0x180005b76  call    cs:__imp_GetACP
0x180005b7c  xorps   xmm0, xmm0
0x180005b7f  mov     ecx, eax; lpSrc
0x180005b81  lea     rdx, [rbp+110h+var_108]; lpCs
0x180005b85  mov     [rbp+110h+CodePage], eax
0x180005b88  mov     r8d, r13d; dwFlags
0x180005b8b  movups  xmmword ptr [rbp+110h+var_108.ciCharset], xmm0
0x180005b8f  movups  xmmword ptr [rbp+110h+var_108.fs.fsUsb+8], xmm0
0x180005b93  call    cs:__imp_TranslateCharsetInfo
0x180005b99  test    eax, eax
0x180005b9b  jz      short loc_180005BE6
0x180005b9d  mov     r8d, r12d; Size
0x180005ba0  lea     rcx, [rbp+110h+lf]; void *
0x180005ba4  xor     edx, edx; Val
0x180005ba6  call    memset_0
0x180005bab  mov     al, byte ptr [rbp+110h+var_108.ciCharset]
0x180005bae  lea     rcx, [rbp+110h+lf]; lplf
0x180005bb2  mov     [rbp+110h+lf.lfCharSet], al
0x180005bb8  mov     [rbp+110h+lf.lfWeight], 190h
0x180005bc2  mov     [rbp+110h+lf.lfPitchAndFamily], 1
0x180005bc9  call    cs:__imp_CreateFontIndirectW
0x180005bcf  mov     rcx, [rbx+68h]; hdc
0x180005bd3  mov     rdx, rax; h
0x180005bd6  mov     [rbp+110h+ho], rax
0x180005bda  call    cs:__imp_SelectObject
0x180005be0  mov     [rbp+110h+h], rax
0x180005be4  jmp     short loc_180005BEE
0x180005be6  mov     [rbp+110h+h], rsi
0x180005bea  mov     [rbp+110h+ho], rsi
0x180005bee  mov     rcx, [rbx+68h]; hdc
0x180005bf2  lea     rdx, [rbp+110h+tm]; lptm
0x180005bf6  call    cs:__imp_GetTextMetricsW
0x180005bfc  test    eax, eax
0x180005bfe  jz      loc_18000605E
0x180005c04  mov     r13d, [rbp+110h+tm.tmAveCharWidth]
0x180005c08  mov     [rbp+110h+var_158], r13d
0x180005c0c  test    r13d, r13d
0x180005c0f  jz      loc_180006058
0x180005c15  mov     r12d, [rbp+110h+tm.tmExternalLeading]
0x180005c19  add     r12d, [rbp+110h+tm.tmHeight]
0x180005c1d  mov     [rbp+110h+var_15C], r12d
0x180005c21  jz      loc_180006058
0x180005c27  mov     rcx, [rbx+68h]; hdc
0x180005c2b  mov     edx, 76h ; 'v'; index
0x180005c30  call    cs:__imp_GetDeviceCaps
0x180005c36  mov     rcx, [rbx+68h]; hdc
0x180005c3a  xor     edx, edx
0x180005c3c  div     r13d
0x180005c3f  mov     edx, 75h ; 'u'; index
0x180005c44  mov     r13d, eax
0x180005c47  mov     [rbp+110h+var_168], eax
0x180005c4a  call    cs:__imp_GetDeviceCaps
0x180005c50  test    r13d, r13d
0x180005c53  jz      loc_180006058
0x180005c59  xor     edx, edx
0x180005c5b  div     r12d
0x180005c5e  mov     [rsp+210h+var_194], eax
0x180005c62  test    eax, eax
0x180005c64  jz      loc_180006058
0x180005c6a  mov     r12d, 40h ; '@'
0x180005c70  lea     edx, [r13+5]; uBytes
0x180005c74  mov     ecx, r12d; uFlags
0x180005c77  call    cs:__imp_LocalAlloc
0x180005c7d  mov     [rsp+210h+lpString], rax
0x180005c82  mov     rdi, rax
0x180005c85  test    rax, rax
0x180005c88  jz      loc_180006058
0x180005c8e  mov     rcx, [rbx+68h]; hdc
0x180005c92  lea     rdx, [rbp+110h+var_130]; lpdi
0x180005c96  call    cs:__imp_StartDocW
0x180005c9c  test    eax, eax
0x180005c9e  jz      loc_180006058
0x180005ca4  mov     edx, 40000h; uBytes
0x180005ca9  mov     ecx, r12d; uFlags
0x180005cac  call    cs:__imp_LocalAlloc
0x180005cb2  mov     [rbp+110h+var_150], rax
0x180005cb6  mov     r15, rax
0x180005cb9  test    rax, rax
0x180005cbc  jz      loc_180006058
0x180005cc2  mov     edi, [rbx+5Ch]
0x180005cc5  mov     [rbp+110h+var_180], edi
0x180005cc8  mov     [rbp+110h+Src], rsi
0x180005ccc  mov     [rbp+110h+var_170], rsi
0x180005cd0  test    edi, edi
0x180005cd2  jz      loc_180006047
0x180005cd8  mov     rcx, [rbp+110h+pPrinterName]; pPrinterName
0x180005cdc  lea     rdx, [rsp+210h+phPrinter]; phPrinter
0x180005ce1  xor     r12d, r12d
0x180005ce4  mov     [rbp+110h+var_164], r14d
0x180005ce8  mov     edi, 180h
0x180005ced  mov     [rsp+210h+var_1B4], r12d
0x180005cf2  xor     r8d, r8d; pDefault
0x180005cf5  mov     [rsp+210h+var_1BC], edi
0x180005cf9  call    cs:__imp_OpenPrinterW
0x180005cff  xor     r13d, r13d
0x180005d02  test    eax, eax
0x180005d04  jz      loc_18000602D
0x180005d0a  mov     rcx, [rsp+210h+phPrinter]; hPrinter
0x180005d0f  lea     rax, [rsp+210h+var_198]
0x180005d14  mov     [rsp+210h+pcbNeeded], rax; pcbNeeded
0x180005d19  lea     r9, [rbp+110h+pData]; pData
0x180005d1d  xor     r8d, r8d; pType
0x180005d20  mov     [rsp+210h+nSize], 4; nSize
0x180005d28  lea     rdx, aWinprintTextno; "Winprint_TextNoTranslation"
0x180005d2f  mov     esi, edi
0x180005d31  call    cs:__imp_GetPrinterDataW
0x180005d37  test    eax, eax
0x180005d39  jnz     short loc_180005D4C
0x180005d3b  cmp     dword ptr [rbp+110h+pData], r13d
0x180005d3f  jz      short loc_180005D4C
0x180005d41  mov     edi, r13d
0x180005d44  mov     [rsp+210h+var_1BC], r13d
0x180005d49  mov     esi, r13d
0x180005d4c  mov     rcx, [rsp+210h+phPrinter]; hPrinter
0x180005d51  lea     rax, [rsp+210h+var_198]
0x180005d56  mov     [rsp+210h+pcbNeeded], rax; pcbNeeded
0x180005d5b  lea     r9, [rbp+110h+var_188]; pData
0x180005d5f  xor     r8d, r8d; pType
0x180005d62  mov     [rsp+210h+nSize], 4; nSize
0x180005d6a  lea     rdx, aWinprintTextno_0; "Winprint_TextNoCRTranslation"
0x180005d71  call    cs:__imp_GetPrinterDataW
0x180005d77  test    eax, eax
0x180005d79  jnz     short loc_180005DD6
0x180005d7b  cmp     dword ptr [rbp+110h+var_188], r13d
0x180005d7f  jz      short loc_180005DD6
0x180005d81  mov     rcx, [rsp+210h+phPrinter]; hPrinter
0x180005d86  lea     rax, [rsp+210h+var_198]
0x180005d8b  mov     [rsp+210h+pcbNeeded], rax; pcbNeeded
0x180005d90  lea     r9, [rbp+110h+var_190]; pData
0x180005d94  mov     edi, esi
0x180005d96  mov     [rsp+210h+nSize], 4; nSize
0x180005d9e  btr     edi, 8
0x180005da2  lea     rdx, aTransparency; "Transparency"
0x180005da9  xor     r8d, r8d; pType
0x180005dac  mov     [rsp+210h+var_1BC], edi
0x180005db0  call    cs:__imp_GetPrinterDataW
0x180005db6  test    eax, eax
0x180005db8  jnz     short loc_180005DD6
0x180005dba  cmp     dword ptr [rbp+110h+var_190], r13d
0x180005dbe  jz      short loc_180005DD6
0x180005dc0  mov     rcx, [rbx+68h]; hdc
0x180005dc4  lea     edx, [rax+1]; mode
0x180005dc7  call    cs:__imp_SetBkMode
0x180005dcd  mov     r13d, eax
0x180005dd0  mov     [rsp+210h+var_1C0], eax
0x180005dd4  jmp     short loc_180005DDB
0x180005dd6  mov     r13d, [rsp+210h+var_1C0]
0x180005ddb  mov     rcx, [rbx+68h]; hdc
0x180005ddf  call    cs:__imp_StartPage
0x180005de5  cmp     eax, 0FFFFFFFFh
0x180005de8  jz      loc_18000601D
0x180005dee  mov     r10, [rbp+110h+Src]
0x180005df2  xor     ecx, ecx
0x180005df4  xor     r13d, r13d
0x180005df7  mov     [rsp+210h+var_1B8], ecx
0x180005dfb  xor     edx, edx
0x180005dfd  mov     [rsp+210h+var_1AC], edx
0x180005e01  test    dil, 8
0x180005e05  jz      short loc_180005E26
0x180005e07  mov     eax, dword ptr [rbp+110h+var_170]
0x180005e0a  mov     rdx, r10; Src
0x180005e0d  sub     eax, r10d
0x180005e10  mov     rcx, r15; void *
0x180005e13  mov     r8d, eax; Size
0x180005e16  mov     esi, eax
0x180005e18  call    memcpy_0
0x180005e1d  and     edi, 0FFFFFFF7h
0x180005e20  mov     [rsp+210h+var_1BC], edi
0x180005e24  jmp     short loc_180005E28
0x180005e26  xor     esi, esi
0x180005e28  mov     rcx, [rsp+210h+phPrinter]; hPrinter
0x180005e2d  lea     r9, [rbp+110h+pNoBytesRead]; pNoBytesRead
0x180005e31  mov     r8d, 40000h
0x180005e37  mov     r15d, esi
0x180005e3a  sub     r8d, esi; cbBuf
0x180005e3d  mov     rsi, [rbp+110h+var_150]
0x180005e41  lea     rdx, [r15+rsi]; pBuf
0x180005e45  call    cs:__imp_ReadPrinter
0x180005e4b  test    eax, eax
0x180005e4d  jz      short loc_180005E6E
0x180005e4f  mov     eax, [rbp+110h+pNoBytesRead]
0x180005e52  test    eax, eax
0x180005e54  jz      short loc_180005E6E
0x180005e56  lea     rcx, [r15+rax]
0x180005e5a  mov     [rbp+110h+Src], rsi
0x180005e5e  mov     eax, [rsp+210h+var_1AC]
0x180005e62  add     rcx, rsi
0x180005e65  mov     [rbp+110h+var_170], rcx
0x180005e69  mov     r10, rsi
0x180005e6c  jmp     short loc_180005E7F
0x180005e6e  mov     rcx, [rbp+110h+var_170]
0x180005e72  mov     eax, 1
0x180005e77  mov     r10, [rbp+110h+Src]
0x180005e7b  mov     [rsp+210h+var_1AC], eax
0x180005e7f  mov     r15, rsi
0x180005e82  mov     esi, [rsp+210h+var_1B8]
0x180005e86  test    eax, eax
0x180005e88  jnz     short loc_180005EF1
0x180005e8a  mov     r9d, [rbp+110h+var_168]
0x180005e8e  lea     rax, [rsp+210h+var_1BC]
0x180005e93  mov     r8, [rsp+210h+lpString]; unsigned __int8 *
0x180005e98  mov     edx, ecx
0x180005e9a  mov     [rsp+210h+var_1D0], rax; unsigned int *
0x180005e9f  sub     r9d, esi; unsigned int
0x180005ea2  lea     rax, [rbp+110h+var_164]
0x180005ea6  sub     edx, r10d; unsigned int
0x180005ea9  mov     [rsp+210h+var_1D8], rax; unsigned int *
0x180005eae  mov     rcx, r10; unsigned __int8 *
0x180005eb1  lea     rax, [rsp+210h+var_1B4]
0x180005eb6  mov     [rsp+210h+var_1E0], rax; unsigned int *
0x180005ebb  mov     eax, [rbp+110h+CodePage]
0x180005ebe  mov     dword ptr [rsp+210h+pcbNeeded], eax; CodePage
0x180005ec2  mov     eax, [rbx+60h]
0x180005ec5  mov     [rsp+210h+nSize], eax; unsigned int
0x180005ec9  call    ?GetTabbedLineFromBuffer@@YAPEAEPEAEK0KKKPEAK11@Z; GetTabbedLineFromBuffer(uchar *,ulong,uchar *,ulong,ulong,ulong,ulong *,ulong *,ulong *)
0x180005ece  mov     edi, [rsp+210h+var_1BC]
0x180005ed2  mov     r10, rax
0x180005ed5  mov     r12d, [rsp+210h+var_1B4]
0x180005eda  mov     [rbp+110h+Src], rax
0x180005ede  test    rax, rax
0x180005ee1  jz      loc_180005E01
0x180005ee7  test    dil, 8
0x180005eeb  jnz     loc_180005E07
0x180005ef1  test    byte ptr [rbx+10h], 8
0x180005ef5  jz      short loc_180005F04
0x180005ef7  mov     rcx, [rbx+18h]; hHandle
0x180005efb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005efe  call    cs:__imp_WaitForSingleObject
0x180005f04  test    byte ptr [rbx+10h], 1
0x180005f08  jnz     loc_180006013
0x180005f0e  test    r12d, r12d
0x180005f11  jz      short loc_180005F78
0x180005f13  mov     eax, [rsp+210h+var_194]
0x180005f17  mov     rcx, [rbx+68h]; hdc
0x180005f1b  cmp     r13d, eax
0x180005f1e  jb      short loc_180005F4B
0x180005f20  call    cs:__imp_EndPage
0x180005f26  cmp     eax, 0FFFFFFFFh
0x180005f29  jz      loc_18000600D
0x180005f2f  mov     rcx, [rbx+68h]; hdc
0x180005f33  call    cs:__imp_StartPage
0x180005f39  cmp     eax, 0FFFFFFFFh
0x180005f3c  jz      loc_18000600D
0x180005f42  mov     eax, [rsp+210h+var_194]
0x180005f46  sub     r13d, eax
0x180005f49  jmp     short loc_180005F17
0x180005f4b  mov     r8d, [rbp+110h+var_15C]
0x180005f4f  mov     edx, [rbp+110h+var_158]
0x180005f52  mov     r9, [rsp+210h+lpString]; lpString
0x180005f57  imul    r8d, r13d; y
0x180005f5b  imul    edx, esi; x
0x180005f5e  mov     [rsp+210h+nSize], r12d; c
0x180005f63  call    cs:__imp_TextOutA
0x180005f69  test    eax, eax
  ... truncated ...
```
