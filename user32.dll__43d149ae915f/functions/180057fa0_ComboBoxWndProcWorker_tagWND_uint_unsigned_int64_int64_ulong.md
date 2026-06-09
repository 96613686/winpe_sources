# ComboBoxWndProcWorker(tagWND *,uint,unsigned __int64,__int64,ulong)

- ea: `0x180057fa0`
- end: `0x1800591a0`
- name: `?ComboBoxWndProcWorker@@YA_JPEAUtagWND@@I_K_JK@Z`
- size: `4608`
- prototype: `__int64 __fastcall(struct tagWND *, unsigned int, unsigned __int64, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `43`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180038734`
- `0x180057e40`
- `0x180057ef0`
- `0x180079a1c`

## callees

- `0x18000b4e0`
- `0x18000cf20`
- `0x18000d210`
- `0x18000d9f0`
- `0x180010950`
- `0x180016320`
- `0x1800385c8`
- `0x1800386b8`
- `0x18003b4a0`
- `0x18003bb00`
- `0x180043ac0`
- `0x180044150`
- `0x18004b360`
- `0x18004bc84`
- `0x18004c550`
- `0x18004cc10`
- `0x18004dce4`
- `0x180052578`
- `0x180057fa0`
- `0x180061ed0`
- `0x180062c6c`
- `0x18006ea48`
- `0x18006eb30`
- `0x18006fad4`
- `0x1800753c8`
- `0x1800754c4`
- `0x1800755e4`
- `0x1800757a4`
- `0x18007583c`
- `0x180075970`
- `0x180075f5c`
- `0x180076044`
- `0x180076168`
- `0x180076400`
- `0x1800767a0`
- `0x180076804`
- `0x180076b90`
- `0x180076c00`
- `0x180076d3c`
- `0x180085fac`
- `0x180096c4c`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserEnableWindow` at `0x1800581a8`
- `win32u!NtUserEnableWindow` at `0x1800581c1`
- `win32u!NtUserEnableWindow` at `0x1800581a8`
- `win32u!NtUserEnableWindow` at `0x1800581c1`
- `win32u!NtUserSetWindowFNID` at `0x180058043`
- `win32u!NtUserSetWindowFNID` at `0x1800580e3`
- `win32u!NtUserSetWindowFNID` at `0x180058043`
- `win32u!NtUserSetWindowFNID` at `0x1800580e3`
- `win32u!NtUserReleaseCapture` at `0x180058c9b`
- `win32u!NtUserReleaseCapture` at `0x180058ed4`
- `win32u!NtUserReleaseCapture` at `0x180058f6a`
- `win32u!NtUserReleaseCapture` at `0x180058c9b`
- `win32u!NtUserReleaseCapture` at `0x180058ed4`
- `win32u!NtUserReleaseCapture` at `0x180058f6a`
- `win32u!NtUserSetFocus` at `0x180058275`
- `win32u!NtUserSetFocus` at `0x180058f06`
- `win32u!NtUserSetFocus` at `0x180058275`
- `win32u!NtUserSetFocus` at `0x180058f06`
- `win32u!NtUserSetCapture` at `0x180058fa7`
- `win32u!NtUserSetCapture` at `0x180058fa7`
- `win32u!NtUserInvalidateRect` at `0x180058184`
- `win32u!NtUserInvalidateRect` at `0x180058521`
- `win32u!NtUserInvalidateRect` at `0x180058184`
- `win32u!NtUserInvalidateRect` at `0x180058521`
- `win32u!NtUserGetComboBoxInfo` at `0x180058c1c`
- `win32u!NtUserGetComboBoxInfo` at `0x180058c1c`
- `win32u!NtUserEndPaint` at `0x1800583a3`
- `win32u!NtUserEndPaint` at `0x1800583a3`
- `win32u!NtUserDestroyWindow` at `0x1800580ec`
- `win32u!NtUserDestroyWindow` at `0x1800580ec`
- `win32u!NtUserBeginPaint` at `0x18005836d`
- `win32u!NtUserBeginPaint` at `0x18005836d`
- `ntdll!RtlSetLastWin32Error` at `0x180058a27`
- `ntdll!RtlSetLastWin32Error` at `0x18005910e`
- `ntdll!RtlSetLastWin32Error` at `0x180058a27`
- `ntdll!RtlSetLastWin32Error` at `0x18005910e`
- `ntdll!RtlFreeHeap` at `0x180058232`
- `ntdll!RtlFreeHeap` at `0x1800588de`
- `ntdll!RtlFreeHeap` at `0x180058232`
- `ntdll!RtlFreeHeap` at `0x1800588de`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800586b4`
- `api-ms-win-core-localization-l1-2-0!IsDBCSLeadByteEx` at `0x1800586b4`
- `GDI32!RestoreDC` at `0x1800590fb`
- `GDI32!RestoreDC` at `0x1800590fb`
- `GDI32!OffsetWindowOrgEx` at `0x1800590d0`
- `GDI32!OffsetWindowOrgEx` at `0x1800590d0`
- `GDI32!SaveDC` at `0x1800590b4`
- `GDI32!SaveDC` at `0x1800590b4`

## pseudocode

