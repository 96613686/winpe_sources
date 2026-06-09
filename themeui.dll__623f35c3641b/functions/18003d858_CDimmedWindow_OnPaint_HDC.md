# CDimmedWindow::OnPaint(HDC__ *)

- ea: `0x18003d858`
- end: `0x18003dbb2`
- name: `?OnPaint@CDimmedWindow@@AEAAXPEAUHDC__@@@Z`
- size: `858`
- prototype: `void(CDimmedWindow *__hidden this, HDC)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001f3d0`
- `0x180034fb0`

## callees

- `0x1800358c0`
- `0x18003633c`
- `0x18003d858`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003d9b5`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x18003d9b5`
- `SHCORE!__imp_ScaleRelativePixelsForDevice` at `0x18003d9c4`
- `SHCORE!__imp_ScaleRelativePixelsForDevice` at `0x18003d9c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003d994`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003d9e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003da5c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003d994`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003d9e5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003da5c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18003dab4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x18003dab4`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18003da8b`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18003da8b`
- `GDI32!DeleteObject` at `0x18003d8e8`
- `GDI32!DeleteObject` at `0x18003db07`
- `GDI32!DeleteObject` at `0x18003d8e8`
- `GDI32!DeleteObject` at `0x18003db07`
- `GDI32!BitBlt` at `0x18003db82`
- `GDI32!BitBlt` at `0x18003db82`
- `GDI32!SetLayout` at `0x18003db40`
- `GDI32!SetLayout` at `0x18003db4c`
- `GDI32!SetLayout` at `0x18003db40`
- `GDI32!SetLayout` at `0x18003db4c`
- `GDI32!GetObjectW` at `0x18003db31`
- `GDI32!GetObjectW` at `0x18003db31`
- `GDI32!SetTextColor` at `0x18003da40`
- `GDI32!SetTextColor` at `0x18003da40`
- `GDI32!SetBkMode` at `0x18003da34`
- `GDI32!SetBkMode` at `0x18003da34`
- `GDI32!CreateFontIndirectW` at `0x18003da02`
- `GDI32!CreateFontIndirectW` at `0x18003da02`
- `GDI32!CreateSolidBrush` at `0x18003d8c6`
- `GDI32!CreateSolidBrush` at `0x18003d8c6`
- `GDI32!SelectObject` at `0x18003da1a`
- `GDI32!SelectObject` at `0x18003dafe`
- `GDI32!SelectObject` at `0x18003da1a`
- `GDI32!SelectObject` at `0x18003dafe`
- `USER32!GetSystemMetrics` at `0x18003d947`
- `USER32!GetSystemMetrics` at `0x18003d956`
- `USER32!GetSystemMetrics` at `0x18003d947`
- `USER32!GetSystemMetrics` at `0x18003d956`
- `USER32!GetClientRect` at `0x18003d8bd`
- `USER32!GetClientRect` at `0x18003d978`
- `USER32!GetClientRect` at `0x18003d8bd`
- `USER32!GetClientRect` at `0x18003d978`
- `USER32!FillRect` at `0x18003d8df`
- `USER32!FillRect` at `0x18003d8df`
- `USER32!MonitorFromPoint` at `0x18003d903`
- `USER32!MonitorFromPoint` at `0x18003d903`
- `USER32!GetMonitorInfoW` at `0x18003d931`
- `USER32!GetMonitorInfoW` at `0x18003d931`
- `USER32!OffsetRect` at `0x18003d968`
- `USER32!OffsetRect` at `0x18003d968`
- `USER32!GetWindowLongW` at `0x18003da70`
- `USER32!GetWindowLongW` at `0x18003da70`
- `USER32!DrawTextW` at `0x18003daf2`
- `USER32!DrawTextW` at `0x18003daf2`

## pseudocode

