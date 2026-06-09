# CRegTreeOptions::CreateStandardImageList(void)

- ea: `0x18041b76c`
- end: `0x18041bb90`
- name: `?CreateStandardImageList@CRegTreeOptions@@IEAAXXZ`
- size: `1060`
- prototype: `void __fastcall(CRegTreeOptions *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18041bce0`
- `0x18041c120`

## callees

- `0x1800b1050`
- `0x180249490`
- `0x18041b76c`
- `0x180552750`
- `0x180552924`
- `0x180552994`

## import_xrefs

- `USER32!GetWindowLongW` at `0x18041b79f`
- `USER32!GetWindowLongW` at `0x18041b79f`
- `GDI32!DeleteObject` at `0x18041bafe`
- `GDI32!DeleteObject` at `0x18041bb3b`
- `GDI32!DeleteObject` at `0x18041bafe`
- `GDI32!DeleteObject` at `0x18041bb3b`
- `GDI32!CreateDIBSection` at `0x18041b8a9`
- `GDI32!CreateDIBSection` at `0x18041b8a9`
- `GDI32!CreateCompatibleDC` at `0x18041b7f0`
- `GDI32!CreateCompatibleDC` at `0x18041b987`
- `GDI32!CreateCompatibleDC` at `0x18041b7f0`
- `GDI32!CreateCompatibleDC` at `0x18041b987`
- `GDI32!SelectObject` at `0x18041b8da`
- `GDI32!SelectObject` at `0x18041b93f`
- `GDI32!SelectObject` at `0x18041b9a5`
- `GDI32!SelectObject` at `0x18041b9bb`
- `GDI32!SelectObject` at `0x18041bab8`
- `GDI32!SelectObject` at `0x18041bacb`
- `GDI32!SelectObject` at `0x18041b8da`
- `GDI32!SelectObject` at `0x18041b93f`
- `GDI32!SelectObject` at `0x18041b9a5`
- `GDI32!SelectObject` at `0x18041b9bb`
- `GDI32!SelectObject` at `0x18041bab8`
- `GDI32!SelectObject` at `0x18041bacb`
- `GDI32!DeleteDC` at `0x18041bada`
- `GDI32!DeleteDC` at `0x18041bb54`
- `GDI32!DeleteDC` at `0x18041bada`
- `GDI32!DeleteDC` at `0x18041bb54`
- `GDI32!StretchBlt` at `0x18041ba88`
- `GDI32!StretchBlt` at `0x18041ba88`
- `GDI32!SetStretchBltMode` at `0x18041b9e9`
- `GDI32!SetStretchBltMode` at `0x18041b9e9`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x18041b8f3`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x18041ba3f`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x18041b8f3`
- `api-ms-win-shlwapi-ie-l1-1-0!__imp_SHFillRectClr` at `0x18041ba3f`
- `UxTheme!DrawThemeBackground` at `0x18041b92d`
- `UxTheme!DrawThemeBackground` at `0x18041b92d`
- `UxTheme!OpenThemeData` at `0x18041b7d6`
- `UxTheme!OpenThemeData` at `0x18041b7d6`
- `UxTheme!GetThemePartSize` at `0x18041b827`
- `UxTheme!GetThemePartSize` at `0x18041b827`
- `UxTheme!CloseThemeData` at `0x18041bb63`
- `UxTheme!CloseThemeData` at `0x18041bb63`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18041ba29`
- `UxTheme!__imp_DrawThemeBackgroundEx` at `0x18041ba29`

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
      DrawThemeBackground(v6, CompatibleDC, dword_180649C38[v10], dword_180649C28[v10], &pRect, 0);
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
          DrawThemeBackgroundEx(v6, v16, dword_180649C38[i], dword_180649C28[i], &pRect, &pOptions);
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
0x18041b76c  push    rbp
0x18041b76e  push    rbx
0x18041b76f  push    rsi
0x18041b770  push    rdi
0x18041b771  push    r12
0x18041b773  push    r13
0x18041b775  push    r14
0x18041b777  push    r15
0x18041b779  lea     rbp, [rsp-1Fh]
0x18041b77e  sub     rsp, 0E8h
0x18041b785  mov     rax, cs:__security_cookie
0x18041b78c  xor     rax, rsp
0x18041b78f  mov     [rbp+57h+var_48], rax
0x18041b793  mov     r14, rcx
0x18041b796  mov     edx, 0FFFFFFECh; nIndex
0x18041b79b  mov     rcx, [rcx+20h]; hWnd
0x18041b79f  call    cs:__imp_GetWindowLongW
0x18041b7a6  nop     dword ptr [rax+rax+00h]
0x18041b7ab  mov     rcx, [r14+20h]; hwnd
0x18041b7af  lea     rdx, aButton; "Button"
0x18041b7b6  and     eax, 400000h
0x18041b7bb  neg     eax
0x18041b7bd  mov     eax, 10h
0x18041b7c2  sbb     ebx, ebx
0x18041b7c4  mov     [rbp+57h+var_A8.cx], eax
0x18041b7c7  xor     r13d, r13d
0x18041b7ca  mov     [rbp+57h+var_A8.cy], eax
0x18041b7cd  mov     edi, r13d
0x18041b7d0  and     ebx, 0A000h
0x18041b7d6  call    cs:__imp_OpenThemeData
0x18041b7dd  nop     dword ptr [rax+rax+00h]
0x18041b7e2  lea     r15d, [r13+1]
0x18041b7e6  mov     rsi, rax
0x18041b7e9  test    rax, rax
0x18041b7ec  jz      short loc_18041B833
0x18041b7ee  xor     ecx, ecx; hdc
0x18041b7f0  call    cs:__imp_CreateCompatibleDC
0x18041b7f7  nop     dword ptr [rax+rax+00h]
0x18041b7fc  mov     rdi, rax
0x18041b7ff  test    rax, rax
0x18041b802  jz      short loc_18041B833
0x18041b804  lea     rax, [rbp+57h+var_A8]
0x18041b808  mov     r9d, r15d; iStateId
0x18041b80b  mov     [rsp+120h+psz], rax; psz
0x18041b810  lea     r8d, [r13+3]; iPartId
0x18041b814  mov     [rsp+120h+eSize], 2; eSize
0x18041b81c  mov     rdx, rdi; hdc
0x18041b81f  mov     rcx, rsi; hTheme
0x18041b822  mov     [rsp+120h+prc], r13; prc
0x18041b827  call    cs:__imp_GetThemePartSize
0x18041b82e  nop     dword ptr [rax+rax+00h]
0x18041b833  mov     edx, [rbp+57h+var_A8.cy]; cy
0x18041b836  lea     r8d, [rbx+21h]; flags
0x18041b83a  mov     ecx, [rbp+57h+var_A8.cx]; cx
0x18041b83d  mov     r9d, 5; cInitial
0x18041b843  mov     dword ptr [rsp+120h+prc], 4; iNumMaps
0x18041b84b  call    ImageList_Create
0x18041b850  mov     [r14+38h], rax
0x18041b854  test    rsi, rsi
0x18041b857  jz      loc_18041BB11
0x18041b85d  test    rdi, rdi
0x18041b860  jz      loc_18041BB60
0x18041b866  xor     eax, eax
0x18041b868  mov     [rsp+120h+eSize], r13d; offset
0x18041b86d  xorps   xmm0, xmm0
0x18041b870  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biClrImportant], rax
0x18041b874  mov     eax, [rbp+57h+var_A8.cx]
0x18041b877  lea     rdx, [rbp+57h+pbmi]; pbmi
0x18041b87b  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biWidth], xmm0
0x18041b87f  mov     [rbp+57h+pbmi.bmiHeader.biWidth], eax
0x18041b882  xor     r9d, r9d; ppvBits
0x18041b885  mov     eax, [rbp+57h+var_A8.cy]
0x18041b888  xor     r8d, r8d; usage
0x18041b88b  mov     rcx, rdi; hdc
0x18041b88e  mov     [rbp+57h+pbmi.bmiHeader.biHeight], eax
0x18041b891  movups  xmmword ptr [rbp+57h+pbmi.bmiHeader.biSizeImage], xmm0
0x18041b895  mov     [rbp+57h+pbmi.bmiHeader.biSize], 28h ; '('
0x18041b89c  mov     qword ptr [rbp+57h+pbmi.bmiHeader.biPlanes], 200001h
0x18041b8a4  mov     [rsp+120h+prc], r13; hSection
0x18041b8a9  call    cs:__imp_CreateDIBSection
0x18041b8b0  nop     dword ptr [rax+rax+00h]
0x18041b8b5  mov     r12, rax
0x18041b8b8  test    rax, rax
0x18041b8bb  jz      loc_18041BB51
0x18041b8c1  mov     ecx, [rbp+57h+var_A8.cx]
0x18041b8c4  mov     r15d, r13d
0x18041b8c7  mov     [rbp+57h+pRect.right], ecx
0x18041b8ca  mov     ecx, [rbp+57h+var_A8.cy]
0x18041b8cd  mov     [rbp+57h+pRect.bottom], ecx
0x18041b8d0  mov     qword ptr [rbp+57h+pRect.left], r13
0x18041b8d4  mov     rdx, r12; h
0x18041b8d7  mov     rcx, rdi; hdc
0x18041b8da  call    cs:__imp_SelectObject
0x18041b8e1  nop     dword ptr [rax+rax+00h]
0x18041b8e6  xor     r8d, r8d
0x18041b8e9  lea     rdx, [rbp+57h+pRect]
0x18041b8ed  mov     rcx, rdi
0x18041b8f0  mov     rbx, rax
0x18041b8f3  call    cs:__imp_SHFillRectClr
0x18041b8fa  nop     dword ptr [rax+rax+00h]
0x18041b8ff  movsxd  r8, r15d
0x18041b902  lea     rax, [rbp+57h+pRect]
0x18041b906  mov     qword ptr [rsp+120h+eSize], r13; pClipRect
0x18041b90b  mov     rdx, rdi; hdc
0x18041b90e  mov     [rsp+120h+prc], rax; iNumMaps
0x18041b913  mov     rcx, rsi; hTheme
0x18041b916  lea     rax, __ImageBase
0x18041b91d  mov     r9d, ds:rva dword_180649C28[rax+r8*4]; iStateId
0x18041b925  mov     r8d, ds:rva dword_180649C38[rax+r8*4]; iPartId
0x18041b92d  call    cs:__imp_DrawThemeBackground
0x18041b934  nop     dword ptr [rax+rax+00h]
0x18041b939  mov     rdx, rbx; h
0x18041b93c  mov     rcx, rdi; hdc
0x18041b93f  call    cs:__imp_SelectObject
0x18041b946  nop     dword ptr [rax+rax+00h]
0x18041b94b  mov     rcx, [r14+38h]; himl
0x18041b94f  xor     r8d, r8d; hbmMask
0x18041b952  mov     rdx, r12; hbmImage
0x18041b955  call    ImageList_Add
0x18041b95a  inc     r15d
0x18041b95d  cmp     r15d, 4
0x18041b961  jb      loc_18041B8D4
0x18041b967  xor     r8d, r8d; wFlags
0x18041b96a  mov     edx, 0D3h; idBitmap
0x18041b96f  call    CreateMappedBitmap
0x18041b974  mov     [rbp+57h+var_B0], rax
0x18041b978  mov     rbx, rax
0x18041b97b  test    rax, rax
0x18041b97e  jz      loc_18041BAFB
0x18041b984  mov     rcx, rdi; hdc
0x18041b987  call    cs:__imp_CreateCompatibleDC
0x18041b98e  nop     dword ptr [rax+rax+00h]
0x18041b993  mov     r15, rax
0x18041b996  mov     rdx, rbx; hbmImage
0x18041b999  test    rax, rax
0x18041b99c  jz      loc_18041BAEC
0x18041b9a2  mov     rcx, rax; hdc
0x18041b9a5  call    cs:__imp_SelectObject
0x18041b9ac  nop     dword ptr [rax+rax+00h]
0x18041b9b1  mov     rdx, r12; h
0x18041b9b4  mov     rcx, rdi; hdc
0x18041b9b7  mov     [rbp+57h+var_B8], rax
0x18041b9bb  call    cs:__imp_SelectObject
0x18041b9c2  nop     dword ptr [rax+rax+00h]
0x18041b9c7  xorps   xmm0, xmm0
0x18041b9ca  mov     [rbp+57h+pOptions.dwSize], 18h
0x18041b9d1  mov     edx, 4; mode
0x18041b9d6  mov     [rbp+57h+h], rax
0x18041b9da  mov     rcx, rdi; hdc
0x18041b9dd  mov     [rbp+57h+pOptions.dwFlags], 2
0x18041b9e4  movdqu  xmmword ptr [rbp+57h+pOptions.rcClip.left], xmm0
0x18041b9e9  call    cs:__imp_SetStretchBltMode
0x18041b9f0  nop     dword ptr [rax+rax+00h]
0x18041b9f5  xor     ebx, ebx
0x18041b9f7  lea     r13, __ImageBase
0x18041b9fe  movsxd  r8, ebx
0x18041ba01  lea     rax, [rbp+57h+pOptions]
0x18041ba05  mov     qword ptr [rsp+120h+eSize], rax; pOptions
0x18041ba0a  mov     rdx, r15; hdc
0x18041ba0d  lea     rax, [rbp+57h+pRect]
0x18041ba11  mov     rcx, rsi; hTheme
0x18041ba14  mov     [rsp+120h+prc], rax; pRect
0x18041ba19  mov     r9d, ds:rva dword_180649C28[r13+r8*4]; iStateId
0x18041ba21  mov     r8d, ds:rva dword_180649C38[r13+r8*4]; iPartId
0x18041ba29  call    cs:__imp_DrawThemeBackgroundEx
0x18041ba30  nop     dword ptr [rax+rax+00h]
0x18041ba35  xor     r8d, r8d
0x18041ba38  lea     rdx, [rbp+57h+pRect]
0x18041ba3c  mov     rcx, rdi
0x18041ba3f  call    cs:__imp_SHFillRectClr
0x18041ba46  nop     dword ptr [rax+rax+00h]
0x18041ba4b  mov     r9d, [rbp+57h+var_A8.cx]; wDest
0x18041ba4f  mov     eax, 10h
0x18041ba54  mov     [rsp+120h+rop], 0CC0020h; rop
0x18041ba5c  xor     r8d, r8d; yDest
0x18041ba5f  mov     [rsp+120h+hSrc], eax; hSrc
0x18041ba63  xor     edx, edx; xDest
0x18041ba65  mov     [rsp+120h+wSrc], eax; wSrc
0x18041ba69  mov     rcx, rdi; hdcDest
0x18041ba6c  mov     eax, [rbp+57h+var_A8.cy]
0x18041ba6f  mov     [rsp+120h+ySrc], 0; ySrc
0x18041ba77  mov     dword ptr [rsp+120h+psz], 0; xSrc
0x18041ba7f  mov     qword ptr [rsp+120h+eSize], r15; hdcSrc
0x18041ba84  mov     dword ptr [rsp+120h+prc], eax; hDest
0x18041ba88  call    cs:__imp_StretchBlt
0x18041ba8f  nop     dword ptr [rax+rax+00h]
0x18041ba94  mov     rcx, [r14+38h]; himl
0x18041ba98  mov     r8d, 0FF000000h; crMask
0x18041ba9e  mov     rdx, r12; hbmImage
0x18041baa1  call    ImageList_AddMasked
0x18041baa6  inc     ebx
0x18041baa8  cmp     ebx, 4
0x18041baab  jb      loc_18041B9FE
0x18041bab1  mov     rdx, [rbp+57h+h]; h
0x18041bab5  mov     rcx, rdi; hdc
0x18041bab8  call    cs:__imp_SelectObject
0x18041babf  nop     dword ptr [rax+rax+00h]
0x18041bac4  mov     rdx, [rbp+57h+var_B8]; h
0x18041bac8  mov     rcx, r15; hdc
0x18041bacb  call    cs:__imp_SelectObject
0x18041bad2  nop     dword ptr [rax+rax+00h]
0x18041bad7  mov     rcx, r15; hdc
0x18041bada  call    cs:__imp_DeleteDC
0x18041bae1  nop     dword ptr [rax+rax+00h]
0x18041bae6  mov     rbx, [rbp+57h+var_B0]
0x18041baea  jmp     short loc_18041BAFB
0x18041baec  mov     rcx, [r14+38h]; himl
0x18041baf0  mov     r8d, 0FF000000h; crMask
0x18041baf6  call    ImageList_AddMasked
0x18041bafb  mov     rcx, r12; ho
0x18041bafe  call    cs:__imp_DeleteObject
0x18041bb05  nop     dword ptr [rax+rax+00h]
0x18041bb0a  test    rbx, rbx
0x18041bb0d  jz      short loc_18041BB51
0x18041bb0f  jmp     short loc_18041BB38
0x18041bb11  xor     r8d, r8d; wFlags
0x18041bb14  mov     edx, 0D2h; idBitmap
0x18041bb19  call    CreateMappedBitmap
0x18041bb1e  mov     rbx, rax
0x18041bb21  test    rax, rax
0x18041bb24  jz      short loc_18041BB6F
0x18041bb26  mov     rcx, [r14+38h]; himl
0x18041bb2a  mov     r8d, 0FF000000h; crMask
0x18041bb30  mov     rdx, rax; hbmImage
0x18041bb33  call    ImageList_AddMasked
0x18041bb38  mov     rcx, rbx; ho
0x18041bb3b  call    cs:__imp_DeleteObject
0x18041bb42  nop     dword ptr [rax+rax+00h]
0x18041bb47  test    rsi, rsi
0x18041bb4a  jz      short loc_18041BB6F
0x18041bb4c  test    rdi, rdi
0x18041bb4f  jz      short loc_18041BB60
0x18041bb51  mov     rcx, rdi; hdc
0x18041bb54  call    cs:__imp_DeleteDC
0x18041bb5b  nop     dword ptr [rax+rax+00h]
0x18041bb60  mov     rcx, rsi; hTheme
0x18041bb63  call    cs:__imp_CloseThemeData
0x18041bb6a  nop     dword ptr [rax+rax+00h]
0x18041bb6f  mov     rcx, [rbp+57h+var_48]
0x18041bb73  xor     rcx, rsp; StackCookie
0x18041bb76  call    __security_check_cookie
0x18041bb7b  add     rsp, 0E8h
0x18041bb82  pop     r15
0x18041bb84  pop     r14
0x18041bb86  pop     r13
0x18041bb88  pop     r12
0x18041bb8a  pop     rdi
0x18041bb8b  pop     rsi
0x18041bb8c  pop     rbx
0x18041bb8d  pop     rbp
0x18041bb8e  retn
```
