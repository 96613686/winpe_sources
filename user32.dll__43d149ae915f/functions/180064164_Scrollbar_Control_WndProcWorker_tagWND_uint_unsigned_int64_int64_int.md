# Scrollbar::Control::WndProcWorker(tagWND *,uint,unsigned __int64,__int64,int)

- ea: `0x180064164`
- end: `0x180064b30`
- name: `?WndProcWorker@Control@Scrollbar@@YA_JPEAUtagWND@@I_K_JH@Z`
- size: `2508`
- prototype: `__int64(Scrollbar::Control *__hidden this, struct tagWND *, unsigned int, unsigned __int64, __int64, int)`
- caller_count: `3`
- callee_count: `31`
- tags: `loader_planting, installer_update`

## callers

- `0x180064110`
- `0x180070760`
- `0x180074cd0`

## callees

- `0x1800070e0`
- `0x180007640`
- `0x18000b4e0`
- `0x18000d9f0`
- `0x180010950`
- `0x180029f40`
- `0x18003bb00`
- `0x18003f6f0`
- `0x18003fb84`
- `0x180043ac0`
- `0x18004bc84`
- `0x180052258`
- `0x180053bc8`
- `0x180057d24`
- `0x18005cc64`
- `0x180064164`
- `0x180066410`
- `0x18006fb60`
- `0x180073718`
- `0x18008a3c8`
- `0x18008a5d0`
- `0x18008a6b0`
- `0x18008acf0`
- `0x18008afbc`
- `0x18008b0ac`
- `0x18008b7ec`
- `0x18008bcb4`
- `0x18008c178`
- `0x180096b64`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserShowCaret` at `0x180064314`
- `win32u!NtUserShowCaret` at `0x180064823`
- `win32u!NtUserShowCaret` at `0x180064314`
- `win32u!NtUserShowCaret` at `0x180064823`
- `win32u!NtUserCreateCaret` at `0x180064300`
- `win32u!NtUserCreateCaret` at `0x180064300`
- `win32u!NtUserDestroyCaret` at `0x1800642a4`
- `win32u!NtUserDestroyCaret` at `0x1800642c0`
- `win32u!NtUserDestroyCaret` at `0x1800642a4`
- `win32u!NtUserDestroyCaret` at `0x1800642c0`
- `win32u!NtUserHideCaret` at `0x180064774`
- `win32u!NtUserHideCaret` at `0x180064963`
- `win32u!NtUserHideCaret` at `0x180064774`
- `win32u!NtUserHideCaret` at `0x180064963`
- `win32u!NtUserReleaseDC` at `0x180064817`
- `win32u!NtUserReleaseDC` at `0x180064817`
- `win32u!NtUserSetWindowFNID` at `0x1800641fc`
- `win32u!NtUserSetWindowFNID` at `0x1800641fc`
- `win32u!NtUserSetFocus` at `0x180064957`
- `win32u!NtUserSetFocus` at `0x180064957`
- `win32u!NtUserMoveWindow` at `0x1800644e4`
- `win32u!NtUserMoveWindow` at `0x1800644e4`
- `win32u!NtUserGetWindowDC` at `0x1800647bd`
- `win32u!NtUserGetWindowDC` at `0x1800647bd`
- `win32u!NtUserEndPaint` at `0x18006492a`
- `win32u!NtUserEndPaint` at `0x18006492a`
- `win32u!NtUserBeginPaint` at `0x1800648a3`
- `win32u!NtUserBeginPaint` at `0x1800648a3`
- `ntdll!RtlSetLastWin32Error` at `0x1800644f4`
- `ntdll!RtlSetLastWin32Error` at `0x1800644f4`
- `ntdll!RtlFreeHeap` at `0x180064631`
- `ntdll!RtlFreeHeap` at `0x180064631`
- `GDI32!SelectObject` at `0x1800647dd`
- `GDI32!SelectObject` at `0x18006480e`
- `GDI32!SelectObject` at `0x1800647dd`
- `GDI32!SelectObject` at `0x18006480e`

## pseudocode

```c
unsigned __int64 __fastcall Scrollbar::Control::WndProcWorker(
        Scrollbar::Control *this,
        struct tagWND *a2,
        struct tagWND *a3,
        _OWORD *a4,
        HDC a5)
{
  unsigned int v6; // r15d
  _DWORD *v9; // r14
  unsigned __int8 WindowLongW; // al
  struct tagSCROLLBARINFO *v11; // r9
  unsigned int v12; // edi
  __int64 v13; // rcx
  __int64 v14; // rdx
  bool v15; // zf
  unsigned __int64 result; // rax
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // r9d
  struct tagSBWND *v20; // rdx
  __int64 v21; // r8
  int v22; // r15d
  int v23; // ebx
  int v24; // r13d
  int v25; // r12d
  char v26; // al
  int v27; // ecx
  int v28; // eax
  char v29; // al
  __int64 v30; // rdx
  int v31; // r12d
  int v32; // esi
  unsigned int DpiForSystem; // eax
  int DpiDependentMetric; // r13d
  __int64 v35; // rdx
  __int64 v36; // rcx
  unsigned int v37; // eax
  int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  int v42; // r13d
  __int64 v43; // rax
  __int64 v44; // rdx
  Scrollbar *v45; // rcx
  _QWORD *v46; // r8
  PVOID v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rdx
  struct tagSBWND *v50; // rdx
  struct tagSBWND *v51; // rdx
  unsigned int v52; // r8d
  __int64 v53; // rdx
  struct tagWND *WindowDC; // rsi
  int v55; // r9d
  HDC ColorObjects; // rbx
  HGDIOBJ v57; // rax
  void *v58; // rdi
  struct tagWND *v59; // rsi
  __int64 v60; // rax
  int v61; // edi
  struct tagSBWND *v62; // rdx
  unsigned __int16 KeyState; // ax
  __int64 v64; // rcx
  __int64 v65; // r9
  __int64 v66; // r11
  _QWORD *v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // rax
  char v70; // r10
  __int64 v71; // rax
  struct tagWND *v72; // rcx
  char *v73; // rbx
  char *v74; // rbx
  char *v75; // rbx
  char *v76; // rbx
  char *v77; // rbx
  char *v78; // rbx
  Scrollbar *v79; // rcx
  int v80; // eax
  struct tagWND *v81; // rdx
  __int64 v82; // r8
  char *v83; // rbx
  char *v84; // rbx
  char *v85; // rbx
  char *v86; // rbx
  char *v87; // rbx
  char *v88; // rbx
  struct tagSCROLLINFO *v89; // [rsp+20h] [rbp-A1h]
  HBRUSH v90; // [rsp+20h] [rbp-A1h]
  unsigned int v91; // [rsp+28h] [rbp-99h]
  struct tagSCROLLINFO v92; // [rsp+30h] [rbp-91h] BYREF
  _OWORD v93[2]; // [rsp+50h] [rbp-71h] BYREF
  _BYTE v94[80]; // [rsp+70h] [rbp-51h] BYREF

  v92.fMask = 0;
  v6 = (unsigned int)a2;
  *(_QWORD *)&v92.nMin = 0;
  memset_0(v94, 0, 0x48u);
  memset(v93, 0, 28);
  if ( *((_WORD *)this + 21) )
  {
    if ( *((_WORD *)this + 21) != 666 )
      return 0;
  }
  else
  {
    if ( *((_DWORD *)this + 50) < (int)*(unsigned __int16 *)(gpsi + 328) )
      return 0;
    NtUserSetWindowFNID(*(_QWORD *)this, 666);
  }
  v9 = (_DWORD *)*((_QWORD *)this + 37);
  *(_QWORD *)v9 = this;
  WindowLongW = GetWindowLongW(*(HWND *)this, -16);
  v12 = 1;
  v92.cbSize = WindowLongW;
  v13 = WindowLongW & 0x18;
  v92.nTrackPos = WindowLongW & 0x18;
  v14 = 3;
  if ( v6 > 0xE1 )
  {
    if ( v6 > 0xEB )
    {
      if ( v6 == 256 )
      {
        v83 = (char *)a3 - 33;
        if ( v83 )
        {
          v84 = v83 - 1;
          if ( v84 )
          {
            v85 = v84 - 1;
            if ( v85 )
            {
              v86 = v85 - 1;
              if ( v86 )
              {
                v87 = v86 - 1;
                if ( v87 && (v88 = v87 - 1) != 0 )
                {
                  if ( (unsigned __int64)(v88 - 1) >= 2 )
                    return 0;
                }
                else
                {
                  v12 = 0;
                }
              }
              else
              {
                v12 = 6;
              }
            }
            else
            {
              v12 = 7;
            }
          }
          else
          {
            v12 = 3;
          }
        }
        else
        {
          v12 = 2;
        }
        v79 = *(Scrollbar **)v9;
        v80 = v9[2];
        v81 = *(struct tagWND **)(*(_QWORD *)v9 + 48LL);
        if ( v81 )
          v81 = (struct tagWND *)((char *)v81 + (_QWORD)v79 - *((_QWORD *)v79 + 1));
        v82 = v12;
      }
      else
      {
        if ( v6 != 257 )
        {
          if ( v6 != 513 )
          {
            if ( v6 != 515 )
            {
              v15 = v6 == 792;
              goto LABEL_117;
            }
            if ( (WindowLongW & 0x18) != 0 )
            {
              v64 = *(_QWORD *)v9;
              v92.nMin = (__int16)a4;
              v92.nMax = SWORD1(a4);
              ClientToScreen(v64, &v92.nMin);
              v67 = (_QWORD *)(v65 + 8);
              v68 = *(_QWORD *)(v65 + 48);
              if ( v68 )
                v69 = v65 + v68 - *v67;
              else
                v69 = 0;
              v70 = *(_BYTE *)(v69 + 26) & 0x40;
              if ( v68 )
                v71 = v65 + v68 - *v67;
              else
                v71 = 0;
              if ( v68 )
                v72 = (struct tagWND *)(v65 + v68 - *v67);
              else
                v72 = 0;
              SendMessageWorker(
                v72,
                0x112u,
                v66 | (((v70 == 0) ^ ((unsigned __int64)*(unsigned __int8 *)(v71 + 25) >> 6) & 1) + 7),
                (HTOUCHINPUT)(LOWORD(v92.nMin) | (LOWORD(v92.nMax) << 16)),
                (unsigned int)a5);
              return 0;
            }
          }
          if ( (*(_BYTE *)(*(_QWORD *)v9 + 30LL) & 1) != 0 )
            NtUserSetFocus(**(_QWORD **)v9);
          NtUserHideCaret(**(_QWORD **)v9, v14);
          Scrollbar::Control::Setup((Scrollbar::Control *)v9, v62);
          KeyState = GetKeyState(16);
          Scrollbar::TrackInit(*(Scrollbar **)v9, (struct tagWND *)a4, 0, KeyState >> 15, (unsigned int)a5, v91);
          return 0;
        }
        v73 = (char *)a3 - 33;
        if ( v73 )
        {
          v74 = v73 - 1;
          if ( v74 )
          {
            v75 = v74 - 1;
            if ( v75 )
            {
              v76 = v75 - 1;
              if ( v76 )
              {
                v77 = v76 - 1;
                if ( v77 )
                {
                  v78 = v77 - 1;
                  if ( v78 )
                  {
                    if ( (unsigned __int64)(v78 - 1) > 1 )
                      return 0;
                  }
                }
              }
            }
          }
        }
        v79 = *(Scrollbar **)v9;
        v80 = v9[2];
        v81 = *(struct tagWND **)(*(_QWORD *)v9 + 48LL);
        if ( v81 )
          v81 = (struct tagWND *)((char *)v81 + (_QWORD)v79 - *((_QWORD *)v79 + 1));
        v82 = 8;
      }
      Scrollbar::DoScroll(v79, v81, (struct tagWND *)v82, 0, v80, (int)a5, v92.cbSize);
      return 0;
    }
    if ( v6 == 235 )
    {
      LODWORD(result) = Scrollbar::GetScrollBarInfo(*(Scrollbar **)v9, (struct tagWND *)0xFFFFFFFCLL, (int)a4, v11);
      return (int)result;
    }
    v42 = 0;
    if ( v6 != 226 )
    {
      if ( v6 == 227 )
      {
        *(_DWORD *)a3 = v9[4];
        *(_DWORD *)a4 = v9[5];
        return *((unsigned __int16 *)v9 + 8) | ((unsigned __int64)*((unsigned __int16 *)v9 + 10) << 16);
      }
      if ( v6 == 228 )
      {
        LODWORD(result) = Scrollbar::Control::EnableArrows(
                            *(Scrollbar::Control **)v9,
                            (struct tagWND *)(unsigned int)a3,
                            WindowLongW);
        return (int)result;
      }
      if ( v6 != 230 )
      {
        if ( v6 == 233 )
        {
          v42 = (int)a3;
LABEL_97:
          v92.cbSize = 1;
          if ( (unsigned int)Scrollbar::SetScrollBarParameters(
                               (Scrollbar *)(v9 + 4),
                               (struct tagSBDATA *)a4,
                               &v92,
                               (int *)&v92.fMask,
                               (int *)v89) )
            NotifyWinEvent(0x800Eu, **(HWND **)v9, -4, 0);
          if ( v42 )
          {
            NtUserHideCaret(**(_QWORD **)v9, v49);
            Scrollbar::Control::Setup((Scrollbar::Control *)v9, v50);
            Scrollbar::Control::SetCaretPosition((Scrollbar::Control *)v9, v51);
            if ( (unsigned int)FChildVisible(*(_QWORD *)v9) )
            {
              if ( v92.cbSize || (*((_BYTE *)a4 + 4) & 8) == 0 )
                v53 = 0;
              else
                v53 = 3;
              Scrollbar::Control::EnableArrows(*(Scrollbar::Control **)v9, (struct tagWND *)v53, v52);
              WindowDC = (struct tagWND *)NtUserGetWindowDC(**(_QWORD **)v9);
              ColorObjects = (HDC)Scrollbar::GetColorObjects(*(Scrollbar **)v9, WindowDC, (HDC)(unsigned int)a5, v55);
              v57 = SelectObject((HDC)WindowDC, ColorObjects);
              LODWORD(v90) = v9[2];
              v58 = v57;
              Scrollbar::DrawThumbWorker(
                *(Scrollbar **)v9,
                (struct tagWND *)(v9 + 4),
                WindowDC,
                ColorObjects,
                v90,
                v9[3],
                v92.cbSize);
              SelectObject((HDC)WindowDC, v58);
              NtUserReleaseDC(WindowDC);
            }
            NtUserShowCaret(**(_QWORD **)v9);
          }
          return (int)v92.fMask;
        }
        if ( v6 != 234 )
          return DefWindowProcWorker(*(struct tagWND **)v9, v6, (unsigned __int64)a3, (__int64)a4, (unsigned int)a5);
        LODWORD(result) = Scrollbar::GetScrollBarParameters(
                            *(Scrollbar **)v9,
                            (struct tagWND *)2,
                            (int)v9 + 16,
                            (struct tagSBDATA *)a4,
                            v89);
        return (int)result;
      }
      v42 = 1;
    }
    *((_QWORD *)&v93[0] + 1) = __PAIR64__((unsigned int)a4, (unsigned int)a3);
    DWORD1(v93[0]) = 4097;
LABEL_96:
    a4 = v93;
    LODWORD(v93[0]) = 28;
    goto LABEL_97;
  }
  if ( v6 == 225 )
    return (int)v9[7];
  if ( v6 <= 0x14 )
  {
    if ( v6 != 20 )
    {
      if ( v6 != 1 )
      {
        switch ( v6 )
        {
          case 5u:
            if ( GetFocus() != **(HWND **)v9 )
              return 0;
            ((void (*)(void))NtUserDestroyCaret)();
            break;
          case 7u:
            break;
          case 8u:
            NtUserDestroyCaret(v13, 3);
            return 0;
          case 0xAu:
            return SendMessageWorker(*(struct tagWND **)v9, 0xE4u, -(__int64)(a3 == 0) & 3, 0, (unsigned int)a5);
          default:
            v15 = v6 == 15;
LABEL_117:
            if ( v15 )
            {
              v59 = a3;
              if ( !a3 )
              {
                v60 = NtUserBeginPaint(**(_QWORD **)v9, v94);
                LODWORD(v13) = v92.nTrackPos;
                v59 = (struct tagWND *)v60;
              }
              if ( (_DWORD)v13 )
              {
                v61 = *(_BYTE *)(*(_QWORD *)v9 + 30LL) & 4;
                if ( (*(_BYTE *)(*(_QWORD *)v9 + 30LL) & 4) == 0 )
                  SetWindowState(*(struct tagWND **)v9, 0xE04u);
                Scrollbar::DrawSize(*(Scrollbar **)v9, v59, 0, 0, (int)v89);
                if ( !v61 )
                  ClearWindowState(*(struct tagWND **)v9, 0xE04u);
              }
              else
              {
                Scrollbar::Control::Setup((Scrollbar::Control *)v9, (struct tagSBWND *)v14);
                Scrollbar::DrawScrollBarWorker(
                  *(Scrollbar **)v9,
                  (struct tagWND *)(v9 + 4),
                  v59,
                  (HDC)(unsigned int)v9[2],
                  v9[3],
                  (unsigned int)a5,
                  v92.cbSize);
              }
              if ( !a3 )
                NtUserEndPaint(**(_QWORD **)v9, v94);
              return 0;
            }
            return DefWindowProcWorker(*(struct tagWND **)v9, v6, (unsigned __int64)a3, (__int64)a4, (unsigned int)a5);
        }
        Scrollbar::Control::Setup((Scrollbar::Control *)v9, (struct tagSBWND *)v14);
        v17 = *(_QWORD *)v9;
        if ( v9[2] )
        {
          v18 = *(_DWORD *)(v17 + 96) - *(_DWORD *)(v17 + 88);
          v19 = v9[12];
        }
        else
        {
          v19 = *(_DWORD *)(v17 + 100) - *(_DWORD *)(v17 + 92);
          v18 = v9[12];
        }
        NtUserCreateCaret(*(_QWORD *)v17, 1, (unsigned int)(v18 - 4), (unsigned int)(v19 - 4));
        Scrollbar::Control::SetCaretPosition((Scrollbar::Control *)v9, v20);
        NtUserShowCaret(**(_QWORD **)v9);
        return 0;
      }
      if ( !a4 )
      {
        RtlSetLastWin32Error(0x57u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_32548531b4b03368806a3b84a4bddd4e_Traceguids);
        }
        return 0;
      }
      v21 = *(_QWORD *)v9;
      v22 = *((_DWORD *)a4 + 11);
      v23 = *((_DWORD *)a4 + 10);
      v24 = *((_DWORD *)a4 + 9);
      v25 = *((_DWORD *)a4 + 8);
      v26 = *(_BYTE *)(*(_QWORD *)v9 + 31LL) & 0xC0;
      if ( v22 == 0x80000000 )
      {
        if ( v26 )
          v22 = 0;
        else
          v22 = *(_DWORD *)(v21 + 88);
      }
      if ( v23 == 0x80000000 )
      {
        if ( v26 )
          v23 = 0;
        else
          v23 = *(_DWORD *)(v21 + 92);
      }
      if ( v24 == 0x80000000 )
      {
        if ( v26 )
          v24 = 0;
        else
          v24 = *(_DWORD *)(v21 + 96) - *(_DWORD *)(v21 + 88);
      }
      if ( v25 == 0x80000000 )
      {
        if ( v26 )
          v25 = 0;
        else
          v25 = *(_DWORD *)(v21 + 100) - *(_DWORD *)(v21 + 92);
      }
      if ( !(_DWORD)v13 )
      {
        v27 = *(_DWORD *)a4;
        v28 = (unsigned __int16)*(_DWORD *)a4;
        v9[4] = v28;
        v9[7] = v28;
        v9[5] = HIWORD(v27);
        v29 = GetWindowLongW(*(HWND *)v21, -16);
        v9[6] = 0;
        v9[2] = v29 & 1;
      }
      if ( (GetWindowLongW(**(HWND **)v9, -16) & 0x8000000) != 0 )
        v9[3] = 3;
      if ( (v92.cbSize & 6) == 0 )
        return 0;
      v31 = v23 + v25;
      v32 = v22 + v24;
      if ( v92.nTrackPos )
      {
        DpiForSystem = GetDpiForSystem(v92.cbSize, v30);
        DpiDependentMetric = GetDpiDependentMetric(0, DpiForSystem);
        v37 = GetDpiForSystem(v36, v35);
        v38 = GetDpiDependentMetric(1, v37);
        if ( (v92.cbSize & 4) != 0 )
        {
          v22 = v32 - DpiDependentMetric;
          v23 = v31 - v38;
        }
        v32 = v22 + DpiDependentMetric;
      }
      else
      {
        if ( (v92.cbSize & 1) != 0 )
        {
          v39 = GetDpiForSystem(v92.cbSize, v30);
          if ( (v92.cbSize & 2) != 0 )
            v32 = v22 + GetDpiDependentMetric(0, v39);
          else
            v22 = v32 - GetDpiDependentMetric(0, v39);
          goto LABEL_58;
        }
        if ( (v92.cbSize & 2) == 0 )
        {
          v41 = GetDpiForSystem(v92.cbSize, v30);
          v23 = v31 - GetDpiDependentMetric(1, v41);
          goto LABEL_58;
        }
        v40 = GetDpiForSystem(v92.cbSize, v30);
        v38 = GetDpiDependentMetric(1, v40);
      }
      v31 = v23 + v38;
LABEL_58:
      v92.nMin = v22;
      v92.nPage = v32 - v22;
      v92.nPos = v31 - v23;
      v92.nMax = v23;
      ConstrainWindowSIZERECT(&v92.nMin);
      NtUserMoveWindow(**(_QWORD **)v9, (unsigned int)v92.nMin, (unsigned int)v92.nMax, v92.nPage, v92.nPos, 0);
      return 0;
    }
    return 1;
  }
  switch ( v6 )
  {
    case 0x1Fu:
      v48 = *(_QWORD *)NtCurrentTeb()->Win32ClientInfo[35];
      if ( v48 && *(_QWORD *)(v48 + 48) )
        Scrollbar::EndScroll(this, (struct tagWND *)1, (int)a5, (int)v11);
      return 0;
    case 0x70u:
      v46 = *(_QWORD **)NtCurrentTeb()->Win32ClientInfo[35];
      if ( v46 )
      {
        *(_QWORD *)NtCurrentTeb()->Win32ClientInfo[35] = 0;
        v47 = pUserHeap;
        v46[3] = 0;
        v46[2] = 0;
        v46[1] = 0;
        RtlFreeHeap(v47, 0, v46);
      }
      return 0;
    case 0x7Bu:
      v44 = *(_QWORD *)v9;
      v45 = *(Scrollbar **)(*(_QWORD *)v9 + 48LL);
      if ( v45 )
        v45 = (Scrollbar *)((char *)v45 + v44 - *(_QWORD *)(v44 + 8));
      LODWORD(v89) = (_DWORD)a5;
      Scrollbar::DoScrollMenu(
        v45,
        (struct tagWND *)v44,
        (struct tagWND *)(unsigned int)v9[2],
        (int)a4,
        (__int64)v89,
        v91);
      return 0;
  }
  if ( v6 != 132 )
  {
    if ( v6 == 135 )
      return 1;
    if ( v6 != 224 )
      return DefWindowProcWorker(*(struct tagWND **)v9, v6, (unsigned __int64)a3, (__int64)a4, (unsigned int)a5);
    v42 = (int)a4;
    DWORD1(v93[0]) = 4100;
    DWORD1(v93[1]) = (_DWORD)a3;
    goto LABEL_96;
  }
  if ( (WindowLongW & 0x10) == 0 )
    return DefWindowProcWorker(*(struct tagWND **)v9, v6, (unsigned __int64)a3, (__int64)a4, (unsigned int)a5);
  v43 = *(_QWORD *)(*(_QWORD *)v9 + 48LL);
  if ( v43 )
    v43 = *(_QWORD *)v9 + v43 - *(_QWORD *)(*(_QWORD *)v9 + 8LL);
  return 17LL - (((*(unsigned __int8 *)(*(_QWORD *)v9 + 26LL) >> 6) & 1) != ((*(unsigned __int8 *)(v43 + 25) >> 6) & 1));
}