```c
void __fastcall CDimmedWindow::OnPaint(CDimmedWindow *this, HDC a2)
{
  HDC v4; // rsi
  HWND *v5; // r14
  HWND v6; // rcx
  HBRUSH SolidBrush; // rax
  HBRUSH v8; // rbx
  HMONITOR v9; // rax
  int v10; // ebx
  int SystemMetrics; // eax
  HFONT v12; // rax
  HFONT v13; // r15
  __int32 v14; // ebx
  HGDIOBJ v15; // r13
  int v16; // eax
  UINT format; // r14d
  LANGID UserDefaultUILanguage; // ax
  void *v19; // rcx
  struct tagMONITORINFO Rect; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT rc; // [rsp+78h] [rbp-88h] BYREF
  LOGFONTW lf; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Buffer[32]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR chText[264]; // [rsp+130h] [rbp+30h] BYREF

  if ( *((_QWORD *)this + 6) && (v4 = (HDC)*((_QWORD *)this + 5)) != 0 )
  {
    v5 = (HWND *)((char *)this + 24);
  }
  else
  {
    v5 = (HWND *)((char *)this + 24);
    v6 = (HWND)*((_QWORD *)this + 3);
    v4 = a2;
    *(_OWORD *)&Rect.cbSize = 0;
    GetClientRect(v6, (LPRECT)&Rect);
    SolidBrush = CreateSolidBrush(*((_DWORD *)this + 18));
    v8 = SolidBrush;
    if ( SolidBrush )
    {
      FillRect(a2, (const RECT *)&Rect, SolidBrush);
      DeleteObject(v8);
    }
  }
  *(_QWORD *)&Rect.cbSize = 0;
  rc = 0;
  v9 = MonitorFromPoint(0, 1u);
  if ( v9 )
  {
    Rect.cbSize = 40;
    memset(&Rect.rcMonitor, 0, 36);
    GetMonitorInfoW(v9, &Rect);
    rc = Rect.rcMonitor;
    v10 = -GetSystemMetrics(77);
    SystemMetrics = GetSystemMetrics(76);
    OffsetRect(&rc, -SystemMetrics, v10);
  }
  else
  {
    GetClientRect(*v5, &rc);
  }
  if ( LoadStringW(g_hinst, 0xA73u, Buffer, 32) )
  {
    memset_0(&lf, 0, sizeof(lf));
    _o__wtoi(Buffer);
    lf.lfHeight = -(int)ScaleRelativePixelsForDevice(0);
    if ( LoadStringW(g_hinst, 0xA72u, lf.lfFaceName, 32) )
    {
      lf.lfWeight = 100;
      lf.lfQuality = 0;
      v12 = CreateFontIndirectW(&lf);
      v13 = v12;
      if ( v12 )
      {
        v14 = 0;
        v15 = SelectObject(v4, v12);
        if ( v15 )
        {
          SetBkMode(v4, 1);
          SetTextColor(v4, *((_DWORD *)this + 19));
          if ( LoadStringW(g_hinst, 0xA71u, chText, 260) )
          {
            if ( (GetWindowLongW(*v5, -20) & 0x400000) != 0 )
              goto LABEL_21;
            v16 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
            format = 37;
            if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
            {
              UserDefaultUILanguage = GetUserDefaultUILanguage();
              `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
              if ( UserDefaultUILanguage )
              {
                Rect.cbSize = 0;
                if ( GetLocaleInfoW(UserDefaultUILanguage, 0x20000070u, (LPWSTR)&Rect, 2) > 0 )
                  LOBYTE(v14) = Rect.cbSize == 1;
              }
              _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v14);
              v16 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
            }
            if ( v16 == 1 )
LABEL_21:
              format = 131109;
            DrawTextW(v4, chText, -1, &rc, format);
          }
          SelectObject(v4, v15);
        }
        DeleteObject(v13);
      }
    }
  }
  if ( v4 == *((HDC *)this + 5) )
  {
    v19 = (void *)*((_QWORD *)this + 6);
    memset(&Rect, 0, 32);
    if ( GetObjectW(v19, 32, &Rect) )
    {
      SetLayout(a2, 0);
      SetLayout(*((HDC *)this + 5), 0);
      BitBlt(a2, 0, 0, Rect.rcMonitor.left, Rect.rcMonitor.top, *((HDC *)this + 5), 0, 0, 0xCC0020u);
    }
  }
}

