# AnimateWindow

- ea: `0x180035be0`
- end: `0x180036bbd`
- name: `AnimateWindow`
- size: `4061`
- prototype: `BOOL __stdcall(HWND hWnd, DWORD dwTime, DWORD dwFlags)`
- caller_count: `2`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030f00`
- `0x180076168`

## callees

- `0x18000d210`
- `0x18000e110`
- `0x180035be0`
- `0x180036bc4`
- `0x1800374d0`
- `0x180037930`
- `0x180045830`
- `0x180052258`
- `0x18005c0b4`
- `0x18005cc64`
- `0x18005d130`
- `0x18006736c`
- `0x18006843c`
- `0x180073718`
- `0x180091320`
- `0x1800913c0`
- `0x180091414`
- `0x180096e00`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserUpdateWindows` at `0x180036390`
- `win32u!NtUserUpdateWindows` at `0x180036390`
- `win32u!NtUserShowWindow` at `0x18009c3f7`
- `win32u!NtUserShowWindow` at `0x18009c3f7`
- `win32u!NtUserSetWindowPos` at `0x1800369b6`
- `win32u!NtUserSetWindowPos` at `0x18009c3dc`
- `win32u!NtUserSetWindowPos` at `0x18009c497`
- `win32u!NtUserSetWindowPos` at `0x18009c4c6`
- `win32u!NtUserSetWindowPos` at `0x1800369b6`
- `win32u!NtUserSetWindowPos` at `0x18009c3dc`
- `win32u!NtUserSetWindowPos` at `0x18009c497`
- `win32u!NtUserSetWindowPos` at `0x18009c4c6`
- `win32u!NtUserRedrawWindow` at `0x18003636d`
- `win32u!NtUserRedrawWindow` at `0x1800364a3`
- `win32u!NtUserRedrawWindow` at `0x18003636d`
- `win32u!NtUserRedrawWindow` at `0x1800364a3`
- `win32u!NtUserGetDCEx` at `0x180035c8f`
- `win32u!NtUserGetDCEx` at `0x180035c8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036152`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036184`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800363fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036152`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180036184`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800363fd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800361e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800361e3`
- `GDI32!SelectObject` at `0x180036069`
- `GDI32!SelectObject` at `0x180036069`
- `GDI32!GetLayout` at `0x180035ce8`
- `GDI32!GetLayout` at `0x180035ce8`
- `GDI32!MirrorRgn` at `0x18003697d`
- `GDI32!MirrorRgn` at `0x18003697d`
- `GDI32!OffsetRgn` at `0x1800362f0`
- `GDI32!OffsetRgn` at `0x18009c2f9`
- `GDI32!OffsetRgn` at `0x18009c33f`
- `GDI32!OffsetRgn` at `0x1800362f0`
- `GDI32!OffsetRgn` at `0x18009c2f9`
- `GDI32!OffsetRgn` at `0x18009c33f`
- `GDI32!CreateRectRgnIndirect` at `0x18003627c`
- `GDI32!CreateRectRgnIndirect` at `0x18003627c`
- `GDI32!SetRectRgn` at `0x180035e43`
- `GDI32!SetRectRgn` at `0x18009c291`
- `GDI32!SetRectRgn` at `0x180035e43`
- `GDI32!SetRectRgn` at `0x18009c291`
- `GDI32!CombineRgn` at `0x1800362bd`
- `GDI32!CombineRgn` at `0x18003631a`
- `GDI32!CombineRgn` at `0x180036836`
- `GDI32!CombineRgn` at `0x18009c270`
- `GDI32!CombineRgn` at `0x18009c320`
- `GDI32!CombineRgn` at `0x1800362bd`
- `GDI32!CombineRgn` at `0x18003631a`
- `GDI32!CombineRgn` at `0x180036836`
- `GDI32!CombineRgn` at `0x18009c270`
- `GDI32!CombineRgn` at `0x18009c320`
- `GDI32!CreateRectRgn` at `0x180035df2`
- `GDI32!CreateRectRgn` at `0x180035e13`
- `GDI32!CreateRectRgn` at `0x1800367ef`
- `GDI32!CreateRectRgn` at `0x18003684b`
- `GDI32!CreateRectRgn` at `0x180035df2`
- `GDI32!CreateRectRgn` at `0x180035e13`
- `GDI32!CreateRectRgn` at `0x1800367ef`
- `GDI32!CreateRectRgn` at `0x18003684b`
- `GDI32!DeleteDC` at `0x1800366ed`
- `GDI32!DeleteDC` at `0x1800366ed`
- `GDI32!BitBlt` at `0x1800363df`
- `GDI32!BitBlt` at `0x1800363df`
- `GDI32!CreateCompatibleDC` at `0x180035e69`
- `GDI32!CreateCompatibleDC` at `0x180035e69`
- `GDI32!DeleteObject` at `0x180036025`
- `GDI32!DeleteObject` at `0x18003661e`
- `GDI32!DeleteObject` at `0x18003662c`
- `GDI32!DeleteObject` at `0x180036ba4`
- `GDI32!DeleteObject` at `0x180036bb2`
- `GDI32!DeleteObject` at `0x180036025`
- `GDI32!DeleteObject` at `0x18003661e`
- `GDI32!DeleteObject` at `0x18003662c`
- `GDI32!DeleteObject` at `0x180036ba4`
- `GDI32!DeleteObject` at `0x180036bb2`

## pseudocode

