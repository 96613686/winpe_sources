# CThemeThumbnail::_RenderColorSwatch(void)

- ea: `0x180057ea4`
- end: `0x1800581b4`
- name: `?_RenderColorSwatch@CThemeThumbnail@@AEAAXXZ`
- size: `784`
- prototype: `void __fastcall(CThemeThumbnail *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800575c0`
- `0x180057c90`

## callees

- `0x180003394`
- `0x180030e2c`
- `0x180031704`
- `0x1800358c0`
- `0x18004b794`
- `0x1800535e8`
- `0x1800571d4`
- `0x1800578c0`
- `0x180057ea4`
- `0x18006d010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800580c0`
- `GDI32!DeleteObject` at `0x1800580c9`
- `GDI32!DeleteObject` at `0x180058118`
- `GDI32!DeleteObject` at `0x1800580c0`
- `GDI32!DeleteObject` at `0x1800580c9`
- `GDI32!DeleteObject` at `0x180058118`
- `GDI32!CreateRectRgn` at `0x180058075`
- `GDI32!CreateRectRgn` at `0x180058075`
- `UxTheme!GetCurrentThemeName` at `0x180057f28`
- `UxTheme!GetCurrentThemeName` at `0x180057f28`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f52`
- `OLEAUT32!__imp_SysFreeString` at `0x180058183`
- `OLEAUT32!__imp_SysFreeString` at `0x180057f52`
- `OLEAUT32!__imp_SysFreeString` at `0x180058183`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x18005803f`
- `dwmapi!__imp_DwmpGetColorizationParameters` at `0x18005803f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CThemeThumbnail::_RenderColorSwatch(CThemeThumbnail *this)
{
  _QWORD *v2; // rbx
  HRESULT CurrentThemeName; // esi
  int v4; // edx
  __int64 v5; // rax
  HINSTANCE v6; // rcx
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  unsigned int v11; // ebx
  int ColorizationParameters; // ecx
  int v13; // r8d
  HINSTANCE v14; // rcx
  HRGN RectRgn; // rsi
  HBITMAP BitmapWithWic; // rbx
  HBITMAP v17; // rax
  HBITMAP v18; // rsi
  unsigned int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h] BYREF
  BOOL v22; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  BSTR v24; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+68h] [rbp-98h]
  BSTR *p_bstrString; // [rsp+78h] [rbp-88h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  WCHAR pszColorBuff[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR pszThemeFileName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v24 = 0;
  v2 = (_QWORD *)((char *)this + 72);
  if ( (unsigned __int8)ATL::CComPtrBase<ITheme>::operator!=((char *)this + 72, 0) )
  {
    CurrentThemeName = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*v2 + 56LL))(*v2, &v24);
  }
  else
  {
    CurrentThemeName = GetCurrentThemeName(pszThemeFileName, 260, pszColorBuff, 260, 0, 0);
    v5 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v4, pszColorBuff);
    ATL::CComBSTR::operator=(&v24, v5);
    SysFreeString(bstrString);
  }
  if ( CurrentThemeName < 0 )
    goto LABEL_33;
  v21 = 0;
  if ( (unsigned __int8)ATL::CComPtrBase<ITheme>::operator!=(v2, 0) )
  {
    if ( (*(int (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v2 + 416LL))(*v2, &v21) < 0 )
      goto LABEL_33;
  }
  v20 = 0;
  if ( (unsigned __int8)ATL::CComPtrBase<ITheme>::operator!=(v2, 0) )
  {
    if ( (*(int (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v2 + 464LL))(*v2, &v20) < 0 )
      goto LABEL_33;
    v7 = v20;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v11 = 605;
    goto LABEL_28;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v11 = 606;
    goto LABEL_28;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v11 = 607;
    goto LABEL_28;
  }
  if ( v10 == 1 )
  {
    v11 = 608;
LABEL_28:
    v19 = 0;
    goto LABEL_29;
  }
  v19 = 0;
  if ( !v21 )
  {
    if ( *v2 )
    {
      ColorizationParameters = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v2 + 104LL))(*v2, &v19);
    }
    else
    {
      v25 = 0;
      v26 = 0;
      ColorizationParameters = DwmpGetColorizationParameters(&v25);
      v19 = v25;
    }
    v11 = 602;
    if ( ColorizationParameters >= 0 )
    {
      RectRgn = CreateRectRgn(
                  *((_DWORD *)this + 106),
                  *((_DWORD *)this + 107),
                  *((_DWORD *)this + 108),
                  *((_DWORD *)this + 109));
      if ( RectRgn )
      {
        BitmapWithWic = PremultiplyLoadBitmapWithWic(v14, 0x25Au);
        if ( BitmapWithWic )
        {
          AlphaFillRegion(*((HDC *)this + 12), v19, RectRgn, (struct tagRECT *)((char *)this + 424));
          AlphaDrawImage(*((HDC *)this + 12), BitmapWithWic, (struct tagRECT *)((char *)this + 408));
          DeleteObject(BitmapWithWic);
        }
        DeleteObject(RectRgn);
        v11 = 602;
      }
    }
    goto LABEL_31;
  }
  v11 = 611;
LABEL_29:
  v17 = PremultiplyLoadBitmapWithWic(v6, v11);
  v18 = v17;
  if ( v17 )
  {
    AlphaDrawImage(*((HDC *)this + 12), v17, (struct tagRECT *)((char *)this + 408));
    DeleteObject(v18);
  }
LABEL_31:
  if ( (Microsoft_Windows_ThemeUIEnableBits & 1) != 0 )
  {
    v22 = v11 == 602;
    LODWORD(bstrString) = v19;
    *(_QWORD *)&v26 = &v22;
    *((_QWORD *)&v26 + 1) = 4;
    p_bstrString = &bstrString;
    v28 = 4;
    McGenEventWrite_EtwEventWriteTransfer(v19, (unsigned int)ThemePreview_WindowColor_Info, v13, 3, (__int64)&v25);
  }
LABEL_33:
  SysFreeString(v24);
}

```

