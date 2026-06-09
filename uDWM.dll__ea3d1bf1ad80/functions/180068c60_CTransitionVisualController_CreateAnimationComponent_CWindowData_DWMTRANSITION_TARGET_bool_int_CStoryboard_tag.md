# CTransitionVisualController::CreateAnimationComponent(CWindowData *,DWMTRANSITION_TARGET,bool,int,CStoryboard *,tagRECT *,tagRECT *,int,bool,CAnimationComponent * *)

- ea: `0x180068c60`
- end: `0x180069b67`
- name: `?CreateAnimationComponent@CTransitionVisualController@@QEAAJPEAVCWindowData@@W4DWMTRANSITION_TARGET@@_NHPEAVCStoryboard@@PEAUtagRECT@@4H2PEAPEAVCAnimationComponent@@@Z`
- size: `3847`
- prototype: ``
- caller_count: `1`
- callee_count: `52`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068af0`

## callees

- `0x180004c30`
- `0x180005948`
- `0x180005ff4`
- `0x1800079bc`
- `0x18000802c`
- `0x180008100`
- `0x18000e98c`
- `0x180015cbc`
- `0x18001a2fc`
- `0x18001bca0`
- `0x18001ce00`
- `0x18001ce98`
- `0x18001d6fc`
- `0x18001f43c`
- `0x180029570`
- `0x180029930`
- `0x18002d0a4`
- `0x18002f470`
- `0x18002f4f0`
- `0x18002f7d4`
- `0x18002fbd0`
- `0x1800319b0`
- `0x18003a338`
- `0x180045f40`
- `0x180063e00`
- `0x180068c60`
- `0x18006d13c`
- `0x180070930`
- `0x180070dc8`
- `0x180071758`
- `0x180076a64`
- `0x180080914`
- `0x18008093c`
- `0x180082248`
- `0x180083af0`
- `0x18008a9b8`
- `0x18008ce1c`
- `0x180095130`
- `0x18009bf78`
- `0x18009c090`
- `0x18009c4fc`
- `0x18009c540`
- `0x18009e08c`
- `0x1800c1e04`
- `0x1800ce408`
- `0x1800cedb0`
- `0x1800cee28`
- `0x1800cefb4`
- `0x1800cf140`
- `0x1800cf904`

## import_xrefs

- `USER32!OffsetRect` at `0x180069465`
- `USER32!OffsetRect` at `0x18006947a`
- `USER32!OffsetRect` at `0x180069465`
- `USER32!OffsetRect` at `0x18006947a`
- `USER32!IsRectEmpty` at `0x180069758`
- `USER32!IsRectEmpty` at `0x180069758`
- `USER32!GetDesktopID` at `0x180068d6b`
- `USER32!GetDesktopID` at `0x180068d6b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CTransitionVisualController::CreateAnimationComponent(
        CTransitionVisualController *a1,
        struct CWindowData *WindowDataByHwnd,
        int a3,
        char a4,
        int a5,
        struct CStoryboard *a6,
        LPRECT lprc,
        __int64 a8,
        unsigned int a9,
        char a10,
        struct CAnimationComponent **a11)
{
  CAnimatedTransitionVisual *v14; // r12
  struct tagRECT *v15; // r14
  int v16; // eax
  unsigned int v17; // edi
  bool v18; // zf
  int v19; // edi
  HWND v20; // rbx
  __int64 v21; // r13
  struct tagRECT *v22; // r9
  CTransitionVisualController *v23; // rbx
  int DesktopAnimationComponent; // eax
  int v25; // eax
  char v26; // r15
  unsigned int v27; // ebx
  bool v28; // r13
  int v29; // edx
  int v30; // r8d
  int v31; // ecx
  int v32; // eax
  int v33; // ebx
  HWND *v34; // rdx
  int v35; // r8d
  int v36; // ecx
  int v37; // eax
  int v38; // edi
  int v39; // eax
  int v40; // eax
  bool v41; // di
  bool IsGhostWindow; // r8
  int v43; // ecx
  unsigned __int64 v44; // rcx
  unsigned __int8 v45; // bl
  struct tagRECT *v46; // r9
  void *v47; // rax
  int v48; // eax
  int v49; // eax
  CTransitionVisualController *v50; // rcx
  struct tagRECT *v51; // r9
  CTransitionVisualController **v52; // rax
  struct CWindowData *v53; // rdx
  const struct tagRECT *v54; // r8
  bool v55; // di
  CTransitionVisualController *v56; // r15
  int v57; // eax
  bool v58; // r9
  int v59; // eax
  unsigned int v60; // r15d
  int SharedVisualBrush; // eax
  CBaseObject *v62; // rdi
  int v63; // eax
  int v64; // eax
  int v65; // eax
  CVisual *v66; // rbx
  int v67; // eax
  int v68; // eax
  __int64 v69; // rcx
  int v70; // edx
  int v71; // ecx
  int v72; // eax
  struct tagRECT *v73; // r9
  struct CWindowData *v74; // rdx
  __int64 v75; // r15
  CTransitionVisualController *v76; // rcx
  int v77; // eax
  bool IsRTL; // al
  struct tagRECT v79; // xmm0
  int v80; // eax
  int v81; // eax
  LONG v82; // r8d
  LONG v83; // r9d
  int v84; // edx
  int v85; // ecx
  int v86; // eax
  int v87; // edx
  int v88; // ecx
  char v89; // bl
  int *v90; // rbx
  int v91; // eax
  struct tagRECT *v92; // r9
  bool v93; // r8
  struct CVisual *v94; // rdx
  int v95; // eax
  CAnimationComponent **v96; // r10
  CTransitionVisualController *v97; // rcx
  int v99; // [rsp+28h] [rbp-E0h]
  char v100; // [rsp+28h] [rbp-E0h]
  bool v101; // [rsp+58h] [rbp-B0h]
  bool v102; // [rsp+59h] [rbp-AFh]
  char v103; // [rsp+5Ah] [rbp-AEh]
  char v104; // [rsp+5Bh] [rbp-ADh]
  bool v105[4]; // [rsp+5Ch] [rbp-ACh] BYREF
  char v106; // [rsp+60h] [rbp-A8h]
  char v107; // [rsp+61h] [rbp-A7h]
  char v108; // [rsp+62h] [rbp-A6h]
  char v109; // [rsp+63h] [rbp-A5h]
  int v110; // [rsp+64h] [rbp-A4h]
  __int64 v111; // [rsp+68h] [rbp-A0h]
  CVisual *v112; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v113[3]; // [rsp+78h] [rbp-90h] BYREF
  unsigned int v114; // [rsp+90h] [rbp-78h]
  int v115; // [rsp+94h] [rbp-74h] BYREF
  struct tagPOINT v116; // [rsp+98h] [rbp-70h] BYREF
  CTransitionVisualController *v117; // [rsp+A0h] [rbp-68h]
  struct CVisual *v118; // [rsp+A8h] [rbp-60h] BYREF
  int v119; // [rsp+B0h] [rbp-58h]
  int v120; // [rsp+B4h] [rbp-54h]
  CAnimatedTransitionVisual *v121; // [rsp+B8h] [rbp-50h] BYREF
  struct CAnimationComponent **v122; // [rsp+C0h] [rbp-48h] BYREF
  CBaseObject *v123; // [rsp+C8h] [rbp-40h] BYREF
  struct tagRECT v124; // [rsp+D0h] [rbp-38h] BYREF
  struct CStoryboard *v125; // [rsp+E0h] [rbp-28h]
  struct CTransitionWindowSnapshot *v126; // [rsp+E8h] [rbp-20h] BYREF
  unsigned __int64 v127; // [rsp+F0h] [rbp-18h] BYREF
  struct tagRECT v128; // [rsp+F8h] [rbp-10h] BYREF
  struct tagRECT v129; // [rsp+108h] [rbp+0h] BYREF