```c
BOOL __stdcall AnimateWindow(HWND hWnd, DWORD dwTime, DWORD dwFlags)
{
  HWND v3; // r12
  DWORD v6; // r15d
  HDC DCEx; // rax
  PVOID *v8; // rcx
  struct tagWND *v9; // r8
  __m128i v10; // xmm6
  __int64 v11; // rbx
  __int64 v12; // rdx
  HRGN v13; // rdi
  int v14; // eax
  HDC CompatibleDC; // rax
  unsigned int v16; // r8d
  __int64 v17; // rcx
  PVOID *v18; // r10
  HRGN v19; // rbx
  HRGN v20; // rdi
  HBITMAP v21; // r14
  HRGN v22; // r15
  HBITMAP v24; // rax
  DWORD v25; // eax
  signed int v26; // r12d
  int v27; // ebx
  int v28; // edi
  int v29; // r14d
  int v30; // r10d
  int v31; // eax
  int v32; // ecx
  PVOID *v33; // rcx
  int v34; // r8d
  int v35; // eax
  LONG v36; // r9d
  LONG v37; // r12d
  unsigned int v38; // r8d
  int v39; // ebp
  LONG v40; // r14d
  int v41; // ebx
  int y1; // edi
  HRGN v43; // rax
  unsigned int v44; // ebx
  DWORD v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  PVOID *v48; // rcx
  DWORD v49; // eax
  __int64 (__fastcall *v50)(int, int, int); // rax
  int v51; // eax
  __int64 (__fastcall *v52)(int, int, int); // rax
  HRGN RectRgn; // rax
  HRGN v54; // rax
  int v55; // ecx
  __int64 v56; // rdx
  __m128i v57; // xmm6
  __m128i v58; // xmm0
  __int64 v59; // rbx
  HRGN v60; // rdx
  int v61; // eax
  int v62; // ebx
  int v63; // eax
  int x1; // [rsp+30h] [rbp-168h]
  unsigned int cy; // [rsp+50h] [rbp-148h]
  int v67; // [rsp+60h] [rbp-138h]
  DWORD v68; // [rsp+64h] [rbp-134h]
  int v69; // [rsp+68h] [rbp-130h]
  int v70; // [rsp+6Ch] [rbp-12Ch]
  int v72; // [rsp+74h] [rbp-124h]
  int v73; // [rsp+78h] [rbp-120h]
  int v74; // [rsp+80h] [rbp-118h]
  int bottom; // [rsp+88h] [rbp-110h]
  HRGN hrgnSrc1; // [rsp+90h] [rbp-108h]
  int v77; // [rsp+98h] [rbp-100h]
  int v78; // [rsp+9Ch] [rbp-FCh]
  DWORD v79; // [rsp+A0h] [rbp-F8h]
  unsigned int v80; // [rsp+A4h] [rbp-F4h]
  int v81; // [rsp+A8h] [rbp-F0h]
  struct tagWND *v82; // [rsp+B0h] [rbp-E8h]
  HRGN hrgnSrc2; // [rsp+B8h] [rbp-E0h]
  HRGN hRgn; // [rsp+C0h] [rbp-D8h]
  HBITMAP ho; // [rsp+C8h] [rbp-D0h]
  char Layout; // [rsp+D0h] [rbp-C8h]
  int v87; // [rsp+D0h] [rbp-C8h]
  int v88; // [rsp+D4h] [rbp-C4h]
  int v89; // [rsp+D8h] [rbp-C0h]
  HRGN hrgnDst; // [rsp+E0h] [rbp-B8h]
  HDC hdcSrc; // [rsp+E8h] [rbp-B0h]
  HDC hdc; // [rsp+F0h] [rbp-A8h]
  DWORD TickCount; // [rsp+F8h] [rbp-A0h]
  int v94; // [rsp+FCh] [rbp-9Ch]
  int v95; // [rsp+100h] [rbp-98h]
  DWORD v96; // [rsp+104h] [rbp-94h]
  int y; // [rsp+108h] [rbp-90h]
  int v98; // [rsp+10Ch] [rbp-8Ch]
  int v99; // [rsp+110h] [rbp-88h]
  int x[2]; // [rsp+118h] [rbp-80h]
  __int64 v101; // [rsp+130h] [rbp-68h]
  RECT rect; // [rsp+138h] [rbp-60h] BYREF

  v3 = hWnd;
  rect = 0;
  if ( (dwFlags & 0x8001F) == 0 || (dwFlags & 0xFFF0FFE0) != 0 )
    return 0;
  v82 = ValidateHwnd(hWnd);
  if ( !v82 )
    return 0;
  v6 = dwFlags & 0x10000;
  if ( IsWindowVisible(v3) )
  {
    if ( !v6 )
      return 0;
  }
  else if ( v6 )
  {
    return 0;
  }
  DCEx = (HDC)NtUserGetDCEx(v3, 0, 65539);
  hdc = DCEx;
  if ( !DCEx )
    return 0;
  hdcSrc = 0;
  hRgn = 0;
  hrgnDst = 0;
  hrgnSrc1 = 0;
  hrgnSrc2 = 0;
  ho = 0;
  v73 = 0;
  v95 = 0;
  v72 = 0;
  Layout = GetLayout(DCEx);
  if ( v6 )
  {
    v81 = 0;
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v89 = 1;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v89 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v81 = 1;
  }
  if ( (dwFlags & 0x20000) != 0 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    {
      WPP_SF_(v8[2], 12, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v72 = 1;
  }
  v9 = v82;
  v10 = *(__m128i *)((char *)v82 + 88);
  v11 = *((_QWORD *)v82 + 12);
  v12 = *((_QWORD *)v82 + 11);
  *(_QWORD *)x = v12;
  v74 = v11 - v12;
  if ( (_DWORD)v11 == (_DWORD)v12 )
    goto LABEL_35;
  bottom = HIDWORD(v11) - HIDWORD(v12);
  if ( HIDWORD(v11) == HIDWORD(v12) )
    goto LABEL_35;
  v98 = 0;
  v101 = 0;
  if ( (*((_BYTE *)v82 + 31) & 0x40) != 0 && *((_QWORD *)v82 + 6) )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
    {
      WPP_SF_(v8[2], 13, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
      v9 = v82;
    }
    if ( (dwFlags & 0x80000) != 0 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      {
        WPP_SF_(v8[2], 14, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
        goto LABEL_224;
      }
      goto LABEL_35;
    }
    v98 = 1;
    if ( GetParent(v9) )
      v101 = *(_QWORD *)GetParent(v9);
    else
      v101 = 0;
  }
  v88 = 0;
  if ( (*((_BYTE *)v9 + 31) & 2) != 0 )
  {
    v88 = 1;
    ClearWindowState(v9, 0xF02u);
    v9 = v82;
  }
  if ( *((_QWORD *)v9 + 21) )
  {
    RectRgn = CreateRectRgn(0, 0, 0, 0);
    hRgn = RectRgn;
    v13 = RectRgn;
    if ( !RectRgn || !GetWindowRgn(v3, RectRgn) )
      goto LABEL_33;
  }
  else
  {
    v13 = 0;
  }
  v95 = 1;
  hrgnDst = CreateRectRgn(0, 0, 0, 0);
  if ( !hrgnDst )
    goto LABEL_33;
  hrgnSrc1 = CreateRectRgn(0, 0, 0, 0);
  if ( !hrgnSrc1 )
    goto LABEL_33;
  if ( v6 )
    v14 = v13 ? CombineRgn(hrgnSrc1, v13, 0, 5) : SetRectRgn(hrgnSrc1, 0, 0, v74, bottom);
  else
    v14 = SetRectRgn(hrgnSrc1, 0, 0, 0, 0);
  if ( !v14 )
    goto LABEL_33;
  if ( (dwFlags & 0x80000) == 0 )
  {
    v54 = CreateRectRgn(0, 0, 0, 0);
    if ( !v54 )
      goto LABEL_33;
    RealSetWindowRgn(v3, v54, 0);
    if ( !v6 )
    {
      ShowWindowNoRepaint(v82);
      v81 = 0;
    }
  }
  CompatibleDC = CreateCompatibleDC(hdc);
  hdcSrc = CompatibleDC;
  if ( !CompatibleDC )
    goto LABEL_33;
  ho = TakeWindowSnapshot(v3, hdc, CompatibleDC);
  if ( !ho )
    goto LABEL_33;
  v16 = x[0];
  v17 = *(_QWORD *)x - *((_QWORD *)v82 + 11);
  if ( *(_QWORD *)x == *((_QWORD *)v82 + 11) )
    v17 = v11 - *((_QWORD *)v82 + 12);
  if ( !v17 )
  {
    v24 = ho;
    y = _mm_cvtsi128_si32(_mm_srli_si128(v10, 4));
    goto LABEL_54;
  }
  v18 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      v18 = (PVOID *)WPP_GLOBAL_Control;
      v16 = x[0];
    }
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 && *((_BYTE *)v18 + 25) >= 4u )
    {
      WPP_SF_dddd(
        v18[2],
        16,
        &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids,
        v16,
        _mm_cvtsi128_si32(_mm_srli_si128(v10, 4)),
        v11,
        _mm_cvtsi128_si32(_mm_srli_si128(v10, 12)));
      v18 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v57 = *(__m128i *)((char *)v82 + 88);
  v58 = _mm_loadl_epi64((const __m128i *)v82 + 6);
  v59 = *((_QWORD *)v82 + 11);
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 2) != 0 && *((_BYTE *)v18 + 25) >= 4u )
    WPP_SF_dddd(
      v18[2],
      17,
      &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids,
      (unsigned int)v59,
      HIDWORD(v59),
      _mm_cvtsi128_si32(v58),
      v58.m128i_i32[1]);
  v60 = hRgn;
  if ( hRgn )
  {
    if ( GetWindowRgn(v3, hRgn) )
    {
      v60 = hRgn;
      goto LABEL_240;
    }
LABEL_33:
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_34:
    if ( v88 )
    {
      SetWindowState(v82, 0xF02u);
LABEL_224:
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_35:
    if ( v89 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
        WPP_SF_(v8[2], 26, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      NtUserShowWindow(v3, 0);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v95 )
      goto LABEL_131;
    goto LABEL_37;
  }
LABEL_240:
  v61 = v58.m128i_i32[0] - v59;
  x[0] = v59;
  v74 = v58.m128i_i32[0] - v59;
  y = _mm_cvtsi128_si32(_mm_srli_si128(v57, 4));
  v62 = _mm_cvtsi128_si32(_mm_srli_si128(v57, 12)) - y;
  if ( v6 )
  {
    if ( v60 )
      v63 = CombineRgn(hrgnSrc1, v60, 0, 5);
    else
      v63 = SetRectRgn(hrgnSrc1, 0, 0, v61, v62);
  }
  else
  {
    v63 = SetRectRgn(hrgnSrc1, 0, 0, 0, 0);
  }
  if ( !v63 )
    goto LABEL_33;
  DeleteObject(ho);
  v24 = TakeWindowSnapshot(v3, hdc, hdcSrc);
  ho = v24;
  if ( !v24 )
    goto LABEL_33;
  bottom = v62;
LABEL_54:
  SelectObject(hdcSrc, v24);
  v25 = 165;
  if ( dwTime )
    v25 = dwTime;
  v79 = v25;
  if ( (dwFlags & 0x80000) != 0 )
  {
    v73 = AnimateBlend(v82, hdc, hdcSrc, v25, v6, v72);
    if ( v73 )
    {
      v89 = 0;
      v81 = 0;
    }
    goto LABEL_33;
  }
  v87 = Layout & 1;
  v26 = 0;
  v94 = 1;
  cy = 0;
  if ( v6 )
  {
    v27 = bottom;
    v28 = v74;
  }
  else
  {
    v27 = 0;
    v28 = 0;
  }
  v29 = 0;
  v67 = 0;
  if ( (dwFlags & 0x10) == 0 )
  {
    v96 = dwFlags & 0x40000;
    if ( (dwFlags & 1) != 0 )
    {
      v30 = v6 != 0 ? v74 : 0;
      v31 = -(v6 != 0);
    }
    else
    {
      if ( (dwFlags & 2) == 0 )
      {
        v78 = 0;
        v29 = v74;
        v69 = 0;
        v67 = v74;
LABEL_66:
        if ( (dwFlags & 4) != 0 )
        {
          v70 = -(v6 != 0);
          v77 = bottom & v70;
        }
        else if ( (dwFlags & 8) != 0 )
        {
          v55 = bottom;
          if ( v6 )
            v55 = 0;
          v77 = v55;
          v70 = (v6 != 0) - 1;
        }
        else
        {
          v77 = 0;
          v26 = bottom;
          v70 = 0;
          cy = bottom;
        }
        goto LABEL_69;
      }
      v30 = v74;
      if ( v6 )
        v30 = 0;
      v31 = (v6 != 0) - 1;
    }
    v78 = v30;
    v69 = v31;
    goto LABEL_66;
  }
  v96 = 0;
  v70 = -1;
  v77 = bottom / 2;
  v69 = -1;
  v78 = v74 / 2;
LABEL_69:
  TickCount = GetTickCount();
  v80 = 0;
  do
  {
    while ( 1 )
    {
      v32 = GetTickCount() - TickCount;
      v68 = v32;
      if ( (dwFlags & 0x13) != 0 )
      {
        v50 = AnimDec;
        if ( !v6 )
          v50 = AnimInc;
        v51 = v50(v74, v32, v79);
        v32 = v68;
        v29 = v51;
        v67 = v51;
      }
      if ( (dwFlags & 0x1C) != 0 )
      {
        v52 = AnimDec;
        if ( !v6 )
          v52 = AnimInc;
        v26 = v52(bottom, v32, v79);
        cy = v26;
      }
      if ( v68 > v79 )
      {
        v33 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
          v33 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v6 )
        {
          v26 = 0;
          v29 = 0;
          cy = 0;
          v67 = 0;
        }
        else
        {
          v26 = bottom;
          v29 = v74;
          cy = bottom;
          v67 = v74;
        }
      }
      else
      {
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v28 != v29 || v27 != v26 )
        break;
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 2) != 0 && *((_BYTE *)v33 + 25) >= 4u )
        WPP_SF_(v33[2], 19, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      Sleep(1u);
    }
    if ( (dwFlags & 0x10) != 0 )
    {
      v34 = v29 / 2;
      v35 = v26 / 2;
    }
    else
    {
      v34 = v29;
      v35 = v26;
    }
    v36 = v70 * v35 + v77;
    v37 = v69 * v34 + v78;
    v99 = v36;
    v38 = cy;
    rect.left = v37;
    rect.top = v36;
    rect.right = v37 + v29;
    rect.bottom = v36 + cy;
    if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 2) != 0 && *((_BYTE *)v33 + 25) >= 5u )
    {
      WPP_SF_ddddd(v33[2], v36 + cy, cy, v80, v37, v36, v37 + v29, v36 + cy);
      v36 = v99;
      v38 = cy;
    }
    if ( !v96 )
    {
      v39 = 0;
      v40 = v37;
      v41 = 0;
      y1 = v36;
      goto LABEL_83;
    }
    if ( (dwFlags & 1) != 0 )
    {
      if ( v6 )
      {
        v40 = 0;
LABEL_121:
        v39 = v37;
        goto LABEL_122;
      }
    }
    else
    {
      if ( (dwFlags & 2) == 0 )
      {
        v40 = v37;
        goto LABEL_120;
      }
      if ( !v6 )
      {
        v40 = 0;
        goto LABEL_120;
      }
    }
    v40 = v74 - v67;
LABEL_120:
    if ( !v40 )
      goto LABEL_121;
    v39 = -v40;
LABEL_122:
    if ( (dwFlags & 4) != 0 )
    {
      if ( v6 )
      {
        y1 = 0;
LABEL_126:
        v41 = v36;
        goto LABEL_83;
      }
    }
    else
    {
      if ( (dwFlags & 8) == 0 )
      {
        y1 = v36;
        goto LABEL_125;
      }
      if ( !v6 )
      {
        y1 = 0;
        goto LABEL_125;
      }
    }
    y1 = bottom - v38;
LABEL_125:
    if ( !y1 )
      goto LABEL_126;
    v41 = -y1;
LABEL_83:
    v43 = CreateRectRgnIndirect(&rect);
    hrgnSrc2 = v43;
    if ( !v43 )
      goto LABEL_32;
    if ( hRgn )
    {
      if ( !OffsetRgn(hRgn, v39, v41) || !CombineRgn(hrgnSrc2, hRgn, hrgnSrc2, 1) || !OffsetRgn(hRgn, -v39, -v41) )
        goto LABEL_32;
      v43 = hrgnSrc2;
    }
    if ( !CombineRgn(hrgnDst, hrgnSrc1, v43, 4) )
      goto LABEL_32;
    if ( v87 )
      MirrorRgn(hWnd, hrgnDst);
    if ( !OffsetRgn(hrgnDst, x[0], y) || !CombineRgn(hrgnSrc1, hrgnSrc2, 0, 5) || !RealSetWindowRgn(hWnd, hrgnSrc2, 0) )
      goto LABEL_32;
    hrgnSrc2 = 0;
    if ( v94 && v72 )
      NtUserSetWindowPos(hWnd, 0, 0, 0, 0, 0, 523);
    if ( !(unsigned int)NtUserRedrawWindow(0, 0, hrgnDst, 1157) )
    {
LABEL_32:
      v3 = hWnd;
      goto LABEL_33;
    }
    if ( v98 && !(unsigned int)NtUserUpdateWindows(v101, hrgnDst) )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      v3 = hWnd;
      goto LABEL_34;
    }
    x1 = v40;
    v29 = v67;
    if ( !BitBlt(hdc, v37, v99, v67, cy, hdcSrc, x1, y1, 0x80CC0020) )
      goto LABEL_32;
    v44 = ++v80;
    v45 = GetTickCount();
    v48 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dL(*((_QWORD *)WPP_GLOBAL_Control + 2), v46, v47, v44, v45 - v68 - TickCount);
      v48 = (PVOID *)WPP_GLOBAL_Control;
    }
    v49 = v68;
    if ( v68 > v79 )
    {
      if ( v48 == &WPP_GLOBAL_Control )
        goto LABEL_105;
      if ( (*((_BYTE *)v48 + 28) & 2) != 0 && *((_BYTE *)v48 + 25) >= 4u )
      {
        v56 = 23;
LABEL_255:
        WPP_SF_(v48[2], v56, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
        v49 = v68;
        v48 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_256:
      if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 2) != 0 && *((_BYTE *)v48 + 25) >= 4u )
        WPP_SF_dd(v48[2], 25, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids, v49, v44);
      goto LABEL_105;
    }
    if ( v6 )
    {
      if ( !v67 )
        goto LABEL_104;
      v26 = cy;
      if ( !cy )
        goto LABEL_104;
    }
    else
    {
      v26 = cy;
    }
    v94 = 0;
    v28 = v67;
    v27 = v26;
  }
  while ( v6 || v67 != v74 || v26 != bottom );
  v44 = v80;
LABEL_104:
  if ( v48 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v48 + 28) & 2) != 0 && *((_BYTE *)v48 + 25) >= 4u )
    {
      v56 = 24;
      goto LABEL_255;
    }
    goto LABEL_256;
  }
LABEL_105:
  v73 = 1;
  if ( !v6 )
  {
    v3 = hWnd;
    NtUserRedrawWindow(hWnd, 0, 0, 2104);
    goto LABEL_33;
  }
  if ( v88 )
    SetWindowState(v82, 0xF02u);
  v3 = hWnd;
  NtUserSetWindowPos(hWnd, 0, 0, 0, 0, 0, 671);
LABEL_131:
  RealSetWindowRgn(v3, hRgn, 0);
  v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_37:
  if ( !v81 )
  {
    if ( v72 )
    {
      if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
        WPP_SF_(v8[2], 29, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
      NtUserSetWindowPos(v3, 0, 0, 0, 0, 0, 547);
    }
    goto LABEL_39;
  }
  if ( v72 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      WPP_SF_(v8[2], 27, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
    NtUserSetWindowPos(v3, 0, 0, 0, 0, 0, 611);
LABEL_39:
    v19 = hrgnSrc2;
    v20 = hrgnSrc1;
    v21 = ho;
    v22 = hrgnDst;
  }
  else
  {
    v21 = ho;
    v19 = hrgnSrc2;
    v20 = hrgnSrc1;
    v22 = hrgnDst;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      WPP_SF_(v8[2], 28, &WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids);
    NtUserSetWindowPos(v3, 0, 0, 0, 0, 0, 599);
  }
  if ( hdcSrc )
    DeleteDC(hdcSrc);
  if ( v21 )
    DeleteObject(v21);
  ReleaseDC(v3, hdc);
  if ( v19 )
    DeleteObject(v19);
  if ( v20 )
    DeleteObject(v20);
  if ( v22 )
    DeleteObject(v22);
  return v73;
}

```