```c
LRESULT __fastcall ComboBoxWndProcWorker(HWND *a1, unsigned int a2, unsigned __int64 a3, __int64 a4, unsigned int a5)
{
  HWND v5; // r13
  HWND v10; // r9
  LRESULT result; // rax
  HWND **v12; // rax
  HWND **v13; // rdi
  HWND v14; // rax
  _QWORD *v15; // rdi
  __int64 v16; // r10
  __int64 v17; // rcx
  unsigned int v18; // edx
  _QWORD *v19; // rcx
  struct tagWND *v20; // rax
  __int64 v21; // rbx
  void *v22; // r8
  _QWORD *v23; // rcx
  int v24; // ecx
  __int64 v25; // rcx
  struct tagWND *v26; // rcx
  HDC v27; // r8
  unsigned int v28; // ecx
  unsigned int v29; // r8d
  int v30; // ebx
  LONG WindowLongW; // eax
  HWND *v32; // rcx
  LONG v33; // eax
  __int64 v34; // rax
  int v35; // r8d
  unsigned int v36; // r12d
  struct tagWND *v37; // rcx
  __int64 v38; // rbx
  HWND v39; // rax
  char *v40; // r15
  HWND v41; // rcx
  unsigned int v42; // r12d
  PVOID v43; // r12
  int v44; // eax
  int v45; // ebx
  int v46; // eax
  int v47; // eax
  unsigned int v48; // eax
  ULONG v49; // ecx
  __int64 v50; // r14
  int v51; // eax
  bool v52; // zf
  int v53; // ebx
  int v54; // ebx
  HWND *v55; // rax
  HWND v56; // rax
  HWND v57; // rax
  int v58; // ecx
  int v59; // eax
  unsigned __int64 v60; // rsi
  int v61; // r8d
  int v62; // edx
  __int64 v63; // rax
  unsigned __int64 v64; // r14
  int v65; // r8d
  int v66; // ebx
  int v67; // eax
  unsigned int v68; // eax
  int v69; // ebx
  int v70; // esi
  int v71; // ebx
  HWND v72; // rcx
  int v73; // eax
  int v74; // ebx
  PVOID P; // [rsp+30h] [rbp-71h] BYREF
  HWND hwnd; // [rsp+38h] [rbp-69h]
  __int64 v77; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v78[80]; // [rsp+50h] [rbp-51h] BYREF

  v5 = *a1;
  hwnd = *a1;
  memset_0(v78, 0, 0x48u);
  v10 = 0;
  P = 0;
  if ( *((_WORD *)a1 + 21) )
  {
    if ( *((_WORD *)a1 + 21) != 674 )
      return 0;
  }
  else
  {
    if ( *((_DWORD *)a1 + 50) < (int)*(unsigned __int16 *)(gpsi + 344) )
      return 0;
    NtUserSetWindowFNID(v5, 674);
    v10 = 0;
  }
  if ( !*(_QWORD *)a1[37] )
  {
    if ( dword_1800C88E8 )
    {
      if ( (int)InitLookaside((struct _LOOKASIDE *)&ComboboxLookaside, 0x68u, 8u) < 0 )
        goto LABEL_16;
      dword_1800C88E8 = 0;
    }
    v12 = (HWND **)AllocLookasideEntry((struct _LOOKASIDE *)&ComboboxLookaside);
    v13 = v12;
    if ( v12 )
    {
      _SetWindowLongPtr(v5, 0, (__int64)v12, 0);
      v10 = 0;
      *v13 = a1;
      goto LABEL_13;
    }
LABEL_16:
    NtUserSetWindowFNID(v5, 0x4000);
    NtUserDestroyWindow(v5);
    return 0;
  }
LABEL_13:
  v14 = a1[37];
  v15 = *(_QWORD **)v14;
  v16 = *(_QWORD *)(*(_QWORD *)v14 + 72LL);
  if ( !v16 )
  {
    v77 = 0;
    if ( !(unsigned int)ComboBoxMsgOKInInit(a2, &v77) )
      return v77;
  }
  if ( a2 > 0x147 )
  {
    if ( a2 > 0x200 )
    {
      if ( a2 > 0x215 )
      {
        switch ( a2 )
        {
          case 0x300u:
          case 0x301u:
          case 0x302u:
          case 0x303u:
            goto LABEL_126;
          case 0x317u:
            if ( !DefWindowProcWorker((struct tagWND *)a1, 0x317u, a3, a4, a5) )
              return 0;
            if ( (a4 & 0x20) != 0 && (v15[10] & 2) != 0 && (*(_BYTE *)(v15[9] + 31LL) & 0x10) != 0 )
            {
              v74 = SaveDC((HDC)a3);
              OffsetWindowOrgEx((HDC)a3, 0, *((_DWORD *)a1 + 23) - *(_DWORD *)(v15[9] + 92LL), 0);
              SendMessageWorker((struct tagWND *)v15[9], 0x317u, a3, (HTOUCHINPUT)(a4 & 0xFFFFFFFFFFFFFFFEuLL), 0);
              RestoreDC((HDC)a3, v74);
            }
            break;
          case 0x318u:
            xxxCBPaint((struct tagCBox *)v15, (HDC)a3);
            break;
          default:
            goto LABEL_315;
        }
        return 1;
      }
      switch ( a2 )
      {
        case 0x215u:
          v73 = *((_DWORD *)v15 + 20);
          if ( (v73 & 0x10) == 0 )
            return 1;
          *((_DWORD *)v15 + 20) = v73 & 0xFFFFFFEF;
          xxxPressButton((struct tagCBox *)v15, 0);
          v52 = (v15[10] & 0x40) == 0;
LABEL_307:
          if ( v52 )
            return 1;
          v35 = 0;
          goto LABEL_120;
        case 0x201u:
          goto LABEL_294;
        case 0x202u:
          xxxPressButton((struct tagCBox *)v15, 0);
          v67 = *((_DWORD *)v15 + 20);
          if ( (v67 & 0x10) != 0 )
          {
            v68 = v67 & 0xFFFFFFEF;
            *((_DWORD *)v15 + 20) = v68;
            if ( (v68 & 3) == 3 )
            {
              xxxCBUpdateListBoxWindow((struct tagCBox *)v15, 1);
              xxxCBCompleteEditWindow((struct tagCBox *)v15);
            }
            NtUserReleaseCapture();
            SendMessageWorker((struct tagWND *)v15[9], 0x1AEu, 0, 0, 0);
          }
          return 1;
        case 0x203u:
LABEL_294:
          v69 = *((_DWORD *)v15 + 20);
          if ( (v69 & 4) != 0 || (NtUserSetFocus(v5), v69 = *((_DWORD *)v15 + 20), (v69 & 4) != 0) )
          {
            if ( (LODWORD(P) = (__int16)a4, v70 = v69 & 3, HIDWORD(P) = SWORD1(a4), v70 == 3)
              && PtInRect((const RECT *)v15 + 2, (POINT)P)
              || v70 == 2 )
            {
              v71 = v69 | 0x20;
              *((_DWORD *)v15 + 20) = v71;
              if ( (v71 & 0x40) != 0 )
              {
                if ( (v71 & 0x10) != 0 )
                {
                  *((_DWORD *)v15 + 20) = v71 & 0xFFFFFFEF;
                  NtUserReleaseCapture();
                }
                xxxPressButton((struct tagCBox *)v15, 0);
                if ( !(unsigned int)xxxCBHideListBoxWindow((struct tagCBox *)v15, 1, 1) )
                  return 0;
              }
              else
              {
                xxxCBShowListBoxWindow((struct tagCBox *)v15, 0);
                v72 = hwnd;
                *((_DWORD *)v15 + 20) |= 0x10u;
                NtUserSetCapture(v72);
                NotifyWinEvent(0x800Au, hwnd, -4, 2);
              }
            }
          }
          return 1;
      }
      if ( a2 != 522 && a2 != 526 )
      {
        if ( a2 == 528 )
        {
          if ( (_WORD)a3 == 2 )
          {
            v55 = (HWND *)v15[8];
            if ( v55 )
              v56 = *v55;
            else
              v56 = v10;
            if ( (HWND)a4 == v56 )
            {
              *((_DWORD *)v15 + 20) &= ~1u;
              *((_DWORD *)v15 + 20) |= 0x4000u;
              v15[8] = a1;
            }
            else
            {
              v57 = v10;
              if ( v16 )
                v57 = *(HWND *)v16;
              if ( (HWND)a4 == v57 )
              {
                *((_DWORD *)v15 + 20) &= ~2u;
                v15[9] = v10;
              }
            }
          }
          return 1;
        }
        goto LABEL_315;
      }
      if ( (a3 & 0xC) != 0 )
      {
LABEL_317:
        v42 = a5;
        return DefWindowProcWorker((struct tagWND *)a1, a2, a3, a4, v42);
      }
      if ( (v15[10] & 0x40) == 0 )
      {
        if ( (v15[10] & 0x400) == 0 && (HWND)v15[8] != v10 )
        {
          v58 = (int)v10;
          v59 = (int)v10;
          if ( a2 == 522 )
          {
            LOBYTE(v58) = gcWheelDelta > 0;
            v60 = a3 >> 16;
            v61 = (__int16)v60;
            LOBYTE(v59) = (__int16)v60 > 0;
            if ( v58 == v59 )
              v61 = gcWheelDelta + (__int16)v60;
            v62 = v61 / 120;
            v63 = 40;
            gcWheelDelta = v61 % 120;
            v64 = 38;
          }
          else
          {
            LOBYTE(v58) = gcHorWheelDelta > 0;
            v60 = a3 >> 16;
            v65 = (__int16)v60;
            LOBYTE(v59) = (__int16)v60 > 0;
            if ( v58 == v59 )
              v65 = gcHorWheelDelta + (__int16)v60;
            v62 = v65 / 120;
            v63 = 37;
            gcHorWheelDelta = v65 % 120;
            v64 = 39;
          }
          if ( (__int16)v60 <= 0 )
            v64 = v63;
          v66 = -v62;
          if ( v62 > 0 )
            v66 = v62;
          while ( v66 > 0 )
          {
            --v66;
            SendMessageWorker((struct tagWND *)v15[8], 0x100u, v64, 0, a5);
          }
        }
        return 1;
      }
LABEL_272:
      v36 = a5;
      return SendMessageWorker((struct tagWND *)v15[9], a2, a3, (HTOUCHINPUT)a4, v36);
    }
    if ( a2 == 512 )
    {
      v53 = *((_DWORD *)v15 + 20);
      if ( (v53 & 0x10) == 0 )
        return 1;
      LODWORD(P) = (__int16)a4;
      HIDWORD(P) = SWORD1(a4);
      v54 = v53 & 0x20;
      if ( PtInRect((const RECT *)v15 + 2, (POINT)P) != (v54 != 0) )
        xxxPressButton((struct tagCBox *)v15, v54 == 0);
      ClientToScreen(a1, &P);
      if ( !PtInRect((const RECT *)(v15[9] + 104LL), (POINT)P) )
        return 1;
      *((_DWORD *)v15 + 20) &= ~0x10u;
      NtUserReleaseCapture();
      if ( (v15[10] & 1) != 0 )
        xxxCBUpdateListBoxWindow((struct tagCBox *)v15, 1);
      ScreenToClient(v15[9], &P);
      a2 = 513;
      a4 = (unsigned __int16)P | (WORD2(P) << 16);
      goto LABEL_272;
    }
    switch ( a2 )
    {
      case 0x148u:
        a2 = 393;
        goto LABEL_272;
      case 0x149u:
        a2 = 394;
        goto LABEL_272;
      case 0x14Au:
        if ( ((*((_DWORD *)v15 + 20) >> 11) & 3) != 0 )
          a2 = ((v15[10] & 0x800) == 0) | 0x1AA;
        else
          a2 = 385;
        goto LABEL_272;
      case 0x14Bu:
        SendMessageWorker((struct tagWND *)v16, 0x184u, 0, 0, (unsigned int)v10);
        xxxCBInternalUpdateEditWindow((struct tagCBox *)v15, 0);
        return 1;
      case 0x14Cu:
        a2 = 399;
        goto LABEL_272;
      case 0x14Du:
        v38 = SendMessageWorker((struct tagWND *)v16, 0x18Cu, a3, (HTOUCHINPUT)a4, a5);
        xxxCBInternalUpdateEditWindow((struct tagCBox *)v15, 0);
        return v38;
      case 0x14Eu:
        v50 = SendMessageWorker((struct tagWND *)v16, 0x186u, a3, (HTOUCHINPUT)a4, (unsigned int)v10);
        if ( v50 != -1 )
          SendMessageWorker((struct tagWND *)v15[9], 0x197u, a3, 0, 0);
        xxxCBInternalUpdateEditWindow((struct tagCBox *)v15, 0);
        return v50;
      case 0x14Fu:
        v51 = v15[10] & 0x40;
        if ( !a3 )
        {
          v52 = v51 == 0;
          goto LABEL_307;
        }
        if ( !v51 )
          xxxCBShowListBoxWindow((struct tagCBox *)v15, 1);
        return 1;
      case 0x150u:
        a2 = 409;
        goto LABEL_272;
      case 0x151u:
        a2 = 410;
        goto LABEL_272;
      case 0x152u:
        *(_DWORD *)a4 = *((_DWORD *)a1 + 22);
        *(_DWORD *)(a4 + 4) = *((_DWORD *)a1 + 23);
        v46 = *((_DWORD *)v15 + 14);
        if ( v46 <= *((_DWORD *)v15 + 12) )
          v46 = *((_DWORD *)v15 + 12);
        *(_DWORD *)(a4 + 8) = *((_DWORD *)a1 + 22) + v46;
        *(_DWORD *)(a4 + 12) = *((_DWORD *)a1 + 23) + *((_DWORD *)v15 + 13) + *((_DWORD *)v15 + 15);
        return 1;
      case 0x153u:
        if ( a3 != -1 )
        {
          a2 = 416;
          goto LABEL_272;
        }
        if ( WORD1(a4) )
          return -1;
        LODWORD(result) = xxxCBSetEditItemHeight((struct tagCBox *)v15, (unsigned __int16)a4);
        return (int)result;
      case 0x154u:
        if ( a3 == -1 )
        {
          LODWORD(result) = *((_DWORD *)v15 + 7) - *((_DWORD *)v15 + 5);
          return (int)result;
        }
        a2 = 417;
        goto LABEL_272;
      case 0x155u:
        v47 = *((_DWORD *)v15 + 20);
        if ( (v47 & 2) != 0 )
        {
          if ( !a3 )
          {
            v48 = v47 & 0xFFFFFBFF;
LABEL_202:
            *((_DWORD *)v15 + 20) = v48;
            return 0;
          }
          if ( a3 == 1 )
          {
            v48 = v47 | 0x400;
            goto LABEL_202;
          }
          v49 = 87;
        }
        else
        {
          v49 = 1002;
        }
        RtlSetLastWin32Error(v49);
        return -1;
      case 0x156u:
        return (v15[10] & 0x402) == 0x402;
      case 0x157u:
        return ((unsigned __int64)*((unsigned int *)v15 + 20) >> 6) & 1;
      case 0x158u:
        a2 = 418;
        goto LABEL_272;
      case 0x159u:
        a2 = 421;
        goto LABEL_272;
      case 0x15Au:
        a2 = 422;
        goto LABEL_272;
      case 0x15Bu:
        a2 = 398;
        goto LABEL_272;
      case 0x15Cu:
        a2 = 407;
        goto LABEL_272;
      case 0x15Du:
        a2 = 403;
        goto LABEL_272;
      case 0x15Eu:
        a2 = 404;
        goto LABEL_272;
      case 0x15Fu:
        goto LABEL_195;
      case 0x160u:
        if ( (v15[10] & 2) == 0 )
          return -1;
        if ( a3 )
        {
          if ( a3 <= *((unsigned int *)v15 + 12) )
            a3 = *((unsigned int *)v15 + 12);
          if ( a3 != *((_DWORD *)v15 + 14) )
          {
            *((_DWORD *)v15 + 14) = a3;
            xxxCBPosition((struct tagCBox *)v15);
          }
        }
LABEL_195:
        if ( (v15[10] & 2) == 0 )
          return -1;
        LODWORD(result) = *((_DWORD *)v15 + 14);
        if ( (int)result <= *((_DWORD *)v15 + 12) )
          LODWORD(result) = *((_DWORD *)v15 + 12);
        return (int)result;
      case 0x161u:
        a2 = 424;
        goto LABEL_272;
      case 0x164u:
        LODWORD(result) = NtUserGetComboBoxInfo(hwnd, a4, 0x4000);
        return (int)result;
      case 0x167u:
        xxxCBKillFocusHelper((struct tagCBox *)v15);
        return 1;
      default:
        goto LABEL_315;
    }
  }
  if ( a2 == 327 )
  {
    a2 = 392;
    goto LABEL_272;
  }
  v17 = 129;
  if ( a2 <= 0x81 )
  {
    if ( a2 == 129 )
    {
      LODWORD(result) = CBNcCreateHandler((struct tagCBox *)v15, (struct tagWND *)a1);
      return (int)result;
    }
    if ( a2 <= 0x14 )
    {
      if ( a2 == 20 )
        return 1;
      if ( a2 <= 0xB )
      {
        if ( a2 != 11 )
        {
          if ( a2 == 1 )
            return xxxCBCreateHandler((struct tagCBox *)v15, (struct tagWND *)a1);
          if ( a2 != 5 )
          {
            switch ( a2 )
            {
              case 7u:
                gcWheelDelta = (int)v10;
                gcHorWheelDelta = (int)v10;
                if ( (v15[10] & 0x4000) != 0 )
                {
                  xxxCBGetFocusHelper((struct tagCBox *)v15);
                }
                else
                {
                  v23 = (_QWORD *)v15[8];
                  if ( v23 )
                    NtUserSetFocus(*v23);
                }
                return 1;
              case 8u:
                if ( !a3 || (v20 = ValidateHwnd((HWND)a3), a3 = 0, !v20) || !(unsigned int)IsChild(a1, v20) )
                  xxxCBKillFocusHelper((struct tagCBox *)v15);
                v21 = **(_QWORD **)(v15[9] + 296LL);
                if ( (unsigned __int64)(v21 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                {
                  v22 = *(void **)(v21 + 168);
                  *(_DWORD *)(v21 + 164) = a3;
                  if ( v22 )
                  {
                    RtlFreeHeap(pUserHeap, 0, v22);
                    *(_QWORD *)(v21 + 168) = a3;
                  }
                }
                return 1;
              case 0xAu:
                NtUserInvalidateRect(hwnd, 0, 0);
                if ( (v15[10] & 1) != 0 )
                {
                  v19 = (_QWORD *)v15[8];
                  if ( v19 )
                  {
                    LOBYTE(v18) = ~*((_BYTE *)a1 + 31);
                    NtUserEnableWindow(*v19, (v18 >> 3) & 1);
                  }
                }
                LOBYTE(v18) = ~*((_BYTE *)a1 + 31);
                NtUserEnableWindow(*(_QWORD *)v15[9], (v18 >> 3) & 1);
                return 1;
            }
            goto LABEL_315;
          }
          if ( !(_WORD)a4 || !WORD1(a4) )
            return 0;
          if ( *((_DWORD *)v15 + 12) == *((_DWORD *)a1 + 24) - *((_DWORD *)a1 + 22) )
          {
            v24 = *((_DWORD *)v15 + 13);
            if ( (v15[10] & 0x40) != 0 )
              v24 += *((_DWORD *)v15 + 15);
            if ( v24 == *((_DWORD *)a1 + 25) - *((_DWORD *)a1 + 23) )
              return 0;
          }
          v25 = *v15;
          *((_DWORD *)v15 + 12) = *(_DWORD *)(*v15 + 96LL) - *(_DWORD *)(*v15 + 88LL);
          if ( *(_DWORD *)(v25 + 100) - *((_DWORD *)v15 + 13) - *(_DWORD *)(v25 + 92) > 0 )
            *((_DWORD *)v15 + 15) = -1;
          xxxCBPosition((struct tagCBox *)v15);
          return 1;
        }
        *((_DWORD *)v15 + 20) &= ~8u;
        *((_DWORD *)v15 + 20) |= (_DWORD)a3 == 0 ? 8 : 0;
        if ( (v15[10] & 0x4000) == 0 )
        {
          v26 = (struct tagWND *)v15[8];
          if ( v26 )
            SendMessageWorker(v26, 0xBu, a3, (HTOUCHINPUT)a4, (unsigned int)v10);
        }
        goto LABEL_272;
      }
      switch ( a2 )
      {
        case 0xCu:
          goto LABEL_126;
        case 0xDu:
          if ( (v15[10] & 0x4000) != 0 )
          {
            LODWORD(result) = xxxCBGetTextHelper((struct tagCBox *)v15, a3, (unsigned __int16 *)a4, a5);
            return (int)result;
          }
          break;
        case 0xEu:
          if ( (v15[10] & 0x4000) != 0 )
          {
            LODWORD(result) = xxxCBGetTextLengthHelper((struct tagCBox *)v15, a5);
            return (int)result;
          }
          break;
        case 0xFu:
          if ( !a3 )
            NtUserBeginPaint(v5, v78);
          if ( (v15[10] & 8) == 0 && (unsigned int)IsVisible(*v15) )
            xxxCBPaint((struct tagCBox *)v15, v27);
          if ( !a3 )
            NtUserEndPaint(v5, v78);
          return 1;
        default:
          goto LABEL_315;
      }
LABEL_127:
      v37 = (struct tagWND *)v15[8];
      if ( v37 )
        return SendMessageWorker(v37, a2, a3, (HTOUCHINPUT)a4, a5);
LABEL_326:
      RtlSetLastWin32Error(0x58Eu);
      return -1;
    }
    if ( a2 <= 0x31 )
    {
      if ( a2 == 49 )
        return v15[11];
      if ( a2 != 25 )
      {
        if ( a2 != 43 && a2 != 44 && a2 != 45 )
        {
          if ( a2 != 48 )
            goto LABEL_315;
          xxxCBSetFontHandler((struct tagCBox *)v15, (void *)a3, (unsigned __int16)a4);
          return 1;
        }
        return xxxCBMessageItemHandler((struct tagCBox *)v15, a2, (void *)a4);
      }
      goto LABEL_142;
    }
    if ( a2 == 57 )
      return xxxCBMessageItemHandler((struct tagCBox *)v15, a2, (void *)a4);
    if ( a2 == 83 )
    {
      if ( a4 )
      {
        if ( (v34 = v15[8]) != 0 && *(_DWORD *)(a4 + 8) == *(_DWORD *)(v34 + 320)
          || *(_DWORD *)(a4 + 8) == *(_DWORD *)(v16 + 320) )
        {
          *(_DWORD *)(a4 + 8) = *((_DWORD *)a1 + 80);
          *(_QWORD *)(a4 + 16) = v5;
          *(_QWORD *)(a4 + 24) = (unsigned int)GetContextHelpId(a1, -1, 0x4000);
        }
      }
      goto LABEL_315;
    }
    if ( a2 != 112 )
    {
      if ( a2 == 125 )
      {
        v28 = v15[10] & 0xFFFEFFFF | ((*((_BYTE *)a1 + 25) & 0x20) << 11);
        *((_DWORD *)v15 + 20) = v28;
        v29 = v28 & 0xFFFF7FFF | ((*((_BYTE *)a1 + 25) & 0x10) << 11);
        *((_DWORD *)v15 + 20) = v29;
        v30 = ((v29 & 0x10000) != 0 ? 0x6000 : 0) | 0x1000;
        if ( (v29 & 0x8000) == 0 )
          v30 = (v29 & 0x10000) != 0 ? 0x6000 : 0;
        WindowLongW = GetWindowLongW(*(HWND *)v16, -20);
        _SetWindowLong(*(HWND *)v15[9], -20, v30 | WindowLongW & 0xFFFF8FFF, 0);
        if ( (v15[10] & 0x4000) == 0 )
        {
          v32 = (HWND *)v15[8];
          if ( v32 )
          {
            v33 = GetWindowLongW(*v32, -20);
            _SetWindowLong(*(HWND *)v15[8], -20, v30 | v33 & 0xFFFF8FFF, 0);
          }
        }
        xxxCBPosition((struct tagCBox *)v15);
        NtUserInvalidateRect(v5, 0, 0);
        return 1;
      }
      goto LABEL_315;
    }
LABEL_136:
    xxxCBNcDestroyHandler((struct tagWND *)a1, (struct tagCBox *)v15);
    return 1;
  }
  if ( a2 > 0x135 )
  {
    if ( a2 <= 0x142 )
    {
      if ( a2 == 322 )
      {
        a3 = (__int16)a4;
        a2 = 177;
        a4 = SWORD1(a4);
        goto LABEL_126;
      }
      if ( a2 != 310 && a2 != 311 && a2 != 312 )
      {
        if ( a2 == 320 )
        {
          a2 = 176;
          goto LABEL_126;
        }
        if ( a2 == 321 )
        {
          a2 = 197;
          goto LABEL_126;
        }
        goto LABEL_315;
      }
      goto LABEL_142;
    }
    if ( a2 == 323 )
    {
      if ( ((*((_DWORD *)v15 + 20) >> 11) & 3) != 0 )
        a2 = ((v15[10] & 0x800) == 0) | 0x1AC;
      else
        a2 = 384;
      goto LABEL_272;
    }
    if ( a2 == 324 )
    {
      a2 = 386;
      goto LABEL_272;
    }
    if ( a2 != 325 )
    {
      a2 = 395;
      goto LABEL_272;
    }
    if ( !a5 || !a4 )
    {
      v43 = P;
      goto LABEL_167;
    }
    if ( (unsigned int)MBToWCSEx(0, a4, 0xFFFFFFFFLL, &P, -1, 1) )
    {
      v43 = P;
      a4 = (__int64)P;
LABEL_167:
      v44 = xxxLbDir(**(struct tagLBIV ***)(v15[9] + 296LL), (unsigned __int16)a3, (unsigned __int16 *)a4);
      if ( v44 == -2 )
      {
        v45 = -2;
      }
      else
      {
        v45 = -1;
        if ( v44 != -1 )
          v45 = v44;
      }
      if ( a5 && a4 )
        RtlFreeHeap(pUserHeap, 0, v43);
      return v45;
    }
    return -1;
  }
  if ( a2 == 309 )
    goto LABEL_142;
  if ( a2 > 0x111 )
  {
    if ( a2 == 296 )
    {
      v42 = a5;
      SendMessageWorker((struct tagWND *)v16, 0x128u, a3, (HTOUCHINPUT)a4, a5);
      return DefWindowProcWorker((struct tagWND *)a1, a2, a3, a4, v42);
    }
    if ( a2 != 306 && a2 - 307 > 1 )
      goto LABEL_315;
LABEL_142:
    v39 = a1[6];
    if ( v39 && (v40 = (char *)((char *)a1 - (char *)a1[1]), (HWND)((char *)v39 + (_QWORD)v40)) )
      v41 = *(HWND *)((char *)v39 + (_QWORD)v40);
    else
      v41 = v10;
    return SendMessageW(v41, a2, a3, a4);
  }
  if ( a2 == 273 )
  {
    LODWORD(result) = xxxCBCommandHandler((struct tagCBox *)v15, a3, (HWND)a4);
    return (int)result;
  }
  if ( a2 == 130 )
    goto LABEL_136;
  if ( a2 != 135 )
  {
    if ( a2 != 256 )
    {
      if ( a2 != 258 )
      {
        if ( a2 == 260 )
        {
          if ( (a4 & 0x20000000) != 0
            && ((a4 & 0x1000000) != 0 || (GetKeyState(144) & 1) == 0)
            && ((a3 - 38) & 0xFFFFFFFFFFFFFFFDuLL) == 0 )
          {
            if ( (v15[10] & 0x40) != 0 )
            {
              if ( !(unsigned int)xxxCBHideListBoxWindow((struct tagCBox *)v15, 1, 1) )
                return 0;
            }
            else
            {
              xxxCBShowListBoxWindow((struct tagCBox *)v15, 1);
            }
          }
          goto LABEL_317;
        }
LABEL_315:
        if ( *(_DWORD *)(gpsi + 2060) == (_DWORD)v10 || a2 - 896 > 0xF )
          goto LABEL_317;
LABEL_126:
        if ( (v15[10] & 0x4000) != 0 )
          goto LABEL_326;
        goto LABEL_127;
      }
LABEL_121:
      v36 = a5;
      if ( a5 && (*(_BYTE *)gpsi & 2) != 0 && IsDBCSLeadByteEx(LOWORD(NtCurrentTeb()->Win32ClientInfo[19]), a3) )
        return ComboBoxDBCharHandler((struct tagCBox *)v15, hwnd, a2, a3, a4);
      if ( (v15[10] & 0x4000) == 0 )
        goto LABEL_126;
      return SendMessageWorker((struct tagWND *)v15[9], a2, a3, (HTOUCHINPUT)a4, v36);
    }
    if ( (v15[10] & 0x40) == 0 || a3 != 13 && a3 != 27 )
      goto LABEL_121;
    v35 = (int)v10;
    LOBYTE(v35) = a3 != 27;
LABEL_120:
    xxxCBHideListBoxWindow((struct tagCBox *)v15, 1, v35);
    return 1;
  }
  if ( a4 && *(_DWORD *)(a4 + 8) == 256 && (v15[10] & 0x40) != 0 && (a3 == 13 || a3 == 27) )
    return 133;
  return v17;
}

```