```

## disassembly

```asm
0x18003d858  mov     [rsp-8+arg_10], rbx
0x18003d85d  push    rbp
0x18003d85e  push    rsi
0x18003d85f  push    rdi
0x18003d860  push    r12
0x18003d862  push    r13
0x18003d864  push    r14
0x18003d866  push    r15
0x18003d868  lea     rbp, [rsp-250h]
0x18003d870  sub     rsp, 350h
0x18003d877  mov     rax, cs:__security_cookie
0x18003d87e  xor     rax, rsp
0x18003d881  mov     [rbp+280h+var_40], rax
0x18003d888  xor     r13d, r13d
0x18003d88b  mov     r12, rdx
0x18003d88e  mov     rdi, rcx
0x18003d891  cmp     [rcx+30h], r13
0x18003d895  jz      short loc_18003D8A6
0x18003d897  mov     rsi, [rcx+28h]
0x18003d89b  test    rsi, rsi
0x18003d89e  jz      short loc_18003D8A6
0x18003d8a0  lea     r14, [rcx+18h]
0x18003d8a4  jmp     short loc_18003D8EE
0x18003d8a6  lea     r14, [rcx+18h]
0x18003d8aa  xorps   xmm0, xmm0
0x18003d8ad  mov     rcx, [r14]; hWnd
0x18003d8b0  lea     rdx, [rsp+380h+Rect]; lpRect
0x18003d8b5  mov     rsi, r12
0x18003d8b8  movups  xmmword ptr [rsp+380h+Rect.left], xmm0
0x18003d8bd  call    cs:__imp_GetClientRect
0x18003d8c3  mov     ecx, [rdi+48h]; color
0x18003d8c6  call    cs:__imp_CreateSolidBrush
0x18003d8cc  mov     rbx, rax
0x18003d8cf  test    rax, rax
0x18003d8d2  jz      short loc_18003D8EE
0x18003d8d4  mov     r8, rax; hbr
0x18003d8d7  lea     rdx, [rsp+380h+Rect]; lprc
0x18003d8dc  mov     rcx, r12; hDC
0x18003d8df  call    cs:__imp_FillRect
0x18003d8e5  mov     rcx, rbx; ho
0x18003d8e8  call    cs:__imp_DeleteObject
0x18003d8ee  xorps   xmm0, xmm0
0x18003d8f1  mov     qword ptr [rsp+380h+Rect.left], r13
0x18003d8f6  mov     edx, 1; dwFlags
0x18003d8fb  mov     rcx, r13; pt
0x18003d8fe  movups  xmmword ptr [rsp+380h+rc.left], xmm0
0x18003d903  call    cs:__imp_MonitorFromPoint
0x18003d909  test    rax, rax
0x18003d90c  jz      short loc_18003D970
0x18003d90e  xor     ecx, ecx
0x18003d910  mov     [rsp+380h+Rect.left], 28h ; '('
0x18003d918  xorps   xmm0, xmm0
0x18003d91b  mov     [rsp+380h+var_30C], ecx
0x18003d91f  mov     rcx, rax; hMonitor
0x18003d922  lea     rdx, [rsp+380h+Rect]; lpmi
0x18003d927  movups  xmmword ptr [rsp+380h+Rect.top], xmm0
0x18003d92c  movups  [rsp+380h+var_31C], xmm0
0x18003d931  call    cs:__imp_GetMonitorInfoW
0x18003d937  movups  xmm0, xmmword ptr [rsp+380h+Rect.top]
0x18003d93c  mov     ecx, 4Dh ; 'M'; nIndex
0x18003d941  movdqu  xmmword ptr [rsp+380h+rc.left], xmm0
0x18003d947  call    cs:__imp_GetSystemMetrics
0x18003d94d  mov     ebx, eax
0x18003d94f  mov     ecx, 4Ch ; 'L'; nIndex
0x18003d954  neg     ebx
0x18003d956  call    cs:__imp_GetSystemMetrics
0x18003d95c  mov     r8d, ebx; dy
0x18003d95f  lea     rcx, [rsp+380h+rc]; lprc
0x18003d964  neg     eax
0x18003d966  mov     edx, eax; dx
0x18003d968  call    cs:__imp_OffsetRect
0x18003d96e  jmp     short loc_18003D97E
0x18003d970  mov     rcx, [r14]; hWnd
0x18003d973  lea     rdx, [rsp+380h+rc]; lpRect
0x18003d978  call    cs:__imp_GetClientRect
0x18003d97e  mov     rcx, cs:g_hinst; hInstance
0x18003d985  lea     r8, [rbp+280h+Buffer]; lpBuffer
0x18003d989  mov     r9d, 20h ; ' '; cchBufferMax
0x18003d98f  mov     edx, 0A73h; uID
0x18003d994  call    cs:__imp_LoadStringW
0x18003d99a  test    eax, eax
0x18003d99c  jz      loc_18003DB10
0x18003d9a2  xor     edx, edx; Val
0x18003d9a4  lea     rcx, [rbp+280h+lf]; void *
0x18003d9a8  lea     r8d, [rdx+5Ch]; Size
0x18003d9ac  call    memset_0
0x18003d9b1  lea     rcx, [rbp+280h+Buffer]
0x18003d9b5  call    cs:__imp__o__wtoi
0x18003d9bb  xor     ecx, ecx
0x18003d9bd  movd    xmm1, eax
0x18003d9c1  cvtdq2ps xmm1, xmm1
0x18003d9c4  call    cs:__imp_ScaleRelativePixelsForDevice
0x18003d9ca  mov     rcx, cs:g_hinst; hInstance
0x18003d9d1  lea     r8, [rbp+280h+lf.lfFaceName]; lpBuffer
0x18003d9d5  neg     eax
0x18003d9d7  mov     r9d, 20h ; ' '; cchBufferMax
0x18003d9dd  mov     edx, 0A72h; uID
0x18003d9e2  mov     [rbp+280h+lf.lfHeight], eax
0x18003d9e5  call    cs:__imp_LoadStringW
0x18003d9eb  test    eax, eax
0x18003d9ed  jz      loc_18003DB10
0x18003d9f3  lea     rcx, [rbp+280h+lf]; lplf
0x18003d9f7  mov     [rbp+280h+lf.lfWeight], 64h ; 'd'
0x18003d9fe  mov     [rbp+280h+lf.lfQuality], r13b
0x18003da02  call    cs:__imp_CreateFontIndirectW
0x18003da08  mov     r15, rax
0x18003da0b  test    rax, rax
0x18003da0e  jz      loc_18003DB10
0x18003da14  mov     rdx, rax; h
0x18003da17  mov     rcx, rsi; hdc
0x18003da1a  call    cs:__imp_SelectObject
0x18003da20  xor     ebx, ebx
0x18003da22  mov     r13, rax
0x18003da25  test    rax, rax
0x18003da28  jz      loc_18003DB04
0x18003da2e  lea     edx, [rbx+1]; mode
0x18003da31  mov     rcx, rsi; hdc
0x18003da34  call    cs:__imp_SetBkMode
0x18003da3a  mov     edx, [rdi+4Ch]; color
0x18003da3d  mov     rcx, rsi; hdc
0x18003da40  call    cs:__imp_SetTextColor
0x18003da46  mov     rcx, cs:g_hinst; hInstance
0x18003da4d  lea     r8, [rbp+280h+chText]; lpBuffer
0x18003da51  mov     r9d, 104h; cchBufferMax
0x18003da57  mov     edx, 0A71h; uID
0x18003da5c  call    cs:__imp_LoadStringW
0x18003da62  test    eax, eax
0x18003da64  jz      loc_18003DAF8
0x18003da6a  mov     rcx, [r14]; hWnd
0x18003da6d  lea     edx, [rbx-14h]; nIndex
0x18003da70  call    cs:__imp_GetWindowLongW
0x18003da76  bt      eax, 16h
0x18003da7a  jb      short loc_18003DAD7
0x18003da7c  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x18003da82  lea     r14d, [rbx+25h]
0x18003da86  cmp     eax, 0FFFFFFFFh
0x18003da89  jnz     short loc_18003DAD2
0x18003da8b  call    cs:__imp_GetUserDefaultUILanguage
0x18003da91  xor     ecx, ecx
0x18003da93  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x18003da9a  test    ax, ax
0x18003da9d  jz      short loc_18003DAC6
0x18003da9f  mov     [rsp+380h+Rect.left], ecx
0x18003daa3  lea     r9d, [rbx+2]; cchData
0x18003daa7  movzx   ecx, ax; Locale
0x18003daaa  lea     r8, [rsp+380h+Rect]; lpLCData
0x18003daaf  mov     edx, 20000070h; LCType
0x18003dab4  call    cs:__imp_GetLocaleInfoW
0x18003daba  test    eax, eax
0x18003dabc  jle     short loc_18003DAC6
0x18003dabe  cmp     [rsp+380h+Rect.left], 1
0x18003dac3  setz    bl
0x18003dac6  xchg    ebx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x18003dacc  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x18003dad2  cmp     eax, 1
0x18003dad5  jnz     short loc_18003DADD
0x18003dad7  mov     r14d, 20025h
0x18003dadd  lea     r9, [rsp+380h+rc]; lprc
0x18003dae2  mov     [rsp+380h+format], r14d; format
0x18003dae7  or      r8d, 0FFFFFFFFh; cchText
0x18003daeb  lea     rdx, [rbp+280h+chText]; lpchText
0x18003daef  mov     rcx, rsi; hdc
0x18003daf2  call    cs:__imp_DrawTextW
0x18003daf8  mov     rdx, r13; h
0x18003dafb  mov     rcx, rsi; hdc
0x18003dafe  call    cs:__imp_SelectObject
0x18003db04  mov     rcx, r15; ho
0x18003db07  call    cs:__imp_DeleteObject
0x18003db0d  xor     r13d, r13d
0x18003db10  cmp     rsi, [rdi+28h]
0x18003db14  jnz     short loc_18003DB88
0x18003db16  mov     rcx, [rdi+30h]; h
0x18003db1a  lea     r8, [rsp+380h+Rect]; pv
0x18003db1f  xorps   xmm0, xmm0
0x18003db22  mov     edx, 20h ; ' '; c
0x18003db27  movups  xmmword ptr [rsp+380h+Rect.left], xmm0
0x18003db2c  movups  xmmword ptr [rsp+60h], xmm0
0x18003db31  call    cs:__imp_GetObjectW
0x18003db37  test    eax, eax
0x18003db39  jz      short loc_18003DB88
0x18003db3b  xor     edx, edx; l
0x18003db3d  mov     rcx, r12; hdc
0x18003db40  call    cs:__imp_SetLayout
0x18003db46  mov     rcx, [rdi+28h]; hdc
0x18003db4a  xor     edx, edx; l
0x18003db4c  call    cs:__imp_SetLayout
0x18003db52  mov     rax, [rdi+28h]
0x18003db56  xor     r8d, r8d; y
0x18003db59  mov     r9d, [rsp+380h+Rect.top]; cx
0x18003db5e  xor     edx, edx; x
0x18003db60  mov     [rsp+380h+rop], 0CC0020h; rop
0x18003db68  mov     rcx, r12; hdc
0x18003db6b  mov     [rsp+380h+y1], r13d; y1
0x18003db70  mov     [rsp+380h+x1], r13d; x1
0x18003db75  mov     [rsp+380h+hdcSrc], rax; hdcSrc
0x18003db7a  mov     eax, [rsp+380h+Rect.right]
0x18003db7e  mov     [rsp+380h+format], eax; cy
0x18003db82  call    cs:__imp_BitBlt
0x18003db88  mov     rcx, [rbp+280h+var_40]
0x18003db8f  xor     rcx, rsp; StackCookie
0x18003db92  call    __security_check_cookie
0x18003db97  mov     rbx, [rsp+380h+arg_10]
0x18003db9f  add     rsp, 350h
0x18003dba6  pop     r15
0x18003dba8  pop     r14
0x18003dbaa  pop     r13
0x18003dbac  pop     r12
0x18003dbae  pop     rdi
0x18003dbaf  pop     rsi
0x18003dbb0  pop     rbp
0x18003dbb1  retn
```
