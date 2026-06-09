# CRegTreeOptions::CreateStandardImageList(void)

- ea: `0x1803ef6d8`
- end: `0x1803efa6d`
- name: `?CreateStandardImageList@CRegTreeOptions@@IEAAXXZ`
- size: `917`
- prototype: `void __fastcall(CRegTreeOptions *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1803efbb0`
- `0x1803eff54`

## callees

- `0x18009c9c8`
- `0x180233280`
- `0x1803ef6d8`
- `0x180515150`
- `0x180515324`
- `0x180515394`

## import_xrefs

- `USER32!GetWindowLongW` at `0x1803ef70b`
- `USER32!GetWindowLongW` at `0x1803ef70b`
- `GDI32!DeleteObject` at `0x1803ef9f4`
- `GDI32!DeleteObject` at `0x1803efa2b`
- `GDI32!DeleteObject` at `0x1803ef9f4`
- `GDI32!DeleteObject` at `0x1803efa2b`
- `GDI32!CreateDIBSection` at `0x1803ef7fd`
- `GDI32!CreateDIBSection` at `0x1803ef7fd`
- `GDI32!CreateCompatibleDC` at `0x1803ef750`
- `GDI32!CreateCompatibleDC` at `0x1803ef8b9`
- `GDI32!CreateCompatibleDC` at `0x1803ef750`
- `GDI32!CreateCompatibleDC` at `0x1803ef8b9`
- `GDI32!SelectObject` at `0x1803ef828`
- `GDI32!SelectObject` at `0x1803ef87b`
- `GDI32!SelectObject` at `0x1803ef8d1`
- `GDI32!SelectObject` at `0x1803ef8e1`
- `GDI32!SelectObject` at `0x1803ef9c0`
- `GDI32!SelectObject` at `0x1803ef9cd`
- `GDI32!SelectObject` at `0x1803ef828`
- `GDI32!SelectObject` at `0x1803ef87b`
- `GDI32!SelectObject` at `0x1803ef8d1`
- `GDI32!SelectObject` at `0x1803ef8e1`
- `GDI32!SelectObject` at `0x1803ef9c0`
- `GDI32!SelectObject` at `0x1803ef9cd`
- `GDI32!DeleteDC` at `0x1803ef9d6`
- `GDI32!DeleteDC` at `0x1803efa3e`
- `GDI32!DeleteDC` at `0x1803ef9d6`
- `GDI32!DeleteDC` at `0x1803efa3e`
- `GDI32!StretchBlt` at `0x1803ef996`
- `GDI32!StretchBlt` at `0x1803ef996`
- `GDI32!SetStretchBltMode` at `0x1803ef909`
- `GDI32!SetStretchBltMode` at `0x1803ef909`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1803ef83b`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1803ef953`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1803ef83b`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x1803ef953`
- `UxTheme!DrawThemeBackground` at `0x1803ef86f`
- `UxTheme!DrawThemeBackground` at `0x1803ef86f`
- `UxTheme!OpenThemeData` at `0x1803ef73c`
- `UxTheme!OpenThemeData` at `0x1803ef73c`
- `UxTheme!GetThemePartSize` at `0x1803ef781`
- `UxTheme!GetThemePartSize` at `0x1803ef781`
- `UxTheme!CloseThemeData` at `0x1803efa47`
- `UxTheme!CloseThemeData` at `0x1803efa47`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x1803ef943`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x1803ef943`

## pseudocode

