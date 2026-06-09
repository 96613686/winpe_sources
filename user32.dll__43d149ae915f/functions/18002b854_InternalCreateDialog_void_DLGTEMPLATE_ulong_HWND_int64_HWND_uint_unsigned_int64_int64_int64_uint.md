# InternalCreateDialog(void *,DLGTEMPLATE *,ulong,HWND__ *,__int64 (*)(HWND__ *,uint,unsigned __int64,__int64),__int64,uint)

- ea: `0x18002b854`
- end: `0x18002cbd6`
- name: `?InternalCreateDialog@@YAPEAUHWND__@@PEAXPEAUDLGTEMPLATE@@KPEAU1@P6A_J2I_K_J@Z4I@Z`
- size: `4994`
- prototype: `HWND __fastcall(void *, struct DLGTEMPLATE *, unsigned int, HWND, __int64 (*)(HWND, unsigned int, unsigned __int64, __int64), __int64, unsigned int)`
- caller_count: `2`
- callee_count: `33`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002aafc`
- `0x18002b690`

## callees

- `0x1800060e0`
- `0x180006c18`
- `0x180007640`
- `0x180008828`
- `0x180009510`
- `0x180009ba8`
- `0x18000b4e0`
- `0x18000cf20`
- `0x18000d210`
- `0x18000d9f0`
- `0x1800130e0`
- `0x180013900`
- `0x180014310`
- `0x180015780`
- `0x180029cf4`
- `0x18002a230`
- `0x18002a8ec`
- `0x18002aa38`
- `0x18002aa8c`
- `0x18002ac78`
- `0x18002ad40`
- `0x18002ae74`
- `0x18002b854`
- `0x18002cbdc`
- `0x18002e1a4`
- `0x18002e8c8`
- `0x180030580`
- `0x1800309a0`
- `0x18004c988`
- `0x1800526a0`
- `0x18005a450`
- `0x18005f1c0`
- `0x1800968f4`

## import_xrefs

- `win32u!NtUserGetCursorPos` at `0x18002c4f8`
- `win32u!NtUserGetCursorPos` at `0x18002c4f8`
- `win32u!NtUserSetForegroundWindow` at `0x18002cbaa`
- `win32u!NtUserSetForegroundWindow` at `0x18002cbaa`
- `win32u!NtUserSetDialogSystemMenu` at `0x18002c809`
- `win32u!NtUserSetDialogSystemMenu` at `0x18002c809`
- `win32u!NtUserSetWindowContextHelpId` at `0x18002cb16`
- `win32u!NtUserSetWindowContextHelpId` at `0x18002cb67`
- `win32u!NtUserSetWindowContextHelpId` at `0x18002cb16`
- `win32u!NtUserSetWindowContextHelpId` at `0x18002cb67`
- `win32u!NtUserReleaseDC` at `0x18009abc0`
- `win32u!NtUserReleaseDC` at `0x18009abc0`
- `win32u!NtUserGetThreadState` at `0x18002c5d2`
- `win32u!NtUserGetThreadState` at `0x18002c816`
- `win32u!NtUserGetThreadState` at `0x18002c8d3`
- `win32u!NtUserGetThreadState` at `0x18002c8e9`
- `win32u!NtUserGetThreadState` at `0x18002ca11`
- `win32u!NtUserGetThreadState` at `0x18002c5d2`
- `win32u!NtUserGetThreadState` at `0x18002c816`
- `win32u!NtUserGetThreadState` at `0x18002c8d3`
- `win32u!NtUserGetThreadState` at `0x18002c8e9`
- `win32u!NtUserGetThreadState` at `0x18002ca11`
- `win32u!NtUserGetDC` at `0x18009ab74`
- `win32u!NtUserGetDC` at `0x18009ab74`
- `win32u!NtUserShowWindow` at `0x18002c7d4`
- `win32u!NtUserShowWindow` at `0x18002c7d4`
- `win32u!NtUserIsWindowBroadcastingDpiToChildren` at `0x18002c9d6`
- `win32u!NtUserIsWindowBroadcastingDpiToChildren` at `0x18002c9d6`
- `win32u!NtUserIsTopLevelWindow` at `0x18002c9c5`
- `win32u!NtUserIsTopLevelWindow` at `0x18002c9c5`
- `win32u!NtUserGetSystemMenu` at `0x18002c84b`
- `win32u!NtUserGetSystemMenu` at `0x18002c84b`
- `win32u!NtUserDestroyWindow` at `0x18002c532`
- `win32u!NtUserDestroyWindow` at `0x18002c532`
- `win32u!NtUserDestroyMenu` at `0x18002cbcb`
- `win32u!NtUserDestroyMenu` at `0x18002cbcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c873`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002c873`
- `GDI32!SelectObject` at `0x18002c6ba`
- `GDI32!SelectObject` at `0x18002c6e9`
- `GDI32!SelectObject` at `0x18002ca4e`
- `GDI32!SelectObject` at `0x18009abb3`
- `GDI32!SelectObject` at `0x18002c6ba`
- `GDI32!SelectObject` at `0x18002c6e9`
- `GDI32!SelectObject` at `0x18002ca4e`
- `GDI32!SelectObject` at `0x18009abb3`
- `GDI32!GetStockObject` at `0x18002bc3e`
- `GDI32!GetStockObject` at `0x18002ca2a`
- `GDI32!GetStockObject` at `0x18002bc3e`
- `GDI32!GetStockObject` at `0x18002ca2a`
- `GDI32!GetDCDpiScaleValue` at `0x18009ab89`
- `GDI32!GetDCDpiScaleValue` at `0x18009ab89`
- `GDI32!GdiGetCharDimensions` at `0x18002c6da`
- `GDI32!GdiGetCharDimensions` at `0x18002c6da`
- `GDI32!CreateCompatibleBitmap` at `0x18009ab9f`
- `GDI32!CreateCompatibleBitmap` at `0x18009ab9f`
- `GDI32!DeleteDC` at `0x18002bc57`
- `GDI32!DeleteDC` at `0x18002bc57`
- `GDI32!CreateCompatibleDC` at `0x18002bb71`
- `GDI32!CreateCompatibleDC` at `0x18002bb71`
- `GDI32!DeleteObject` at `0x18002bd6e`
- `GDI32!DeleteObject` at `0x18002c898`
- `GDI32!DeleteObject` at `0x18002ca57`
- `GDI32!DeleteObject` at `0x18002bd6e`
- `GDI32!DeleteObject` at `0x18002c898`
- `GDI32!DeleteObject` at `0x18002ca57`

## pseudocode