  LOBYTE(v111) = a4;
  LODWORD(v113[0]) = a3;
  v117 = a1;
  v120 = a5;
  v125 = a6;
  *(_QWORD *)&v128.left = a8;
  v122 = a11;
  v118 = 0;
  v14 = 0;
  v121 = 0;
  v124.left = 1065353216;
  v124.top = 1065353216;
  v124.right = 1065353216;
  v114 = a3 & 0xFFF;
  v119 = (*(__int64 (__fastcall **)(struct CStoryboard *, _QWORD))(*(_QWORD *)a6 + 120LL))(a6, a3 & 0xFFF);
  v15 = 0;
  v123 = 0;
  v16 = CTransitionVisualController::_SetDesktopId(a1, *((_QWORD *)WindowDataByHwnd + 17));
  v17 = v16;
  if ( v16 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v16,
      0x341u,
      0);
    goto LABEL_230;
  }
  v18 = (v119 & 0x10) == 0;
  v19 = v119 & 0x10;
  v119 = v19;
  if ( v18 )
    v15 = lprc;
  v127 = 0;
  if ( *((_DWORD *)WindowDataByHwnd + 32) == 1 )
  {
    if ( (unsigned int)GetDesktopID(1, &v127) )
    {
      v20 = (HWND)*((_QWORD *)WindowDataByHwnd + 5);
      if ( v20 == CWindowList::GetShellWindowForDesktop(
                    *((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53),
                    v127) )
      {
        v21 = 0;
        v129 = 0;
        CTransitionVisualController::GetMonitorRectFromRectImpl((const struct tagRECT *)WindowDataByHwnd + 3, &v129);
        v22 = &v129;
        if ( v15 )
          v22 = v15;
        v23 = v117;
        DesktopAnimationComponent = CTransitionVisualController::CreateDesktopAnimationComponent(
                                      v117,
                                      WindowDataByHwnd,
                                      v120,
                                      v22,
                                      0,
                                      (*((_DWORD *)WindowDataByHwnd + 186) & 0x4000000) != 0,
                                      v125,
                                      v122);
        v17 = DesktopAnimationComponent;
        if ( DesktopAnimationComponent < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
            2u,
            DesktopAnimationComponent,
            0x353u,
            0);
          return v17;
        }
LABEL_225:
        if ( (*((_DWORD *)WindowDataByHwnd + 186) & 0x20000000) != 0 )
        {
          v122 = 0;
          if ( (int)CTransitionVisualController::GetStoredSnapshotNoRef(
                      v23,
                      *((HWND *)WindowDataByHwnd + 5),
                      (struct CTransitionWindowSnapshot **)&v122) >= 0 )
            CTransitionVisualController::_RemoveSnapshotFromVisualTreeIfExists(
              v97,
              (struct CTransitionWindowSnapshot *)v122);
        }
        if ( !v21 )
          goto LABEL_229;
        goto LABEL_241;
      }
    }
  }
  v129 = 0;
  v126 = 0;
  *(_OWORD *)&v113[1] = 0;
  v105[3] = 0;
  v25 = *((_DWORD *)WindowDataByHwnd + 186);
  v115 = v25 & 0x40000;
  if ( a4 && (v25 & 0x20000000) != 0 )
  {
    v26 = 0;
    if ( (int)CTransitionVisualController::GetStoredSnapshotNoRef(v117, *((HWND *)WindowDataByHwnd + 5), &v126) >= 0 )
    {
      v101 = 1;
LABEL_15:
      v27 = v114;
      goto LABEL_16;
    }
  }
  else
  {
    v26 = 0;
  }
  v101 = 0;
  if ( (*((_DWORD *)WindowDataByHwnd + 186) & 0x2000000) != 0 )
    goto LABEL_15;
  v27 = v114;
  if ( ((*(__int64 (__fastcall **)(struct CStoryboard *, _QWORD))(*(_QWORD *)a6 + 120LL))(a6, v114) & 0x20) == 0 )
  {
    v103 = 1;
    goto LABEL_17;
  }
LABEL_16:
  v103 = 0;
