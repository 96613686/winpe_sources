# FactorAspectRatio

- ea: `0x180026bc0`
- end: `0x180026fa7`
- name: `FactorAspectRatio`
- size: `999`
- prototype: `__int64 __usercall@<rax>(BITMAPINFO *lpbmi@<rcx>, int, HPALETTE hPal, int, COLORREF color, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800266a0`

## callees

- `0x180010a64`
- `0x180021ea0`
- `0x1800268f0`
- `0x180026bc0`
- `0x1800369c5`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f86`
- `GDI32!DeleteDC` at `0x180026f69`
- `GDI32!DeleteDC` at `0x180026f69`
- `GDI32!StretchDIBits` at `0x180026f0c`
- `GDI32!StretchDIBits` at `0x180026f0c`
- `GDI32!Rectangle` at `0x180026e91`
- `GDI32!Rectangle` at `0x180026e91`
- `GDI32!RealizePalette` at `0x180026e67`
- `GDI32!RealizePalette` at `0x180026f54`
- `GDI32!RealizePalette` at `0x180026e67`
- `GDI32!RealizePalette` at `0x180026f54`
- `GDI32!SelectPalette` at `0x180026e5b`
- `GDI32!SelectPalette` at `0x180026f4b`
- `GDI32!SelectPalette` at `0x180026e5b`
- `GDI32!SelectPalette` at `0x180026f4b`
- `GDI32!GetStockObject` at `0x180026e1f`
- `GDI32!GetStockObject` at `0x180026e1f`
- `GDI32!CreateSolidBrush` at `0x180026e11`
- `GDI32!CreateSolidBrush` at `0x180026e11`
- `GDI32!SetStretchBltMode` at `0x180026e08`
- `GDI32!SetStretchBltMode` at `0x180026e08`
- `GDI32!CreateCompatibleDC` at `0x180026be9`
- `GDI32!CreateCompatibleDC` at `0x180026be9`
- `GDI32!DeleteObject` at `0x180026f25`
- `GDI32!DeleteObject` at `0x180026f78`
- `GDI32!DeleteObject` at `0x180026f25`
- `GDI32!DeleteObject` at `0x180026f78`
- `GDI32!SetMapMode` at `0x180026e75`
- `GDI32!SetMapMode` at `0x180026e75`
- `GDI32!SelectObject` at `0x180026df7`
- `GDI32!SelectObject` at `0x180026e2e`
- `GDI32!SelectObject` at `0x180026e3e`
- `GDI32!SelectObject` at `0x180026f1c`
- `GDI32!SelectObject` at `0x180026f32`
- `GDI32!SelectObject` at `0x180026f60`
- `GDI32!SelectObject` at `0x180026df7`
- `GDI32!SelectObject` at `0x180026e2e`
- `GDI32!SelectObject` at `0x180026e3e`
- `GDI32!SelectObject` at `0x180026f1c`
- `GDI32!SelectObject` at `0x180026f32`
- `GDI32!SelectObject` at `0x180026f60`

## pseudocode

```c
_BOOL8 __fastcall FactorAspectRatio(
        BITMAPINFO *lpbmi,
        unsigned __int8 *a2,
        int *a3,
        int *a4,
        int a5,
        HPALETTE hPal,
        int a7,
        COLORREF color,
        HGDIOBJ *a9)
{
  BITMAPINFO *v10; // r14
  HDC CompatibleDC; // rdi
  WORD biBitCount; // ax
  LONG biWidth; // r15d
  int v14; // ebx
  struct _GUID v15; // xmm0
  bool v16; // zf
  LONG v18; // eax
  int SizedDIBSECTION; // eax
  int v20; // r12d
  HGDIOBJ v21; // r15
  HBRUSH SolidBrush; // r12
  HGDIOBJ StockObject; // rbx
  HGDIOBJ v24; // rax
  HPALETTE v25; // rbx
  int v26; // r8d
  int v27; // ecx
  int biHeight; // eax
  int ySrc; // edx
  struct ERRBUF *SrcWidth; // [rsp+40h] [rbp-71h]
  int SrcHeight; // [rsp+48h] [rbp-69h]
  int lpBits; // [rsp+50h] [rbp-61h]
  int v33; // [rsp+68h] [rbp-49h]
  int v34; // [rsp+70h] [rbp-41h]
  unsigned int v35; // [rsp+78h] [rbp-39h] BYREF
  int v36; // [rsp+7Ch] [rbp-35h]
  unsigned __int8 *v37; // [rsp+80h] [rbp-31h] BYREF
  HGDIOBJ v38; // [rsp+88h] [rbp-29h] BYREF
  HGDIOBJ h; // [rsp+90h] [rbp-21h]
  BITMAPINFO *v40; // [rsp+98h] [rbp-19h]
  HGDIOBJ ho; // [rsp+A0h] [rbp-11h] BYREF
  struct _GUID Buf1[4]; // [rsp+A8h] [rbp-9h] BYREF
  int v43; // [rsp+F8h] [rbp+47h]

  v10 = 0;
  v43 = -1;
  v38 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v37 = 0;
  ho = 0;
  if ( CompatibleDC )
  {
    v40 = lpbmi;
    if ( a5 != 8 )
    {
LABEL_30:
      if ( (unsigned int)CreateSizedDIBSECTION((_DWORD)a3, a5, (_DWORD)hPal, 0, (__int64)a9, 0, 0) )
      {
        v21 = SelectObject(CompatibleDC, *a9);
        SetStretchBltMode(CompatibleDC, 3);
        SolidBrush = CreateSolidBrush(color);
        StockObject = GetStockObject(6);
        h = SelectObject(CompatibleDC, SolidBrush);
        v24 = SelectObject(CompatibleDC, StockObject);
        v25 = 0;
        v38 = v24;
        if ( hPal )
        {
          v25 = SelectPalette(CompatibleDC, hPal, 1);
          RealizePalette(CompatibleDC);
        }
        SetMapMode(CompatibleDC, 1);
        Rectangle(CompatibleDC, 0, 0, *a3, a3[1]);
        v26 = a4[3];
        v27 = v26 - a4[1];
        biHeight = v40->bmiHeader.biHeight;
        if ( biHeight >= 0 )
        {
          v26 = a4[1];
          ySrc = 0;
        }
        else
        {
          v27 = a4[1] - a4[3];
          ySrc = -biHeight;
        }
        v43 = StretchDIBits(
                CompatibleDC,
                *a4,
                v26,
                a4[2] - *a4,
                v27,
                0,
                ySrc,
                v40->bmiHeader.biWidth,
                biHeight,
                a2,
                lpbmi,
                0,
                0xCC0020u);
        SelectObject(CompatibleDC, h);
        DeleteObject(SolidBrush);
        SelectObject(CompatibleDC, v38);
        if ( hPal )
        {
          SelectPalette(CompatibleDC, v25, 1);
          RealizePalette(CompatibleDC);
        }
        SelectObject(CompatibleDC, v21);
      }
      DeleteDC(CompatibleDC);
      if ( ho )
        DeleteObject(ho);
      if ( v10 )
        LocalFree(v10);
      return v43 != -1;
    }
    biBitCount = lpbmi->bmiHeader.biBitCount;
    biWidth = lpbmi->bmiHeader.biWidth;
    v14 = biWidth;
    Buf1[0] = GUID_NULL;
    if ( biBitCount == 8 )
    {
      v15 = (struct _GUID)xmmword_1800477D0;
      h = lpbmi->bmiColors;
    }
    else
    {
      h = 0;
      switch ( biBitCount )
      {
        case 0x10u:
          v16 = lpbmi->bmiHeader.biCompression == 3;
          Buf1[0] = (struct _GUID)xmmword_1800477F0;
          if ( v16 && BYTE1(lpbmi[1].bmiHeader.biSize) == 126 )
            Buf1[0] = (struct _GUID)xmmword_1800477C0;
          v14 = 2 * biWidth;
LABEL_15:
          if ( v14 % 4 )
            v14 += 4 - v14 % 4;
          if ( biWidth % 4 )
            biWidth = biWidth - biWidth % 4 + 4;
          if ( memcmp_0(Buf1, &GUID_NULL, 0x10u) )
          {
            if ( !*(_QWORD *)&g_pbCMAP && SHGetInverseCMAP(&g_pbCMAP, 8u) < 0 )
              return 0;
            v35 = lpbmi->bmiHeader.biWidth;
            v18 = lpbmi->bmiHeader.biHeight;
            v36 = v18;
            if ( v18 < 0 )
              v36 = -v18;
            SizedDIBSECTION = CreateSizedDIBSECTION(
                                (unsigned int)&v35,
                                8,
                                (_DWORD)hPal,
                                0,
                                (__int64)&ho,
                                (__int64)&v38,
                                (__int64)&v37);
            v10 = (BITMAPINFO *)v38;
            if ( SizedDIBSECTION )
            {
              v20 = v36;
              if ( (int)DitherTo8(
                          v37,
                          biWidth,
                          a2,
                          v14,
                          Buf1,
                          (struct tagRGBQUAD *)v38 + 10,
                          (struct tagRGBQUAD *)h,
                          SrcWidth,
                          SrcHeight,
                          lpBits,
                          v35,
                          v36,
                          v33,
                          v34) >= 0 )
              {
                if ( v20 != lpbmi->bmiHeader.biHeight )
                  v10->bmiHeader.biHeight = -v20;
                lpbmi = v10;
                a2 = v37;
              }
            }
          }
          goto LABEL_30;
        case 0x18u:
          v15 = (struct _GUID)xmmword_1800477E0;
          v14 = 3 * biWidth;
          break;
        case 0x20u:
          v15 = (struct _GUID)xmmword_180047800;
          v14 = 4 * biWidth;
          break;
        default:
          goto LABEL_15;
      }
    }
    Buf1[0] = v15;
    goto LABEL_15;
  }
  return v43 != -1;
}