```c
HWND __fastcall InternalCreateDialog(
        HINSTANCE a1,
        struct DLGTEMPLATE *a2,
        __int64 a3,
        HWND a4,
        __int64 (*a5)(HWND, unsigned int, unsigned __int64, __int64),
        __int64 a6,
        char a7)
{
  int v9; // eax
  int v10; // eax
  WORD cdit; // dx
  int cy; // eax
  int cx; // r12d
  DWORD dwExtendedStyle; // r14d
  unsigned int style; // ebx
  unsigned __int16 v16; // r15
  int v17; // esi
  HMODULE ModuleHandleW; // rax
  int ExpWinVer; // eax
  int v20; // ecx
  int v21; // r13d
  unsigned __int16 *v22; // rdi
  unsigned __int16 v23; // r15
  unsigned __int8 *v24; // rax
  void *v25; // r8
  unsigned __int16 *v26; // rcx
  HGDIOBJ v27; // rdi
  unsigned __int8 *v28; // rax
  unsigned __int8 *v29; // rax
  int v30; // r8d
  unsigned int v31; // edx
  HBITMAP v32; // r15
  struct tagMONITOR *DialogMonitor; // r12
  HWND v34; // rsi
  HDC CompatibleDC; // rdi
  __int64 v36; // rcx
  __int64 v37; // rax
  HGDIOBJ StockObject; // rsi
  __int64 v39; // rcx
  int v40; // esi
  __int16 v41; // si
  int v42; // r15d
  int v43; // eax
  LONG v44; // edi
  LONG v45; // esi
  __int16 v46; // di
  __int16 v47; // r10
  __int64 v48; // rsi
  __int16 v49; // r11
  __int64 v50; // rax
  int v51; // r8d
  int v52; // edx
  HWND v53; // rax
  HWND v54; // rdi
  struct tagWND *v55; // rax
  struct tagWND *v56; // rbx
  unsigned __int64 v57; // r14
  int *v58; // rsi
  char v59; // al
  __int64 v60; // r9
  int *v62; // r11
  int *v63; // r10
  __int16 *v64; // rax
  __int16 *v65; // r8
  __int16 *v66; // rcx
  __int16 *v67; // r15
  LONG v68; // r12d
  unsigned __int16 *v69; // rdx
  __int64 v70; // rsi
  unsigned __int16 v71; // cx
  unsigned __int8 *v72; // r8
  unsigned __int64 v73; // rdx
  int v74; // r10d
  __int64 v75; // r9
  unsigned __int16 *v76; // r8
  int v77; // r10d
  unsigned __int8 *v78; // rax
  __int64 v79; // r8
  __int64 v80; // rax
  __int64 v81; // rsi
  int v82; // r11d
  int v83; // r8d
  HWND v84; // rsi
  __int64 v85; // rax
  unsigned __int64 v86; // r8
  int v87; // esi
  struct tagWND *ChildControl; // rax
  struct tagWND *v89; // rsi
  struct tagWND *Control; // rax
  struct tagWND *v91; // rdx
  struct tagWND *v92; // rcx
  HWND v93; // rsi
  int v94; // eax
  int v96; // eax
  __m128i v97; // xmm1
  LONG WindowLongW; // eax
  HGDIOBJ v99; // rsi
  struct tagWND *v100; // rax
  struct tagWND *v101; // rsi
  struct tagWND *v102; // rax
  struct tagWND *v103; // rdx
  struct tagWND *v104; // rcx
  const WCHAR *v105; // rdx
  int IsTopLevelWindow; // eax
  HWND v107; // rcx
  _DWORD *MonitorWorkRect; // r8
  HGDIOBJ v109; // r15
  HMENU MenuW; // rax
  int v111; // ecx
  __int64 v112; // rax
  __int64 DC; // rax
  HDC v114; // rsi
  HBITMAP CompatibleBitmap; // rax
  unsigned int v116; // [rsp+28h] [rbp-D8h]
  int v117; // [rsp+80h] [rbp-80h]
  LONG v118; // [rsp+80h] [rbp-80h]
  int v119; // [rsp+84h] [rbp-7Ch]
  LONG v120; // [rsp+88h] [rbp-78h] BYREF
  __int16 y; // [rsp+8Ch] [rbp-74h]
  int epi16; // [rsp+90h] [rbp-70h]
  int x; // [rsp+94h] [rbp-6Ch]
  struct tagPOINT Point[2]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int DpiForSystem; // [rsp+A8h] [rbp-58h]
  int v126; // [rsp+ACh] [rbp-54h]
  HGDIOBJ ho; // [rsp+B0h] [rbp-50h]
  int v128; // [rsp+B8h] [rbp-48h]
  int v129; // [rsp+BCh] [rbp-44h]
  int v130; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v131[8]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned int v132; // [rsp+E8h] [rbp-18h]
  __int128 v133; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v134; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v135; // [rsp+108h] [rbp+8h] BYREF
  __int128 v136; // [rsp+110h] [rbp+10h] BYREF
  __int64 v137; // [rsp+120h] [rbp+20h] BYREF
  HMENU v138; // [rsp+128h] [rbp+28h]
  HGDIOBJ h; // [rsp+130h] [rbp+30h] BYREF
  int v140; // [rsp+138h] [rbp+38h]
  int v141; // [rsp+13Ch] [rbp+3Ch]
  __int64 v142; // [rsp+140h] [rbp+40h]
  unsigned __int16 *v143; // [rsp+148h] [rbp+48h]
  unsigned __int16 *v144; // [rsp+150h] [rbp+50h]
  __int64 v145; // [rsp+158h] [rbp+58h]
  __int64 v146; // [rsp+160h] [rbp+60h]
  WORD v148; // [rsp+1C0h] [rbp+C0h]

  memset(v131, 0, 26);
  v130 = 0;
  *(_OWORD *)&Point[0].x = 0;
  v136 = 0;
  v133 = 0;
  DpiForSystem = GetDpiForSystem();
  v137 = 0;
  if ( !*(_DWORD *)&gfServerProcess )
  {
    if ( NtCurrentTeb() != (struct _TEB *)-2048LL || NtUserGetThreadState(14) )
    {
      if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[29]) )
        v9 = NtCurrentTeb()->Win32ClientInfo[29];
      else
        LOBYTE(v9) = gDefaultDpiContext;
      if ( (v9 & 0xF) != 2 )
      {
LABEL_6:
        if ( *(_DWORD *)&gfServerProcess || NtCurrentTeb() == (struct _TEB *)-2048LL && !NtUserGetThreadState(14) )
          goto LABEL_11;
        if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[29]) )
          v10 = NtCurrentTeb()->Win32ClientInfo[29];
        else
          LOBYTE(v10) = gDefaultDpiContext;
        if ( (v10 & 0xF) != 3 )
          goto LABEL_11;
LABEL_177:
        v117 = 1;
        goto LABEL_12;
      }
    }
    if ( !*(_DWORD *)&gfServerProcess )
    {
      if ( NtCurrentTeb() != (struct _TEB *)-2048LL || NtUserGetThreadState(14) )
      {
        if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[29]) )
          v96 = NtCurrentTeb()->Win32ClientInfo[29];
        else
          LOBYTE(v96) = gDefaultDpiContext;
        if ( (v96 & 0xF0) == 0x20 )
          goto LABEL_177;
      }
      goto LABEL_6;
    }
  }
LABEL_11:
  v117 = 0;
LABEL_12:
  if ( !NtCurrentTeb()->Win32ThreadInfo && !NtUserGetThreadState(14) )
    return 0;
  if ( HIWORD(a2->style) == 0xFFFF )
  {
    v97 = *(__m128i *)&a2->x;
    *(_OWORD *)v131 = *(_OWORD *)&a2->style;
    *(__m128i *)((char *)&v131[2] + 2) = v97;
    style = (unsigned __int64)v97.m128i_i64[0] >> 16;
    dwExtendedStyle = v131[2];
    epi16 = _mm_extract_epi16(v97, 7);
    cx = _mm_extract_epi16(v97, 6);
    y = _mm_extract_epi16(v97, 5);
    x = _mm_extract_epi16(v97, 4);
    v148 = _mm_extract_epi16(v97, 3);
  }
  else
  {
    cdit = a2->cdit;
    cy = (unsigned __int16)a2->cy;
    cx = (unsigned __int16)a2->cx;
    dwExtendedStyle = a2->dwExtendedStyle;
    style = a2->style;
    x = (unsigned __int16)a2->x;
    HIWORD(v131[4]) = x;
    y = a2->y;
    LOWORD(v131[5]) = y;
    v131[2] = dwExtendedStyle;
    v131[3] = style;
    v148 = cdit;
    LOWORD(v131[4]) = cdit;
    HIWORD(v131[5]) = cx;
    epi16 = cy;
    LOWORD(v131[6]) = cy;
  }
  v16 = style;
  v128 = cx;
  v17 = (unsigned __int16)style;
  if ( a1 )
    ModuleHandleW = a1;
  else
    ModuleHandleW = GetModuleHandleW(0);
  ExpWinVer = RtlGetExpWinVer(ModuleHandleW);
  v132 = ExpWinVer | 0x40000000;
  v145 = 4;
  if ( (unsigned __int16)ExpWinVer < 0x400u )
  {
    v20 = 0;
    v126 = 0;
  }
  else
  {
    v20 = 1;
    style &= ~0x8000u;
    v126 = 1;
    v131[3] = style;
    if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[2]) < 0x400 )
    {
      if ( (style & 0x4000) != 0 )
      {
        style &= ~4u;
        v131[3] = style;
        v17 &= ~4u;
        v16 = style;
        goto LABEL_21;
      }
    }
    else
    {
      style |= 4u;
      v131[3] = style;
      v17 |= 4u;
    }
    v16 = style;
  }
LABEL_21:
  v146 = 8;
  v21 = (style >> 6) & 8;
  if ( v17 != v16 && v20 )
    return 0;
  if ( (style & 0x80u) != 0 )
  {
    dwExtendedStyle |= 0x101u;
    v131[2] = dwExtendedStyle;
  }
  if ( (style & 0x2000) != 0 && v20 )
  {
    dwExtendedStyle |= 0x400u;
    v131[2] = dwExtendedStyle;
  }
  if ( (style & 0x400) != 0 )
  {
    style &= 0xFF37FFFD;
    v131[3] = style;
  }
  else if ( (style & 0x400000) != 0 )
  {
    dwExtendedStyle |= 0x100u;
    v131[2] = dwExtendedStyle;
  }
  if ( (style & 2) != 0 )
  {
    dwExtendedStyle |= 8u;
    v131[2] = dwExtendedStyle;
  }
  if ( (style & 0x40000000) == 0 || (style & 0x400) != 0 )
  {
    dwExtendedStyle |= 0x10000u;
    v131[2] = dwExtendedStyle;
  }
  if ( (_WORD)x == 0x8000 )
  {
    LOBYTE(v21) = v21 | 0x10;
    x = 0;
    HIWORD(v131[4]) = 0;
  }
  if ( (_WORD)cx == 0x8000 )
  {
    LOBYTE(v21) = v21 | 0x20;
  }
  else if ( (cx & 0x8000u) == 0 )
  {
    goto LABEL_37;
  }
  HIWORD(v131[5]) = 0;
  v128 = 0;
LABEL_37:
  if ( (epi16 & 0x8000u) != 0 )
  {
    epi16 = 0;
    LOWORD(v131[6]) = 0;
  }
  v22 = (unsigned __int16 *)((char *)&a2[1] + (-(__int64)(LOWORD(v131[0]) != 0) & 8));
  v23 = *v22;
  v134 = v23;
  if ( v23 )
  {
    if ( v23 == 0xFFFF )
      v105 = (const WCHAR *)v22[1];
    else
      v105 = v22;
    MenuW = LoadMenuW(a1, v105);
    v25 = 0;
    v138 = MenuW;
    if ( !MenuW )
      return 0;
    if ( v23 == 0xFFFF )
    {
      v26 = v22 + 2;
      goto LABEL_42;
    }
    v138 = MenuW;
  }
  else
  {
    v138 = 0;
  }
  v24 = SkipSz(v22);
  v26 = (unsigned __int16 *)&v24[(unsigned __int8)v24 & 1];
LABEL_42:
  v142 = (__int64)v26;
  v27 = v25;
  ho = v25;
  v28 = SkipSz(v26);
  v144 = (unsigned __int16 *)&v28[(unsigned __int8)v28 & 1];
  v29 = SkipSz(v144);
  v143 = (unsigned __int16 *)&v29[(unsigned __int8)v29 & 1];
  v135 = v143;
  if ( (style & 0x1000) == 0 || *(_DWORD *)(gpsi + 1972) == v30 )
  {
    v31 = (style & 1) == 0 || (style & 0x1800) != 0 || a4;
    v32 = 0;
    DialogMonitor = GetDialogMonitor(a4, v31);
  }
  else
  {
    NtUserGetCursorPos(&v137, 1);
    v32 = 0;
    DialogMonitor = (struct tagMONITOR *)MonitorFromPoint(v137, 2);
    if ( !DialogMonitor )
      goto LABEL_68;
  }
  if ( !v117 )
    goto LABEL_47;
  if ( (style & 0x40000000) == 0 )
  {
    if ( DialogMonitor )
    {
      if ( *(_DWORD *)&gfServerProcess || NtCurrentTeb() == (struct _TEB *)-2048LL && !NtUserGetThreadState(14) )
      {
        LOBYTE(v111) = 18;
      }
      else if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[29]) )
      {
        v111 = NtCurrentTeb()->Win32ClientInfo[29];
      }
      else
      {
        LOBYTE(v111) = gDefaultDpiContext;
      }
      v112 = 84;
      if ( (v111 & 0xF) != 3 )
        v112 = 60;
      DpiForSystem = *(unsigned __int16 *)((char *)DialogMonitor + v112);
    }
    else
    {
      v117 = 0;
    }
LABEL_47:
    v34 = a4;
    goto LABEL_48;
  }
  v34 = a4;
  IsTopLevelWindow = NtUserIsTopLevelWindow(a4);
  v107 = a4;
  if ( IsTopLevelWindow )
  {
    if ( !(unsigned int)NtUserIsWindowBroadcastingDpiToChildren(a4) )
      goto LABEL_48;
    v107 = a4;
  }
  DpiForSystem = GetWindowDPI(v107);
LABEL_48:
  CompatibleDC = CreateCompatibleDC(0);
  if ( !CompatibleDC )
  {
LABEL_67:
    v27 = ho;
LABEL_68:
    if ( v138 )
      NtUserDestroyMenu(v138);
    if ( v27 )
      DeleteObject(v27);
    return 0;
  }
  h = 0;
  if ( (unsigned int)IsWindowGdiScaledX(v34) )
  {
    DC = NtUserGetDC(v34);
    v114 = (HDC)DC;
    if ( DC )
    {
      if ( (int)GetDCDpiScaleValue(DC) > 1 )
      {
        CompatibleBitmap = CreateCompatibleBitmap(v114, 1, 1);
        v32 = CompatibleBitmap;
        if ( CompatibleBitmap )
          h = SelectObject(CompatibleDC, CompatibleBitmap);
      }
      NtUserReleaseDC(v114);
    }
  }
  if ( (style & 0x40) != 0 )
  {
    v37 = (__int64)CreateDlgFont(CompatibleDC, &v135, (struct DLGTEMPLATE2 *)v131, v132, &v130, v116, DpiForSystem);
    style = v131[3];
    dwExtendedStyle = v131[2];
    StockObject = (HGDIOBJ)v37;
    ho = (HGDIOBJ)v37;
    LOBYTE(v21) = v21 | 4;
    v36 = -v37;
    v129 = v37 != 0 ? v117 : 0;
    v143 = v135;
    epi16 = LOWORD(v131[6]);
    v128 = HIWORD(v131[5]);
    y = v131[5];
    x = HIWORD(v131[4]);
    v148 = v131[4];
  }
  else if ( (unsigned __int16)v132 >= 0x400u && (style & 8) != 0 )
  {
    LOBYTE(v21) = v21 | 4;
    v129 = 0;
    StockObject = GetStockObject(16);
    ho = StockObject;
  }
  else
  {
    StockObject = 0;
    ho = 0;
    v129 = 0;
  }
  v119 = *(_DWORD *)(GetDpiServerInfoForCurrentThread(v36) + 32);
  v118 = *(_DWORD *)(GetDpiServerInfoForCurrentThread(v39) + 36);
  if ( !StockObject )
  {
    if ( (v21 & 4) == 0 )
    {
LABEL_55:
      v40 = v119;
      goto LABEL_56;
    }
LABEL_54:
    ho = GetStockObject(13);
    goto LABEL_55;
  }
  v99 = SelectObject(CompatibleDC, StockObject);
  if ( !v99 )
  {
    DeleteObject(ho);
    goto LABEL_54;
  }
  v120 = 0;
  LODWORD(v135) = GdiGetCharDimensions(CompatibleDC, 0, &v120);
  SelectObject(CompatibleDC, v99);
  if ( !(_DWORD)v135 )
    goto LABEL_55;
  v40 = (int)v135;
  v119 = (int)v135;
  v118 = v120;
LABEL_56:
  if ( v32 )
  {
    SelectObject(CompatibleDC, h);
    DeleteObject(v32);
  }
  DeleteDC(CompatibleDC);
  if ( (style & 0x10000000) != 0 )
  {
    LOBYTE(v21) = v21 | 1;
    style &= ~0x10000000u;
  }
  Point[1].x = (v40 * (__int16)v128 + 2) / 4;
  Point[1].y = (v118 * (__int16)epi16 + 4) / 8;
  AdjustWindowRectExForDpi((unsigned int)Point, style, v134, dwExtendedStyle, DpiForSystem);
  v41 = LOWORD(Point[1].y) - LOWORD(Point[0].y);
  v42 = (__int16)(LOWORD(Point[1].x) - LOWORD(Point[0].x));
  v120 = (unsigned __int16)(LOWORD(Point[1].y) - LOWORD(Point[0].y));
  if ( (style & 0x1000) != 0 )
  {
    v43 = v126;
    if ( *(_DWORD *)(gpsi + 1972) && v126 )
    {
      v44 = v137 - v42 / 2;
      Point[0].x = v44;
      v45 = HIDWORD(v137) - v41 / 2;
      Point[0].y = v45;
      goto LABEL_75;
    }
  }
  else
  {
    v43 = v126;
  }
  if ( (style & 0x1800) != 0 && v43 )
  {
    MonitorWorkRect = (_DWORD *)GetMonitorWorkRect(&h, DialogMonitor);
    v44 = (*MonitorWorkRect + MonitorWorkRect[2] - v42) / 2;
    Point[0].x = v44;
    v45 = (MonitorWorkRect[1] + MonitorWorkRect[3] - v41) / 2;
    Point[0].y = v45;
    goto LABEL_75;
  }
  v44 = (v119 * (__int16)x + 2) / 4;
  Point[0].x = v44;
  Point[0].y = (v118 * y + 4) / 8;
  v45 = Point[0].y;
  if ( (style & 1) == 0 && a4 )
  {
    if ( (HIWORD(style) & 0xC000) != 0x4000 )
    {
      ClientToScreen(a4, Point);
      WindowLongW = GetWindowLongW(a4, -20);
      v44 = Point[0].x;
      v45 = Point[0].y;
      if ( (WindowLongW & 0x400000) != 0 )
      {
        v44 = Point[0].x - v42;
        Point[0].x -= v42;
      }
    }
  }
  else if ( !DialogMonitor )
  {
    LODWORD(h) = (v119 * (__int16)x + 2) / 4;
    v140 = v44 + v42;
    HIDWORD(h) = (v118 * y + 4) / 8;
    v141 = Point[0].y + (__int16)v120;
    DialogMonitor = (struct tagMONITOR *)MonitorFromRect(&h, 1, 0);
    if ( !DialogMonitor )
      goto LABEL_67;
  }
LABEL_75:
  Point[1].x = v42 + v44;
  Point[1].y = (__int16)v120 + v45;
  if ( v44 > v42 + v44 || v45 > (__int16)v120 + v45 )
    OffsetRect((LPRECT)Point, -v42, -(__int16)v120);
  RepositionRect(DialogMonitor, (struct tagRECT *)Point, style, dwExtendedStyle);
  v46 = 0x8000;
  if ( (v21 & 0x10) == 0 )
    v46 = Point[0].x;
  if ( (v21 & 0x20) != 0 )
    v47 = 0x8000;
  else
    v47 = LOWORD(Point[1].x) - LOWORD(Point[0].x);
  v48 = v142;
  v49 = LOWORD(Point[1].y) - LOWORD(Point[0].y);
  if ( *(_WORD *)v142 )
  {
    if ( (v142 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      RtlInitLargeUnicodeString(&v136, v142);
      v48 = (__int64)&v136;
    }
  }
  else
  {
    v48 = 32770;
  }
  DWORD1(v133) &= ~0x80000000;
  *((_QWORD *)&v133 + 1) = v144;
  if ( v144 )
  {
    v50 = -1;
    do
      ++v50;
    while ( v144[v50] );
    LODWORD(v133) = 2 * v50;
    DWORD1(v133) = (2 * v50 + 2) & 0x7FFFFFFF;
  }
  else
  {
    *(_QWORD *)&v133 = 0;
  }
  v51 = 0x8000;
  if ( v47 != (__int16)0x8000 )
    v51 = v47;
  v52 = 0x8000;
  if ( v46 != (__int16)0x8000 )
    v52 = v46;
  x = a7 & 2;
  v53 = (HWND)VerNtUserCreateWindowEx(
                dwExtendedStyle | (x != 0 ? 0x80000000 : 0),
                v48,
                &v133,
                style,
                v52,
                SLOWORD(Point[0].y),
                v51,
                v49,
                a4,
                v138,
                a1,
                0,
                0,
                0,
                v132);
  v54 = v53;
  if ( !v53 )
    goto LABEL_67;
  v55 = ValidateHwnd(v53);
  v56 = v55;
  if ( !v55 || !(unsigned int)ValidateDialogPwnd(v55) )
    goto LABEL_67;
  v57 = 0;
  v58 = (int *)((char *)v143 + (-(int)v143 & 3));
  if ( v129 )
  {
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 24LL) |= 8u;
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 60LL) = DpiForSystem;
  }
  if ( v131[1] )
    NtUserSetWindowContextHelpId(v54);
  v59 = *((_BYTE *)v56 + 30);
  if ( (v59 & 8) != 0 )
  {
    if ( (v59 & 7) != 0 )
      NtUserGetSystemMenu(v54, 0);
    else
      NtUserSetDialogSystemMenu(v54);
  }
  v60 = 1;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 24LL) &= ~2u;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 8LL) = v119;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 12LL) = v118;
  **(_QWORD **)(*((_QWORD *)v56 + 37) + 8LL) = a5;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 24LL) &= ~1u;
  *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 32LL) = 1;
  *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 80LL) = v130;
  if ( (a7 & 2) != 0 )
    *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 24LL) |= 4u;
  if ( (v21 & 4) != 0 )
  {
    v109 = ho;
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 48LL) = ho;
    if ( a5 )
    {
      SendMessageWorker(v56, 0x30u, (unsigned __int64)v109, 0, 0);
      v60 = 1;
    }
  }
  while ( 1 )
  {
    if ( !v148-- )
    {
      v86 = 0;
      if ( (*((_BYTE *)v56 + 29) & 4) != 0 )
      {
LABEL_138:
        if ( !a5 )
          goto LABEL_154;
        v87 = SendMessageWorker(v56, 0x110u, v86, a6, 0);
        if ( !HMValidateHandleNoSecure(v54) )
          goto LABEL_163;
        if ( !v87
          || ((unsigned __int8)~(*((_BYTE *)v56 + 29) >> 2)
            & ((*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 24LL) & 1) == 0)) == 0 )
        {
LABEL_154:
          if ( !IsWindow(v54) )
          {
            if ( LODWORD(NtCurrentTeb()->Win32ClientInfo[2]) >= 0x400 )
              return 0;
            return v54;
          }
          if ( *(char *)gpsi >= 0 )
          {
            v94 = *(_DWORD *)(gpsi + 7004);
            if ( (v94 & 0x20) == 0
              && v94 < 0
              && (GetAppCompatFlags2(1024) & 2) == 0
              && (*((_BYTE *)v56 + 31) & 0xC0) != 0x40 )
            {
              SendMessageWorker(v56, 0x127u, 3u, 0, 0);
            }
          }
          if ( (v21 & 8) == 0 || (NtUserSetForegroundWindow(v54), IsWindow(v54)) )
          {
            if ( (v21 & 1) != 0
              && (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 24LL) & 1) == 0
              && (*((_BYTE *)v56 + 31) & 0x10) == 0 )
            {
              NtUserShowWindow(v54, 1);
              UpdateWindow(v54);
            }
          }
          else
          {
            v54 = 0;
          }
LABEL_163:
          if ( (a7 & 4) == 0 )
            return (HWND)(-(__int64)(HMValidateHandleNoSecure(v54) != 0) & (unsigned __int64)v54);
          return v54;
        }
        ChildControl = _GetChildControl(v56, 0);
        v89 = ChildControl;
        if ( ChildControl && !(unsigned int)IsDescendant(v56, ChildControl) )
          goto LABEL_211;
        Control = _NextControl(v56, v89, 3u);
        v91 = Control;
        if ( Control )
        {
          if ( Control == v89 )
            goto LABEL_151;
          do
          {
            if ( v91 == v56 )
              break;
            v92 = v91;
            if ( v89 )
              v92 = v89;
            v89 = v92;
            if ( (*((_DWORD *)v91 + 7) & 0x18010000) == 0x10010000 )
              break;
            v91 = _NextControl(v56, v91, 3u);
          }
          while ( v91 != v89 );
        }
        if ( !v91 )
        {
LABEL_211:
          v93 = 0;
LABEL_153:
          xxxCheckDefPushButton(v56, 0, v93);
          goto LABEL_154;
        }
LABEL_151:
        v93 = *(HWND *)v91;
        if ( *(_QWORD *)v91 )
          DlgSetFocus(*(HWND *)v91);
        goto LABEL_153;
      }
      v100 = _GetChildControl(v56, 0);
      v101 = v100;
      if ( v100 && !(unsigned int)IsDescendant(v56, v100) )
      {
LABEL_221:
        v86 = 0;
        goto LABEL_138;
      }
      v102 = _NextControl(v56, v101, 3u);
      v103 = v102;
      if ( v102 )
      {
        if ( v102 == v101 )
          goto LABEL_206;
        do
        {
          if ( v103 == v56 )
            break;
          v104 = v103;
          if ( v101 )
            v104 = v101;
          v101 = v104;
          if ( (*((_DWORD *)v103 + 7) & 0x18010000) == 0x10010000 )
            break;
          v103 = _NextControl(v56, v103, 3u);
        }
        while ( v103 != v101 );
      }
      if ( !v103 )
        goto LABEL_221;
LABEL_206:
      v86 = *(_QWORD *)v103;
      goto LABEL_138;
    }
    v62 = v58 + 2;
    v63 = v58;
    v64 = (__int16 *)(v58 + 3);
    v65 = (__int16 *)v58 + 7;
    v66 = (__int16 *)(v58 + 4);
    if ( LOWORD(v131[0]) )
    {
      v67 = (__int16 *)v58 + 9;
      v68 = v58[5];
      v130 = *v58;
    }
    else
    {
      v130 = 0;
      v67 = (__int16 *)v58 + 7;
      v68 = (unsigned __int16)*v66;
      v65 = (__int16 *)v58 + 5;
      v66 = (__int16 *)(v58 + 3);
      v64 = (__int16 *)(v58 + 2);
      v62 = v58;
    }
    v120 = v68;
    v126 = (v119 * *v64 + 2) / (int)v145;
    v129 = (v118 * *v65 + 4) / (int)v146;
    LODWORD(v135) = (v119 * *v66 + 2) / 4;
    epi16 = (v118 * *v67 + 4) / 8;
    v69 = (unsigned __int16 *)((char *)v58 + (LOWORD(v131[0]) != 0 ? 24LL : 18LL));
    v70 = gpsi;
    if ( *v69 == 0xFFFF )
    {
      v71 = v69[1] & 0xFF7F;
      if ( v71 >= 0x19u )
        break;
      v72 = (unsigned __int8 *)(v69 + 2);
      v73 = *(unsigned __int16 *)(gpsi + 2LL * v71 + 868);
    }
    else
    {
      v72 = SkipSz(v69);
    }
    v74 = v63[v60];
    v75 = (unsigned int)*v62;
    v76 = (unsigned __int16 *)&v72[(unsigned __int8)v72 & 1];
    v77 = v74 | 4;
    if ( (*((_BYTE *)v56 + 28) & 4) != 0 && ((v75 & 0x800000) != 0 || v73 == *(unsigned __int16 *)(v70 + 878)) )
    {
      LODWORD(v75) = v75 & 0xFF7FFFFF;
      v77 |= 0x200u;
    }
    if ( *v76 == 0xFFFF )
    {
      *(_QWORD *)&v133 = 0x400000004LL;
      v57 = (unsigned __int64)(v76 + 2);
      *((_QWORD *)&v133 + 1) = v76;
    }
    else
    {
      v78 = SkipSz(v76);
      *((_QWORD *)&v133 + 1) = v79;
      DWORD1(v133) &= ~0x80000000;
      v57 = (unsigned __int64)&v78[(unsigned __int8)v78 & 1];
      v80 = -1;
      do
        ++v80;
      while ( *(_WORD *)(v79 + 2 * v80) );
      LODWORD(v133) = 2 * v80;
      DWORD1(v133) = (2 * v80 + 2) & 0x7FFFFFFF;
    }
    v81 = v57 & -(__int64)(*(_WORD *)v57 != 0);
    if ( v68 )
    {
      v75 &= 0x3FFFFFFFu;
      LODWORD(v75) = v75 | 0x40000000;
    }
    if ( (v73 & 0xFFFFFFFFFFFF0000uLL) != 0 )
    {
      DWORD1(v136) &= ~0x80000000;
      *((_QWORD *)&v136 + 1) = v73;
      if ( v73 )
      {
        v85 = -1;
        do
          ++v85;
        while ( *(_WORD *)(v73 + 2 * v85) );
        LODWORD(v136) = 2 * v85;
        DWORD1(v136) = (2 * v85 + 2) & 0x7FFFFFFF;
      }
      else
      {
        *(_QWORD *)&v136 = 0;
      }
      v73 = (unsigned __int64)&v136;
    }
    v82 = 0x8000;
    if ( (_WORD)v135 != 0x8000 )
      v82 = (__int16)v135;
    v83 = 0x8000;
    if ( (_WORD)v126 != 0x8000 )
      v83 = (__int16)v126;
    v84 = (HWND)VerNtUserCreateWindowEx(
                  v77 | (x != 0 ? 0x80000000 : 0),
                  v73,
                  &v133,
                  v75,
                  v83,
                  (__int16)v129,
                  v82,
                  (__int16)epi16,
                  v54,
                  v68,
                  a1,
                  v81,
                  0,
                  0,
                  v132);
    if ( !v84 )
      break;
    if ( v130 )
      NtUserSetWindowContextHelpId(v84);
    if ( ho )
      SendMessageW(v84, 0x30u, (WPARAM)ho, 0);
    if ( (SendMessageW(v84, 0x87u, 0, 0) & 0x10) != 0 )
      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v56 + 37) + 8LL) + 32LL) = (unsigned int)v120;
LABEL_129:
    v60 = 1;
    v58 = (int *)(*(unsigned __int16 *)v57 + ((-2LL - *(unsigned __int16 *)v57 - v57) & 3) + v57 + 2);
  }
  if ( (*((_BYTE *)v56 + 28) & 0x10) != 0 )
    goto LABEL_129;
  NtUserDestroyWindow(v54);
  return 0;
}

```