LABEL_17:
  if ( v19
    || (v28 = 0, ((*(__int64 (__fastcall **)(struct CStoryboard *, _QWORD))(*(_QWORD *)a6 + 120LL))(a6, v27) & 0x40) != 0) )
  {
    v28 = 1;
  }
  v105[2] = v28;
  v29 = *((_DWORD *)WindowDataByHwnd + 189) - *((_DWORD *)WindowDataByHwnd + 187);
  v30 = *((_DWORD *)WindowDataByHwnd + 197) - *((_DWORD *)WindowDataByHwnd + 195);
  v31 = 0;
  if ( v30 >= 0 )
    v31 = *((_DWORD *)WindowDataByHwnd + 197) - *((_DWORD *)WindowDataByHwnd + 195);
  v32 = 0;
  if ( v29 >= 0 )
    v32 = *((_DWORD *)WindowDataByHwnd + 189) - *((_DWORD *)WindowDataByHwnd + 187);
  v33 = 0;
  if ( v32 <= v31 )
  {
    if ( v30 >= 0 )
      v33 = *((_DWORD *)WindowDataByHwnd + 197) - *((_DWORD *)WindowDataByHwnd + 195);
  }
  else if ( v29 >= 0 )
  {
    v33 = *((_DWORD *)WindowDataByHwnd + 189) - *((_DWORD *)WindowDataByHwnd + 187);
  }
  v34 = (HWND *)(unsigned int)(*((_DWORD *)WindowDataByHwnd + 190) - *((_DWORD *)WindowDataByHwnd + 188));
  v35 = *((_DWORD *)WindowDataByHwnd + 198) - *((_DWORD *)WindowDataByHwnd + 196);
  v36 = 0;
  if ( v35 >= 0 )
    v36 = *((_DWORD *)WindowDataByHwnd + 198) - *((_DWORD *)WindowDataByHwnd + 196);
  v37 = 0;
  if ( (int)v34 >= 0 )
    v37 = *((_DWORD *)WindowDataByHwnd + 190) - *((_DWORD *)WindowDataByHwnd + 188);
  v38 = 0;
  if ( v37 <= v36 )
  {
    if ( v35 >= 0 )
      v38 = *((_DWORD *)WindowDataByHwnd + 198) - *((_DWORD *)WindowDataByHwnd + 196);
  }
  else if ( (int)v34 >= 0 )
  {
    v38 = *((_DWORD *)WindowDataByHwnd + 190) - *((_DWORD *)WindowDataByHwnd + 188);
  }
  if ( (*((_DWORD *)WindowDataByHwnd + 186) & 0x10000000) == 0
    || (v108 = 1, (int)CTransitionVisualController::GetClonableOwnedWindowCount(WindowDataByHwnd) <= 0) )
  {
    v108 = 0;
  }
  if ( (*((_DWORD *)WindowDataByHwnd + 29) & 0x20000000) == 0
    && !*((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 516)
    || (v18 = *((_QWORD *)WindowDataByHwnd + 60) == 0, v107 = 1, v18) )
  {
    v107 = 0;
  }
  if ( !a10 )
    goto LABEL_62;
  v39 = 0;
  if ( *((_DWORD *)WindowDataByHwnd + 14) - *((_DWORD *)WindowDataByHwnd + 12) >= 0 )
    v39 = *((_DWORD *)WindowDataByHwnd + 14) - *((_DWORD *)WindowDataByHwnd + 12);
  if ( v39 < v33 )
    goto LABEL_62;
  v40 = 0;
  if ( *((_DWORD *)WindowDataByHwnd + 15) - *((_DWORD *)WindowDataByHwnd + 13) >= 0 )
    v40 = *((_DWORD *)WindowDataByHwnd + 15) - *((_DWORD *)WindowDataByHwnd + 13);
  if ( v40 < v38
    || (*((_DWORD *)WindowDataByHwnd + 186) & 0x1000000) != 0
    && (*((_DWORD *)WindowDataByHwnd + 187) || *((_DWORD *)WindowDataByHwnd + 188)) )
  {
LABEL_62:
    v41 = 0;
  }
  else
  {
    v41 = 1;
  }
  v105[1] = v41;
  IsGhostWindow = CWindowData::IsGhostWindow(WindowDataByHwnd, v34);
  v102 = IsGhostWindow;
  v43 = *((_DWORD *)WindowDataByHwnd + 186);
  v110 = 4;
  if ( (v43 & 0x200000) == 0 )
    goto LABEL_73;
  if ( (v43 & 0x10000000) != 0 )
  {
    if ( (unsigned int)CTransitionVisualController::GetClonableOwnedWindowCount(WindowDataByHwnd) )
    {
LABEL_73:
      v106 = 0;
      IsGhostWindow = v102;
      goto LABEL_74;
    }
    IsGhostWindow = v102;
  }
  if ( (*((_BYTE *)WindowDataByHwnd + 736) & 4) != 0
    || IsGhostWindow
    || (*((_DWORD *)WindowDataByHwnd + 186) & 0x1000000) != 0
    && (*((_DWORD *)WindowDataByHwnd + 187) || *((_DWORD *)WindowDataByHwnd + 188)) )
  {
    goto LABEL_73;
  }
  v106 = 1;
LABEL_74:
  v44 = *((unsigned int *)WindowDataByHwnd + 140);
  if ( (_DWORD)v44 == 1
    && (v112 = (CVisual *)**((_QWORD **)WindowDataByHwnd + 67), (*((_DWORD *)v112 + 9) & 0x900000) == 0x900000) )
  {
    v45 = 1;
  }
  else
  {
    v45 = 0;
    v112 = 0;
  }
  if ( IsGhostWindow && !v45 && (*((_BYTE *)WindowDataByHwnd + 740) & 1) != 0 && v41 && (_DWORD)v44 )
  {
    v46 = v15;
    if ( !v15 )
      v46 = (struct tagRECT *)((char *)WindowDataByHwnd + 48);
    if ( (int)CTransitionVisualController::GetSurfaceFromThumbnail(
                v44,
                *(_QWORD *)(**((_QWORD **)WindowDataByHwnd + 67) + 24LL),
                *((unsigned int *)WindowDataByHwnd + 186),
                v46,
                v28,
                &v113[1],
                &v124) >= 0 )
    {
      v103 = 0;
      v26 = 1;
    }
  }
  if ( !v101 && !*((_QWORD *)WindowDataByHwnd + 3) )
  {
    WindowDataByHwnd = CWindowList::FindWindowDataByHwnd(
                         *((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53),
                         *((HWND *)WindowDataByHwnd + 5));
    if ( !WindowDataByHwnd )
    {
      v17 = -2147024890;
      MilInstrumentationCheckHR_MaybeFailFast(
        0x14u,
        &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        -2147024890,
        0x393u,
        0);
      CVisualBrush::~CVisualBrush((CVisualBrush *)&v113[1]);
      return v17;
    }
  }
  v47 = CAnimationComponent::operator new(v44);
  v116 = (struct tagPOINT)v47;
  if ( !v47
    || (v21 = CAnimationComponent::CAnimationComponent(
                v47,
                *((_QWORD *)WindowDataByHwnd + 5),
                LODWORD(v113[0]),
                (unsigned int)v120,
                v125)) == 0 )
  {
    v17 = -2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      -2147024882,
      0x397u,
      0);
    CVisualBrush::~CVisualBrush((CVisualBrush *)&v113[1]);
    goto LABEL_229;
  }
  v48 = CTransitionVisualController::_EnsureTransitionVisualRoot(v117);
  v17 = v48;
  if ( v48 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v48,
      0x399u,
      0);
    goto LABEL_240;
  }
  v49 = CTransitionVisualController::_EnsureStagingVisualRoot(v117);
  v17 = v49;
  if ( v49 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      v49,
      0x39Au,
      0);
    goto LABEL_240;
  }
  v116 = 0;
  v104 = 0;
  v109 = 0;
  v105[0] = 0;
  if ( v45
    || CWindowData::IsImmersiveWindow(WindowDataByHwnd) && (*((_BYTE *)WindowDataByHwnd + 740) & 0x10) != 0 && v103 )
  {
    v110 = 8 * v45 + 2;
    if ( *(_QWORD *)&v128.left && v15 )
      v15 = *(struct tagRECT **)&v128.left;
    if ( (v113[0] & 0x4000000) != 0 || (v71 = 0, v102) )
      v71 = 4096;
    v72 = v71 | 0x2000;
    if ( v15 )
      v72 = v71;
    v73 = v15;
    if ( !v15 )
      v73 = (struct tagRECT *)((char *)WindowDataByHwnd + 48);
    if ( v45 )
      v74 = (struct CWindowData *)*((_QWORD *)v112 + 3);
    else
      v74 = WindowDataByHwnd;
    if ( (int)CTransitionVisualController::GetIconicThumbnailRepresentation(&v123, v74, v21, v73, v72, &v123) < 0 )
    {
      v110 = 8 * v45 + 2;
      goto LABEL_182;
    }
    v62 = v123;
    goto LABEL_178;
  }
  if ( v105[1] )
  {
    if ( v26 )
      goto LABEL_246;
    v51 = v15;
    if ( !v15 )
      v51 = (struct tagRECT *)((char *)WindowDataByHwnd + 48);
    if ( v102 && *((_DWORD *)WindowDataByHwnd + 140) )
    {
      v52 = (CTransitionVisualController **)*((_QWORD *)WindowDataByHwnd + 67);
      v50 = *v52;
      v53 = (struct CWindowData *)*((_QWORD *)*v52 + 3);
    }
    else
    {
      v53 = WindowDataByHwnd;
    }
    LOBYTE(v99) = v105[2];
    if ( (int)CTransitionVisualController::GetSurfaceFromThumbnail(
                v50,
                v53,
                *((unsigned int *)WindowDataByHwnd + 186),
                v51,
                v99,
                &v113[1],
                &v124) >= 0 )
    {
LABEL_246:
      if ( CTransitionVisualController::HasVisibleStyle(*((HWND *)WindowDataByHwnd + 5)) )
        CTransitionVisualController::_MoveWindowOffscreen(*((struct CTopLevelWindow **)WindowDataByHwnd + 55), 1);
      goto LABEL_182;
    }
  }
  if ( a10 )
  {
    v54 = v15;
    if ( !v15 )
      v54 = (const struct tagRECT *)((char *)WindowDataByHwnd + 48);
    v55 = v101;
    v56 = v117;
    if ( CTransitionVisualController::GetSurfaceFromExistingAnimationComponent(
           v117,
           (struct CAnimationComponent *)v21,
           v54,
           v101,
           (struct CVisualBrush *)&v113[1],
           &v105[3],
           (struct D2D_POINT_3F *)&v124) >= 0 )
    {
      v110 = 3;
      if ( CTransitionVisualController::HasVisibleStyle(*((HWND *)WindowDataByHwnd + 5)) )
        CTransitionVisualController::_MoveWindowOffscreen(*((struct CTopLevelWindow **)WindowDataByHwnd + 55), 1);
      if ( v105[3] )
        *(_BYTE *)(v21 + 67) = 1;
      goto LABEL_182;
    }
  }
  else
  {
    v55 = v101;
    v56 = v117;
  }
  if ( v106 )
  {
    v57 = CContainerVisual::Create(&v118);
    v17 = v57;
    if ( v57 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(
        0x14u,
        &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        v57,
        0x3ECu,
        0);
    }
    else
    {
      v59 = CTransitionVisualController::_StageClone(
              v56,
              *((struct CTopLevelWindow **)WindowDataByHwnd + 55),
              v118,
              v58,
              1,
              0);
      v17 = v59;
      if ( v59 >= 0 )
      {
        v110 = 6;
        v109 = 1;
        goto LABEL_182;
      }
      MilInstrumentationCheckHR_MaybeFailFast(
        0x14u,
        &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        v59,
        0x3EDu,
        0);
    }
LABEL_240:
    CVisualBrush::~CVisualBrush((CVisualBrush *)&v113[1]);
    goto LABEL_241;
  }
  v60 = 0;
  if ( !v55 )
  {
    if ( !a10 || !v107 || !*(_QWORD *)(*((_QWORD *)WindowDataByHwnd + 60) + 24LL) )
    {
      if ( !v108 )
      {
        v110 = 0;
        goto LABEL_182;
      }
      v112 = 0;
      CTransitionVisualController::_RecursivelyRenderOwnedWindows(v50, WindowDataByHwnd);
      v63 = CCompositor::CommitDwmChannel(*((CCompositor **)CDesktopManager::s_pDesktopManagerInstance + 6));
      v17 = v63;
      if ( v63 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(
          0x14u,
          &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
          2u,
          v63,
          0x422u,
          0);
      }
      else
      {
        v64 = CContainerVisual::Create(&v118);
        v17 = v64;
        if ( v64 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
            2u,
            v64,
            0x426u,
            0);
        }
        else
        {
          wil::com_ptr_t<CImage,wil::err_exception_policy>::reset(&v112);
          v65 = CContainerVisual::Create(&v112);
          v17 = v65;
          if ( v65 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              0x14u,
              &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
              2u,
              v65,
              0x427u,
              0);
          }
          else
          {
            v66 = v112;
            v67 = CContainerVisual::AddChild(v118, v112);
            v17 = v67;
            if ( v67 < 0 )
            {
              MilInstrumentationCheckHR_MaybeFailFast(
                0x14u,
                &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
                2u,
                v67,
                0x428u,
                0);
            }
            else
            {
              LOBYTE(v60) = v115 != 0;
              v116.x = -*((_DWORD *)WindowDataByHwnd + 12);
              v116.y = -*((_DWORD *)WindowDataByHwnd + 13);
              CVisual::SetOffset(v66, &v116);
              v68 = CTransitionVisualController::_StageCloneWithOwnedWindows(
                      v117,
                      *((_QWORD *)WindowDataByHwnd + 55),
                      v66,
                      a9,
                      v60);
              v17 = v68;
              if ( v68 >= 0 )
              {
                v110 = 8;
                if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
                  McTemplateU0pp_EtwEventWriteTransfer(
                    v69,
                    CommitChannel_Transition_OwnedWindow,
                    WindowDataByHwnd,
                    *((_QWORD *)WindowDataByHwnd + 5));
                CAnimationComponent::SetStagingVisual((CAnimationComponent *)v21, v118);
                if ( (*((_DWORD *)WindowDataByHwnd + 186) & 0x20000000) != 0 && (_BYTE)v111 )
                  *(_BYTE *)(v21 + 67) = 1;
                v70 = *((_DWORD *)WindowDataByHwnd + 186);
                if ( (v70 & 0x20000000) != 0 )
                {
                  CTransitionVisualController::_MoveOwnedWindowTreeOffscreen(WindowDataByHwnd);
                  v70 = *((_DWORD *)WindowDataByHwnd + 186);
                }
                v62 = *(CBaseObject **)(*((_QWORD *)v66 + 18) + 8LL * v60);
                v116 = (struct tagPOINT)v62;
                v105[0] = (v70 & 0x80000) != 0 && (*((_BYTE *)WindowDataByHwnd + 737) & 0x20) != 0;
                wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(&v112);
LABEL_179:
                if ( v62 )
                {
                  v75 = v113[1];
                  goto LABEL_184;
                }
                goto LABEL_182;
              }
              MilInstrumentationCheckHR_MaybeFailFast(
                0x14u,
                &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
                2u,
                v68,
                0x42Fu,
                0);
            }
          }
        }
      }
      wil::com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>::~com_ptr_t<CDisplaySecondaryOnlyToExtendAnimatedVisual,wil::err_returncode_policy>(&v112);
      goto LABEL_240;
    }
    v110 = 11;
    if ( *((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 516) && v15 )
    {
      OffsetRect(v15, -*((_DWORD *)WindowDataByHwnd + 16), -*((_DWORD *)WindowDataByHwnd + 18));
      OffsetRect(v15, -*((_DWORD *)WindowDataByHwnd + 24), -*((_DWORD *)WindowDataByHwnd + 26));
    }
    v62 = *(CBaseObject **)(*((_QWORD *)WindowDataByHwnd + 60) + 24LL);
LABEL_178:
    v116 = (struct tagPOINT)v62;
    goto LABEL_179;
  }
  if ( CTransitionVisualController::HasVisibleStyle(*((HWND *)WindowDataByHwnd + 5)) )
    CTransitionVisualController::_MoveOwnedWindowTreeOffscreen(WindowDataByHwnd);
  *(float *)&v115 = 0.0;
  SharedVisualBrush = CTransitionWindowSnapshot::GetSharedVisualBrush(
                        v126,
                        (struct CVisualBrush *)&v113[1],
                        (float *)&v115);
  v17 = SharedVisualBrush;
  if ( SharedVisualBrush < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(
      0x14u,
      &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
      2u,
      SharedVisualBrush,
      0x402u,
      0);
    goto LABEL_240;
  }
  v110 = 7;
  *(float *)&v124.top = 1.0 / *(float *)&v115;
  *(float *)&v124.left = 1.0 / *(float *)&v115;
  *(_BYTE *)(v21 + 67) = 1;
  v104 = 1;
