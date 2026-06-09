# CreateSizedDIBSECTION

- ea: `0x1800268f0`
- end: `0x180026bac`
- name: `CreateSizedDIBSECTION`
- size: `700`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800266a0`
- `0x180026bc0`

## callees

- `0x180012550`
- `0x180013066`
- `0x180026078`
- `0x1800268f0`
- `0x1800369d1`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026ae1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026ae1`
- `GDI32!DeleteDC` at `0x180026b6d`
- `GDI32!DeleteDC` at `0x180026b6d`
- `GDI32!CreateDIBSection` at `0x180026abb`
- `GDI32!CreateDIBSection` at `0x180026abb`
- `GDI32!RealizePalette` at `0x180026a47`
- `GDI32!RealizePalette` at `0x180026a47`
- `GDI32!SelectPalette` at `0x180026a3e`
- `GDI32!SelectPalette` at `0x180026a3e`
- `GDI32!CreateCompatibleDC` at `0x180026960`
- `GDI32!CreateCompatibleDC` at `0x180026960`
- `GDI32!GetPaletteEntries` at `0x180026a5f`
- `GDI32!GetPaletteEntries` at `0x180026a5f`
- `USER32!GetDC` at `0x180026949`
- `USER32!GetDC` at `0x180026949`
- `USER32!ReleaseDC` at `0x180026b7a`
- `USER32!ReleaseDC` at `0x180026b7a`

## pseudocode

```c
_BOOL8 __fastcall CreateSizedDIBSECTION(
        LONG *a1,
        unsigned int a2,
        HPALETTE a3,
        __int64 a4,
        HBITMAP *a5,
        _QWORD *a6,
        HPALETTE *a7)
{
  HDC DC; // rax
  HDC CompatibleDC; // rsi
  LONG v12; // ecx
  __int64 v13; // r14
  int v14; // r10d
  HPALETTE hSection; // r11
  int i; // r8d
  __int64 v17; // rdx
  HBITMAP v18; // rax
  _OWORD *v19; // rax
  _OWORD *v20; // rcx
  BITMAPINFO *p_pbmi; // rax
  __int128 v22; // xmm1
  HDC hDC; // [rsp+30h] [rbp-D0h]
  HPALETTE hPal; // [rsp+38h] [rbp-C8h] BYREF
  BITMAPINFO pbmi; // [rsp+40h] [rbp-C0h] BYREF

  hPal = a3;
  *a5 = 0;
  DC = GetDC(0);
  hDC = DC;
  if ( DC )
  {
    CompatibleDC = CreateCompatibleDC(DC);
    if ( !CompatibleDC )
    {
LABEL_24:
      ReleaseDC(0, hDC);
      return *a5 != 0;
    }
    memset_0(&pbmi, 0, 0x428u);
    pbmi.bmiHeader.biWidth = *a1;
    v12 = a1[1];
    pbmi.bmiHeader.biSize = 40;
    pbmi.bmiHeader.biHeight = v12;
    v13 = 8;
    pbmi.bmiHeader.biPlanes = 1;
    pbmi.bmiHeader.biBitCount = a2;
    pbmi.bmiHeader.biCompression = 0;
    *(_QWORD *)&pbmi.bmiHeader.biXPelsPerMeter = 0;
    if ( a2 > 8 )
      pbmi.bmiHeader.biClrUsed = 0;
    else
      pbmi.bmiHeader.biClrUsed = 1 << a2;
    pbmi.bmiHeader.biClrImportant = 0;
    pbmi.bmiHeader.biSizeImage = CalcBitmapSize(&pbmi);
    if ( a2 <= 8 )
    {
      if ( a4 && *(unsigned __int16 *)(a4 + 14) == a2 )
      {
        if ( *(_DWORD *)(a4 + 32) != (_DWORD)hSection )
          v14 = *(_DWORD *)(a4 + 32);
        if ( v14 > 256 )
          goto LABEL_23;
        memcpy_0(pbmi.bmiColors, (const void *)(a4 + 40), 4LL * v14);
        hSection = 0;
      }
      else
      {
        SelectPalette(CompatibleDC, hPal, 1);
        RealizePalette(CompatibleDC);
        GetPaletteEntries(hPal, 0, 0x100u, (LPPALETTEENTRY)pbmi.bmiColors);
        hSection = 0;
        for ( i = 0;
              i < (int)pbmi.bmiHeader.biClrUsed;
              pbmi.bmiColors[v17] = (RGBQUAD)((pbmi.bmiColors[v17].rgbBlue << 16)
                                            | pbmi.bmiColors[v17].rgbRed
                                            | (pbmi.bmiColors[v17].rgbGreen << 8)) )
        {
          v17 = i++;
        }
      }
    }
    hPal = hSection;
    v18 = CreateDIBSection(CompatibleDC, &pbmi, 0, (void **)&hPal, hSection, (DWORD)hSection);
    *a5 = v18;
    if ( v18 )
    {
      if ( a6 )
      {
        v19 = LocalAlloc(0x40u, 0x428u);
        *a6 = v19;
        v20 = v19;
        if ( v19 )
        {
          p_pbmi = &pbmi;
          do
          {
            *v20 = *(_OWORD *)&p_pbmi->bmiHeader.biSize;
            v20[1] = *(_OWORD *)&p_pbmi->bmiHeader.biCompression;
            v20[2] = *(_OWORD *)&p_pbmi->bmiHeader.biClrUsed;
            v20[3] = *(_OWORD *)&p_pbmi[1].bmiHeader.biWidth;
            v20[4] = *(_OWORD *)&p_pbmi[1].bmiHeader.biSizeImage;
            v20[5] = *(_OWORD *)&p_pbmi[1].bmiHeader.biClrImportant;
            v20[6] = *(_OWORD *)&p_pbmi[2].bmiHeader.biHeight;
            v22 = *(_OWORD *)&p_pbmi[2].bmiHeader.biXPelsPerMeter;
            p_pbmi = (BITMAPINFO *)((char *)p_pbmi + 128);
            v20[7] = v22;
            v20 += 8;
            --v13;
          }
          while ( v13 );
          *v20 = *(_OWORD *)&p_pbmi->bmiHeader.biSize;
          v20[1] = *(_OWORD *)&p_pbmi->bmiHeader.biCompression;
          *((_QWORD *)v20 + 4) = *(_QWORD *)&p_pbmi->bmiHeader.biClrUsed;
        }
      }
      if ( a7 )
        *a7 = hPal;
    }
LABEL_23:
    DeleteDC(CompatibleDC);
    goto LABEL_24;
  }
  return *a5 != 0;
}

```