```

## disassembly

```asm
0x180064164  push    rbp
0x180064166  push    rbx
0x180064167  push    rsi
0x180064168  push    rdi
0x180064169  push    r12
0x18006416b  push    r13
0x18006416d  push    r14
0x18006416f  push    r15
0x180064171  lea     rbp, [rsp-17h]
0x180064176  sub     rsp, 0D8h
0x18006417d  mov     rax, cs:__security_cookie
0x180064184  xor     rax, rsp
0x180064187  mov     [rbp+4Fh+var_50], rax
0x18006418b  mov     r12d, dword ptr [rbp+4Fh+arg_20]
0x18006418f  xor     edi, edi
0x180064191  mov     rbx, r8
0x180064194  mov     [rsp+110h+var_E0.fMask], edi
0x180064198  mov     r15d, edx
0x18006419b  mov     qword ptr [rsp+110h+var_E0.nMin], rdi
0x1800641a0  mov     r13, rcx
0x1800641a3  xor     edx, edx; Val
0x1800641a5  lea     r8d, [rdi+48h]; Size
0x1800641a9  mov     rsi, r9
0x1800641ac  lea     rcx, [rbp+4Fh+var_A0]; void *
0x1800641b0  call    memset_0
0x1800641b5  xorps   xmm0, xmm0
0x1800641b8  movups  [rbp+4Fh+var_C0], xmm0
0x1800641bc  movups  [rbp+4Fh+var_C0+0Ch], xmm0
0x1800641c0  cmp     [r13+2Ah], di
0x1800641c5  jz      short loc_1800641D8
0x1800641c7  mov     edx, 29Ah
0x1800641cc  cmp     [r13+2Ah], dx
0x1800641d1  jz      short loc_180064202
0x1800641d3  jmp     loc_180064B0E
0x1800641d8  mov     rax, cs:gpsi
0x1800641df  movzx   ecx, word ptr [rax+148h]
0x1800641e6  cmp     [r13+0C8h], ecx
0x1800641ed  jl      loc_180064B0E
0x1800641f3  mov     rcx, [r13+0]
0x1800641f7  mov     edx, 29Ah
0x1800641fc  call    cs:__imp_NtUserSetWindowFNID
0x180064202  mov     r14, [r13+128h]
0x180064209  mov     edx, 0FFFFFFF0h; nIndex
0x18006420e  mov     [r14], r13
0x180064211  mov     rcx, [r13+0]; hWnd
0x180064215  call    GetWindowLongW
0x18006421a  movzx   r8d, al; unsigned int
0x18006421e  mov     edi, 1
0x180064223  mov     ecx, r8d
0x180064226  mov     [rsp+110h+var_E0.cbSize], r8d; int
0x18006422b  and     ecx, 18h
0x18006422e  mov     eax, 0E1h
0x180064233  mov     [rbp+4Fh+var_E0.nTrackPos], ecx
0x180064236  lea     edx, [rdi+2]
0x180064239  cmp     r15d, eax
0x18006423c  ja      loc_18006467E
0x180064242  jz      loc_180064675
0x180064248  cmp     r15d, 14h
0x18006424c  ja      loc_18006453F
0x180064252  jz      loc_18006457D
0x180064258  mov     eax, r15d
0x18006425b  sub     eax, edi
0x18006425d  jz      loc_18006431F
0x180064263  sub     eax, 4
0x180064266  jz      short loc_1800642AF
0x180064268  sub     eax, 2
0x18006426b  jz      short loc_1800642C6
0x18006426d  sub     eax, edi
0x18006426f  jz      short loc_1800642A4
0x180064271  sub     eax, 2
0x180064274  jz      short loc_18006427E
0x180064276  cmp     eax, 5
0x180064279  jmp     loc_180064874
0x18006427e  mov     rcx, [r14]; struct tagWND *
0x180064281  neg     rbx
0x180064284  mov     dword ptr [rsp+110h+var_F0], r12d; int
0x180064289  sbb     r8, r8
0x18006428c  xor     r9d, r9d; __int64
0x18006428f  not     r8
0x180064292  and     r8, rdx; unsigned __int64
0x180064295  mov     edx, 0E4h; unsigned int
0x18006429a  call    ?SendMessageWorker@@YA_JPEAUtagWND@@I_K_JH@Z; SendMessageWorker(tagWND *,uint,unsigned __int64,__int64,int)
0x18006429f  jmp     loc_180064B10
0x1800642a4  call    cs:__imp_NtUserDestroyCaret
0x1800642aa  jmp     loc_180064B0E
0x1800642af  call    GetFocus
0x1800642b4  mov     rcx, [r14]
0x1800642b7  cmp     rax, [rcx]
0x1800642ba  jnz     loc_180064B0E
0x1800642c0  call    cs:__imp_NtUserDestroyCaret
0x1800642c6  mov     rcx, r14; this
0x1800642c9  call    ?Setup@Control@Scrollbar@@YAXPEAUtagSBWND@@@Z; Scrollbar::Control::Setup(tagSBWND *)
0x1800642ce  cmp     dword ptr [r14+8], 0
0x1800642d3  mov     rcx, [r14]
0x1800642d6  jz      short loc_1800642E6
0x1800642d8  mov     r8d, [rcx+60h]
0x1800642dc  sub     r8d, [rcx+58h]
0x1800642e0  mov     r9d, [r14+30h]
0x1800642e4  jmp     short loc_1800642F2
0x1800642e6  mov     r9d, [rcx+64h]
0x1800642ea  sub     r9d, [rcx+5Ch]
0x1800642ee  mov     r8d, [r14+30h]
0x1800642f2  mov     rcx, [rcx]
0x1800642f5  add     r9d, 0FFFFFFFCh
0x1800642f9  add     r8d, 0FFFFFFFCh
0x1800642fd  mov     rdx, rdi
0x180064300  call    cs:__imp_NtUserCreateCaret
0x180064306  mov     rcx, r14; this
0x180064309  call    ?SetCaretPosition@Control@Scrollbar@@YAXPEAUtagSBWND@@@Z; Scrollbar::Control::SetCaretPosition(tagSBWND *)
0x18006430e  mov     rcx, [r14]
0x180064311  mov     rcx, [rcx]
0x180064314  call    cs:__imp_NtUserShowCaret
0x18006431a  jmp     loc_180064B0E
0x18006431f  xor     edx, edx
0x180064321  test    rsi, rsi
0x180064324  jz      loc_1800644EF
0x18006432a  mov     r8, [r14]
0x18006432d  mov     r9d, 80000000h
0x180064333  mov     r15d, [rsi+2Ch]
0x180064337  mov     ebx, [rsi+28h]
0x18006433a  mov     r13d, [rsi+24h]
0x18006433e  mov     al, [r8+1Fh]
0x180064342  mov     r12d, [rsi+20h]
0x180064346  and     al, 0C0h
0x180064348  cmp     r15d, r9d
0x18006434b  jnz     short loc_18006435A
0x18006434d  test    al, al
0x18006434f  jnz     short loc_180064357
0x180064351  mov     r15d, [r8+58h]
0x180064355  jmp     short loc_18006435A
0x180064357  mov     r15d, edx
0x18006435a  cmp     ebx, r9d
0x18006435d  jnz     short loc_18006436B
0x18006435f  test    al, al
0x180064361  jnz     short loc_180064369
0x180064363  mov     ebx, [r8+5Ch]
0x180064367  jmp     short loc_18006436B
0x180064369  mov     ebx, edx
0x18006436b  cmp     r13d, r9d
0x18006436e  jnz     short loc_180064381
0x180064370  test    al, al
0x180064372  jnz     short loc_18006437E
0x180064374  mov     r13d, [r8+60h]
0x180064378  sub     r13d, [r8+58h]
0x18006437c  jmp     short loc_180064381
0x18006437e  mov     r13d, edx
0x180064381  cmp     r12d, r9d
0x180064384  jnz     short loc_180064397
0x180064386  test    al, al
0x180064388  jnz     short loc_180064394
0x18006438a  mov     r12d, [r8+64h]
0x18006438e  sub     r12d, [r8+5Ch]
0x180064392  jmp     short loc_180064397
0x180064394  mov     r12d, edx
0x180064397  test    ecx, ecx
0x180064399  jnz     short loc_1800643CE
0x18006439b  mov     ecx, [rsi]
0x18006439d  mov     edx, 0FFFFFFF0h; nIndex
0x1800643a2  movzx   eax, cx
0x1800643a5  shr     rcx, 10h
0x1800643a9  mov     [r14+10h], eax
0x1800643ad  mov     [r14+1Ch], eax
0x1800643b1  movzx   eax, cx
0x1800643b4  mov     [r14+14h], eax
0x1800643b8  mov     rcx, [r8]; hWnd
0x1800643bb  call    GetWindowLongW
0x1800643c0  and     eax, edi
0x1800643c2  mov     dword ptr [r14+18h], 0
0x1800643ca  mov     [r14+8], eax
0x1800643ce  mov     rcx, [r14]
0x1800643d1  mov     edx, 0FFFFFFF0h; nIndex
0x1800643d6  mov     rcx, [rcx]; hWnd
0x1800643d9  call    GetWindowLongW
0x1800643de  bt      eax, 1Bh
0x1800643e2  jnb     short loc_1800643EC
0x1800643e4  mov     dword ptr [r14+0Ch], 3
0x1800643ec  mov     ecx, [rsp+110h+var_E0.cbSize]
0x1800643f0  test    cl, 6
0x1800643f3  jz      loc_180064B0E
0x1800643f9  add     r12d, ebx
0x1800643fc  lea     esi, [r15+r13]
0x180064400  cmp     [rbp+4Fh+var_E0.nTrackPos], 0
0x180064404  jz      short loc_18006443D
0x180064406  call    GetDpiForSystem
0x18006440b  mov     edx, eax
0x18006440d  xor     ecx, ecx
0x18006440f  call    GetDpiDependentMetric
0x180064414  mov     r13d, eax
0x180064417  call    GetDpiForSystem
0x18006441c  mov     edx, eax
0x18006441e  mov     ecx, edi
0x180064420  call    GetDpiDependentMetric
0x180064425  test    byte ptr [rsp+110h+var_E0.cbSize], 4
0x18006442a  jz      short loc_180064437
0x18006442c  mov     r15d, esi
0x18006442f  mov     ebx, r12d
0x180064432  sub     r15d, r13d
0x180064435  sub     ebx, eax
0x180064437  lea     esi, [r15+r13]
0x18006443b  jmp     short loc_180064487
0x18006443d  mov     eax, ecx
0x18006443f  and     eax, 2
0x180064442  test    dil, cl
0x180064445  jz      short loc_180064475
0x180064447  test    eax, eax
0x180064449  jz      short loc_18006445F
0x18006444b  call    GetDpiForSystem
0x180064450  mov     edx, eax
0x180064452  xor     ecx, ecx
0x180064454  call    GetDpiDependentMetric
0x180064459  lea     esi, [r15+rax]
0x18006445d  jmp     short loc_1800644A0
0x18006445f  call    GetDpiForSystem
0x180064464  mov     edx, eax
0x180064466  xor     ecx, ecx
0x180064468  call    GetDpiDependentMetric
0x18006446d  mov     r15d, esi
0x180064470  sub     r15d, eax
0x180064473  jmp     short loc_1800644A0
0x180064475  test    eax, eax
0x180064477  jz      short loc_18006448D
0x180064479  call    GetDpiForSystem
0x18006447e  mov     edx, eax
0x180064480  mov     ecx, edi
0x180064482  call    GetDpiDependentMetric
0x180064487  lea     r12d, [rbx+rax]
0x18006448b  jmp     short loc_1800644A0
0x18006448d  call    GetDpiForSystem
0x180064492  mov     edx, eax
0x180064494  mov     ecx, edi
0x180064496  call    GetDpiDependentMetric
0x18006449b  mov     ebx, r12d
0x18006449e  sub     ebx, eax
0x1800644a0  sub     esi, r15d
0x1800644a3  mov     [rsp+110h+var_E0.nMin], r15d
0x1800644a8  sub     r12d, ebx
0x1800644ab  mov     [rsp+110h+var_E0.nPage], esi
0x1800644af  lea     rcx, [rsp+110h+var_E0.nMin]
0x1800644b4  mov     [rbp+4Fh+var_E0.nPos], r12d
0x1800644b8  mov     [rsp+110h+var_E0.nMax], ebx
0x1800644bc  call    ConstrainWindowSIZERECT
0x1800644c1  mov     rcx, [r14]
0x1800644c4  mov     eax, [rbp+4Fh+var_E0.nPos]
0x1800644c7  mov     r9d, [rsp+110h+var_E0.nPage]
0x1800644cc  mov     r8d, [rsp+110h+var_E0.nMax]
0x1800644d1  mov     rcx, [rcx]
0x1800644d4  mov     edx, [rsp+110h+var_E0.nMin]
0x1800644d8  mov     [rsp+110h+var_E8], 0
0x1800644e0  mov     dword ptr [rsp+110h+var_F0], eax
0x1800644e4  call    cs:__imp_NtUserMoveWindow
0x1800644ea  jmp     loc_180064B0E
0x1800644ef  mov     ecx, 57h ; 'W'; LastError
0x1800644f4  call    cs:__imp_RtlSetLastWin32Error
0x1800644fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180064501  lea     rax, WPP_GLOBAL_Control
0x180064508  cmp     rcx, rax
0x18006450b  jz      loc_180064B0E
0x180064511  test    byte ptr [rcx+1Ch], 20h
0x180064515  jz      loc_180064B0E
0x18006451b  cmp     byte ptr [rcx+19h], 2
0x18006451f  jb      loc_180064B0E
0x180064525  mov     rcx, [rcx+10h]
0x180064529  lea     r8, WPP_32548531b4b03368806a3b84a4bddd4e_Traceguids
0x180064530  mov     edx, 43h ; 'C'
0x180064535  call    WPP_SF_
0x18006453a  jmp     loc_180064B0E
0x18006453f  mov     eax, r15d
0x180064542  sub     eax, 1Fh
0x180064545  jz      loc_18006463C
0x18006454b  sub     eax, 51h ; 'Q'
0x18006454e  jz      loc_1800645ED
0x180064554  sub     eax, 0Bh
0x180064557  jz      short loc_1800645C4
0x180064559  sub     eax, 9
0x18006455c  jz      short loc_180064585
0x18006455e  sub     eax, edx
0x180064560  jz      short loc_18006457D
0x180064562  cmp     eax, 59h ; 'Y'
0x180064565  jnz     loc_180064876
0x18006456b  mov     r13d, esi
0x18006456e  mov     dword ptr [rbp+4Fh+var_C0+4], 1004h
0x180064575  mov     [rbp+4Fh+var_AC], ebx
0x180064578  jmp     loc_1800646EA
0x18006457d  mov     rax, rdi
0x180064580  jmp     loc_180064B10
0x180064585  test    r8b, 10h
0x180064589  jz      loc_180064876
0x18006458f  mov     rdx, [r14]
0x180064592  movzx   ecx, byte ptr [rdx+1Ah]
0x180064596  mov     rax, [rdx+30h]
0x18006459a  shr     ecx, 6
0x18006459d  and     ecx, edi
0x18006459f  test    rax, rax
0x1800645a2  jz      short loc_1800645AB
0x1800645a4  sub     rax, [rdx+8]
0x1800645a8  add     rax, rdx
0x1800645ab  movzx   eax, byte ptr [rax+19h]
0x1800645af  shr     eax, 6
0x1800645b2  and     eax, edi
0x1800645b4  sub     eax, ecx
  ... truncated ...
```