LABEL_182:
  v75 = v113[1];
  if ( !v113[1] )
  {
    v110 = 9;
    v116 = (struct tagPOINT)*((_QWORD *)WindowDataByHwnd + 55);
    CTransitionVisualController::_MoveWindowOffscreen(*(struct CTopLevelWindow **)&v116, 1);
    CTopLevelWindow::ForceShowWindow(*((CTopLevelWindow **)WindowDataByHwnd + 55), 1);
  }
LABEL_184:
  CAnimationComponent::RecordWindowRect((CAnimationComponent *)v21);
  if ( !IsRectEmpty((const RECT *)((char *)WindowDataByHwnd + 812)) )
  {
    *(_OWORD *)(v21 + 104) = *(_OWORD *)((char *)WindowDataByHwnd + 812);
    *(_DWORD *)(v21 + 68) = 2;
  }
  CTransitionVisualController::_StopAnimations(v76, WindowDataByHwnd);
  v77 = CAnimatedTransitionVisual::Create(&v121);
  v17 = v77;
  if ( v77 >= 0 )
  {
    IsRTL = CStoryboard::IsRTL();
    v14 = v121;
    *((_BYTE *)v121 + 908) = IsRTL;
    if ( v15 )
    {
      v79 = *v15;
    }
    else if ( v104 )
    {
      v79 = *(struct tagRECT *)(*(_QWORD *)(*((_QWORD *)v126 + 26) + 32LL) + 48LL);
    }
    else
    {
      v79 = *(struct tagRECT *)(v21 + 88);
    }
    v129 = v79;
    v80 = 0;
    if ( v79.right - v79.left >= 0 )
      v80 = v79.right - v79.left;
    LODWORD(v121) = v80;
    v81 = 0;
    if ( v129.bottom - v129.top >= 0 )
      v81 = v129.bottom - v129.top;
    HIDWORD(v121) = v81;
    *((_QWORD *)v14 + 111) = v121;
    if ( !v15 )
    {
      v82 = *(_DWORD *)(v21 + 120);
      v83 = *(_DWORD *)(v21 + 128);
      v84 = *(_DWORD *)(v21 + 132);
      v85 = 0;
      if ( v129.right - v129.left >= 0 )
        v85 = v129.right - v129.left;
      v129.right = v85 - *(_DWORD *)(v21 + 124);
      v86 = 0;
      if ( v129.bottom - v129.top >= 0 )
        v86 = v129.bottom - v129.top;
      v129.bottom = v86 - v84;
      v129.left = v82;
      v129.top = v83;
    }
    if ( v75 )
    {
      CAnimatedTransitionVisual::SetSharedVisualBrush(
        v14,
        (const struct CVisualBrush *)&v113[1],
        (const struct D2D_POINT_3F *)&v124);
LABEL_204:
      v89 = v113[0];
LABEL_205:
      if ( (Microsoft_Windows_Dwm_UdwmEnableBits & 1) != 0 )
      {
        v100 = v89;
        v90 = (int *)v125;
        McTemplateU0pddddddd_EtwEventWriteTransfer(
          v88,
          v87,
          *((_QWORD *)WindowDataByHwnd + 5),
          *((_DWORD *)v125 + 18),
          v100,
          v110,
          v129.left,
          v129.top,
          v129.right,
          v129.bottom);
      }
      else
      {
        v90 = (int *)v125;
      }
      if ( v119 )
      {
        v124 = *(struct tagRECT *)((char *)WindowDataByHwnd + 748);
        v128 = *(struct tagRECT *)((char *)WindowDataByHwnd + 780);
        CAnimatedTransitionVisual::SetBeginClip(v14, &v124);
        CAnimatedTransitionVisual::SetEndClip(v14, &v128);
        *((_BYTE *)v14 + 922) = 1;
      }
      CAnimatedTransitionVisual::SetTransitionStoryboardAndTarget(v14, v90[18], v120);
      if ( (*(char (__fastcall **)(int *, _QWORD))(*(_QWORD *)v90 + 120LL))(v90, v114) < 0 )
        *((_BYTE *)v14 + 973) = 0;
      *v122 = (struct CAnimationComponent *)v21;
      CBaseObject::AddRef((CBaseObject *)v21);
      CAnimationComponent::SetTransitionVisual(*v96, v14);
      CVisualBrush::~CVisualBrush((CVisualBrush *)&v113[1]);
      v23 = v117;
      goto LABEL_225;
    }
    if ( v109 )
    {
      v91 = CAnimatedTransitionVisual::StealStagedVisual(v14, v118);
      v17 = v91;
      if ( v91 >= 0 )
        goto LABEL_204;
      MilInstrumentationCheckHR_MaybeFailFast(
        0x14u,
        &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        v91,
        0x49Au,
        0);
    }
    else
    {
      v92 = &v129;
      if ( v104 )
        v92 = 0;
      v89 = v113[0];
      if ( (v113[0] & 0x4000000) == 0 || (v93 = 1, v105[0]) )
        v93 = 0;
      v94 = (struct CVisual *)v116;
      if ( v118 )
        v94 = v118;
      v95 = CAnimatedTransitionVisual::SetVisual(v14, v94, v93, v92);
      v17 = v95;
      if ( v95 >= 0 )
        goto LABEL_205;
      MilInstrumentationCheckHR_MaybeFailFast(
        0x14u,
        &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
        2u,
        v95,
        0x49Eu,
        0);
    }
    goto LABEL_240;
  }
  MilInstrumentationCheckHR_MaybeFailFast(
    0x14u,
    &CTransitionVisualController::MILINSTRUMENTATIONHRESULTLIST,
    2u,
    v77,
    0x466u,
    0);
  CVisualBrush::~CVisualBrush((CVisualBrush *)&v113[1]);
  v14 = v121;