## disassembly

```asm
0x1800268f0  push    rbp
0x1800268f2  push    rbx
0x1800268f3  push    rsi
0x1800268f4  push    rdi
0x1800268f5  push    r12
0x1800268f7  push    r13
0x1800268f9  push    r14
0x1800268fb  push    r15
0x1800268fd  lea     rbp, [rsp-388h]
0x180026905  sub     rsp, 488h
0x18002690c  mov     rax, cs:__security_cookie
0x180026913  xor     rax, rsp
0x180026916  mov     [rbp+3C0h+var_50], rax
0x18002691d  mov     r13, [rbp+3C0h+arg_20]
0x180026924  mov     r14, rcx
0x180026927  mov     r15, [rbp+3C0h+arg_28]
0x18002692e  xor     ecx, ecx; hWnd
0x180026930  mov     r12, [rbp+3C0h+arg_30]
0x180026937  mov     rbx, r9
0x18002693a  mov     [rsp+4C0h+hPal], r8
0x18002693f  mov     edi, edx
0x180026941  mov     qword ptr [r13+0], 0
0x180026949  call    cs:__imp_GetDC
0x18002694f  mov     [rsp+4C0h+hDC], rax
0x180026954  test    rax, rax
0x180026957  jz      loc_180026B80
0x18002695d  mov     rcx, rax; hdc
0x180026960  call    cs:__imp_CreateCompatibleDC
0x180026966  mov     rsi, rax
0x180026969  test    rax, rax
0x18002696c  jz      loc_180026B73
0x180026972  xor     edx, edx; Val
0x180026974  lea     rcx, [rsp+4C0h+pbmi]; void *
0x180026979  mov     r8d, 428h; Size
0x18002697f  call    memset_0
0x180026984  mov     ecx, [r14]
0x180026987  xor     r11d, r11d
0x18002698a  mov     eax, 1
0x18002698f  mov     [rsp+4C0h+pbmi.bmiHeader.biWidth], ecx
0x180026993  mov     ecx, [r14+4]
0x180026997  mov     [rsp+4C0h+pbmi.bmiHeader.biSize], 28h ; '('
0x18002699f  mov     [rsp+4C0h+pbmi.bmiHeader.biHeight], ecx
0x1800269a3  lea     r14d, [rax+7]
0x1800269a7  mov     [rsp+4C0h+pbmi.bmiHeader.biPlanes], ax
0x1800269ac  mov     [rsp+4C0h+pbmi.bmiHeader.biBitCount], di
0x1800269b1  mov     [rsp+4C0h+pbmi.bmiHeader.biCompression], r11d
0x1800269b6  mov     qword ptr [rsp+4C0h+pbmi.bmiHeader.biXPelsPerMeter], r11
0x1800269bb  cmp     edi, r14d
0x1800269be  ja      short loc_1800269CF
0x1800269c0  mov     ecx, edi
0x1800269c2  mov     r10d, eax
0x1800269c5  shl     r10d, cl
0x1800269c8  mov     [rsp+4C0h+pbmi.bmiHeader.biClrUsed], r10d
0x1800269cd  jmp     short loc_1800269D7
0x1800269cf  mov     r10d, r11d
0x1800269d2  mov     [rsp+4C0h+pbmi.bmiHeader.biClrUsed], r11d
0x1800269d7  lea     rcx, [rsp+4C0h+pbmi]; struct tagBITMAPINFO *
0x1800269dc  mov     [rsp+4C0h+pbmi.bmiHeader.biClrImportant], r11d
0x1800269e1  call    ?CalcBitmapSize@@YAKPEBUtagBITMAPINFO@@@Z; CalcBitmapSize(tagBITMAPINFO const *)
0x1800269e6  mov     [rsp+4C0h+pbmi.bmiHeader.biSizeImage], eax
0x1800269ea  cmp     edi, r14d
0x1800269ed  ja      loc_180026A9C
0x1800269f3  test    rbx, rbx
0x1800269f6  jz      short loc_180026A30
0x1800269f8  movzx   eax, word ptr [rbx+0Eh]
0x1800269fc  cmp     eax, edi
0x1800269fe  jnz     short loc_180026A30
0x180026a00  cmp     [rbx+20h], r11d
0x180026a04  cmovnz  r10d, [rbx+20h]
0x180026a09  cmp     r10d, 100h
0x180026a10  jg      loc_180026B6A
0x180026a16  movsxd  r8, r10d
0x180026a19  lea     rdx, [rbx+28h]; Src
0x180026a1d  shl     r8, 2; Size
0x180026a21  lea     rcx, [rsp+4C0h+pbmi.bmiColors]; void *
0x180026a26  call    memcpy_0
0x180026a2b  xor     r11d, r11d
0x180026a2e  jmp     short loc_180026A9C
0x180026a30  mov     rdx, [rsp+4C0h+hPal]; hPal
0x180026a35  mov     r8d, 1; bForceBkgd
0x180026a3b  mov     rcx, rsi; hdc
0x180026a3e  call    cs:__imp_SelectPalette
0x180026a44  mov     rcx, rsi; hdc
0x180026a47  call    cs:__imp_RealizePalette
0x180026a4d  mov     rcx, [rsp+4C0h+hPal]; hpal
0x180026a52  lea     r9, [rsp+4C0h+pbmi.bmiColors]; pPalEntries
0x180026a57  xor     edx, edx; iStart
0x180026a59  mov     r8d, 100h; cEntries
0x180026a5f  call    cs:__imp_GetPaletteEntries
0x180026a65  xor     r11d, r11d
0x180026a68  mov     r8d, r11d
0x180026a6b  cmp     [rsp+4C0h+pbmi.bmiHeader.biClrUsed], r11d
0x180026a70  jle     short loc_180026A9C
0x180026a72  movsxd  rdx, r8d
0x180026a75  inc     r8d
0x180026a78  movzx   eax, [rsp+rdx*4+4C0h+pbmi.bmiColors.rgbRed]
0x180026a7d  movzx   ecx, [rsp+rdx*4+4C0h+pbmi.bmiColors.rgbGreen]
0x180026a82  shl     ecx, 8
0x180026a85  or      ecx, eax
0x180026a87  movzx   eax, [rsp+rdx*4+4C0h+pbmi.bmiColors.rgbBlue]
0x180026a8c  shl     eax, 10h
0x180026a8f  or      ecx, eax
0x180026a91  mov     dword ptr [rsp+rdx*4+4C0h+pbmi.bmiColors.rgbBlue], ecx
0x180026a95  cmp     r8d, [rsp+4C0h+pbmi.bmiHeader.biClrUsed]
0x180026a9a  jl      short loc_180026A72
0x180026a9c  mov     [rsp+4C0h+offset], r11d; offset
0x180026aa1  lea     r9, [rsp+4C0h+hPal]; ppvBits
0x180026aa6  xor     r8d, r8d; usage
0x180026aa9  mov     [rsp+4C0h+hSection], r11; hSection
0x180026aae  lea     rdx, [rsp+4C0h+pbmi]; pbmi
0x180026ab3  mov     [rsp+4C0h+hPal], r11
0x180026ab8  mov     rcx, rsi; hdc
0x180026abb  call    cs:__imp_CreateDIBSection
0x180026ac1  mov     [r13+0], rax
0x180026ac5  test    rax, rax
0x180026ac8  jz      loc_180026B6A
0x180026ace  test    r15, r15
0x180026ad1  jz      loc_180026B5C
0x180026ad7  mov     edx, 428h; uBytes
0x180026adc  mov     ecx, 40h ; '@'; uFlags
0x180026ae1  call    cs:__imp_LocalAlloc
0x180026ae7  mov     [r15], rax
0x180026aea  mov     rcx, rax
0x180026aed  test    rax, rax
0x180026af0  jz      short loc_180026B5C
0x180026af2  lea     rax, [rsp+4C0h+pbmi]
0x180026af7  mov     edx, 80h
0x180026afc  movups  xmm0, xmmword ptr [rax]
0x180026aff  movups  xmmword ptr [rcx], xmm0
0x180026b02  movups  xmm1, xmmword ptr [rax+10h]
0x180026b06  movups  xmmword ptr [rcx+10h], xmm1
0x180026b0a  movups  xmm0, xmmword ptr [rax+20h]
0x180026b0e  movups  xmmword ptr [rcx+20h], xmm0
0x180026b12  movups  xmm1, xmmword ptr [rax+30h]
0x180026b16  movups  xmmword ptr [rcx+30h], xmm1
0x180026b1a  movups  xmm0, xmmword ptr [rax+40h]
0x180026b1e  movups  xmmword ptr [rcx+40h], xmm0
0x180026b22  movups  xmm1, xmmword ptr [rax+50h]
0x180026b26  movups  xmmword ptr [rcx+50h], xmm1
0x180026b2a  movups  xmm0, xmmword ptr [rax+60h]
0x180026b2e  movups  xmmword ptr [rcx+60h], xmm0
0x180026b32  movups  xmm1, xmmword ptr [rax+70h]
0x180026b36  add     rax, rdx
0x180026b39  movups  xmmword ptr [rcx+70h], xmm1
0x180026b3d  add     rcx, rdx
0x180026b40  sub     r14, 1
0x180026b44  jnz     short loc_180026AFC
0x180026b46  movups  xmm0, xmmword ptr [rax]
0x180026b49  movups  xmmword ptr [rcx], xmm0
0x180026b4c  movups  xmm1, xmmword ptr [rax+10h]
0x180026b50  movups  xmmword ptr [rcx+10h], xmm1
0x180026b54  mov     rax, [rax+20h]
0x180026b58  mov     [rcx+20h], rax
0x180026b5c  test    r12, r12
0x180026b5f  jz      short loc_180026B6A
0x180026b61  mov     rax, [rsp+4C0h+hPal]
0x180026b66  mov     [r12], rax
0x180026b6a  mov     rcx, rsi; hdc
0x180026b6d  call    cs:__imp_DeleteDC
0x180026b73  mov     rdx, [rsp+4C0h+hDC]; hDC
0x180026b78  xor     ecx, ecx; hWnd
0x180026b7a  call    cs:__imp_ReleaseDC
0x180026b80  xor     eax, eax
0x180026b82  cmp     [r13+0], rax
0x180026b86  setnz   al
0x180026b89  mov     rcx, [rbp+3C0h+var_50]
0x180026b90  xor     rcx, rsp; StackCookie
0x180026b93  call    __security_check_cookie
0x180026b98  add     rsp, 488h
0x180026b9f  pop     r15
0x180026ba1  pop     r14
0x180026ba3  pop     r13
0x180026ba5  pop     r12
0x180026ba7  pop     rdi
0x180026ba8  pop     rsi
0x180026ba9  pop     rbx
0x180026baa  pop     rbp
0x180026bab  retn
```