```

## disassembly

```asm
0x180026bc0  mov     rax, rsp
0x180026bc3  mov     [rax+20h], r9
0x180026bc7  mov     [rax+18h], r8
0x180026bcb  mov     [rax+10h], rdx
0x180026bcf  push    rbp
0x180026bd0  push    rbx
0x180026bd1  push    rsi
0x180026bd2  push    rdi
0x180026bd3  push    r12
0x180026bd5  push    r14
0x180026bd7  push    r15
0x180026bd9  lea     rbp, [rax-3Fh]
0x180026bdd  sub     rsp, 0B0h
0x180026be4  mov     rsi, rcx
0x180026be7  xor     ecx, ecx; hdc
0x180026be9  call    cs:__imp_CreateCompatibleDC
0x180026bef  xor     r14d, r14d
0x180026bf2  mov     [rbp+37h+arg_0], 0FFFFFFFFh
0x180026bf9  mov     [rbp+37h+var_60], r14
0x180026bfd  mov     rdi, rax
0x180026c00  mov     [rbp+37h+var_68], r14
0x180026c04  mov     [rbp+37h+ho], r14
0x180026c08  test    rax, rax
0x180026c0b  jz      loc_180026F8C
0x180026c11  lea     r12d, [r14+8]
0x180026c15  mov     [rbp+37h+var_50], rsi
0x180026c19  cmp     [rbp+37h+arg_20], r12d
0x180026c1d  jnz     loc_180026DB8
0x180026c23  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180026c2a  movzx   eax, word ptr [rsi+0Eh]
0x180026c2e  lea     r8d, [r14+10h]; Size
0x180026c32  mov     r15d, [rsi+4]
0x180026c36  mov     ebx, r15d
0x180026c39  movdqu  [rbp+37h+Buf1], xmm0
0x180026c3e  cmp     ax, r12w
0x180026c42  jz      short loc_180026CA0
0x180026c44  mov     [rbp+37h+h], r14
0x180026c48  cmp     ax, r8w
0x180026c4c  jz      short loc_180026C78
0x180026c4e  cmp     ax, 18h
0x180026c52  jz      short loc_180026C6B
0x180026c54  cmp     ax, 20h ; ' '
0x180026c58  jnz     short loc_180026CB4
0x180026c5a  movups  xmm0, cs:xmmword_180047800
0x180026c61  lea     ebx, ds:0[r15*4]
0x180026c69  jmp     short loc_180026CAF
0x180026c6b  movups  xmm0, cs:xmmword_1800477E0
0x180026c72  lea     ebx, [r15+r15*2]
0x180026c76  jmp     short loc_180026CAF
0x180026c78  cmp     dword ptr [rsi+10h], 3
0x180026c7c  movups  xmm0, cs:xmmword_1800477F0
0x180026c83  movdqu  [rbp+37h+Buf1], xmm0
0x180026c88  jnz     short loc_180026C9C
0x180026c8a  cmp     byte ptr [rsi+2Dh], 7Eh ; '~'
0x180026c8e  jnz     short loc_180026C9C
0x180026c90  movups  xmm0, cs:xmmword_1800477C0
0x180026c97  movdqu  [rbp+37h+Buf1], xmm0
0x180026c9c  add     ebx, ebx
0x180026c9e  jmp     short loc_180026CB4
0x180026ca0  movups  xmm0, cs:xmmword_1800477D0
0x180026ca7  lea     rax, [rsi+28h]
0x180026cab  mov     [rbp+37h+h], rax
0x180026caf  movdqu  [rbp+37h+Buf1], xmm0
0x180026cb4  mov     eax, ebx
0x180026cb6  mov     ecx, 4
0x180026cbb  cdq
0x180026cbc  idiv    ecx
0x180026cbe  test    edx, edx
0x180026cc0  jz      short loc_180026CC8
0x180026cc2  mov     eax, ecx
0x180026cc4  sub     eax, edx
0x180026cc6  add     ebx, eax
0x180026cc8  mov     eax, r15d
0x180026ccb  cdq
0x180026ccc  idiv    ecx
0x180026cce  test    edx, edx
0x180026cd0  jz      short loc_180026CD8
0x180026cd2  sub     r15d, edx
0x180026cd5  add     r15d, ecx
0x180026cd8  lea     rdx, GUID_NULL; Buf2
0x180026cdf  lea     rcx, [rbp+37h+Buf1]; Buf1
0x180026ce3  call    memcmp_0
0x180026ce8  test    eax, eax
0x180026cea  jz      loc_180026DB8
0x180026cf0  cmp     cs:?g_pbCMAP@@3PEAEEA, r14; uchar * g_pbCMAP
0x180026cf7  jnz     short loc_180026D13
0x180026cf9  mov     edx, r12d; cbMap
0x180026cfc  lea     rcx, ?g_pbCMAP@@3PEAEEA; pbMap
0x180026d03  call    SHGetInverseCMAP
0x180026d08  test    eax, eax
0x180026d0a  jns     short loc_180026D13
0x180026d0c  xor     eax, eax
0x180026d0e  jmp     loc_180026F95
0x180026d13  mov     eax, [rsi+4]
0x180026d16  mov     [rbp+37h+var_70], eax
0x180026d19  mov     eax, [rsi+8]
0x180026d1c  mov     [rbp+37h+var_6C], eax
0x180026d1f  test    eax, eax
0x180026d21  jns     short loc_180026D28
0x180026d23  neg     eax
0x180026d25  mov     [rbp+37h+var_6C], eax
0x180026d28  mov     r8, [rbp+37h+hPal]
0x180026d2c  lea     rax, [rbp+37h+var_68]
0x180026d30  mov     qword ptr [rsp+0E0h+ySrc], rax
0x180026d35  lea     rcx, [rbp+37h+var_70]
0x180026d39  lea     rax, [rbp+37h+var_60]
0x180026d3d  xor     r9d, r9d
0x180026d40  mov     qword ptr [rsp+0E0h+xSrc], rax
0x180026d45  mov     edx, r12d
0x180026d48  lea     rax, [rbp+37h+ho]
0x180026d4c  mov     qword ptr [rsp+0E0h+bottom], rax
0x180026d51  call    CreateSizedDIBSECTION
0x180026d56  mov     r14, [rbp+37h+var_60]
0x180026d5a  test    eax, eax
0x180026d5c  jz      short loc_180026DB8
0x180026d5e  mov     eax, [rbp+37h+var_70]
0x180026d61  lea     rcx, [r14+28h]
0x180026d65  mov     r12d, [rbp+37h+var_6C]
0x180026d69  mov     r9d, ebx; int
0x180026d6c  mov     r8, [rbp+37h+arg_8]; unsigned __int8 *
0x180026d70  mov     edx, r15d; int
0x180026d73  mov     [rsp+0E0h+iUsage], r12d; int
0x180026d78  mov     dword ptr [rsp+0E0h+lpbmi], eax; unsigned int
0x180026d7c  mov     rax, [rbp+37h+h]
0x180026d80  mov     qword ptr [rsp+0E0h+ySrc], rax; struct tagRGBQUAD *
0x180026d85  lea     rax, [rbp+37h+Buf1]
0x180026d89  mov     qword ptr [rsp+0E0h+xSrc], rcx; struct tagRGBQUAD *
0x180026d8e  mov     rcx, [rbp+37h+var_68]; unsigned __int8 *
0x180026d92  mov     qword ptr [rsp+0E0h+bottom], rax; Buf1
0x180026d97  call    ?DitherTo8@@YAJPEAEJ0JAEBU_GUID@@PEAUtagRGBQUAD@@2PEBEJJJJJJ@Z; DitherTo8(uchar *,long,uchar *,long,_GUID const &,tagRGBQUAD *,tagRGBQUAD *,uchar const *,long,long,long,long,long,long)
0x180026d9c  test    eax, eax
0x180026d9e  js      short loc_180026DB8
0x180026da0  cmp     r12d, [rsi+8]
0x180026da4  jz      short loc_180026DAD
0x180026da6  neg     r12d
0x180026da9  mov     [r14+8], r12d
0x180026dad  mov     rax, [rbp+37h+var_68]
0x180026db1  mov     rsi, r14
0x180026db4  mov     [rbp+37h+arg_8], rax
0x180026db8  mov     rbx, [rbp+37h+arg_40]
0x180026dbf  xor     r9d, r9d
0x180026dc2  mov     r8, [rbp+37h+hPal]
0x180026dc6  mov     edx, [rbp+37h+arg_20]
0x180026dc9  mov     rcx, [rbp+37h+arg_10]
0x180026dcd  mov     qword ptr [rsp+0E0h+ySrc], 0
0x180026dd6  mov     qword ptr [rsp+0E0h+xSrc], 0
0x180026ddf  mov     qword ptr [rsp+0E0h+bottom], rbx
0x180026de4  call    CreateSizedDIBSECTION
0x180026de9  test    eax, eax
0x180026deb  jz      loc_180026F66
0x180026df1  mov     rdx, [rbx]; h
0x180026df4  mov     rcx, rdi; hdc
0x180026df7  call    cs:__imp_SelectObject
0x180026dfd  mov     edx, 3; mode
0x180026e02  mov     rcx, rdi; hdc
0x180026e05  mov     r15, rax
0x180026e08  call    cs:__imp_SetStretchBltMode
0x180026e0e  mov     ecx, [rbp+37h+color]; color
0x180026e11  call    cs:__imp_CreateSolidBrush
0x180026e17  mov     ecx, 6; i
0x180026e1c  mov     r12, rax
0x180026e1f  call    cs:__imp_GetStockObject
0x180026e25  mov     rdx, r12; h
0x180026e28  mov     rcx, rdi; hdc
0x180026e2b  mov     rbx, rax
0x180026e2e  call    cs:__imp_SelectObject
0x180026e34  mov     rdx, rbx; h
0x180026e37  mov     rcx, rdi; hdc
0x180026e3a  mov     [rbp+37h+h], rax
0x180026e3e  call    cs:__imp_SelectObject
0x180026e44  xor     ebx, ebx
0x180026e46  mov     [rbp+37h+var_60], rax
0x180026e4a  cmp     [rbp+37h+hPal], rbx
0x180026e4e  jz      short loc_180026E6D
0x180026e50  mov     rdx, [rbp+37h+hPal]; hPal
0x180026e54  lea     r8d, [rbx+1]; bForceBkgd
0x180026e58  mov     rcx, rdi; hdc
0x180026e5b  call    cs:__imp_SelectPalette
0x180026e61  mov     rcx, rdi; hdc
0x180026e64  mov     rbx, rax
0x180026e67  call    cs:__imp_RealizePalette
0x180026e6d  mov     edx, 1; iMode
0x180026e72  mov     rcx, rdi; hdc
0x180026e75  call    cs:__imp_SetMapMode
0x180026e7b  mov     rax, [rbp+37h+arg_10]
0x180026e7f  xor     r8d, r8d; top
0x180026e82  xor     edx, edx; left
0x180026e84  mov     ecx, [rax+4]
0x180026e87  mov     r9d, [rax]; right
0x180026e8a  mov     [rsp+0E0h+bottom], ecx; bottom
0x180026e8e  mov     rcx, rdi; hdc
0x180026e91  call    cs:__imp_Rectangle
0x180026e97  mov     r11, [rbp+37h+arg_18]
0x180026e9b  mov     rax, [rbp+37h+var_50]
0x180026e9f  mov     r8d, [r11+0Ch]
0x180026ea3  mov     ecx, r8d
0x180026ea6  sub     ecx, [r11+4]
0x180026eaa  mov     eax, [rax+8]
0x180026ead  test    eax, eax
0x180026eaf  jns     short loc_180026EBC
0x180026eb1  neg     ecx
0x180026eb3  mov     edx, eax
0x180026eb5  neg     edx
0x180026eb7  cmovs   edx, eax
0x180026eba  jmp     short loc_180026EC2
0x180026ebc  mov     r8d, [r11+4]; yDest
0x180026ec0  xor     edx, edx
0x180026ec2  mov     r10, [rbp+37h+arg_8]
0x180026ec6  mov     r9d, [r11+8]
0x180026eca  sub     r9d, [r11]; DestWidth
0x180026ecd  mov     dword ptr [rsp+60h], 0CC0020h; rop
0x180026ed5  mov     [rsp+0E0h+iUsage], 0; iUsage
0x180026edd  mov     [rsp+0E0h+lpbmi], rsi; lpbmi
0x180026ee2  mov     [rsp+0E0h+lpBits], r10; lpBits
0x180026ee7  mov     [rsp+0E0h+SrcHeight], eax; SrcHeight
0x180026eeb  mov     rax, [rbp+37h+var_50]
0x180026eef  mov     eax, [rax+4]
0x180026ef2  mov     dword ptr [rsp+0E0h+SrcWidth], eax; SrcWidth
0x180026ef6  mov     [rsp+0E0h+ySrc], edx; ySrc
0x180026efa  mov     edx, [r11]; xDest
0x180026efd  mov     [rsp+0E0h+xSrc], 0; xSrc
0x180026f05  mov     [rsp+0E0h+bottom], ecx; DestHeight
0x180026f09  mov     rcx, rdi; hdc
0x180026f0c  call    cs:__imp_StretchDIBits
0x180026f12  mov     rdx, [rbp+37h+h]; h
0x180026f16  mov     rcx, rdi; hdc
0x180026f19  mov     [rbp+37h+arg_0], eax
0x180026f1c  call    cs:__imp_SelectObject
0x180026f22  mov     rcx, r12; ho
0x180026f25  call    cs:__imp_DeleteObject
0x180026f2b  mov     rdx, [rbp+37h+var_60]; h
0x180026f2f  mov     rcx, rdi; hdc
0x180026f32  call    cs:__imp_SelectObject
0x180026f38  cmp     [rbp+37h+hPal], 0
0x180026f3d  jz      short loc_180026F5A
0x180026f3f  mov     r8d, 1; bForceBkgd
0x180026f45  mov     rdx, rbx; hPal
0x180026f48  mov     rcx, rdi; hdc
0x180026f4b  call    cs:__imp_SelectPalette
0x180026f51  mov     rcx, rdi; hdc
0x180026f54  call    cs:__imp_RealizePalette
0x180026f5a  mov     rdx, r15; h
0x180026f5d  mov     rcx, rdi; hdc
0x180026f60  call    cs:__imp_SelectObject
0x180026f66  mov     rcx, rdi; hdc
0x180026f69  call    cs:__imp_DeleteDC
0x180026f6f  mov     rcx, [rbp+37h+ho]; ho
0x180026f73  test    rcx, rcx
0x180026f76  jz      short loc_180026F7E
0x180026f78  call    cs:__imp_DeleteObject
0x180026f7e  test    r14, r14
0x180026f81  jz      short loc_180026F8C
0x180026f83  mov     rcx, r14; hMem
0x180026f86  call    cs:__imp_LocalFree
0x180026f8c  xor     eax, eax
0x180026f8e  cmp     [rbp+37h+arg_0], 0FFFFFFFFh
0x180026f92  setnz   al
0x180026f95  add     rsp, 0B0h
0x180026f9c  pop     r15
0x180026f9e  pop     r14
0x180026fa0  pop     r12
0x180026fa2  pop     rdi
0x180026fa3  pop     rsi
0x180026fa4  pop     rbx
0x180026fa5  pop     rbp
0x180026fa6  retn
```