## disassembly

```asm
0x18002b854  mov     rax, rsp
0x18002b857  mov     [rax+10h], rbx
0x18002b85b  mov     [rax+20h], r9
0x18002b85f  mov     [rax+18h], r8d
0x18002b863  mov     [rax+8], rcx
0x18002b867  push    rbp
0x18002b868  push    rsi
0x18002b869  push    rdi
0x18002b86a  push    r12
0x18002b86c  push    r13
0x18002b86e  push    r14
0x18002b870  push    r15
0x18002b872  lea     rbp, [rsp-70h]
0x18002b877  sub     rsp, 170h
0x18002b87e  xorps   xmm0, xmm0
0x18002b881  xorps   xmm1, xmm1
0x18002b884  movups  xmmword ptr [rbp+0A0h+var_D8], xmm0
0x18002b888  xor     ebx, ebx
0x18002b88a  mov     rdi, rdx
0x18002b88d  movups  xmmword ptr [rbp+0A0h+var_D8+0Ah], xmm0
0x18002b891  mov     r13, rcx
0x18002b894  mov     [rbp+0A0h+var_E0], ebx
0x18002b897  movups  xmmword ptr [rbp+0A0h+Point.x], xmm0
0x18002b89b  movups  [rbp+0A0h+var_90], xmm0
0x18002b89f  movups  [rbp+0A0h+var_B0], xmm1
0x18002b8a3  call    GetDpiForSystem
0x18002b8a8  mov     [rbp+0A0h+var_F8], eax
0x18002b8ab  lea     esi, [rbx+0Eh]
0x18002b8ae  mov     eax, cs:gfServerProcess
0x18002b8b4  lea     ecx, [rbx+2]
0x18002b8b7  mov     [rbp+0A0h+var_80], rbx
0x18002b8bb  mov     r14d, 800h
0x18002b8c1  test    eax, eax
0x18002b8c3  jnz     loc_18002B94B
0x18002b8c9  mov     rax, gs:30h
0x18002b8d2  add     rax, r14
0x18002b8d5  jz      loc_18002C814
0x18002b8db  mov     rax, gs:30h
0x18002b8e4  cmp     [rax+8E8h], ebx
0x18002b8ea  jnz     loc_18002C70A
0x18002b8f0  mov     eax, cs:gDefaultDpiContext
0x18002b8f6  and     al, 0Fh
0x18002b8f8  cmp     al, cl
0x18002b8fa  jz      loc_18002C54B
0x18002b900  mov     eax, cs:gfServerProcess
0x18002b906  test    eax, eax
0x18002b908  jnz     short loc_18002B94B
0x18002b90a  mov     rax, gs:30h
0x18002b913  add     rax, r14
0x18002b916  jz      loc_18002C8E7
0x18002b91c  mov     rax, gs:30h
0x18002b925  cmp     [rax+8E8h], ebx
0x18002b92b  jz      loc_18002C8FD
0x18002b931  mov     rax, gs:30h
0x18002b93a  mov     eax, [rax+8E8h]
0x18002b940  and     eax, 0Fh
0x18002b943  cmp     al, 3
0x18002b945  jz      loc_18002C590
0x18002b94b  mov     [rbp+0A0h+var_120], ebx
0x18002b94e  mov     rax, gs:30h
0x18002b957  cmp     [rax+78h], rbx
0x18002b95b  jz      loc_18002C5D0
0x18002b961  mov     eax, 0FFFFh
0x18002b966  cmp     [rdi+2], ax
0x18002b96a  jz      loc_18002C5E8
0x18002b970  movzx   ecx, word ptr [rdi+0Ah]
0x18002b974  movzx   edx, word ptr [rdi+8]
0x18002b978  movzx   eax, word ptr [rdi+10h]
0x18002b97c  movzx   r12d, word ptr [rdi+0Eh]
0x18002b981  mov     r14d, [rdi+4]
0x18002b985  mov     ebx, [rdi]
0x18002b987  mov     [rbp+0A0h+var_10C], ecx
0x18002b98a  mov     [rbp+0A0h+var_C6], cx
0x18002b98e  movzx   ecx, word ptr [rdi+0Ch]
0x18002b992  mov     [rbp+0A0h+var_114], cx
0x18002b996  mov     [rbp+0A0h+var_C4], cx
0x18002b99a  mov     [rbp+0A0h+var_D8+8], r14d
0x18002b99e  mov     [rbp+0A0h+var_D8+0Ch], ebx
0x18002b9a1  mov     [rbp+0A0h+arg_10], dx
0x18002b9a8  mov     [rbp+0A0h+var_C8], dx
0x18002b9ac  mov     [rbp+0A0h+var_C2], r12w
0x18002b9b1  mov     [rbp+0A0h+var_110], eax
0x18002b9b4  mov     [rbp+0A0h+var_C0], ax
0x18002b9b8  movzx   r15d, bx
0x18002b9bc  mov     [rbp+0A0h+var_E8], r12d
0x18002b9c0  mov     esi, r15d
0x18002b9c3  test    r13, r13
0x18002b9c6  jz      loc_18002C871
0x18002b9cc  mov     rax, r13
0x18002b9cf  mov     rcx, rax
0x18002b9d2  call    RtlGetExpWinVer
0x18002b9d7  mov     r10d, 40000000h
0x18002b9dd  mov     r9d, 400h
0x18002b9e3  or      eax, r10d
0x18002b9e6  mov     edx, 4
0x18002b9eb  mov     [rbp+0A0h+var_B8], eax
0x18002b9ee  mov     [rbp+0A0h+var_48], rdx
0x18002b9f2  cmp     ax, r9w
0x18002b9f6  jb      loc_18002C5AB
0x18002b9fc  mov     rax, gs:30h
0x18002ba05  lea     ecx, [rdx-3]
0x18002ba08  btr     ebx, 0Fh
0x18002ba0c  mov     [rbp+0A0h+var_F4], ecx
0x18002ba0f  mov     [rbp+0A0h+var_D8+0Ch], ebx
0x18002ba12  cmp     [rax+810h], r9d
0x18002ba19  jb      loc_18002C908
0x18002ba1f  or      ebx, edx
0x18002ba21  mov     [rbp+0A0h+var_D8+0Ch], ebx
0x18002ba24  or      esi, edx
0x18002ba26  movzx   r15d, bx
0x18002ba2a  xor     r8d, r8d
0x18002ba2d  mov     edx, 8
0x18002ba32  movzx   eax, r15w
0x18002ba36  mov     r13d, ebx
0x18002ba39  mov     [rbp+0A0h+var_40], rdx
0x18002ba3d  shr     r13d, 6
0x18002ba41  and     r13d, edx
0x18002ba44  cmp     esi, eax
0x18002ba46  jnz     loc_18002C887
0x18002ba4c  test    bl, bl
0x18002ba4e  js      loc_18002C926
0x18002ba54  bt      ebx, 0Dh
0x18002ba58  jb      loc_18002C936
0x18002ba5e  test    r9d, ebx
0x18002ba61  jnz     loc_18002C5B9
0x18002ba67  bt      ebx, 16h
0x18002ba6b  jb      loc_18002C94A
0x18002ba71  test    bl, 2
0x18002ba74  jnz     loc_18002C958
0x18002ba7a  mov     esi, ebx
0x18002ba7c  and     esi, r10d
0x18002ba7f  jz      loc_18002C53D
0x18002ba85  test    r9d, ebx
0x18002ba88  jnz     loc_18002C53D
0x18002ba8e  mov     ecx, 0FFFF8000h
0x18002ba93  cmp     word ptr [rbp+0A0h+var_10C], cx
0x18002ba97  jz      loc_18002C964
0x18002ba9d  cmp     r12w, cx
0x18002baa1  jz      loc_18002C5C7
0x18002baa7  test    r12w, r12w
0x18002baab  jns     short loc_18002BAB7
0x18002baad  mov     eax, r8d
0x18002bab0  mov     [rbp+0A0h+var_C2], ax
0x18002bab4  mov     [rbp+0A0h+var_E8], eax
0x18002bab7  cmp     word ptr [rbp+0A0h+var_110], r8w
0x18002babc  jl      loc_18002C977
0x18002bac2  movzx   eax, word ptr [rbp+0A0h+var_D8]
0x18002bac6  neg     ax
0x18002bac9  sbb     rcx, rcx
0x18002bacc  and     rcx, rdx
0x18002bacf  add     rcx, 12h
0x18002bad3  add     rdi, rcx
0x18002bad6  movzx   r15d, word ptr [rdi]
0x18002bada  mov     [rbp+0A0h+var_A0], r15w
0x18002badf  test    r15w, r15w
0x18002bae3  jnz     loc_18002C986
0x18002bae9  mov     [rbp+0A0h+var_78], r8
0x18002baed  mov     rcx, rdi; unsigned __int16 *
0x18002baf0  call    ?SkipSz@@YAPEAEPEAG@Z; SkipSz(ushort *)
0x18002baf5  mov     rcx, rax
0x18002baf8  and     ecx, 1
0x18002bafb  add     rcx, rax; unsigned __int16 *
0x18002bafe  mov     [rbp+0A0h+var_60], rcx
0x18002bb02  mov     rdi, r8
0x18002bb05  mov     [rbp+0A0h+ho], r8
0x18002bb09  call    ?SkipSz@@YAPEAEPEAG@Z; SkipSz(ushort *)
0x18002bb0e  mov     rcx, rax
0x18002bb11  and     ecx, 1
0x18002bb14  add     rax, rcx
0x18002bb17  mov     rcx, rax; unsigned __int16 *
0x18002bb1a  mov     [rbp+0A0h+var_50], rax
0x18002bb1e  call    ?SkipSz@@YAPEAEPEAG@Z; SkipSz(ushort *)
0x18002bb23  mov     rcx, rax
0x18002bb26  and     ecx, 1
0x18002bb29  add     rcx, rax
0x18002bb2c  mov     [rbp+0A0h+var_58], rcx
0x18002bb30  mov     [rbp+0A0h+var_98], rcx
0x18002bb34  bt      ebx, 0Ch
0x18002bb38  jb      loc_18002C4DB
0x18002bb3e  mov     rcx, [rbp+0A0h+hWnd]; HWND
0x18002bb45  test    bl, 1
0x18002bb48  jnz     loc_18002C99F
0x18002bb4e  mov     edx, 1; unsigned int
0x18002bb53  call    ?GetDialogMonitor@@YAPEAUtagMONITOR@@PEAUHWND__@@K@Z; GetDialogMonitor(HWND__ *,ulong)
0x18002bb58  xor     r15d, r15d
0x18002bb5b  mov     r12, rax
0x18002bb5e  cmp     [rbp+0A0h+var_120], r15d
0x18002bb62  jnz     loc_18002C82F
0x18002bb68  mov     rsi, [rbp+0A0h+hWnd]
0x18002bb6f  xor     ecx, ecx; hdc
0x18002bb71  call    cs:__imp_CreateCompatibleDC
0x18002bb77  mov     rdi, rax
0x18002bb7a  test    rax, rax
0x18002bb7d  jz      loc_18002BD51
0x18002bb83  mov     rcx, rsi; HWND
0x18002bb86  mov     [rbp+0A0h+h], r15
0x18002bb8a  call    IsWindowGdiScaledX
0x18002bb8f  test    eax, eax
0x18002bb91  jnz     loc_18009AB71
0x18002bb97  test    bl, 40h
0x18002bb9a  jz      loc_18002C62E
0x18002bba0  mov     eax, [rbp+0A0h+var_F8]
0x18002bba3  lea     r8, [rbp+0A0h+var_D8]; struct DLGTEMPLATE2 *
0x18002bba7  mov     r9d, [rbp+0A0h+var_B8]; unsigned int
0x18002bbab  lea     rdx, [rbp+0A0h+var_98]; unsigned __int16 **
0x18002bbaf  mov     [rsp+1A0h+var_170], eax; unsigned int
0x18002bbb3  mov     rcx, rdi; hdc
0x18002bbb6  lea     rax, [rbp+0A0h+var_E0]
0x18002bbba  mov     [rsp+1A0h+var_180], rax; int *
0x18002bbbf  call    ?CreateDlgFont@@YAPEAUHFONT__@@PEAUHDC__@@PEAPEAGPEAUDLGTEMPLATE2@@KPEAHII@Z; CreateDlgFont(HDC__ *,ushort * *,DLGTEMPLATE2 *,ulong,int *,uint,uint)
0x18002bbc4  mov     ebx, [rbp+0A0h+var_D8+0Ch]
0x18002bbc7  mov     rcx, rax
0x18002bbca  mov     r14d, [rbp+0A0h+var_D8+8]
0x18002bbce  mov     rsi, rax
0x18002bbd1  mov     [rbp+0A0h+ho], rax
0x18002bbd5  or      r13d, 4
0x18002bbd9  neg     rcx
0x18002bbdc  sbb     eax, eax
0x18002bbde  and     eax, [rbp+0A0h+var_120]
0x18002bbe1  mov     [rbp+0A0h+var_E4], eax
0x18002bbe4  mov     rax, [rbp+0A0h+var_98]
0x18002bbe8  mov     [rbp+0A0h+var_58], rax
0x18002bbec  movzx   eax, [rbp+0A0h+var_C0]
0x18002bbf0  mov     [rbp+0A0h+var_110], eax
0x18002bbf3  movzx   eax, [rbp+0A0h+var_C2]
0x18002bbf7  mov     [rbp+0A0h+var_E8], eax
0x18002bbfa  movzx   eax, [rbp+0A0h+var_C4]
0x18002bbfe  mov     [rbp+0A0h+var_114], ax
0x18002bc02  movzx   eax, [rbp+0A0h+var_C6]
0x18002bc06  mov     [rbp+0A0h+var_10C], eax
0x18002bc09  movzx   eax, [rbp+0A0h+var_C8]
0x18002bc0d  mov     [rbp+0A0h+arg_10], ax
0x18002bc14  call    GetDpiServerInfoForCurrentThread
0x18002bc19  mov     eax, [rax+20h]
0x18002bc1c  mov     [rbp+0A0h+var_11C], eax
0x18002bc1f  call    GetDpiServerInfoForCurrentThread
0x18002bc24  mov     eax, [rax+24h]
0x18002bc27  mov     [rbp+0A0h+var_120], eax
0x18002bc2a  test    rsi, rsi
0x18002bc2d  jnz     loc_18002C6B4
0x18002bc33  test    r13b, 4
0x18002bc37  jz      short loc_18002BC48
0x18002bc39  mov     ecx, 0Dh; i
0x18002bc3e  call    cs:__imp_GetStockObject
0x18002bc44  mov     [rbp+0A0h+ho], rax
0x18002bc48  mov     esi, [rbp+0A0h+var_11C]
0x18002bc4b  test    r15, r15
0x18002bc4e  jnz     loc_18002CA47
0x18002bc54  mov     rcx, rdi; hdc
0x18002bc57  call    cs:__imp_DeleteDC
0x18002bc5d  bt      ebx, 1Ch
0x18002bc61  jb      loc_18002CA62
0x18002bc67  movsx   eax, word ptr [rbp+0A0h+var_E8]
0x18002bc6b  mov     edi, 4
0x18002bc70  movzx   r8d, [rbp+0A0h+var_A0]
0x18002bc75  mov     r9d, r14d
0x18002bc78  imul    eax, esi
0x18002bc7b  lea     ecx, [rdi+4]
0x18002bc7e  add     eax, 2
0x18002bc81  cdq
0x18002bc82  idiv    edi
0x18002bc84  mov     [rbp+0A0h+Point.x+8], eax
0x18002bc87  movsx   eax, word ptr [rbp+0A0h+var_110]
0x18002bc8b  imul    eax, [rbp+0A0h+var_120]
0x18002bc8f  add     eax, edi
0x18002bc91  cdq
0x18002bc92  idiv    ecx
0x18002bc94  mov     edx, ebx
0x18002bc96  lea     rcx, [rbp+0A0h+Point]
0x18002bc9a  mov     [rbp+0A0h+Point.y+8], eax
0x18002bc9d  mov     eax, [rbp+0A0h+var_F8]
0x18002bca0  mov     dword ptr [rsp+1A0h+var_180], eax
0x18002bca4  call    _AdjustWindowRectExForDpi
0x18002bca9  movzx   esi, word ptr [rbp+0A0h+Point.y+8]
0x18002bcad  sub     si, word ptr [rbp+0A0h+Point.y]
0x18002bcb1  movzx   eax, word ptr [rbp+0A0h+Point.x+8]
0x18002bcb5  sub     ax, word ptr [rbp+0A0h+Point.x]
0x18002bcb9  movsx   r15d, ax
0x18002bcbd  mov     [rbp+0A0h+var_118], esi
0x18002bcc0  bt      ebx, 0Ch
0x18002bcc4  jb      loc_18002BD79
0x18002bcca  mov     eax, [rbp+0A0h+var_F4]
0x18002bccd  test    ebx, 1800h
0x18002bcd3  jnz     loc_18002CA6F
0x18002bcd9  movsx   eax, word ptr [rbp+0A0h+var_10C]
0x18002bcdd  mov     ecx, 8
0x18002bce2  imul    eax, [rbp+0A0h+var_11C]
0x18002bce6  add     eax, 2
0x18002bce9  cdq
0x18002bcea  idiv    edi
0x18002bcec  mov     edi, eax
0x18002bcee  mov     [rbp+0A0h+Point.x], eax
0x18002bcf1  movsx   eax, [rbp+0A0h+var_114]
0x18002bcf5  imul    eax, [rbp+0A0h+var_120]
0x18002bcf9  add     eax, 4
0x18002bcfc  cdq
0x18002bcfd  idiv    ecx
0x18002bcff  mov     [rbp+0A0h+Point.y], eax
0x18002bd02  mov     esi, eax
0x18002bd04  test    bl, 1
  ... truncated ...
```
