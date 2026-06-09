# SimulateDocIcon(IImageList2 *,HICON__ *,int,int)

- ea: `0x1805b7f14`
- end: `0x1805b846b`
- name: `?SimulateDocIcon@@YAPEAUHICON__@@PEAUIImageList2@@PEAU1@HH@Z`
- size: `1367`
- prototype: `HICON(struct IImageList2 *, HICON, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180148ba0`

## callees

- `0x180093b10`
- `0x180249e34`
- `0x1802e47e8`
- `0x1803b1f60`
- `0x1805b7ba4`
- `0x1805b7f14`
- `0x18067d010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1805b839e`
- `GDI32!DeleteObject` at `0x1805b8417`
- `GDI32!DeleteObject` at `0x1805b8426`
- `GDI32!DeleteObject` at `0x1805b839e`
- `GDI32!DeleteObject` at `0x1805b8417`
- `GDI32!DeleteObject` at `0x1805b8426`
- `GDI32!SelectObject` at `0x1805b8045`
- `GDI32!SelectObject` at `0x1805b80b6`
- `GDI32!SelectObject` at `0x1805b82ad`
- `GDI32!SelectObject` at `0x1805b838e`
- `GDI32!SelectObject` at `0x1805b83c4`
- `GDI32!SelectObject` at `0x1805b8045`
- `GDI32!SelectObject` at `0x1805b80b6`
- `GDI32!SelectObject` at `0x1805b82ad`
- `GDI32!SelectObject` at `0x1805b838e`
- `GDI32!SelectObject` at `0x1805b83c4`
- `GDI32!CreateCompatibleDC` at `0x1805b8026`
- `GDI32!CreateCompatibleDC` at `0x1805b8248`
- `GDI32!CreateCompatibleDC` at `0x1805b8026`
- `GDI32!CreateCompatibleDC` at `0x1805b8248`
- `GDI32!CreateBitmap` at `0x1805b800a`
- `GDI32!CreateBitmap` at `0x1805b800a`
- `GDI32!CreateCompatibleBitmap` at `0x1805b7fd8`
- `GDI32!CreateCompatibleBitmap` at `0x1805b7fd8`
- `GDI32!BitBlt` at `0x1805b8378`
- `GDI32!BitBlt` at `0x1805b8378`
- `GDI32!DeleteDC` at `0x1805b83b1`
- `GDI32!DeleteDC` at `0x1805b83d3`
- `GDI32!DeleteDC` at `0x1805b83b1`
- `GDI32!DeleteDC` at `0x1805b83d3`
- `GDI32!GetDeviceCaps` at `0x1805b7f99`
- `GDI32!GetDeviceCaps` at `0x1805b7f99`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetCurColorRes` at `0x1805b811d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetCurColorRes` at `0x1805b811d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x1805b82e4`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHFillRectClr` at `0x1805b82e4`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x1805b8192`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x1805b8329`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x1805b8192`
- `ext-ms-win-ntuser-gui-l1-1-0!DrawIconEx` at `0x1805b8329`
- `ext-ms-win-ntuser-gui-l1-3-0!CreateIconIndirect` at `0x1805b8405`
- `ext-ms-win-ntuser-gui-l1-3-0!CreateIconIndirect` at `0x1805b8405`
- `USER32!ReleaseDC` at `0x1805b8437`
- `USER32!ReleaseDC` at `0x1805b8437`
- `USER32!GetDC` at `0x1805b7f76`
- `USER32!GetDC` at `0x1805b7f76`

## pseudocode

```c
HICON __fastcall SimulateDocIcon(struct IImageList2 *a1, HICON a2, unsigned int a3, unsigned int a4)
{
  __int64 v4; // r12
  __int64 v5; // r15
  HICON v6; // rsi
  HDC DC; // rax
  HDC v9; // r13
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v11; // rdi
  HDC CompatibleDC; // rax
  HDC v13; // r14
  unsigned int StockImageIndex; // ecx
  void (__fastcall *v15)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, int); // rax
  void (__fastcall *v16)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, int, _DWORD); // rax
  __int64 v17; // rcx
  HICON v18; // r9
  unsigned int v19; // ebx
  unsigned int v20; // esi
  unsigned int v21; // r9d
  unsigned int v22; // ecx
  struct tagRGBQUAD *v23; // r11
  unsigned int v24; // edx
  unsigned int v25; // r12d
  unsigned int v26; // r10d
  unsigned int v27; // r9d
  unsigned int v28; // edx
  __int64 v29; // rax
  HDC v30; // rbx
  HBITMAP v31; // rax
  HGDIOBJ v32; // rax
  void *v33; // rsi
  HGDIOBJ v34; // rbx
  unsigned int cyWidth; // [rsp+60h] [rbp-69h] BYREF
  int xLeft; // [rsp+64h] [rbp-65h]
  HDC hdc; // [rsp+68h] [rbp-61h]
  HBITMAP v39; // [rsp+70h] [rbp-59h]
  HGDIOBJ h; // [rsp+78h] [rbp-51h]
  HICON hIcon; // [rsp+80h] [rbp-49h]
  HGDIOBJ ho; // [rsp+88h] [rbp-41h]
  HGDIOBJ v43; // [rsp+90h] [rbp-39h]
  struct tagRGBQUAD *ppvBits; // [rsp+98h] [rbp-31h] BYREF
  ICONINFO piconinfo; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v46; // [rsp+C0h] [rbp-9h] BYREF
  int v47; // [rsp+C8h] [rbp-1h]
  unsigned int v48; // [rsp+CCh] [rbp+3h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  hIcon = a2;
  if ( !a2 || ((int (__fastcall *)(struct IImageList2 *, _QWORD, _QWORD))a1->lpVtbl->Resize)(a1, a3, a4) < 0 )
    return 0;
  DC = GetDC(0);
  v9 = DC;
  if ( DC )
  {
    ppvBits = 0;
    if ( GetDeviceCaps(DC, 12) < 24 )
    {
      cyWidth = 0;
      CompatibleBitmap = CreateCompatibleBitmap(v9, v5, v4);
    }
    else
    {
      cyWidth = 1;
      CompatibleBitmap = DIBSectionUtil::Create(v9, 0x20u, v5, v4, &ppvBits);
    }
    v39 = CompatibleBitmap;
    v11 = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      h = CreateBitmap(v5, v4, 1u, 1u, 0);
      if ( h )
      {
        CompatibleDC = CreateCompatibleDC(v9);
        v13 = CompatibleDC;
        if ( CompatibleDC )
        {
          v43 = SelectObject(CompatibleDC, h);
          StockImageIndex = Shell_GetStockImageIndex(SIID_DOCNOASSOC);
          xLeft = StockImageIndex;
          v15 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, int))qword_1808266D8;
          if ( qword_1808266D8 == -1 )
          {
            GetProcFromComCtl32(&qword_1808266D8, "ImageList_Draw");
            v15 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, int))qword_1808266D8;
            StockImageIndex = xLeft;
          }
          if ( v15 )
            v15(a1, StockImageIndex, v13, 0, 0, 16);
          SelectObject(v13, v11);
          v16 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, int, _DWORD))qword_1808266E0;
          if ( qword_1808266E0 == -1 )
          {
            GetProcFromComCtl32(&qword_1808266E0, "ImageList_DrawEx");
            v16 = (void (__fastcall *)(struct IImageList2 *, _QWORD, HDC, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, int, _DWORD))qword_1808266E0;
          }
          v17 = 0;
          if ( v16 )
            v16(a1, (unsigned int)xLeft, v13, 0, 0, 0, 0, 0, -16777216, 0);
          if ( (unsigned int)SHGetCurColorRes(v17) <= 8 )
          {
            hdc = CreateCompatibleDC(v13);
            v30 = hdc;
            if ( hdc )
            {
              cyWidth = (int)v4 / 2;
              xLeft = (int)v5 / 2;
              v31 = DIBSectionUtil::Create(v9, 0x18u, (int)v5 / 2 + 2, (int)v4 / 2 + 2, 0);
              ho = v31;
              if ( v31 )
              {
                v32 = SelectObject(hdc, v31);
                v47 = xLeft + 3;
                v48 = cyWidth + 3;
                v33 = v32;
                v46 = 0;
                SHFillRectClr(hdc, &v46, 0xFFFFFF);
                DrawIconEx(hdc, 1, 1, hIcon, xLeft, cyWidth, 0, 0, 3u);
                BitBlt(v13, (int)v5 / 4 - 1, (int)v4 / 4 - 1, xLeft + 3, cyWidth + 3, hdc, 0, 0, 0xCC0020u);
                v30 = hdc;
                SelectObject(hdc, v33);
                DeleteObject(ho);
                v11 = v39;
              }
              DeleteDC(v30);
            }
          }
          else
          {
            v18 = v6;
            v19 = (int)v4 / 4;
            xLeft = (int)v5 / 4;
            v20 = (int)v5 / 4;
            LODWORD(v39) = (int)v4 / 2;
            LODWORD(hdc) = (int)v5 / 2;
            DrawIconEx(v13, (int)v5 / 4, (int)v4 / 4, v18, (int)v5 / 2, (int)v4 / 2, 0, 0, 3u);
            if ( cyWidth )
            {
              cyWidth = 0;
              if ( (int)ULongLongToULong(v5 * v4, &cyWidth) >= 0 )
              {
                v22 = v21;
                v23 = ppvBits;
                v24 = v21;
                if ( cyWidth )
                {
                  v25 = v21 + 1;
                  while ( !v22 )
                  {
                    if ( ppvBits[v24].rgbReserved != (_BYTE)v21 )
                      v22 = v21 + 1;
                    v24 += v25;
                    if ( v24 >= cyWidth )
                    {
                      if ( !v22 )
                        goto LABEL_39;
                      break;
                    }
                  }
                  v26 = v19 + (_DWORD)v39;
                  if ( v19 < v19 + (unsigned int)v39 )
                  {
                    v27 = v20 + (_DWORD)hdc;
                    do
                    {
                      if ( v20 < v27 )
                      {
                        v28 = (int)v5 / 4;
                        do
                        {
                          v29 = (_DWORD)v5 * v19 + v28;
                          v28 += v25;
                          v23[v29].rgbReserved = -1;
                        }
                        while ( v28 < v27 );
                      }
                      v19 += v25;
                    }
                    while ( v19 < v26 );
                  }
                }
              }
            }
          }