```c
void __fastcall CRegTreeOptions::CreateStandardImageList(CRegTreeOptions *this)
{
  LONG WindowLongW; // eax
  HWND v3; // rcx
  HDC CompatibleDC; // rdi
  int v5; // ebx
  HTHEME v6; // rsi
  HINSTANCE v7; // rcx
  struct _COLORMAP *v8; // r9
  HBITMAP v9; // r12
  unsigned int v10; // r15d
  HGDIOBJ v11; // rbx
  HINSTANCE v12; // rcx
  struct _COLORMAP *v13; // r9
  HBITMAP v14; // rbx
  HDC v15; // rax
  HDC v16; // r15
  HGDIOBJ v17; // rax
  unsigned int i; // ebx
  HBITMAP v19; // rax
  int prc; // [rsp+20h] [rbp-A9h]
  int prca; // [rsp+20h] [rbp-A9h]
  HGDIOBJ h; // [rsp+60h] [rbp-69h]
  HGDIOBJ v23; // [rsp+68h] [rbp-61h]
  HBITMAP MappedBitmap; // [rsp+70h] [rbp-59h]
  SIZE psz; // [rsp+78h] [rbp-51h] BYREF
  RECT pRect; // [rsp+80h] [rbp-49h] BYREF
  BITMAPINFO pbmi; // [rsp+90h] [rbp-39h] BYREF
  DTBGOPTS pOptions; // [rsp+C0h] [rbp-9h] BYREF

  WindowLongW = GetWindowLongW(*((HWND *)this + 4), -20);
  v3 = (HWND)*((_QWORD *)this + 4);
  psz.cx = 16;
  psz.cy = 16;
  CompatibleDC = 0;
  v5 = (WindowLongW & 0x400000) != 0 ? 0xA000 : 0;
  v6 = OpenThemeData(v3, L"Button");
  if ( v6 )
  {
    CompatibleDC = CreateCompatibleDC(0);
    if ( CompatibleDC )
      GetThemePartSize(v6, CompatibleDC, 3, 1, 0, TS_DRAW, &psz);
  }
  *((_QWORD *)this + 7) = ImageList_Create(psz.cx, psz.cy, v5 + 33, 5, 4);
  if ( v6 )
  {
    if ( !CompatibleDC )
      goto LABEL_22;
    *(SIZE *)&pbmi.bmiHeader.biWidth = psz;
    memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
    pbmi.bmiHeader.biSize = 40;
    *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
    v9 = CreateDIBSection(CompatibleDC, &pbmi, 0, 0, 0, 0);
    if ( !v9 )
      goto LABEL_21;
    v10 = 0;
    *(SIZE *)&pRect.right = psz;
    *(_QWORD *)&pRect.left = 0;
    do
    {
      v11 = SelectObject(CompatibleDC, v9);
      SHFillRectClr(CompatibleDC, &pRect, 0);
      DrawThemeBackground(v6, CompatibleDC, dword_180609110[v10], dword_180609100[v10], &pRect, 0);
      SelectObject(CompatibleDC, v11);
      ImageList_Add(*((HIMAGELIST *)this + 7), v9, 0);
      ++v10;
    }
    while ( v10 < 4 );
    MappedBitmap = CreateMappedBitmap(v12, 211, 0, v13, prca);
    v14 = MappedBitmap;
    if ( MappedBitmap )
    {
      v15 = CreateCompatibleDC(CompatibleDC);
      v16 = v15;
      if ( v15 )
      {
        v23 = SelectObject(v15, MappedBitmap);
        v17 = SelectObject(CompatibleDC, v9);
        pOptions.dwSize = 24;
        h = v17;
        pOptions.dwFlags = 2;
        pOptions.rcClip = 0;
        SetStretchBltMode(CompatibleDC, 4);
        for ( i = 0; i < 4; ++i )
        {
          DrawThemeBackgroundEx(v6, v16, dword_180609110[i], dword_180609100[i], &pRect, &pOptions);
          SHFillRectClr(CompatibleDC, &pRect, 0);
          StretchBlt(CompatibleDC, 0, 0, psz.cx, psz.cy, v16, 0, 0, 16, 16, 0xCC0020u);
          ImageList_AddMasked(*((HIMAGELIST *)this + 7), v9, 0xFF000000);
        }
        SelectObject(CompatibleDC, h);
        SelectObject(v16, v23);
        DeleteDC(v16);
        v14 = MappedBitmap;
      }
      else
      {
        ImageList_AddMasked(*((HIMAGELIST *)this + 7), MappedBitmap, 0xFF000000);
      }
    }
    DeleteObject(v9);
    if ( !v14 )
    {
LABEL_21:
      DeleteDC(CompatibleDC);
      goto LABEL_22;
    }
  }
  else
  {
    v19 = CreateMappedBitmap(v7, 210, 0, v8, prc);
    v14 = v19;
    if ( !v19 )
      return;
    ImageList_AddMasked(*((HIMAGELIST *)this + 7), v19, 0xFF000000);
  }
  DeleteObject(v14);
  if ( !v6 )
    return;
  if ( CompatibleDC )
    goto LABEL_21;
LABEL_22:
  CloseThemeData(v6);
}

```

## disassembly