## disassembly

```asm
0x180057fa0  push    rbp
0x180057fa2  push    rbx
0x180057fa3  push    rsi
0x180057fa4  push    rdi
0x180057fa5  push    r12
0x180057fa7  push    r13
0x180057fa9  push    r14
0x180057fab  push    r15
0x180057fad  lea     rbp, [rsp-17h]
0x180057fb2  sub     rsp, 0B8h
0x180057fb9  mov     rax, cs:__security_cookie
0x180057fc0  xor     rax, rsp
0x180057fc3  mov     [rbp+4Fh+var_50], rax
0x180057fc7  mov     r13, [rcx]
0x180057fca  mov     ebx, edx
0x180057fcc  xor     edx, edx; Val
0x180057fce  mov     [rbp+4Fh+hwnd], r13
0x180057fd2  mov     rsi, r8
0x180057fd5  mov     r15, rcx
0x180057fd8  lea     rcx, [rbp+4Fh+var_A0]; void *
0x180057fdc  mov     r14, r9
0x180057fdf  lea     r8d, [rdx+48h]; Size
0x180057fe3  call    memset_0
0x180057fe8  xor     r9d, r9d
0x180057feb  mov     [rbp+4Fh+P], r9
0x180057fef  cmp     [r15+2Ah], r9w
0x180057ff4  jz      short loc_180058024
0x180057ff6  mov     edx, 2A2h
0x180057ffb  cmp     [r15+2Ah], dx
0x180058000  jz      short loc_18005804C
0x180058002  xor     eax, eax
0x180058004  mov     rcx, [rbp+4Fh+var_50]
0x180058008  xor     rcx, rsp; StackCookie
0x18005800b  call    __security_check_cookie
0x180058010  add     rsp, 0B8h
0x180058017  pop     r15
0x180058019  pop     r14
0x18005801b  pop     r13
0x18005801d  pop     r12
0x18005801f  pop     rdi
0x180058020  pop     rsi
0x180058021  pop     rbx
0x180058022  pop     rbp
0x180058023  retn
0x180058024  mov     rax, cs:gpsi
0x18005802b  movzx   ecx, word ptr [rax+158h]
0x180058032  cmp     [r15+0C8h], ecx
0x180058039  jl      short loc_180058002
0x18005803b  mov     edx, 2A2h
0x180058040  mov     rcx, r13
0x180058043  call    cs:__imp_NtUserSetWindowFNID
0x180058049  xor     r9d, r9d
0x18005804c  mov     rax, [r15+128h]
0x180058053  cmp     [rax], r9
0x180058056  jnz     short loc_1800580AC
0x180058058  cmp     cs:dword_1800C88E8, r9d
0x18005805f  jz      short loc_180058082
0x180058061  mov     edx, 68h ; 'h'; unsigned int
0x180058066  lea     rcx, ?ComboboxLookaside@@3U_LOOKASIDE@@A; struct _LOOKASIDE *
0x18005806d  lea     r8d, [rdx-60h]; unsigned int
0x180058071  call    ?InitLookaside@@YAJPEAU_LOOKASIDE@@KK@Z; InitLookaside(_LOOKASIDE *,ulong,ulong)
0x180058076  xor     ecx, ecx
0x180058078  test    eax, eax
0x18005807a  js      short loc_1800580DB
0x18005807c  mov     cs:dword_1800C88E8, ecx
0x180058082  lea     rcx, ?ComboboxLookaside@@3U_LOOKASIDE@@A; struct _LOOKASIDE *
0x180058089  call    ?AllocLookasideEntry@@YAPEAXPEAU_LOOKASIDE@@@Z; AllocLookasideEntry(_LOOKASIDE *)
0x18005808e  mov     rdi, rax
0x180058091  test    rax, rax
0x180058094  jz      short loc_1800580DB
0x180058096  xor     r9d, r9d; int
0x180058099  mov     r8, rax; __int64
0x18005809c  xor     edx, edx; int
0x18005809e  mov     rcx, r13; HWND
0x1800580a1  call    ?_SetWindowLongPtr@@YA_JPEAUHWND__@@H_JH@Z; _SetWindowLongPtr(HWND__ *,int,__int64,int)
0x1800580a6  xor     r9d, r9d
0x1800580a9  mov     [rdi], r15
0x1800580ac  mov     rax, [r15+128h]
0x1800580b3  mov     rdi, [rax]
0x1800580b6  mov     r10, [rdi+48h]
0x1800580ba  test    r10, r10
0x1800580bd  jnz     short loc_1800580F7
0x1800580bf  lea     rdx, [rbp+4Fh+var_B0]; __int64 *
0x1800580c3  mov     [rbp+4Fh+var_B0], r9
0x1800580c7  mov     ecx, ebx; unsigned int
0x1800580c9  call    ?ComboBoxMsgOKInInit@@YAHIPEA_J@Z; ComboBoxMsgOKInInit(uint,__int64 *)
0x1800580ce  test    eax, eax
0x1800580d0  jnz     short loc_1800580F7
0x1800580d2  mov     rax, [rbp+4Fh+var_B0]
0x1800580d6  jmp     loc_180058004
0x1800580db  mov     edx, 4000h
0x1800580e0  mov     rcx, r13
0x1800580e3  call    cs:__imp_NtUserSetWindowFNID
0x1800580e9  mov     rcx, r13
0x1800580ec  call    cs:__imp_NtUserDestroyWindow
0x1800580f2  jmp     loc_180058002
0x1800580f7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800580fb  mov     eax, 147h
0x180058100  mov     r8d, 4000h
0x180058106  mov     r12d, 1
0x18005810c  cmp     ebx, eax
0x18005810e  ja      loc_180058927
0x180058114  jz      loc_18005891D
0x18005811a  mov     ecx, 81h
0x18005811f  cmp     ebx, ecx
0x180058121  ja      loc_1800585A6
0x180058127  jz      loc_180058596
0x18005812d  cmp     ebx, 14h
0x180058130  ja      loc_1800583E8
0x180058136  jz      loc_180059101
0x18005813c  cmp     ebx, 0Bh
0x18005813f  ja      loc_18005833E
0x180058145  jz      loc_1800582FB
0x18005814b  mov     eax, ebx
0x18005814d  sub     eax, r12d
0x180058150  jz      loc_1800582EB
0x180058156  sub     eax, 4
0x180058159  jz      loc_180058280
0x18005815f  lea     r13d, [r12+1]
0x180058164  sub     eax, r13d
0x180058167  jz      loc_180058244
0x18005816d  sub     eax, r12d
0x180058170  jz      short loc_1800581CC
0x180058172  cmp     eax, r13d
0x180058175  jnz     def_180058960; jumptable 0000000180058960 default case, cases 354,355,357,358
0x18005817b  mov     rcx, [rbp+4Fh+hwnd]
0x18005817f  xor     r8d, r8d
0x180058182  xor     edx, edx
0x180058184  call    cs:__imp_NtUserInvalidateRect
0x18005818a  test    [rdi+50h], r12b
0x18005818e  jz      short loc_1800581AE
0x180058190  mov     rcx, [rdi+40h]
0x180058194  test    rcx, rcx
0x180058197  jz      short loc_1800581AE
0x180058199  mov     dl, [r15+1Fh]
0x18005819d  mov     rcx, [rcx]
0x1800581a0  not     dl
0x1800581a2  shr     edx, 3
0x1800581a5  and     edx, r12d
0x1800581a8  call    cs:__imp_NtUserEnableWindow
0x1800581ae  mov     dl, [r15+1Fh]
0x1800581b2  mov     rcx, [rdi+48h]
0x1800581b6  not     dl
0x1800581b8  shr     edx, 3
0x1800581bb  and     edx, r12d
0x1800581be  mov     rcx, [rcx]
0x1800581c1  call    cs:__imp_NtUserEnableWindow
0x1800581c7  jmp     loc_180059101
0x1800581cc  test    rsi, rsi
0x1800581cf  jz      short loc_1800581EF
0x1800581d1  mov     rcx, rsi; HWND
0x1800581d4  call    ?ValidateHwnd@@YAPEAUtagWND@@PEAUHWND__@@@Z; ValidateHwnd(HWND__ *)
0x1800581d9  xor     esi, esi
0x1800581db  test    rax, rax
0x1800581de  jz      short loc_1800581EF
0x1800581e0  mov     rdx, rax
0x1800581e3  mov     rcx, r15
0x1800581e6  call    _IsChild
0x1800581eb  test    eax, eax
0x1800581ed  jnz     short loc_1800581F7
0x1800581ef  mov     rcx, rdi; struct tagCBox *
0x1800581f2  call    ?xxxCBKillFocusHelper@@YAXPEAUtagCBox@@@Z; xxxCBKillFocusHelper(tagCBox *)
0x1800581f7  mov     rax, [rdi+48h]
0x1800581fb  mov     rcx, [rax+128h]
0x180058202  mov     rbx, [rcx]
0x180058205  lea     rax, [rbx-1]
0x180058209  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005820d  ja      loc_180059101
0x180058213  mov     r8, [rbx+0A8h]; P
0x18005821a  mov     [rbx+0A4h], esi
0x180058220  test    r8, r8
0x180058223  jz      loc_180059101
0x180058229  mov     rcx, cs:pUserHeap; HeapHandle
0x180058230  xor     edx, edx; Flags
0x180058232  call    cs:__imp_RtlFreeHeap
0x180058238  mov     [rbx+0A8h], rsi
0x18005823f  jmp     loc_180059101
0x180058244  mov     cs:?gcWheelDelta@@3HA, r9d; int gcWheelDelta
0x18005824b  mov     cs:?gcHorWheelDelta@@3HA, r9d; int gcHorWheelDelta
0x180058252  test    [rdi+50h], r8d
0x180058256  jz      short loc_180058265
0x180058258  mov     rcx, rdi; struct tagCBox *
0x18005825b  call    ?xxxCBGetFocusHelper@@YAXPEAUtagCBox@@@Z; xxxCBGetFocusHelper(tagCBox *)
0x180058260  jmp     loc_180059101
0x180058265  mov     rcx, [rdi+40h]
0x180058269  test    rcx, rcx
0x18005826c  jz      loc_180059101
0x180058272  mov     rcx, [rcx]
0x180058275  call    cs:__imp_NtUserSetFocus
0x18005827b  jmp     loc_180059101
0x180058280  test    r14w, r14w
0x180058284  jz      loc_180058002
0x18005828a  shr     r14, 10h
0x18005828e  test    r14w, r14w
0x180058292  jz      loc_180058002
0x180058298  mov     eax, [r15+60h]
0x18005829c  sub     eax, [r15+58h]
0x1800582a0  cmp     [rdi+30h], eax
0x1800582a3  jnz     short loc_1800582C2
0x1800582a5  mov     r8d, [r15+64h]
0x1800582a9  sub     r8d, [r15+5Ch]
0x1800582ad  test    byte ptr [rdi+50h], 40h
0x1800582b1  mov     ecx, [rdi+34h]
0x1800582b4  jz      short loc_1800582B9
0x1800582b6  add     ecx, [rdi+3Ch]
0x1800582b9  cmp     ecx, r8d
0x1800582bc  jz      loc_180058002
0x1800582c2  mov     rcx, [rdi]
0x1800582c5  mov     eax, [rcx+60h]
0x1800582c8  sub     eax, [rcx+58h]
0x1800582cb  mov     [rdi+30h], eax
0x1800582ce  mov     eax, [rcx+64h]
0x1800582d1  sub     eax, [rdi+34h]
0x1800582d4  sub     eax, [rcx+5Ch]
0x1800582d7  test    eax, eax
0x1800582d9  jle     short loc_1800582DE
0x1800582db  mov     [rdi+3Ch], edx
0x1800582de  mov     rcx, rdi; struct tagCBox *
0x1800582e1  call    ?xxxCBPosition@@YAXPEAUtagCBox@@@Z; xxxCBPosition(tagCBox *)
0x1800582e6  jmp     loc_180059101
0x1800582eb  mov     rdx, r15; struct tagWND *
0x1800582ee  mov     rcx, rdi; struct tagCBox *
0x1800582f1  call    ?xxxCBCreateHandler@@YA_JPEAUtagCBox@@PEAUtagWND@@@Z; xxxCBCreateHandler(tagCBox *,tagWND *)
0x1800582f6  jmp     loc_180058004
0x1800582fb  and     dword ptr [rdi+50h], 0FFFFFFF7h
0x1800582ff  mov     eax, esi
0x180058301  neg     eax
0x180058303  sbb     ecx, ecx
0x180058305  not     ecx
0x180058307  and     ecx, 8
0x18005830a  or      [rdi+50h], ecx
0x18005830d  test    [rdi+50h], r8d
0x180058311  jnz     loc_180058D86
0x180058317  mov     rcx, [rdi+40h]; struct tagWND *
0x18005831b  test    rcx, rcx
0x18005831e  jz      loc_180058D86
0x180058324  mov     [rsp+0F0h+var_D0], r9d; int
0x180058329  mov     r8, rsi; unsigned __int64
0x18005832c  mov     r9, r14; __int64
0x18005832f  mov     edx, 0Bh; unsigned int
0x180058334  call    ?SendMessageWorker@@YA_JPEAUtagWND@@I_K_JH@Z; SendMessageWorker(tagWND *,uint,unsigned __int64,__int64,int)
0x180058339  jmp     loc_180058D86
0x18005833e  mov     eax, ebx
0x180058340  sub     eax, 0Ch
0x180058343  jz      loc_1800586EA
0x180058349  sub     eax, r12d
0x18005834c  jz      short loc_1800583C8
0x18005834e  sub     eax, r12d
0x180058351  jz      short loc_1800583AE
0x180058353  cmp     eax, r12d
0x180058356  jnz     def_180058960; jumptable 0000000180058960 default case, cases 354,355,357,358
0x18005835c  test    rsi, rsi
0x18005835f  jz      short loc_180058366
0x180058361  mov     r8, rsi
0x180058364  jmp     short loc_180058376
0x180058366  lea     rdx, [rbp+4Fh+var_A0]
0x18005836a  mov     rcx, r13
0x18005836d  call    cs:__imp_NtUserBeginPaint
0x180058373  mov     r8, rax
0x180058376  test    byte ptr [rdi+50h], 8
0x18005837a  jnz     short loc_180058393
0x18005837c  mov     rcx, [rdi]
0x18005837f  call    IsVisible
0x180058384  test    eax, eax
0x180058386  jz      short loc_180058393
0x180058388  mov     rdx, r8; HDC
0x18005838b  mov     rcx, rdi; struct tagCBox *
0x18005838e  call    ?xxxCBPaint@@YAXPEAUtagCBox@@PEAUHDC__@@@Z; xxxCBPaint(tagCBox *,HDC__ *)
0x180058393  test    rsi, rsi
0x180058396  jnz     loc_180059101
0x18005839c  lea     rdx, [rbp+4Fh+var_A0]
0x1800583a0  mov     rcx, r13
0x1800583a3  call    cs:__imp_NtUserEndPaint
0x1800583a9  jmp     loc_180059101
0x1800583ae  test    [rdi+50h], r8d
0x1800583b2  jz      loc_1800586F4
0x1800583b8  mov     edx, [rbp+4Fh+arg_20]; int
0x1800583bb  mov     rcx, rdi; struct tagCBox *
0x1800583be  call    ?xxxCBGetTextLengthHelper@@YAJPEAUtagCBox@@H@Z; xxxCBGetTextLengthHelper(tagCBox *,int)
0x1800583c3  jmp     loc_180058768
0x1800583c8  test    [rdi+50h], r8d
0x1800583cc  jz      loc_1800586F4
0x1800583d2  mov     r9d, [rbp+4Fh+arg_20]; int
0x1800583d6  mov     edx, esi; int
0x1800583d8  mov     r8, r14; unsigned __int16 *
0x1800583db  mov     rcx, rdi; struct tagCBox *
0x1800583de  call    ?xxxCBGetTextHelper@@YAJPEAUtagCBox@@HPEAGH@Z; xxxCBGetTextHelper(tagCBox *,int,ushort *,int)
0x1800583e3  jmp     loc_180058768
0x1800583e8  cmp     ebx, 31h ; '1'
0x1800583eb  ja      short loc_18005843B
0x1800583ed  jz      short loc_180058432
0x1800583ef  mov     eax, ebx
0x1800583f1  sub     eax, 19h
0x1800583f4  jz      loc_18005878D
0x1800583fa  sub     eax, 12h
0x1800583fd  jz      loc_180058584
0x180058403  sub     eax, r12d
0x180058406  jz      loc_180058584
0x18005840c  sub     eax, r12d
0x18005840f  jz      loc_180058584
  ... truncated ...
```