## disassembly

```asm
0x180035be0  mov     r11, rsp
0x180035be3  mov     [r11+18h], rbx
0x180035be7  push    rbp
0x180035be8  push    rsi
0x180035be9  push    rdi
0x180035bea  push    r12
0x180035bec  push    r13
0x180035bee  push    r14
0x180035bf0  push    r15
0x180035bf2  sub     rsp, 160h
0x180035bf9  movaps  xmmword ptr [r11-48h], xmm6
0x180035bfe  mov     rax, cs:__security_cookie
0x180035c05  xor     rax, rsp
0x180035c08  mov     [rsp+198h+var_50], rax
0x180035c10  test    r8d, 8001Fh
0x180035c17  mov     [rsp+198h+var_140], rcx
0x180035c1c  mov     r12, rcx
0x180035c1f  mov     ebx, r8d
0x180035c22  setnz   cl
0x180035c25  mov     [rsp+198h+var_128], ebx
0x180035c29  test    r8d, 0FFF0FFE0h
0x180035c30  xorps   xmm0, xmm0
0x180035c33  mov     r14d, edx
0x180035c36  setz    al
0x180035c39  movups  xmmword ptr [r11-60h], xmm0
0x180035c3e  test    al, cl
0x180035c40  jz      loc_180036701
0x180035c46  mov     rcx, r12; HWND
0x180035c49  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x180035c4e  xor     edi, edi
0x180035c50  mov     [rsp+198h+var_E8], rax
0x180035c58  test    rax, rax
0x180035c5b  jz      loc_180036701
0x180035c61  mov     r15d, ebx
0x180035c64  mov     rcx, r12; hWnd
0x180035c67  and     r15d, 10000h
0x180035c6e  call    IsWindowVisible
0x180035c73  test    eax, eax
0x180035c75  jnz     loc_1800366F8
0x180035c7b  test    r15d, r15d
0x180035c7e  jnz     loc_180036701
0x180035c84  xor     edx, edx
0x180035c86  mov     r8d, 10003h
0x180035c8c  mov     rcx, r12
0x180035c8f  call    cs:__imp_NtUserGetDCEx
0x180035c95  mov     [rsp+198h+hdc], rax
0x180035c9d  test    rax, rax
0x180035ca0  jz      loc_180036701
0x180035ca6  mov     rcx, rax; hdc
0x180035ca9  mov     [rsp+198h+var_B0], rdi
0x180035cb1  mov     [rsp+198h+hRgn], rdi
0x180035cb9  mov     [rsp+198h+hrgnDst], rdi
0x180035cc1  mov     [rsp+198h+hrgnSrc1], rdi
0x180035cc9  mov     [rsp+198h+hrgnSrc2], rdi
0x180035cd1  mov     [rsp+198h+ho], rdi
0x180035cd9  mov     [rsp+198h+var_120], edi
0x180035cdd  mov     [rsp+198h+var_98], edi
0x180035ce4  mov     [rsp+198h+var_124], edi
0x180035ce8  call    cs:__imp_GetLayout
0x180035cee  mov     [rsp+198h+var_C8], eax
0x180035cf5  test    r15d, r15d
0x180035cf8  jz      loc_18009C03C
0x180035cfe  mov     [rsp+198h+var_F0], edi
0x180035d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d0c  lea     rbp, WPP_GLOBAL_Control
0x180035d13  lea     rdi, WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids
0x180035d1a  mov     r13d, 4
0x180035d20  lea     esi, [r13-2]
0x180035d24  cmp     rcx, rbp
0x180035d27  jnz     loc_180036708
0x180035d2d  mov     [rsp+198h+var_C0], 1
0x180035d38  bt      ebx, 11h
0x180035d3c  jb      loc_180036739
0x180035d42  mov     r8, [rsp+198h+var_E8]
0x180035d4a  movups  xmm6, xmmword ptr [r8+58h]
0x180035d4f  mov     rbx, [r8+60h]
0x180035d53  mov     eax, ebx
0x180035d55  movq    rdx, xmm6
0x180035d5a  sub     eax, edx
0x180035d5c  mov     qword ptr [rsp+198h+x], rdx
0x180035d64  mov     [rsp+198h+var_118], rax
0x180035d6c  jz      loc_180035F30
0x180035d72  mov     rax, rdx
0x180035d75  mov     rdx, rbx
0x180035d78  shr     rdx, 20h
0x180035d7c  shr     rax, 20h
0x180035d80  sub     edx, eax
0x180035d82  mov     [rsp+198h+var_110], rdx
0x180035d8a  jz      loc_180035F30
0x180035d90  test    byte ptr [r8+1Fh], 40h
0x180035d95  mov     [rsp+198h+var_8C], 0
0x180035da0  mov     [rsp+198h+var_68], 0
0x180035dac  jnz     loc_180036773
0x180035db2  mov     [rsp+198h+var_C4], 0
0x180035dbd  test    [r8+1Fh], sil
0x180035dc1  jnz     loc_1800367C0
0x180035dc7  cmp     qword ptr [r8+0A8h], 0
0x180035dcf  jnz     loc_1800367E5
0x180035dd5  mov     rdi, [rsp+198h+hRgn]
0x180035ddd  xor     r9d, r9d; y2
0x180035de0  mov     [rsp+198h+var_98], 1
0x180035deb  xor     r8d, r8d; x2
0x180035dee  xor     edx, edx; y1
0x180035df0  xor     ecx, ecx; x1
0x180035df2  call    cs:__imp_CreateRectRgn
0x180035df8  mov     [rsp+198h+hrgnDst], rax
0x180035e00  test    rax, rax
0x180035e03  jz      loc_180035F1B
0x180035e09  xor     r9d, r9d; y2
0x180035e0c  xor     r8d, r8d; x2
0x180035e0f  xor     edx, edx; y1
0x180035e11  xor     ecx, ecx; x1
0x180035e13  call    cs:__imp_CreateRectRgn
0x180035e19  mov     [rsp+198h+hrgnSrc1], rax
0x180035e21  mov     rcx, rax; hrgnDst
0x180035e24  test    rax, rax
0x180035e27  jz      loc_180035F1B
0x180035e2d  test    r15d, r15d
0x180035e30  jnz     loc_180036821
0x180035e36  mov     [rsp+198h+bottom], r15d; bottom
0x180035e3b  xor     r9d, r9d; right
0x180035e3e  xor     r8d, r8d; top
0x180035e41  xor     edx, edx; left
0x180035e43  call    cs:__imp_SetRectRgn
0x180035e49  test    eax, eax
0x180035e4b  jz      loc_180035F1B
0x180035e51  mov     edi, [rsp+198h+var_128]
0x180035e55  and     edi, 80000h
0x180035e5b  jz      loc_180036841
0x180035e61  mov     rcx, [rsp+198h+hdc]; hdc
0x180035e69  call    cs:__imp_CreateCompatibleDC
0x180035e6f  mov     [rsp+198h+var_B0], rax
0x180035e77  test    rax, rax
0x180035e7a  jz      loc_180035F1B
0x180035e80  mov     rdx, [rsp+198h+hdc]; hdc
0x180035e88  mov     r8, rax; HDC
0x180035e8b  mov     rcx, r12; hWnd
0x180035e8e  call    ?TakeWindowSnapshot@@YAPEAUHBITMAP__@@PEAUHWND__@@PEAUHDC__@@1@Z; TakeWindowSnapshot(HWND__ *,HDC__ *,HDC__ *)
0x180035e93  mov     [rsp+198h+ho], rax
0x180035e9b  test    rax, rax
0x180035e9e  jz      short loc_180035F1B
0x180035ea0  mov     rax, [rsp+198h+var_E8]
0x180035ea8  mov     r8, qword ptr [rsp+198h+x]
0x180035eb0  mov     rcx, r8
0x180035eb3  sub     rcx, [rax+58h]
0x180035eb7  jnz     short loc_180035EC0
0x180035eb9  mov     rcx, rbx
0x180035ebc  sub     rcx, [rax+60h]
0x180035ec0  test    rcx, rcx
0x180035ec3  jz      loc_180036005
0x180035ec9  mov     r10, cs:WPP_GLOBAL_Control
0x180035ed0  cmp     r10, rbp
0x180035ed3  jz      loc_18009C18E
0x180035ed9  test    [r10+1Ch], sil
0x180035edd  jz      loc_18009C140
0x180035ee3  cmp     [r10+19h], r13b
0x180035ee7  jb      loc_18009C140
0x180035eed  mov     rcx, [r10+10h]
0x180035ef1  lea     r8, WPP_f3c2c0ad0e433deb9614afee938c3690_Traceguids
0x180035ef8  mov     edx, 0Fh
0x180035efd  call    WPP_SF_
0x180035f02  mov     r10, cs:WPP_GLOBAL_Control
0x180035f09  mov     r8, qword ptr [rsp+198h+x]
0x180035f11  jmp     loc_18009C140
0x180035f16  mov     r12, [rsp+198h+var_140]
0x180035f1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180035f22  cmp     [rsp+198h+var_C4], 0
0x180035f2a  jnz     loc_180036ACF
0x180035f30  cmp     [rsp+198h+var_C0], 0
0x180035f38  jnz     loc_180036AE7
0x180035f3e  lea     rbp, WPP_GLOBAL_Control
0x180035f45  cmp     [rsp+198h+var_98], 0
0x180035f4d  jnz     loc_1800365FC
0x180035f53  cmp     [rsp+198h+var_F0], 0
0x180035f5b  jnz     loc_180036B26
0x180035f61  cmp     [rsp+198h+var_124], 0
0x180035f66  jnz     loc_180036B69
0x180035f6c  mov     rbx, [rsp+198h+hrgnSrc2]
0x180035f74  mov     rdi, [rsp+198h+hrgnSrc1]
0x180035f7c  mov     r14, [rsp+198h+ho]
0x180035f84  mov     r15, [rsp+198h+hrgnDst]
0x180035f8c  mov     rax, [rsp+198h+var_B0]
0x180035f94  test    rax, rax
0x180035f97  jnz     loc_1800366EA
0x180035f9d  test    r14, r14
0x180035fa0  jnz     loc_18003661B
0x180035fa6  mov     rdx, [rsp+198h+hdc]; hDC
0x180035fae  mov     rcx, r12; hWnd
0x180035fb1  call    ReleaseDC
0x180035fb6  test    rbx, rbx
0x180035fb9  jnz     loc_180036BA1
0x180035fbf  test    rdi, rdi
0x180035fc2  jnz     loc_180036BAF
0x180035fc8  test    r15, r15
0x180035fcb  jnz     loc_180036629
0x180035fd1  mov     eax, [rsp+198h+var_120]
0x180035fd5  mov     rcx, [rsp+198h+var_50]
0x180035fdd  xor     rcx, rsp; StackCookie
0x180035fe0  call    __security_check_cookie
0x180035fe5  lea     r11, [rsp+198h+var_38]
0x180035fed  mov     rbx, [r11+50h]
0x180035ff1  movaps  xmm6, xmmword ptr [r11-10h]
0x180035ff6  mov     rsp, r11
0x180035ff9  pop     r15
0x180035ffb  pop     r14
0x180035ffd  pop     r13
0x180035fff  pop     r12
0x180036001  pop     rdi
0x180036002  pop     rsi
0x180036003  pop     rbp
0x180036004  retn
0x180036005  mov     rax, [rsp+198h+ho]
0x18003600d  psrldq  xmm6, 4
0x180036012  movd    [rsp+198h+y], xmm6
0x18003601b  jmp     short loc_18003605B
0x18003601d  mov     rcx, [rsp+198h+ho]; ho
0x180036025  call    cs:__imp_DeleteObject
0x18003602b  mov     r8, [rsp+198h+var_B0]; HDC
0x180036033  mov     rcx, r12; hWnd
0x180036036  mov     rdx, [rsp+198h+hdc]; hdc
0x18003603e  call    ?TakeWindowSnapshot@@YAPEAUHBITMAP__@@PEAUHWND__@@PEAUHDC__@@1@Z; TakeWindowSnapshot(HWND__ *,HDC__ *,HDC__ *)
0x180036043  mov     [rsp+198h+ho], rax
0x18003604b  test    rax, rax
0x18003604e  jz      loc_180035F1B
0x180036054  mov     dword ptr [rsp+198h+var_110], ebx
0x18003605b  mov     rbx, [rsp+198h+var_B0]
0x180036063  mov     rdx, rax; h
0x180036066  mov     rcx, rbx; hdc
0x180036069  call    cs:__imp_SelectObject
0x18003606f  xor     r11d, r11d
0x180036072  mov     eax, 0A5h
0x180036077  test    r14d, r14d
0x18003607a  cmovnz  eax, r14d
0x18003607e  mov     [rsp+198h+var_F8], eax
0x180036085  test    edi, edi
0x180036087  jnz     loc_180036657
0x18003608d  mov     rdx, [rsp+198h+var_110]
0x180036095  lea     r9d, [r11+1]
0x180036099  and     [rsp+198h+var_C8], r9d
0x1800360a1  mov     r12d, r11d
0x1800360a4  mov     rcx, [rsp+198h+var_118]
0x1800360ac  mov     [rsp+198h+var_9C], r9d
0x1800360b4  mov     [rsp+198h+cy], r11d
0x1800360b9  test    r15d, r15d
0x1800360bc  jnz     loc_1800366A6
0x1800360c2  mov     ebx, r11d
0x1800360c5  mov     edi, r11d
0x1800360c8  mov     r8d, [rsp+198h+var_128]
0x1800360cd  mov     r14d, r11d
0x1800360d0  mov     eax, r8d
0x1800360d3  mov     [rsp+198h+var_138], r11d
0x1800360d8  and     eax, 10h
0x1800360db  mov     [rsp+198h+var_78], eax
0x1800360e2  jnz     loc_1800366AF
0x1800360e8  mov     eax, r8d
0x1800360eb  and     eax, 40000h
0x1800360f0  mov     [rsp+198h+var_94], eax
0x1800360f7  test    r9b, r8b
0x1800360fa  jnz     loc_18003688B
0x180036100  test    sil, r8b
0x180036103  jz      loc_1800368A2
0x180036109  test    r15d, r15d
0x18003610c  mov     r10d, ecx
0x18003610f  mov     eax, r15d
0x180036112  cmovnz  r10d, r11d
0x180036116  neg     eax
0x180036118  sbb     eax, eax
0x18003611a  neg     eax
0x18003611c  sub     eax, r9d
0x18003611f  mov     [rsp+198h+var_FC], r10d
0x180036127  mov     [rsp+198h+var_130], eax
0x18003612b  test    r13b, r8b
0x18003612e  jnz     loc_180036637
0x180036134  test    r8b, 8
0x180036138  jnz     loc_1800368BB
0x18003613e  mov     [rsp+198h+var_100], r11d
0x180036146  mov     r12d, edx
0x180036149  mov     [rsp+198h+var_12C], r11d
0x18003614e  mov     [rsp+198h+cy], edx
0x180036152  call    cs:__imp_GetTickCount
0x180036158  mov     [rsp+198h+var_A0], eax
0x18003615f  mov     eax, [rsp+198h+var_128]
0x180036163  mov     ecx, eax
0x180036165  and     ecx, 13h
0x180036168  mov     [rsp+198h+var_F4], 0
0x180036173  and     eax, 1Ch
0x180036176  mov     [rsp+198h+var_74], ecx
0x18003617d  mov     [rsp+198h+var_70], eax
0x180036184  call    cs:__imp_GetTickCount
0x18003618a  mov     ecx, eax
0x18003618c  sub     ecx, [rsp+198h+var_A0]
0x180036193  cmp     [rsp+198h+var_74], 0
0x18003619b  mov     [rsp+198h+var_134], ecx
0x18003619f  jnz     loc_1800364AE
0x1800361a5  cmp     [rsp+198h+var_70], 0
0x1800361ad  jnz     loc_1800364E9
0x1800361b3  mov     eax, [rsp+198h+var_F8]
0x1800361ba  cmp     [rsp+198h+var_134], eax
0x1800361be  ja      loc_1800368E0
0x1800361c4  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