```asm
0x1803ef6d8  push    rbp
0x1803ef6da  push    rbx
0x1803ef6db  push    rsi
0x1803ef6dc  push    rdi
0x1803ef6dd  push    r12
0x1803ef6df  push    r13
0x1803ef6e1  push    r14
0x1803ef6e3  push    r15
0x1803ef6e5  lea     rbp, [rsp-1Fh]
0x1803ef6ea  sub     rsp, 0E8h
0x1803ef6f1  mov     rax, cs:__security_cookie
0x1803ef6f8  xor     rax, rsp
0x1803ef6fb  mov     [rbp+57h+var_48], rax
0x1803ef6ff  mov     r14, rcx
0x1803ef702  mov     edx, 0FFFFFFECh; nIndex
0x1803ef707  mov     rcx, [rcx+20h]; hWnd
0x1803ef70b  call    cs:__imp_GetWindowLongW
0x1803ef711  mov     rcx, [r14+20h]; hwnd
0x1803ef715  lea     rdx, aButton; "Button"
0x1803ef71c  and     eax, 400000h
0x1803ef721  neg     eax
0x1803ef723  mov     eax, 10h
0x1803ef728  sbb     ebx, ebx
0x1803ef72a  mov     [rbp+57h+var_A8.cx], eax
0x1803ef72d  xor     r13d, r13d
0x1803ef730  mov     [rbp+57h+var_A8.cy], eax
0x1803ef733  mov     edi, r13d
0x1803ef736  and     ebx, 0A000h
0x1803ef73c  call    cs:__imp_OpenThemeData
0x1803ef742  lea     r15d, [r13+1]
0x1803ef746  mov     rsi, rax
0x1803ef749  test    rax, rax
0x1803ef74c  jz      short loc_1803EF787
0x1803ef74e  xor     ecx, ecx; hdc
0x1803ef750  call    cs:__imp_CreateCompatibleDC
0x1803ef756  mov     rdi, rax
0x1803ef759  test    rax, rax
0x1803ef75c  jz      short loc_1803EF787
0x1803ef75e  lea     rax, [rbp+57h+var_A8]
0x1803ef762  mov     r9d, r15d; iStateId
0x1803ef765  mov     [rsp+120h+psz], rax; psz
0x1803ef76a  lea     r8d, [r13+3]; iPartId
0x1803ef76e  mov     [rsp+120h+eSize], 2; eSize
0x1803ef776  mov     rdx, rdi; hdc
0x1803ef779  mov     rcx, rsi; hTheme
0x1803ef77c  mov     [rsp+120h+prc], r13; prc
0x1803ef781  call    cs:__imp_GetThemePartSize
0x1803ef787  mov     edx, [rbp+57h+var_A8.cy]; cy
0x1803ef78a  lea     r8d, [rbx+21h]; flags
0x1803ef78e  mov     ecx, [rbp+57h+var_A8.cx]; cx
0x1803ef791  mov     r9d, 5; cInitial
0x1803ef797  mov     dword ptr [rsp+120h+prc], 4; iNumMaps
0x1803ef79f  call    ImageList_Create
0x1803ef7a4  mov     [r14+38h], rax
0x1803ef7a8  test    rsi, rsi
0x1803ef7ab  jz      loc_1803EFA01
0x1803ef7b1  test    rdi, rdi
0x1803ef7b4  jz      loc_1803EFA44
0x1803ef7ba  xor     eax, eax
0x1803ef7bc  mov     [rsp+120h+eSize], r13d; offset
0x1803ef7c1  xorps   xmm0, xmm0
0x1803ef7c4  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x1803ef7c8  mov     eax, [rbp+57h+var_A8.cx]
0x1803ef7cb  lea     rdx, [rbp+57h+pbmi]; pbmi
0x1803ef7cf  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x1803ef7d3  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x1803ef7d6  xor     r9d, r9d; ppvBits
0x1803ef7d9  mov     eax, [rbp+57h+var_A8.cy]
0x1803ef7dc  xor     r8d, r8d; usage
0x1803ef7df  mov     rcx, rdi; hdc
0x1803ef7e2  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x1803ef7e5  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x1803ef7e9  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x1803ef7f0  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x1803ef7f8  mov     [rsp+120h+prc], r13; hSection
0x1803ef7fd  call    cs:__imp_CreateDIBSection
0x1803ef803  mov     r12, rax
0x1803ef806  test    rax, rax
0x1803ef809  jz      loc_1803EFA3B
0x1803ef80f  mov     ecx, [rbp+57h+var_A8.cx]
0x1803ef812  mov     r15d, r13d
0x1803ef815  mov     [rbp+57h+pRect.right], ecx
0x1803ef818  mov     ecx, [rbp+57h+var_A8.cy]
0x1803ef81b  mov     [rbp+57h+pRect.bottom], ecx
0x1803ef81e  mov     qword ptr [rbp+57h+pRect.left], r13
0x1803ef822  mov     rdx, r12; h
0x1803ef825  mov     rcx, rdi; hdc
0x1803ef828  call    cs:__imp_SelectObject
0x1803ef82e  xor     r8d, r8d
0x1803ef831  lea     rdx, [rbp+57h+pRect]
0x1803ef835  mov     rcx, rdi
0x1803ef838  mov     rbx, rax
0x1803ef83b  call    cs:__imp_SHFillRectClr
0x1803ef841  movsxd  r8, r15d
0x1803ef844  lea     rax, [rbp+57h+pRect]
0x1803ef848  mov     qword ptr [rsp+120h+eSize], r13; pClipRect
0x1803ef84d  mov     rdx, rdi; hdc
0x1803ef850  mov     [rsp+120h+prc], rax; iNumMaps
0x1803ef855  mov     rcx, rsi; hTheme
0x1803ef858  lea     rax, __ImageBase
0x1803ef85f  mov     r9d, ds:rva dword_180609100[rax+r8*4]; iStateId
0x1803ef867  mov     r8d, ds:rva dword_180609110[rax+r8*4]; iPartId
0x1803ef86f  call    cs:__imp_DrawThemeBackground
0x1803ef875  mov     rdx, rbx; h
0x1803ef878  mov     rcx, rdi; hdc
0x1803ef87b  call    cs:__imp_SelectObject
0x1803ef881  mov     rcx, [r14+38h]; himl
0x1803ef885  xor     r8d, r8d; hbmMask
0x1803ef888  mov     rdx, r12; hbmImage
0x1803ef88b  call    ImageList_Add
0x1803ef890  inc     r15d
0x1803ef893  cmp     r15d, 4
0x1803ef897  jb      short loc_1803EF822
0x1803ef899  xor     r8d, r8d; wFlags
0x1803ef89c  mov     edx, 0D3h; idBitmap
0x1803ef8a1  call    CreateMappedBitmap
0x1803ef8a6  mov     [rbp+57h+var_B0], rax
0x1803ef8aa  mov     rbx, rax
0x1803ef8ad  test    rax, rax
0x1803ef8b0  jz      loc_1803EF9F1
0x1803ef8b6  mov     rcx, rdi; hdc
0x1803ef8b9  call    cs:__imp_CreateCompatibleDC
0x1803ef8bf  mov     r15, rax
0x1803ef8c2  mov     rdx, rbx; hbmImage
0x1803ef8c5  test    rax, rax
0x1803ef8c8  jz      loc_1803EF9E2
0x1803ef8ce  mov     rcx, rax; hdc
0x1803ef8d1  call    cs:__imp_SelectObject
0x1803ef8d7  mov     rdx, r12; h
0x1803ef8da  mov     rcx, rdi; hdc
0x1803ef8dd  mov     [rbp+57h+var_B8], rax
0x1803ef8e1  call    cs:__imp_SelectObject
0x1803ef8e7  xorps   xmm0, xmm0
0x1803ef8ea  mov     [rbp+57h+pOptions.dwSize], 18h
0x1803ef8f1  mov     edx, 4; mode
0x1803ef8f6  mov     [rbp+57h+h], rax
0x1803ef8fa  mov     rcx, rdi; hdc
0x1803ef8fd  mov     [rbp+57h+pOptions.dwFlags], 2
0x1803ef904  movdqu  xmmword ptr [rbp+57h+pOptions.rcClip.left], xmm0
0x1803ef909  call    cs:__imp_SetStretchBltMode
0x1803ef90f  xor     ebx, ebx
0x1803ef911  lea     r13, __ImageBase
0x1803ef918  movsxd  r8, ebx
0x1803ef91b  lea     rax, [rbp+57h+pOptions]
0x1803ef91f  mov     qword ptr [rsp+120h+eSize], rax; pOptions
0x1803ef924  mov     rdx, r15; hdc
0x1803ef927  lea     rax, [rbp+57h+pRect]
0x1803ef92b  mov     rcx, rsi; hTheme
0x1803ef92e  mov     [rsp+120h+prc], rax; pRect
0x1803ef933  mov     r9d, ds:rva dword_180609100[r13+r8*4]; iStateId
0x1803ef93b  mov     r8d, ds:rva dword_180609110[r13+r8*4]; iPartId
0x1803ef943  call    cs:__imp_DrawThemeBackgroundEx
0x1803ef949  xor     r8d, r8d
0x1803ef94c  lea     rdx, [rbp+57h+pRect]
0x1803ef950  mov     rcx, rdi
0x1803ef953  call    cs:__imp_SHFillRectClr
0x1803ef959  mov     r9d, [rbp+57h+var_A8.cx]; wDest
0x1803ef95d  mov     eax, 10h
0x1803ef962  mov     [rsp+120h+rop], 0CC0020h; rop
0x1803ef96a  xor     r8d, r8d; yDest
0x1803ef96d  mov     [rsp+120h+hSrc], eax; hSrc
0x1803ef971  xor     edx, edx; xDest
0x1803ef973  mov     [rsp+120h+wSrc], eax; wSrc
0x1803ef977  mov     rcx, rdi; hdcDest
0x1803ef97a  mov     eax, [rbp+57h+var_A8.cy]
0x1803ef97d  mov     [rsp+120h+ySrc], 0; ySrc
0x1803ef985  mov     dword ptr [rsp+120h+psz], 0; xSrc
0x1803ef98d  mov     qword ptr [rsp+120h+eSize], r15; hdcSrc
0x1803ef992  mov     dword ptr [rsp+120h+prc], eax; hDest
0x1803ef996  call    cs:__imp_StretchBlt
0x1803ef99c  mov     rcx, [r14+38h]; himl
0x1803ef9a0  mov     r8d, 0FF000000h; crMask
0x1803ef9a6  mov     rdx, r12; hbmImage
0x1803ef9a9  call    ImageList_AddMasked
0x1803ef9ae  inc     ebx
0x1803ef9b0  cmp     ebx, 4
0x1803ef9b3  jb      loc_1803EF918
0x1803ef9b9  mov     rdx, [rbp+57h+h]; h
0x1803ef9bd  mov     rcx, rdi; hdc
0x1803ef9c0  call    cs:__imp_SelectObject
0x1803ef9c6  mov     rdx, [rbp+57h+var_B8]; h
0x1803ef9ca  mov     rcx, r15; hdc
0x1803ef9cd  call    cs:__imp_SelectObject
0x1803ef9d3  mov     rcx, r15; hdc
0x1803ef9d6  call    cs:__imp_DeleteDC
0x1803ef9dc  mov     rbx, [rbp+57h+var_B0]
0x1803ef9e0  jmp     short loc_1803EF9F1
0x1803ef9e2  mov     rcx, [r14+38h]; himl
0x1803ef9e6  mov     r8d, 0FF000000h; crMask
0x1803ef9ec  call    ImageList_AddMasked
0x1803ef9f1  mov     rcx, r12; ho
0x1803ef9f4  call    cs:__imp_DeleteObject
0x1803ef9fa  test    rbx, rbx
0x1803ef9fd  jz      short loc_1803EFA3B
0x1803ef9ff  jmp     short loc_1803EFA28
0x1803efa01  xor     r8d, r8d; wFlags
0x1803efa04  mov     edx, 0D2h; idBitmap
0x1803efa09  call    CreateMappedBitmap
0x1803efa0e  mov     rbx, rax
0x1803efa11  test    rax, rax
0x1803efa14  jz      short loc_1803EFA4D
0x1803efa16  mov     rcx, [r14+38h]; himl
0x1803efa1a  mov     r8d, 0FF000000h; crMask
0x1803efa20  mov     rdx, rax; hbmImage
0x1803efa23  call    ImageList_AddMasked
0x1803efa28  mov     rcx, rbx; ho
0x1803efa2b  call    cs:__imp_DeleteObject
0x1803efa31  test    rsi, rsi
0x1803efa34  jz      short loc_1803EFA4D
0x1803efa36  test    rdi, rdi
0x1803efa39  jz      short loc_1803EFA44
0x1803efa3b  mov     rcx, rdi; hdc
0x1803efa3e  call    cs:__imp_DeleteDC
0x1803efa44  mov     rcx, rsi; hTheme
0x1803efa47  call    cs:__imp_CloseThemeData
0x1803efa4d  mov     rcx, [rbp+57h+var_48]
0x1803efa51  xor     rcx, rsp; StackCookie
0x1803efa54  call    __security_check_cookie
0x1803efa59  add     rsp, 0E8h
0x1803efa60  pop     r15
0x1803efa62  pop     r14
0x1803efa64  pop     r13
0x1803efa66  pop     r12
0x1803efa68  pop     rdi
0x1803efa69  pop     rsi
0x1803efa6a  pop     rbx
0x1803efa6b  pop     rbp
0x1803efa6c  retn
```