## disassembly

```asm
0x180057ea4  mov     [rsp-8+arg_8], rbx
0x180057ea9  mov     [rsp-8+arg_10], rsi
0x180057eae  push    rbp
0x180057eaf  push    rdi
0x180057eb0  push    r12
0x180057eb2  push    r14
0x180057eb4  push    r15
0x180057eb6  lea     rbp, [rsp-3C0h]
0x180057ebe  sub     rsp, 4C0h
0x180057ec5  mov     rax, cs:__security_cookie
0x180057ecc  xor     rax, rsp
0x180057ecf  mov     [rbp+3E0h+var_30], rax
0x180057ed6  mov     rdi, rcx
0x180057ed9  xor     r15d, r15d
0x180057edc  mov     [rsp+4E0h+var_490], r15
0x180057ee1  lea     rbx, [rcx+48h]
0x180057ee5  xor     edx, edx
0x180057ee7  mov     rcx, rbx
0x180057eea  call    ??9?$CComPtrBase@UITheme@@@ATL@@QEBA_NPEAUITheme@@@Z; ATL::CComPtrBase<ITheme>::operator!=(ITheme *)
0x180057eef  test    al, al
0x180057ef1  jz      short loc_180057F0B
0x180057ef3  mov     rcx, [rbx]
0x180057ef6  mov     rax, [rcx]
0x180057ef9  lea     rdx, [rsp+4E0h+var_490]
0x180057efe  mov     rax, [rax+38h]
0x180057f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f07  mov     esi, eax
0x180057f09  jmp     short loc_180057F58
0x180057f0b  mov     [rsp+4E0h+cchMaxSizeChars], r15d; cchMaxSizeChars
0x180057f10  mov     [rsp+4E0h+pszSizeBuff], r15; pszSizeBuff
0x180057f15  mov     edx, 104h; cchMaxNameChars
0x180057f1a  mov     r9d, edx; cchMaxColorChars
0x180057f1d  lea     r8, [rbp+3E0h+pszColorBuff]; pszColorBuff
0x180057f21  lea     rcx, [rbp+3E0h+pszThemeFileName]; pszThemeFileName
0x180057f28  call    cs:__imp_GetCurrentThemeName
0x180057f2e  mov     esi, eax
0x180057f30  lea     r8, [rbp+3E0h+pszColorBuff]; unsigned __int16 *
0x180057f34  lea     rcx, [rsp+4E0h+bstrString]; this
0x180057f39  call    ??0CComBSTR@ATL@@QEAA@HPEBG@Z; ATL::CComBSTR::CComBSTR(int,ushort const *)
0x180057f3e  nop
0x180057f3f  mov     rdx, rax
0x180057f42  lea     rcx, [rsp+4E0h+var_490]
0x180057f47  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x180057f4c  nop
0x180057f4d  mov     rcx, [rsp+4E0h+bstrString]; bstrString
0x180057f52  call    cs:__imp_SysFreeString
0x180057f58  test    esi, esi
0x180057f5a  js      loc_18005817E
0x180057f60  mov     [rsp+4E0h+var_4A8], r15d
0x180057f65  xor     edx, edx
0x180057f67  mov     rcx, rbx
0x180057f6a  call    ??9?$CComPtrBase@UITheme@@@ATL@@QEBA_NPEAUITheme@@@Z; ATL::CComPtrBase<ITheme>::operator!=(ITheme *)
0x180057f6f  test    al, al
0x180057f71  jz      short loc_180057F92
0x180057f73  mov     rcx, [rbx]
0x180057f76  mov     rax, [rcx]
0x180057f79  lea     rdx, [rsp+4E0h+var_4A8]
0x180057f7e  mov     rax, [rax+1A0h]
0x180057f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057f8a  test    eax, eax
0x180057f8c  js      loc_18005817E
0x180057f92  mov     r8d, r15d
0x180057f95  mov     [rsp+4E0h+var_4AC], r15d
0x180057f9a  xor     edx, edx
0x180057f9c  mov     rcx, rbx
0x180057f9f  call    ??9?$CComPtrBase@UITheme@@@ATL@@QEBA_NPEAUITheme@@@Z; ATL::CComPtrBase<ITheme>::operator!=(ITheme *)
0x180057fa4  test    al, al
0x180057fa6  jz      short loc_180057FCC
0x180057fa8  mov     rcx, [rbx]
0x180057fab  mov     rax, [rcx]
0x180057fae  lea     rdx, [rsp+4E0h+var_4AC]
0x180057fb3  mov     rax, [rax+1D0h]
0x180057fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057fbf  test    eax, eax
0x180057fc1  js      loc_18005817E
0x180057fc7  mov     r8d, [rsp+4E0h+var_4AC]
0x180057fcc  mov     r12d, 25Ah
0x180057fd2  sub     r8d, 1
0x180057fd6  jz      loc_1800580E9
0x180057fdc  sub     r8d, 1
0x180057fe0  jz      loc_1800580E2
0x180057fe6  sub     r8d, 1
0x180057fea  jz      loc_1800580DB
0x180057ff0  cmp     r8d, 1
0x180057ff4  jz      loc_1800580D4
0x180057ffa  mov     [rsp+4E0h+var_4B0], r15d
0x180057fff  cmp     [rsp+4E0h+var_4A8], r15d
0x180058004  jz      short loc_180058010
0x180058006  lea     ebx, [r12+9]
0x18005800b  jmp     loc_1800580F3
0x180058010  mov     rcx, [rbx]
0x180058013  test    rcx, rcx
0x180058016  jz      short loc_18005802D
0x180058018  mov     rax, [rcx]
0x18005801b  lea     rdx, [rsp+4E0h+var_4B0]
0x180058020  mov     rax, [rax+68h]
0x180058024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058029  mov     ecx, eax
0x18005802b  jmp     short loc_18005804F
0x18005802d  xorps   xmm0, xmm0
0x180058030  movups  [rsp+4E0h+var_488], xmm0
0x180058035  movups  [rsp+4E0h+var_478], xmm0
0x18005803a  lea     rcx, [rsp+4E0h+var_488]
0x18005803f  call    cs:__imp_DwmpGetColorizationParameters
0x180058045  mov     ecx, eax
0x180058047  mov     eax, dword ptr [rsp+4E0h+var_488]
0x18005804b  mov     [rsp+4E0h+var_4B0], eax
0x18005804f  mov     ebx, r12d
0x180058052  test    ecx, ecx
0x180058054  js      loc_18005811E
0x18005805a  lea     r14, [rdi+1A8h]
0x180058061  mov     r9d, [r14+0Ch]; y2
0x180058065  mov     r8d, [rdi+1B0h]; x2
0x18005806c  mov     edx, [rdi+1ACh]; y1
0x180058072  mov     ecx, [r14]; x1
0x180058075  call    cs:__imp_CreateRectRgn
0x18005807b  mov     rsi, rax
0x18005807e  test    rax, rax
0x180058081  jz      loc_18005811E
0x180058087  mov     edx, r12d; unsigned int
0x18005808a  call    ?PremultiplyLoadBitmapWithWic@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@I@Z; PremultiplyLoadBitmapWithWic(HINSTANCE__ *,uint)
0x18005808f  mov     rbx, rax
0x180058092  test    rax, rax
0x180058095  jz      short loc_1800580C6
0x180058097  mov     r9, r14; struct tagRECT *
0x18005809a  mov     r8, rsi; HRGN
0x18005809d  mov     edx, [rsp+4E0h+var_4B0]; unsigned int
0x1800580a1  mov     rcx, [rdi+60h]; hdcDest
0x1800580a5  call    ?AlphaFillRegion@@YAXPEAUHDC__@@KPEAUHRGN__@@PEAUtagRECT@@@Z; AlphaFillRegion(HDC__ *,ulong,HRGN__ *,tagRECT *)
0x1800580aa  lea     r8, [rdi+198h]; struct tagRECT *
0x1800580b1  mov     rdx, rbx; h
0x1800580b4  mov     rcx, [rdi+60h]; hdcDest
0x1800580b8  call    ?AlphaDrawImage@@YAHPEAUHDC__@@PEAUHBITMAP__@@PEAUtagRECT@@@Z; AlphaDrawImage(HDC__ *,HBITMAP__ *,tagRECT *)
0x1800580bd  mov     rcx, rbx; ho
0x1800580c0  call    cs:__imp_DeleteObject
0x1800580c6  mov     rcx, rsi; ho
0x1800580c9  call    cs:__imp_DeleteObject
0x1800580cf  mov     ebx, r12d
0x1800580d2  jmp     short loc_18005811E
0x1800580d4  mov     ebx, 260h
0x1800580d9  jmp     short loc_1800580EE
0x1800580db  mov     ebx, 25Fh
0x1800580e0  jmp     short loc_1800580EE
0x1800580e2  mov     ebx, 25Eh
0x1800580e7  jmp     short loc_1800580EE
0x1800580e9  mov     ebx, 25Dh
0x1800580ee  mov     [rsp+4E0h+var_4B0], r15d
0x1800580f3  mov     edx, ebx; unsigned int
0x1800580f5  call    ?PremultiplyLoadBitmapWithWic@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@I@Z; PremultiplyLoadBitmapWithWic(HINSTANCE__ *,uint)
0x1800580fa  mov     rsi, rax
0x1800580fd  test    rax, rax
0x180058100  jz      short loc_18005811E
0x180058102  lea     r8, [rdi+198h]; struct tagRECT *
0x180058109  mov     rdx, rax; h
0x18005810c  mov     rcx, [rdi+60h]; hdcDest
0x180058110  call    ?AlphaDrawImage@@YAHPEAUHDC__@@PEAUHBITMAP__@@PEAUtagRECT@@@Z; AlphaDrawImage(HDC__ *,HBITMAP__ *,tagRECT *)
0x180058115  mov     rcx, rsi; ho
0x180058118  call    cs:__imp_DeleteObject
0x18005811e  test    cs:Microsoft_Windows_ThemeUIEnableBits, 1
0x180058125  jz      short loc_18005817E
0x180058127  mov     ecx, [rsp+4E0h+var_4B0]
0x18005812b  mov     eax, r15d
0x18005812e  cmp     ebx, r12d
0x180058131  setz    al
0x180058134  mov     [rsp+4E0h+var_4A0], eax
0x180058138  mov     dword ptr [rsp+4E0h+bstrString], ecx
0x18005813c  lea     rax, [rsp+4E0h+var_4A0]
0x180058141  mov     qword ptr [rsp+4E0h+var_478], rax
0x180058146  mov     qword ptr [rsp+4E0h+var_478+8], 4
0x18005814f  lea     rax, [rsp+4E0h+bstrString]
0x180058154  mov     [rsp+4E0h+var_468], rax
0x180058159  mov     [rbp+3E0h+var_460], 4
0x180058161  lea     rax, [rsp+4E0h+var_488]
0x180058166  mov     [rsp+4E0h+pszSizeBuff], rax
0x18005816b  mov     r9d, 3
0x180058171  lea     rdx, ThemePreview_WindowColor_Info
0x180058178  call    McGenEventWrite_EtwEventWriteTransfer
0x18005817d  nop
0x18005817e  mov     rcx, [rsp+4E0h+var_490]; bstrString
0x180058183  call    cs:__imp_SysFreeString
0x180058189  mov     rcx, [rbp+3E0h+var_30]
0x180058190  xor     rcx, rsp; StackCookie
0x180058193  call    __security_check_cookie
0x180058198  lea     r11, [rsp+4E0h+var_20]
0x1800581a0  mov     rbx, [r11+38h]
0x1800581a4  mov     rsi, [r11+40h]
0x1800581a8  mov     rsp, r11
0x1800581ab  pop     r15
0x1800581ad  pop     r14
0x1800581af  pop     r12
0x1800581b1  pop     rdi
0x1800581b2  pop     rbp
0x1800581b3  retn
```