LABEL_39:
          SelectObject(v13, v43);
          DeleteDC(v13);
        }
        v34 = h;
        piconinfo.hbmMask = (HBITMAP)h;
        *(_QWORD *)&piconinfo.xHotspot = 0;
        *(&piconinfo.yHotspot + 1) = 0;
        piconinfo.fIcon = 1;
        piconinfo.hbmColor = v11;
        v6 = CreateIconIndirect(&piconinfo);
        DeleteObject(v34);
      }
      DeleteObject(v11);
    }
    ReleaseDC(0, v9);
  }
  return v6;
}

```

## disassembly

```asm
0x1805b7f14  push    rbp
0x1805b7f16  push    rbx
0x1805b7f17  push    rsi
0x1805b7f18  push    rdi
0x1805b7f19  push    r12
0x1805b7f1b  push    r13
0x1805b7f1d  push    r14
0x1805b7f1f  push    r15
0x1805b7f21  lea     rbp, [rsp-1Fh]
0x1805b7f26  sub     rsp, 0E8h
0x1805b7f2d  mov     rax, cs:__security_cookie
0x1805b7f34  xor     rax, rsp
0x1805b7f37  mov     [rbp+57h+var_50], rax
0x1805b7f3b  xor     r14d, r14d
0x1805b7f3e  mov     r12d, r9d
0x1805b7f41  mov     r15d, r8d
0x1805b7f44  mov     rsi, rdx
0x1805b7f47  mov     [rbp+57h+hIcon], rdx
0x1805b7f4b  mov     rbx, rcx
0x1805b7f4e  test    rdx, rdx
0x1805b7f51  jz      loc_1805B8448
0x1805b7f57  mov     rax, [rcx]
0x1805b7f5a  mov     r8d, r12d
0x1805b7f5d  mov     edx, r15d
0x1805b7f60  mov     rax, [rax+100h]
0x1805b7f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805b7f6c  test    eax, eax
0x1805b7f6e  js      loc_1805B8448
0x1805b7f74  xor     ecx, ecx; hWnd
0x1805b7f76  call    cs:__imp_GetDC
0x1805b7f7d  nop     dword ptr [rax+rax+00h]
0x1805b7f82  mov     r13, rax
0x1805b7f85  test    rax, rax
0x1805b7f88  jz      loc_1805B8443
0x1805b7f8e  lea     edx, [r14+0Ch]; index
0x1805b7f92  mov     [rbp+57h+ppvBits], r14
0x1805b7f96  mov     rcx, rax; hdc
0x1805b7f99  call    cs:__imp_GetDeviceCaps
0x1805b7fa0  nop     dword ptr [rax+rax+00h]
0x1805b7fa5  mov     rcx, r13; HDC
0x1805b7fa8  cmp     eax, 18h
0x1805b7fab  jl      short loc_1805B7FCE
0x1805b7fad  lea     rax, [rbp+57h+ppvBits]
0x1805b7fb1  mov     [rbp+57h+var_C0], 1
0x1805b7fb8  lea     edx, [r14+20h]; unsigned __int16
0x1805b7fbc  mov     [rsp+120h+lpBits], rax; ppvBits
0x1805b7fc1  mov     r9d, r12d; unsigned int
0x1805b7fc4  mov     r8d, r15d; unsigned int
0x1805b7fc7  call    ?Create@DIBSectionUtil@@SAPEAUHBITMAP__@@PEAUHDC__@@GIIPEAPEAUtagRGBQUAD@@@Z; DIBSectionUtil::Create(HDC__ *,ushort,uint,uint,tagRGBQUAD * *)
0x1805b7fcc  jmp     short loc_1805B7FE4
0x1805b7fce  mov     r8d, r12d; cy
0x1805b7fd1  mov     [rbp+57h+var_C0], r14d
0x1805b7fd5  mov     edx, r15d; cx
0x1805b7fd8  call    cs:__imp_CreateCompatibleBitmap
0x1805b7fdf  nop     dword ptr [rax+rax+00h]
0x1805b7fe4  mov     [rbp+57h+var_B0], rax
0x1805b7fe8  mov     rdi, rax
0x1805b7feb  test    rax, rax
0x1805b7fee  jz      loc_1805B8432
0x1805b7ff4  mov     eax, 1
0x1805b7ff9  mov     [rsp+120h+lpBits], r14; lpBits
0x1805b7ffe  mov     r9d, eax; nBitCount
0x1805b8001  mov     r8d, eax; nPlanes
0x1805b8004  mov     edx, r12d; nHeight
0x1805b8007  mov     ecx, r15d; nWidth
0x1805b800a  call    cs:__imp_CreateBitmap
0x1805b8011  nop     dword ptr [rax+rax+00h]
0x1805b8016  mov     [rbp+57h+h], rax
0x1805b801a  test    rax, rax
0x1805b801d  jz      loc_1805B8423
0x1805b8023  mov     rcx, r13; hdc
0x1805b8026  call    cs:__imp_CreateCompatibleDC
0x1805b802d  nop     dword ptr [rax+rax+00h]
0x1805b8032  mov     r14, rax
0x1805b8035  test    rax, rax
0x1805b8038  jz      loc_1805B83DF
0x1805b803e  mov     rdx, [rbp+57h+h]; h
0x1805b8042  mov     rcx, rax; hdc
0x1805b8045  call    cs:__imp_SelectObject
0x1805b804c  nop     dword ptr [rax+rax+00h]
0x1805b8051  xor     ecx, ecx; enum SHSTOCKICONID
0x1805b8053  mov     [rbp+57h+var_90], rax
0x1805b8057  call    ?Shell_GetStockImageIndex@@YAHW4SHSTOCKICONID@@@Z; Shell_GetStockImageIndex(SHSTOCKICONID)
0x1805b805c  mov     ecx, eax
0x1805b805e  mov     [rbp+57h+xLeft], eax
0x1805b8061  mov     rax, cs:qword_1808266D8
0x1805b8068  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805b806c  jnz     short loc_1805B808B
0x1805b806e  lea     rdx, aImagelistDraw; "ImageList_Draw"
0x1805b8075  lea     rcx, qword_1808266D8
0x1805b807c  call    _GetProcFromComCtl32
0x1805b8081  mov     rax, cs:qword_1808266D8
0x1805b8088  mov     ecx, [rbp+57h+xLeft]
0x1805b808b  test    rax, rax
0x1805b808e  jz      short loc_1805B80B0
0x1805b8090  mov     edx, ecx
0x1805b8092  mov     [rsp+120h+cyWidth], 10h
0x1805b809a  mov     rcx, rbx
0x1805b809d  mov     dword ptr [rsp+120h+lpBits], 0
0x1805b80a5  xor     r9d, r9d
0x1805b80a8  mov     r8, r14
0x1805b80ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805b80b0  mov     rdx, rdi; h
0x1805b80b3  mov     rcx, r14; hdc
0x1805b80b6  call    cs:__imp_SelectObject
0x1805b80bd  nop     dword ptr [rax+rax+00h]
0x1805b80c2  mov     rax, cs:qword_1808266E0
0x1805b80c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1805b80cd  jnz     short loc_1805B80E9
0x1805b80cf  lea     rdx, aImagelistDrawe; "ImageList_DrawEx"
0x1805b80d6  lea     rcx, qword_1808266E0
0x1805b80dd  call    _GetProcFromComCtl32
0x1805b80e2  mov     rax, cs:qword_1808266E0
0x1805b80e9  xor     ecx, ecx
0x1805b80eb  test    rax, rax
0x1805b80ee  jz      short loc_1805B811D
0x1805b80f0  mov     edx, [rbp+57h+xLeft]
0x1805b80f3  xor     r9d, r9d
0x1805b80f6  mov     [rsp+120h+var_D8], ecx
0x1805b80fa  mov     r8, r14
0x1805b80fd  mov     [rsp+120h+diFlags], 0FF000000h
0x1805b8105  mov     dword ptr [rsp+120h+hbrFlickerFreeDraw], ecx
0x1805b8109  mov     [rsp+120h+istepIfAniCur], ecx
0x1805b810d  mov     [rsp+120h+cyWidth], ecx
0x1805b8111  mov     dword ptr [rsp+120h+lpBits], ecx
0x1805b8115  mov     rcx, rbx
0x1805b8118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805b811d  call    cs:__imp_SHGetCurColorRes
0x1805b8124  nop     dword ptr [rax+rax+00h]
0x1805b8129  cmp     eax, 8
0x1805b812c  jbe     loc_1805B8245
0x1805b8132  mov     ecx, 4
0x1805b8137  mov     [rsp+120h+diFlags], 3; diFlags
0x1805b813f  mov     eax, r12d
0x1805b8142  mov     [rsp+120h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x1805b814b  cdq
0x1805b814c  mov     [rsp+120h+istepIfAniCur], 0; istepIfAniCur
0x1805b8154  idiv    ecx
0x1805b8156  mov     r9, rsi; hIcon
0x1805b8159  mov     ebx, eax
0x1805b815b  mov     eax, r15d
0x1805b815e  cdq
0x1805b815f  idiv    ecx
0x1805b8161  mov     ecx, 2
0x1805b8166  mov     [rbp+57h+xLeft], eax
0x1805b8169  mov     eax, r12d
0x1805b816c  mov     esi, [rbp+57h+xLeft]
0x1805b816f  cdq
0x1805b8170  idiv    ecx
0x1805b8172  mov     r8d, eax
0x1805b8175  mov     dword ptr [rbp+57h+var_B0], eax
0x1805b8178  mov     eax, r15d
0x1805b817b  mov     [rsp+120h+cyWidth], r8d; cyWidth
0x1805b8180  cdq
0x1805b8181  mov     r8d, ebx; yTop
0x1805b8184  idiv    ecx
0x1805b8186  mov     edx, esi; xLeft
0x1805b8188  mov     rcx, r14; hdc
0x1805b818b  mov     dword ptr [rbp+57h+hdc], eax
0x1805b818e  mov     dword ptr [rsp+120h+lpBits], eax; cxWidth
0x1805b8192  call    cs:__imp_DrawIconEx
0x1805b8199  nop     dword ptr [rax+rax+00h]
0x1805b819e  xor     r9d, r9d
0x1805b81a1  cmp     [rbp+57h+var_C0], r9d
0x1805b81a5  jz      loc_1805B83BD
0x1805b81ab  mov     rcx, r12
0x1805b81ae  mov     [rbp+57h+var_C0], r9d
0x1805b81b2  imul    rcx, r15; unsigned __int64
0x1805b81b6  lea     rdx, [rbp+57h+var_C0]; unsigned int *
0x1805b81ba  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1805b81bf  test    eax, eax
0x1805b81c1  js      loc_1805B83BD
0x1805b81c7  mov     r8d, [rbp+57h+var_C0]
0x1805b81cb  mov     ecx, r9d
0x1805b81ce  mov     r11, [rbp+57h+ppvBits]
0x1805b81d2  mov     edx, r9d
0x1805b81d5  test    r8d, r8d
0x1805b81d8  jz      loc_1805B83BD
0x1805b81de  lea     r12d, [r9+1]
0x1805b81e2  test    ecx, ecx
0x1805b81e4  jnz     short loc_1805B8201
0x1805b81e6  mov     eax, edx
0x1805b81e8  cmp     [r11+rax*4+3], r9b
0x1805b81ed  cmovnz  ecx, r12d
0x1805b81f1  add     edx, r12d
0x1805b81f4  cmp     edx, r8d
0x1805b81f7  jb      short loc_1805B81E2
0x1805b81f9  test    ecx, ecx
0x1805b81fb  jz      loc_1805B83BD
0x1805b8201  mov     r10d, dword ptr [rbp+57h+var_B0]
0x1805b8205  add     r10d, ebx
0x1805b8208  cmp     ebx, r10d
0x1805b820b  jnb     loc_1805B83BD
0x1805b8211  mov     r9d, dword ptr [rbp+57h+hdc]
0x1805b8215  add     r9d, esi
0x1805b8218  cmp     esi, r9d
0x1805b821b  jnb     short loc_1805B8238
0x1805b821d  mov     r8d, ebx
0x1805b8220  mov     edx, esi
0x1805b8222  imul    r8d, r15d
0x1805b8226  lea     eax, [r8+rdx]
0x1805b822a  add     edx, r12d
0x1805b822d  mov     byte ptr [r11+rax*4+3], 0FFh
0x1805b8233  cmp     edx, r9d
0x1805b8236  jb      short loc_1805B8226
0x1805b8238  add     ebx, r12d
0x1805b823b  cmp     ebx, r10d
0x1805b823e  jb      short loc_1805B8218
0x1805b8240  jmp     loc_1805B83BD
0x1805b8245  mov     rcx, r14; hdc
0x1805b8248  call    cs:__imp_CreateCompatibleDC
0x1805b824f  nop     dword ptr [rax+rax+00h]
0x1805b8254  mov     [rbp+57h+hdc], rax
0x1805b8258  mov     rbx, rax
0x1805b825b  test    rax, rax
0x1805b825e  jz      loc_1805B83BD
0x1805b8264  mov     ecx, 2
0x1805b8269  mov     [rsp+120h+lpBits], 0; ppvBits
0x1805b8272  mov     eax, r12d
0x1805b8275  cdq
0x1805b8276  idiv    ecx
0x1805b8278  mov     r8d, eax
0x1805b827b  mov     [rbp+57h+var_C0], eax
0x1805b827e  mov     eax, r15d
0x1805b8281  cdq
0x1805b8282  idiv    ecx
0x1805b8284  lea     r9d, [r8+2]; unsigned int
0x1805b8288  lea     edx, [rcx+16h]; unsigned __int16
0x1805b828b  mov     [rbp+57h+xLeft], eax
0x1805b828e  mov     rcx, r13; HDC
0x1805b8291  lea     r8d, [rax+2]; unsigned int
0x1805b8295  call    ?Create@DIBSectionUtil@@SAPEAUHBITMAP__@@PEAUHDC__@@GIIPEAPEAUtagRGBQUAD@@@Z; DIBSectionUtil::Create(HDC__ *,ushort,uint,uint,tagRGBQUAD * *)
0x1805b829a  mov     [rbp+57h+ho], rax
0x1805b829e  test    rax, rax
0x1805b82a1  jz      loc_1805B83AE
0x1805b82a7  mov     rdx, rax; h
0x1805b82aa  mov     rcx, rbx; hdc
0x1805b82ad  call    cs:__imp_SelectObject
0x1805b82b4  nop     dword ptr [rax+rax+00h]
0x1805b82b9  mov     edi, [rbp+57h+xLeft]
0x1805b82bc  lea     rdx, [rbp+57h+var_60]
0x1805b82c0  mov     ebx, [rbp+57h+var_C0]
0x1805b82c3  add     edi, 3
0x1805b82c6  mov     rcx, [rbp+57h+hdc]
0x1805b82ca  add     ebx, 3
0x1805b82cd  mov     r8d, 0FFFFFFh
0x1805b82d3  mov     [rbp+57h+var_58], edi
0x1805b82d6  mov     [rbp+57h+var_54], ebx
0x1805b82d9  mov     rsi, rax
0x1805b82dc  mov     [rbp+57h+var_60], 0
0x1805b82e4  call    cs:__imp_SHFillRectClr
0x1805b82eb  nop     dword ptr [rax+rax+00h]
0x1805b82f0  mov     eax, [rbp+57h+var_C0]
0x1805b82f3  mov     r9, [rbp+57h+hIcon]; hIcon
0x1805b82f7  mov     rcx, [rbp+57h+hdc]; hdc
0x1805b82fb  mov     [rsp+120h+diFlags], 3; diFlags
0x1805b8303  mov     [rsp+120h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x1805b830c  mov     [rsp+120h+istepIfAniCur], 0; istepIfAniCur
0x1805b8314  mov     [rsp+120h+cyWidth], eax; cyWidth
0x1805b8318  mov     eax, [rbp+57h+xLeft]
0x1805b831b  mov     dword ptr [rsp+120h+lpBits], eax; cxWidth
0x1805b831f  mov     eax, 1
0x1805b8324  mov     r8d, eax; yTop
0x1805b8327  mov     edx, eax; xLeft
0x1805b8329  call    cs:__imp_DrawIconEx
0x1805b8330  nop     dword ptr [rax+rax+00h]
0x1805b8335  mov     eax, r12d
0x1805b8338  mov     [rsp+120h+diFlags], 0CC0020h; rop
0x1805b8340  cdq
0x1805b8341  mov     dword ptr [rsp+120h+hbrFlickerFreeDraw], 0; y1
0x1805b8349  mov     ecx, 4
0x1805b834e  mov     [rsp+120h+istepIfAniCur], 0; x1
0x1805b8356  idiv    ecx
0x1805b8358  mov     r9d, edi; cx
0x1805b835b  lea     r8d, [rax-1]; y
0x1805b835f  mov     eax, r15d
0x1805b8362  cdq
0x1805b8363  idiv    ecx
0x1805b8365  mov     rcx, [rbp+57h+hdc]
0x1805b8369  mov     qword ptr [rsp+120h+cyWidth], rcx; hdcSrc
0x1805b836e  mov     rcx, r14; hdc
0x1805b8371  mov     dword ptr [rsp+120h+lpBits], ebx; cy
0x1805b8375  lea     edx, [rax-1]; x
0x1805b8378  call    cs:__imp_BitBlt
0x1805b837f  nop     dword ptr [rax+rax+00h]
0x1805b8384  mov     rbx, [rbp+57h+hdc]
0x1805b8388  mov     rdx, rsi; h
0x1805b838b  mov     rcx, rbx; hdc
0x1805b838e  call    cs:__imp_SelectObject
0x1805b8395  nop     dword ptr [rax+rax+00h]
0x1805b839a  mov     rcx, [rbp+57h+ho]; ho
0x1805b839e  call    cs:__imp_DeleteObject
0x1805b83a5  nop     dword ptr [rax+rax+00h]
0x1805b83aa  mov     rdi, [rbp+57h+var_B0]
0x1805b83ae  mov     rcx, rbx; hdc
0x1805b83b1  call    cs:__imp_DeleteDC
0x1805b83b8  nop     dword ptr [rax+rax+00h]
0x1805b83bd  mov     rdx, [rbp+57h+var_90]; h
0x1805b83c1  mov     rcx, r14; hdc
0x1805b83c4  call    cs:__imp_SelectObject
  ... truncated ...
```