LABEL_241:
  CBaseObject::Release((CBaseObject *)v21);
LABEL_229:
  v15 = (struct tagRECT *)v123;
LABEL_230:
  if ( v118 )
    CBaseObject::Release(v118);
  if ( v14 )
    CBaseObject::Release((CAnimatedTransitionVisual *)((char *)v14 + 8));
  if ( v15 )
    CBaseObject::Release((CBaseObject *)v15);
  return v17;
}

```

## disassembly

```asm
0x180068c60  mov     rax, rsp
0x180068c63  mov     [rax+20h], rbx
0x180068c67  push    rbp
0x180068c68  push    rsi
0x180068c69  push    rdi
0x180068c6a  push    r12
0x180068c6c  push    r13
0x180068c6e  push    r14
0x180068c70  push    r15
0x180068c72  lea     rbp, [rax-68h]
0x180068c76  sub     rsp, 130h
0x180068c7d  movaps  xmmword ptr [rax-48h], xmm6
0x180068c81  mov     rax, cs:__security_cookie
0x180068c88  xor     rax, rsp
0x180068c8b  mov     [rbp+60h+var_50], rax
0x180068c8f  mov     r15b, r9b
0x180068c92  mov     byte ptr [rsp+160h+var_100], r9b
0x180068c97  mov     dword ptr [rsp+160h+var_F0], r8d
0x180068c9c  mov     rsi, rdx
0x180068c9f  mov     rdi, rcx
0x180068ca2  mov     [rbp+60h+var_C8], rcx
0x180068ca6  mov     rbx, [rbp+60h+lprc]
0x180068cad  mov     eax, [rbp+60h+arg_20]
0x180068cb3  mov     [rbp+60h+var_B4], eax
0x180068cb6  mov     r13, [rbp+60h+arg_28]
0x180068cbd  mov     [rbp+60h+var_88], r13
0x180068cc1  mov     rax, [rbp+60h+arg_38]
0x180068cc8  mov     qword ptr [rbp+60h+var_70.left], rax
0x180068ccc  mov     rax, [rbp+60h+arg_50]
0x180068cd3  mov     [rbp+60h+var_A8], rax
0x180068cd7  mov     [rbp+60h+var_C0], 0
0x180068cdf  xor     r12d, r12d
0x180068ce2  mov     [rbp+60h+var_B0], r12
0x180068ce6  movss   xmm6, cs:__real@3f800000
0x180068cee  mov     [rbp+60h+var_98.left], 3F800000h
0x180068cf5  mov     [rbp+60h+var_98.top], 3F800000h
0x180068cfc  mov     [rbp+60h+var_98.right], 3F800000h
0x180068d03  mov     ecx, r8d
0x180068d06  and     ecx, 0FFFh
0x180068d0c  mov     [rbp+60h+var_D8], ecx
0x180068d0f  mov     rax, [r13+0]
0x180068d13  mov     edx, ecx
0x180068d15  mov     rcx, r13
0x180068d18  mov     rax, [rax+78h]
0x180068d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d21  mov     [rbp+60h+var_B8], eax
0x180068d24  xor     r14d, r14d
0x180068d27  mov     [rbp+60h+var_A0], r14
0x180068d2b  mov     rdx, [rsi+88h]; unsigned __int64
0x180068d32  mov     rcx, rdi; this
0x180068d35  call    ?_SetDesktopId@CTransitionVisualController@@IEAAJ_K@Z; CTransitionVisualController::_SetDesktopId(unsigned __int64)
0x180068d3a  mov     edi, eax
0x180068d3c  test    eax, eax
0x180068d3e  js      loc_180069B3C
0x180068d44  mov     edi, [rbp+60h+var_B8]
0x180068d47  and     edi, 10h
0x180068d4a  mov     [rbp+60h+var_B8], edi
0x180068d4d  cmovz   r14, rbx
0x180068d51  mov     [rbp+60h+var_78], r12
0x180068d55  cmp     dword ptr [rsi+80h], 1
0x180068d5c  jnz     loc_180068E30
0x180068d62  lea     rdx, [rbp+60h+var_78]
0x180068d66  lea     ecx, [r12+1]
0x180068d6b  call    cs:__imp_GetDesktopID
0x180068d71  test    eax, eax
0x180068d73  jz      loc_180068E30
0x180068d79  mov     rbx, [rsi+28h]
0x180068d7d  mov     rdx, [rbp+60h+var_78]; unsigned __int64
0x180068d81  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180068d88  mov     rcx, [rcx+1A8h]; this
0x180068d8f  call    ?GetShellWindowForDesktop@CWindowList@@QEAAPEAUHWND__@@_K@Z; CWindowList::GetShellWindowForDesktop(unsigned __int64)
0x180068d94  cmp     rbx, rax
0x180068d97  jnz     loc_180068E30
0x180068d9d  xor     r15d, r15d
0x180068da0  mov     r13d, r15d
0x180068da3  xorps   xmm0, xmm0
0x180068da6  movups  xmmword ptr [rbp+60h+var_60.left], xmm0
0x180068daa  lea     rcx, [rsi+30h]; struct tagRECT *
0x180068dae  lea     rdx, [rbp+60h+var_60]; struct tagRECT *
0x180068db2  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x180068db7  mov     eax, [rsi+2E8h]
0x180068dbd  shr     eax, 1Ah
0x180068dc0  and     al, 1
0x180068dc2  lea     r9, [rbp+60h+var_60]
0x180068dc6  test    r14, r14
0x180068dc9  cmovnz  r9, r14; struct tagRECT *
0x180068dcd  mov     r10, [rbp+60h+var_A8]
0x180068dd1  mov     [rsp+160h+var_128], r10; struct CAnimationComponent **
0x180068dd6  mov     rcx, [rbp+60h+var_88]
0x180068dda  mov     [rsp+160h+var_130], rcx; struct CStoryboard *
0x180068ddf  mov     byte ptr [rsp+160h+var_138], al; bool
0x180068de3  mov     byte ptr [rsp+160h+var_140], r15b; bool
0x180068de8  mov     r8d, [rbp+60h+var_B4]; int
0x180068dec  mov     rdx, rsi; struct CWindowData *
0x180068def  mov     rbx, [rbp+60h+var_C8]
0x180068df3  mov     rcx, rbx; this
0x180068df6  call    ?CreateDesktopAnimationComponent@CTransitionVisualController@@QEAAJPEAVCWindowData@@HAEBUtagRECT@@_N2PEAVCStoryboard@@PEAPEAVCAnimationComponent@@@Z; CTransitionVisualController::CreateDesktopAnimationComponent(CWindowData *,int,tagRECT const &,bool,bool,CStoryboard *,CAnimationComponent * *)
0x180068dfb  mov     edi, eax
0x180068dfd  test    eax, eax
0x180068dff  jns     loc_1800699D8
0x180068e05  mov     [rsp+160h+var_138], r15; void *
0x180068e0a  mov     dword ptr [rsp+160h+var_140], 353h; unsigned int
0x180068e12  mov     r9d, eax; int
0x180068e15  lea     r8d, [r12+2]; unsigned int
0x180068e1a  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CTransitionVisualController@@2QBJB; int *
0x180068e21  lea     ecx, [r12+14h]; unsigned int
0x180068e26  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180068e2b  jmp     loc_180069A3F
0x180068e30  xorps   xmm0, xmm0
0x180068e33  movups  xmmword ptr [rbp+60h+var_60.left], xmm0
0x180068e37  mov     [rbp+60h+var_80], r12
0x180068e3b  movdqu  xmmword ptr [rsp+160h+var_F0+8], xmm0
0x180068e41  mov     [rsp+160h+var_10C+3], 0
0x180068e46  mov     eax, [rsi+2E8h]
0x180068e4c  mov     ecx, eax
0x180068e4e  and     ecx, 40000h
0x180068e54  mov     [rbp+60h+var_D4], ecx
0x180068e57  test    r15b, r15b
0x180068e5a  jz      loc_180068EEB
0x180068e60  bt      eax, 1Dh
0x180068e64  jnb     loc_180068EEB
0x180068e6a  lea     r8, [rbp+60h+var_80]; struct CTransitionWindowSnapshot **
0x180068e6e  mov     rdx, [rsi+28h]; HWND
0x180068e72  mov     rcx, [rbp+60h+var_C8]; this
0x180068e76  call    ?GetStoredSnapshotNoRef@CTransitionVisualController@@QEAAJPEAUHWND__@@PEAPEAVCTransitionWindowSnapshot@@@Z; CTransitionVisualController::GetStoredSnapshotNoRef(HWND__ *,CTransitionWindowSnapshot * *)
0x180068e7b  xor     r15d, r15d
0x180068e7e  test    eax, eax
0x180068e80  js      short loc_180068EEE
0x180068e82  mov     [rsp+160h+var_110], 1
0x180068e87  mov     ebx, [rbp+60h+var_D8]
0x180068e8a  mov     [rsp+160h+var_10E], r15b
0x180068e8f  test    edi, edi
0x180068e91  jnz     short loc_180068EAC
0x180068e93  mov     rax, [r13+0]
0x180068e97  mov     edx, ebx
0x180068e99  mov     rcx, r13
0x180068e9c  mov     rax, [rax+78h]
0x180068ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ea5  test    al, 40h
0x180068ea7  mov     r13b, r15b
0x180068eaa  jz      short loc_180068EAF
0x180068eac  mov     r13b, 1
0x180068eaf  mov     [rsp+160h+var_10C+2], r13b
0x180068eb4  mov     edx, [rsi+2F4h]
0x180068eba  sub     edx, [rsi+2ECh]
0x180068ec0  mov     r8d, [rsi+314h]
0x180068ec7  sub     r8d, [rsi+30Ch]
0x180068ece  mov     ecx, r15d
0x180068ed1  cmovns  ecx, r8d
0x180068ed5  mov     eax, r15d
0x180068ed8  test    edx, edx
0x180068eda  cmovns  eax, edx
0x180068edd  mov     ebx, r15d
0x180068ee0  cmp     eax, ecx
0x180068ee2  jle     short loc_180068F26
0x180068ee4  test    edx, edx
0x180068ee6  cmovns  ebx, edx
0x180068ee9  jmp     short loc_180068F2D
0x180068eeb  xor     r15d, r15d
0x180068eee  mov     [rsp+160h+var_110], r15b
0x180068ef3  test    dword ptr [rsi+2E8h], 2000000h
0x180068efd  jnz     short loc_180068E87
0x180068eff  mov     rax, [r13+0]
0x180068f03  mov     ebx, [rbp+60h+var_D8]
0x180068f06  mov     edx, ebx
0x180068f08  mov     rcx, r13
0x180068f0b  mov     rax, [rax+78h]
0x180068f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f14  test    al, 20h
0x180068f16  jnz     loc_180068E8A
0x180068f1c  mov     [rsp+160h+var_10E], 1
0x180068f21  jmp     loc_180068E8F
0x180068f26  test    r8d, r8d
0x180068f29  cmovns  ebx, r8d
0x180068f2d  mov     edx, [rsi+2F8h]
0x180068f33  sub     edx, [rsi+2F0h]
0x180068f39  mov     r8d, [rsi+318h]
0x180068f40  sub     r8d, [rsi+310h]
0x180068f47  mov     ecx, r15d
0x180068f4a  cmovns  ecx, r8d
0x180068f4e  mov     eax, r15d
0x180068f51  test    edx, edx
0x180068f53  cmovns  eax, edx
0x180068f56  mov     edi, r15d
0x180068f59  cmp     eax, ecx
0x180068f5b  jle     short loc_180068F64
0x180068f5d  test    edx, edx
0x180068f5f  cmovns  edi, edx
0x180068f62  jmp     short loc_180068F6B
0x180068f64  test    r8d, r8d
0x180068f67  cmovns  edi, r8d
0x180068f6b  test    dword ptr [rsi+2E8h], 10000000h
0x180068f75  jz      short loc_180068F88
0x180068f77  mov     rcx, rsi; struct CWindowData *
0x180068f7a  call    ?GetClonableOwnedWindowCount@CTransitionVisualController@@SAHPEAVCWindowData@@@Z; CTransitionVisualController::GetClonableOwnedWindowCount(CWindowData *)
0x180068f7f  test    eax, eax
0x180068f81  mov     [rsp+160h+var_106], 1
0x180068f86  jg      short loc_180068F8D
0x180068f88  mov     [rsp+160h+var_106], r15b
0x180068f8d  test    dword ptr [rsi+74h], 20000000h
0x180068f94  jnz     short loc_180068FA6
0x180068f96  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x180068f9d  cmp     [rax+204h], r15b
0x180068fa4  jz      short loc_180068FB4
0x180068fa6  cmp     [rsi+1E0h], r15
0x180068fad  mov     [rsp+160h+var_107], 1
0x180068fb2  jnz     short loc_180068FB9
0x180068fb4  mov     [rsp+160h+var_107], r15b
0x180068fb9  cmp     [rbp+60h+arg_48], r15b
0x180068fc0  jz      short loc_180069005
0x180068fc2  mov     ecx, [rsi+38h]
0x180068fc5  sub     ecx, [rsi+30h]
0x180068fc8  mov     eax, r15d
0x180068fcb  cmovns  eax, ecx
0x180068fce  cmp     eax, ebx
0x180068fd0  jl      short loc_180069005
0x180068fd2  mov     ecx, [rsi+3Ch]
0x180068fd5  sub     ecx, [rsi+34h]
0x180068fd8  mov     eax, r15d
0x180068fdb  cmovns  eax, ecx
0x180068fde  cmp     eax, edi
0x180068fe0  jl      short loc_180069005
0x180068fe2  test    dword ptr [rsi+2E8h], 1000000h
0x180068fec  jz      short loc_180069000
0x180068fee  cmp     [rsi+2ECh], r15d
0x180068ff5  jnz     short loc_180069005
0x180068ff7  cmp     [rsi+2F0h], r15d
0x180068ffe  jnz     short loc_180069005
0x180069000  mov     dil, 1
0x180069003  jmp     short loc_180069008
0x180069005  mov     dil, r15b
0x180069008  mov     [rsp+160h+var_10C+1], dil
0x18006900d  mov     rcx, rsi; this
0x180069010  call    ?IsGhostWindow@CWindowData@@QEBA_NPEAPEAUHWND__@@@Z; CWindowData::IsGhostWindow(HWND__ * *)
0x180069015  mov     r8b, al
0x180069018  mov     [rsp+160h+var_10F], al
0x18006901c  mov     ecx, [rsi+2E8h]
0x180069022  mov     ebx, 4
0x180069027  mov     [rsp+160h+var_104], ebx
0x18006902b  bt      ecx, 15h
0x18006902f  jnb     short loc_18006907A
0x180069031  bt      ecx, 1Ch
0x180069035  jnb     short loc_180069048
0x180069037  mov     rcx, rsi; struct CWindowData *
0x18006903a  call    ?GetClonableOwnedWindowCount@CTransitionVisualController@@SAHPEAVCWindowData@@@Z; CTransitionVisualController::GetClonableOwnedWindowCount(CWindowData *)
0x18006903f  test    eax, eax
0x180069041  jnz     short loc_18006907A
0x180069043  mov     r8b, [rsp+160h+var_10F]
0x180069048  test    [rsi+2E0h], bl
0x18006904e  jnz     short loc_18006907A
0x180069050  test    r8b, r8b
0x180069053  jnz     short loc_18006907A
0x180069055  test    dword ptr [rsi+2E8h], 1000000h
0x18006905f  jz      short loc_180069073
0x180069061  cmp     [rsi+2ECh], r15d
0x180069068  jnz     short loc_18006907A
0x18006906a  cmp     [rsi+2F0h], r15d
0x180069071  jnz     short loc_18006907A
0x180069073  mov     [rsp+160h+var_108], 1
0x180069078  jmp     short loc_180069084
0x18006907a  mov     [rsp+160h+var_108], r15b
0x18006907f  mov     r8b, [rsp+160h+var_10F]
0x180069084  mov     ecx, [rsi+230h]
0x18006908a  cmp     ecx, 1
0x18006908d  jnz     short loc_1800690B0
0x18006908f  mov     rax, [rsi+218h]
0x180069096  mov     rdx, [rax]
0x180069099  mov     [rsp+160h+var_F8], rdx
0x18006909e  mov     eax, [rdx+24h]
0x1800690a1  mov     edx, 900000h
0x1800690a6  and     eax, edx
0x1800690a8  cmp     eax, edx
0x1800690aa  jnz     short loc_1800690B0
0x1800690ac  mov     bl, cl
0x1800690ae  jmp     short loc_1800690B8
0x1800690b0  mov     bl, r15b
0x1800690b3  mov     [rsp+160h+var_F8], r15
0x1800690b8  test    r8b, r8b
0x1800690bb  jz      short loc_18006911D
0x1800690bd  test    bl, bl
0x1800690bf  jnz     short loc_18006911D
0x1800690c1  test    byte ptr [rsi+2E4h], 1
0x1800690c8  jz      short loc_18006911D
0x1800690ca  test    dil, dil
0x1800690cd  jz      short loc_18006911D
0x1800690cf  test    ecx, ecx
0x1800690d1  jz      short loc_18006911D
0x1800690d3  test    r14, r14
0x1800690d6  mov     r9, r14
0x1800690d9  jnz     short loc_1800690DF
0x1800690db  lea     r9, [rsi+30h]
0x1800690df  mov     rax, [rsi+218h]
0x1800690e6  mov     rdx, [rax]
0x1800690e9  lea     rax, [rbp+60h+var_98]
0x1800690ed  mov     [rsp+160h+var_130], rax
0x1800690f2  lea     rax, [rsp+160h+var_F0+8]
0x1800690f7  mov     [rsp+160h+var_138], rax
0x1800690fc  mov     byte ptr [rsp+160h+var_140], r13b
0x180069101  mov     r8d, [rsi+2E8h]
0x180069108  mov     rdx, [rdx+18h]
  ... truncated ...
```
