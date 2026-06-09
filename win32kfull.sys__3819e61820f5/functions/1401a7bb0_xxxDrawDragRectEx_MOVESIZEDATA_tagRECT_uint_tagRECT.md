# xxxDrawDragRectEx(MOVESIZEDATA *,tagRECT *,uint,tagRECT *)

- ea: `0x1401a7bb0`
- end: `0x1401a85a4`
- name: `?xxxDrawDragRectEx@@YAXPEAUMOVESIZEDATA@@PEAUtagRECT@@I1@Z`
- size: `2548`
- prototype: `void __fastcall(struct MOVESIZEDATA *, struct tagRECT *, unsigned int, struct tagRECT *)`
- caller_count: `3`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401a7b94`
- `0x14027ad54`
- `0x14027c120`

## callees

- `0x140020cf0`
- `0x1400292ec`
- `0x1400af078`
- `0x1400bcaa0`
- `0x1400c027c`
- `0x1400de860`
- `0x1400df540`
- `0x1400e6480`
- `0x1400eb064`
- `0x140148b90`
- `0x14016c0e0`
- `0x1401a7bb0`
- `0x1401a85ac`
- `0x1401a9d10`
- `0x1401de39c`
- `0x140209b64`
- `0x14020e08c`
- `0x14020e2b0`
- `0x14020f598`
- `0x140215938`
- `0x14021ba54`
- `0x14021c87c`
- `0x1402214b0`
- `0x14022a9c8`
- `0x140242e10`
- `0x1402507c4`
- `0x140255dd0`
- `0x1402c95cc`
- `0x140341ff0`

## import_xrefs

- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a7ee4`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a80e4`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a7ee4`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a80e4`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401a84c0`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401a84c0`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x1401a82b5`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x1401a82b5`
- `win32kbase!GenerateMouseMove` at `0x1401a7de7`
- `win32kbase!GenerateMouseMove` at `0x1401a7de7`
- `win32kbase!GreCombineRgn` at `0x1401a7f12`
- `win32kbase!GreCombineRgn` at `0x1401a8112`
- `win32kbase!GreCombineRgn` at `0x1401a8147`
- `win32kbase!GreCombineRgn` at `0x1401a7f12`
- `win32kbase!GreCombineRgn` at `0x1401a8112`
- `win32kbase!GreCombineRgn` at `0x1401a8147`
- `win32kbase!GreDeleteObject` at `0x1401a812b`
- `win32kbase!GreDeleteObject` at `0x1401a81dc`
- `win32kbase!GreDeleteObject` at `0x1401a81eb`
- `win32kbase!GreDeleteObject` at `0x1401a812b`
- `win32kbase!GreDeleteObject` at `0x1401a81dc`
- `win32kbase!GreDeleteObject` at `0x1401a81eb`
- `win32kbase!ValidateHmonitor` at `0x1401a8046`
- `win32kbase!ValidateHmonitor` at `0x1401a8046`
- `WIN32K!W32GetUserSessionState` at `0x1401a7d04`
- `WIN32K!W32GetUserSessionState` at `0x1401a7f9a`
- `WIN32K!W32GetUserSessionState` at `0x1401a818f`
- `WIN32K!W32GetUserSessionState` at `0x1401a8228`
- `WIN32K!W32GetUserSessionState` at `0x1401a82c7`
- `WIN32K!W32GetUserSessionState` at `0x1401a830f`
- `WIN32K!W32GetUserSessionState` at `0x1401a832f`
- `WIN32K!W32GetUserSessionState` at `0x1401a838f`
- `WIN32K!W32GetUserSessionState` at `0x1401a83cc`
- `WIN32K!W32GetUserSessionState` at `0x1401a83f1`
- `WIN32K!W32GetUserSessionState` at `0x1401a842f`
- `WIN32K!W32GetUserSessionState` at `0x1401a844f`
- `WIN32K!W32GetUserSessionState` at `0x1401a8527`
- `WIN32K!W32GetUserSessionState` at `0x1401a7d04`
- `WIN32K!W32GetUserSessionState` at `0x1401a7f9a`
- `WIN32K!W32GetUserSessionState` at `0x1401a818f`
- `WIN32K!W32GetUserSessionState` at `0x1401a8228`
- `WIN32K!W32GetUserSessionState` at `0x1401a82c7`
- `WIN32K!W32GetUserSessionState` at `0x1401a830f`
- `WIN32K!W32GetUserSessionState` at `0x1401a832f`
- `WIN32K!W32GetUserSessionState` at `0x1401a838f`
- `WIN32K!W32GetUserSessionState` at `0x1401a83cc`
- `WIN32K!W32GetUserSessionState` at `0x1401a83f1`
- `WIN32K!W32GetUserSessionState` at `0x1401a842f`
- `WIN32K!W32GetUserSessionState` at `0x1401a844f`
- `WIN32K!W32GetUserSessionState` at `0x1401a8527`

## pseudocode

```c
void __fastcall xxxDrawDragRectEx(struct MOVESIZEDATA *a1, struct tagRECT *a2, int a3, struct tagRECT *a4)
{
  struct tagRECT *v4; // rbx
  __int64 v5; // r13
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // esi
  __int64 v12; // rcx
  unsigned int v13; // r12d
  struct tagRECT *v14; // rdi
  struct MOVESIZEDATA *v15; // rcx
  char v16; // al
  __int64 UserSessionState; // rax
  int v18; // r8d
  const char *v19; // rcx
  int v20; // edx
  struct tagRECT v21; // xmm0
  int v22; // eax
  struct tagWND **v23; // rsi
  ULONG_PTR v24; // r13
  struct tagWND *v25; // r10
  __m128i v26; // xmm6
  __int64 v27; // r9
  __int64 v28; // r9
  __int64 v29; // r9
  __int64 v30; // r9
  int left; // ebx
  LONG right; // r12d
  __int64 RectRgnIndirect; // rax
  HRGN v34; // rdi
  __int64 v35; // r8
  _DWORD *v36; // rdx
  struct tagWND *v37; // rbx
  unsigned int v38; // eax
  __int64 v39; // rbx
  unsigned int v40; // r12d
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rax
  int v46; // eax
  unsigned int v47; // r12d
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // rax
  struct tagWND *v51; // rcx
  struct tagWND *v52; // r9
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r9
  __int64 v56; // r15
  __int64 v57; // rdx
  __int64 v58; // r8
  struct tagWND *v59; // rbx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // rbx
  __int64 v65; // rax
  struct tagRECT v66; // xmm0
  __int64 v67; // rax
  __int64 v68; // rcx
  __int64 WindowMargins; // rax
  __int64 v70; // rdx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  __int64 v74; // rax
  __int64 v75; // rbx
  __int64 v76; // rdi
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // r9
  BOOL v86; // ebx
  __int64 v87; // rax
  __int64 v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // r8
  __int64 v92; // r9
  __int64 v93; // rbx
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rcx
  __int64 v97; // r8
  __int64 v98; // r9
  struct tagWND *v99; // rax
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  int v103; // edi
  char v104; // si
  bool v105; // bl
  bool v106; // r14
  __int64 v107; // rax
  int v108; // r8d
  int v109; // edx
  char v110; // [rsp+88h] [rbp-80h]
  char v111; // [rsp+89h] [rbp-7Fh]
  unsigned int v112; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v113; // [rsp+90h] [rbp-78h] BYREF
  int v114; // [rsp+94h] [rbp-74h]
  struct tagRECT v115; // [rsp+98h] [rbp-70h] BYREF
  struct tagRECT *v116; // [rsp+A8h] [rbp-60h] BYREF
  struct tagRECT *v117; // [rsp+B0h] [rbp-58h] BYREF
  struct tagWND *v118; // [rsp+B8h] [rbp-50h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+C0h] [rbp-48h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v121; // [rsp+E0h] [rbp-28h]
  struct tagTHREADINFO *v122[2]; // [rsp+E8h] [rbp-20h] BYREF
  struct tagRECT v123; // [rsp+F8h] [rbp-10h] BYREF

  v4 = a4;
  v5 = a3;
  v117 = a4;
  v11 = 0;
  if ( !*((_QWORD *)PtiCurrent() + 61)
    || (v112 = 5, (*(_DWORD *)(**(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL) + 64LL) & 1) == 0) )
  {
    v112 = 4;
  }
  if ( (*((_DWORD *)a1 + 50) & 0x10) == 0 && (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 40LL) + 27LL) & 8) == 0 )
  {
    if ( a2 )
      *v4 = *a2;
    return;
  }
  if ( !a2 )
    goto LABEL_12;
  v12 = *((_QWORD *)a1 + 3) - *(_QWORD *)&a2->left;
  if ( !v12 )
    v12 = *((_QWORD *)a1 + 4) - *(_QWORD *)&a2->right;
  if ( v12 )
  {
LABEL_12:
    v114 = 0;
    v13 = v5 & 0xFFFFFFF;
    v14 = a2;
    if ( !a2 )
      v14 = v4;
    v116 = v14;
    v123 = *v14;
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (LOBYTE(v8) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      LOBYTE(v8) = 0;
    }
    v111 = v8;
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || (v16 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      v16 = 0;
    }
    v110 = v16;
    if ( (_BYTE)v8 || v16 )
    {
      UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, v8, v9, v10);
      LOBYTE(v18) = v110;
      v19 = "Preview";
      LOBYTE(v20) = v111;
      if ( (int)v5 >= 0 )
        v19 = "Drag";
      WPP_RECORDER_AND_TRACE_SF_sdddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v20,
        v18,
        *(_QWORD *)(UserSessionState + 69152),
        5,
        1,
        16,
        (__int64)WPP_b1ea2d8fe1293d1854b7a8cb55068641_Traceguids,
        (__int64)v19,
        v123.left,
        v123.top,
        v123.right,
        v123.bottom,
        LOBYTE(v123.right) - LOBYTE(v123.left),
        LOBYTE(v123.bottom) - LOBYTE(v123.top));
      v4 = v117;
      v11 = 0;
      v14 = v116;
    }
    if ( (int)v5 >= 0 && v13 == 3 && (unsigned int)xxxDetectNewMonitor(a1, &v123) )
    {
      v21 = v123;
      v15 = *(struct MOVESIZEDATA **)(*((_QWORD *)a1 + 2) + 40LL);
      v22 = *((_DWORD *)v15 + 72) & 0xF;
      *v4 = v123;
      LOBYTE(v11) = v22 != 2;
      v114 = v11;
      if ( a2 )
        *a2 = v21;
      if ( v22 == 2 )
      {
        v114 = v11;
      }
      else
      {
        xxxMS_FlushWigglies();
        GenerateMouseMove(0);
      }
    }
    if ( (*((_DWORD *)a1 + 50) & 0x20) != 0 && v13 >= 2 )
    {
      v23 = (struct tagWND **)((char *)a1 + 16);
      v24 = *(_QWORD *)(*((_QWORD *)a1 + 2) + 16LL);
      v122[0] = PtiCurrent();
      v121 = -1;
      v113 = 0;
      LODWORD(v116) = 0;
      v112 = 0;
      *(_OWORD *)BugCheckParameter2 = 0;
      if ( (struct tagTHREADINFO *)v24 != v122[0] )
        Win32RawLockedW32Thread::ManualLock((ULONG_PTR)BugCheckParameter2, v24);
      _InterlockedOr((volatile signed __int32 *)(v24 + 520), 0x8000u);
      if ( a2 )
        *v4 = *a2;
      v25 = *v23;
      v26 = *(__m128i *)v4;
      v27 = *((_QWORD *)*v23 + 13);
      v115 = *v4;
      if ( !v27 || (unsigned int)IsTopLevelWindow(v25) )
      {
        right = _mm_cvtsi128_si32(v26);
        left = _mm_cvtsi128_si32(_mm_srli_si128(v26, 8));
      }
      else
      {
        ScreenToClient(v28, &v115);
        ScreenToClient(v29, &v115.right);
        if ( (*(_BYTE *)(*(_QWORD *)(v30 + 40) + 26LL) & 0x40) != 0 )
        {
          left = v115.left;
          right = v115.right;
          v115.left = v115.right;
          v115.right = left;
        }
        else
        {
          left = v115.right;
          right = v115.left;
        }
        v26 = (__m128i)v115;
      }
      RectRgnIndirect = GreCreateRectRgnIndirect(*((_QWORD *)v25 + 5) + 88LL);
      v34 = (HRGN)RectRgnIndirect;
      v35 = *(_QWORD *)(*((_QWORD *)*v23 + 5) + 168LL);
      if ( v35 )
        GreCombineRgn(RectRgnIndirect, RectRgnIndirect, v35, 1);
      Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, *v23);
      v118 = *v23;
      v36 = (_DWORD *)*((_QWORD *)v118 + 5);
      if ( v36[24] - v36[22] == left - right
        && v36[25] - v36[23] == _mm_cvtsi128_si32(_mm_srli_si128(v26, 12)) - _mm_cvtsi128_si32(_mm_srli_si128(v26, 4))
        || !(unsigned int)DoesQualifyForResizeOptimization(a1) )
      {
        v47 = v112;
      }
      else
      {
        v37 = v118;
        v113 = 0;
        v38 = DoesRequireResizeLayoutSynchronization(v118);
        v39 = *(_QWORD *)v37;
        v40 = v38;
        LODWORD(v116) = v38;
        v45 = W32GetUserSessionState(v42, v41, v43, v44);
        v46 = GreWindowResizeStarted(*(_QWORD *)(*(_QWORD *)(v45 + 56744) + 40LL), v39, v40, &v112, &v113);
        v47 = v112;
        if ( v46 && v112 )
          SetSystemTimer((unsigned int)*v23, 65522, v113, (unsigned int)ResizeTimerFunc, 1);
        v113 = 1;
      }
      if ( (unsigned int)Feature_ApplyWindowActionConvergence__private_IsEnabledDeviceUsageNoInline() )
      {
        xxxMoveSizeSetWindowPos(a1, &v115);
      }
      else
      {
        v115 = (struct tagRECT)v26;
        xxxMoveSizeSetWindowPosOld(a1, &v115);
        if ( (*((_DWORD *)a1 + 50) & 0x200000) != 0 )
        {
          v50 = ValidateHmonitor(*(_QWORD *)(*((_QWORD *)*v23 + 5) + 256LL), v48, v49);
          v51 = *v23;
          *((_QWORD *)a1 + 27) = v50;
          if ( (unsigned int)IsTopLevelWindow(v51) )
          {
            v53 = *((_QWORD *)v52 + 5);
            if ( (*(_DWORD *)(v53 + 288) & 0xF) == 2 && (*(_DWORD *)(*((_QWORD *)v52 + 2) + 680LL) & 0x2000000) == 0 )
            {
              if ( a2 )
              {
                *a2 = *(struct tagRECT *)(v53 + 88);
                v52 = *v23;
              }
              *v117 = *(struct tagRECT *)(*((_QWORD *)v52 + 5) + 88LL);
              *(_OWORD *)((char *)a1 + 120) = *(_OWORD *)(*((_QWORD *)*v23 + 5) + 88LL);
            }
          }
          *((_DWORD *)a1 + 50) &= ~0x200000u;
        }
      }
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
      if ( *(struct MOVESIZEDATA **)(v24 + 704) == a1 )
      {
        v54 = GreCreateRectRgnIndirect(*((_QWORD *)*v23 + 5) + 88LL);
        v56 = v54;
        v57 = *((_QWORD *)*v23 + 5);
        v58 = *(_QWORD *)(v57 + 168);
        if ( v58 )
          GreCombineRgn(v54, v54, v58, 1);
        if ( v34 )
        {
          if ( v56 )
          {
            GreCombineRgn(v34, v34, v56, 4);
          }
          else
          {
            GreDeleteObject(v34);
            v34 = 0;
          }
        }
        v59 = *(struct tagWND **)(GetDesktopWindow(*v23, v57, v58, v55) + 112);
        Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, v59);
        xxxUpdateThreadsWindows(v122[0], v59, v34);
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
        if ( v113 )
        {
          v64 = *(_QWORD *)*v23;
          v65 = W32GetUserSessionState(v61, v60, v62, v63);
          GreWindowResizeComplete(*(_QWORD *)(*(_QWORD *)(v65 + 56744) + 40LL), v64);
          if ( v47 )
          {
            if ( !(_DWORD)v116 )
              FindTimer((unsigned int)*v23, 65522, 2, 1, 0);
          }
        }
        GreDeleteObject(v56);
      }
      GreDeleteObject(v34);
      _InterlockedAnd((volatile signed __int32 *)(v24 + 520), 0xFFFF7FFF);
      if ( v121 != -1 )
        PopAndFreeW32ThreadLock(BugCheckParameter2);
      goto LABEL_101;
    }
    v66 = *v14;
    v116 = 0;
    *(struct tagRECT *)v122 = v66;
    v67 = W32GetUserSessionState(v15, v8, v9, v10);
    v23 = (struct tagWND **)((char *)a1 + 16);
    v68 = *((_QWORD *)a1 + 2);
    v115 = *(struct tagRECT *)(**(_QWORD **)(v67 + 56744) + 24LL);
    v116 = *(struct tagRECT **)((char *)a1 + ((v5 >> 63) & 0x18) + 216);
    WindowMargins = WindowMargins::_anonymous_namespace_::GetWindowMargins(
                      v68,
                      *(unsigned __int16 *)(*(_QWORD *)&v116[2].right + 60LL));
    LODWORD(v122[0]) = (__int16)WindowMargins + v66.left;
    HIDWORD(v122[0]) = SWORD2(WindowMargins) + v66.top;
    LODWORD(v122[1]) = v66.right - SWORD1(WindowMargins);
    HIDWORD(v122[1]) = v66.bottom - SHIWORD(WindowMargins);
    LogicalToPhysicalDPIRect(v122, v122, *(unsigned int *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 40LL) + 288LL), &v116);
    if ( v114 )
    {
      v74 = W32GetUserSessionState(v71, v70, v72, v73);
      bSetDevDragRect(*(HDEV *)(*(_QWORD *)(v74 + 56744) + 40LL));
    }
    if ( a2 )
    {
      if ( (int)v5 < 0 && (*((_DWORD *)a1 + 50) & 0x20) != 0 )
      {
        v75 = *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v71, v70, v72, v73) + 19704) + 4960LL);
        v76 = *(_QWORD *)*v23;
        v81 = W32GetUserSessionState(v78, v77, v79, v80);
        bMoveDevPreviewRect(*(_QWORD *)(*(_QWORD *)(v81 + 56744) + 40LL), v122, v112, v76, v75);
      }
      else
      {
        v86 = 0;
        if ( *((_QWORD *)PtiCurrent() + 61) )
        {
          v83 = **(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL);
          if ( (*(_DWORD *)(v83 + 64) & 1) != 0 )
            v86 = 1;
        }
        v87 = W32GetUserSessionState(v83, v82, v84, v85);
        bMoveDevDragRect(*(_QWORD *)(*(_QWORD *)(v87 + 56744) + 40LL), v122, &v115, v86);
      }
      *v117 = *a2;
      goto LABEL_101;
    }
    if ( v13 )
    {
      if ( v13 == 1 && (int)v5 < 0 )
      {
        v93 = *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v71, v70, v72, v73) + 19704) + 4960LL);
        v94 = W32GetUserSessionState(v96, v95, v97, v98);
        goto LABEL_100;
      }
    }
    else
    {
      v88 = W32GetUserSessionState(v71, v70, v72, v73);
      if ( (int)v5 < 0 )
      {
        v93 = *(_QWORD *)(*(_QWORD *)(v88 + 19704) + 4960LL);
        v94 = W32GetUserSessionState(v90, v89, v91, v92);
LABEL_100:
        bSetDevPreviewRect(*(HDEV *)(*(_QWORD *)(v94 + 56744) + 40LL), v93);
        goto LABEL_101;
      }
      bSetDevDragRect(*(HDEV *)(*(_QWORD *)(v88 + 56744) + 40LL));
    }
LABEL_101:
    if ( v114 && *((_DWORD *)a1 + 44) == 9 )
    {
      v122[0] = *((struct tagTHREADINFO **)a1 + 27);
      v99 = *v23;
      v117 = 0;
      PhysicalToLogicalDPIPoint(&v117, (char *)a1 + 260, *(unsigned int *)(*((_QWORD *)v99 + 5) + 288LL), v122);
      v103 = v123.left - (_DWORD)v117;
      v104 = LOBYTE(v123.top) - BYTE4(v117);
      *((_DWORD *)a1 + 43) = v123.top - HIDWORD(v117);
      *((_DWORD *)a1 + 42) = v103;
      v105 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v106 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v105 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v107 = W32GetUserSessionState(WPP_GLOBAL_Control, v100, v101, v102);
        LOBYTE(v108) = v106;
        LOBYTE(v109) = v105;
        WPP_RECORDER_AND_TRACE_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v109,
          v108,
          *(_QWORD *)(v107 + 69152),
          4,
          1,
          17,
          (__int64)WPP_b1ea2d8fe1293d1854b7a8cb55068641_Traceguids,
          v103,
          v104);
      }
    }
  }
}

```

## disassembly

```asm
0x1401a7bb0  mov     rax, rsp
0x1401a7bb3  mov     [rax+18h], rbx
0x1401a7bb7  push    rbp
0x1401a7bb8  push    rsi
0x1401a7bb9  push    rdi
0x1401a7bba  push    r12
0x1401a7bbc  push    r13
0x1401a7bbe  push    r14
0x1401a7bc0  push    r15
0x1401a7bc2  lea     rbp, [rax-58h]
0x1401a7bc6  sub     rsp, 120h
0x1401a7bcd  movaps  xmmword ptr [rax-48h], xmm6
0x1401a7bd1  mov     rax, cs:__security_cookie
0x1401a7bd8  xor     rax, rsp
0x1401a7bdb  mov     [rbp+50h+var_50], rax
0x1401a7bdf  mov     rbx, r9
0x1401a7be2  movsxd  r13, r8d
0x1401a7be5  mov     [rbp+50h+var_A8], rbx
0x1401a7be9  mov     r15, rdx
0x1401a7bec  mov     r14, rcx
0x1401a7bef  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401a7bf4  xor     esi, esi
0x1401a7bf6  cmp     [rax+1E8h], rsi
0x1401a7bfd  jz      short loc_1401A7C20
0x1401a7bff  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401a7c04  mov     [rbp+50h+var_CC], 5
0x1401a7c0b  mov     rcx, [rax+1E8h]
0x1401a7c12  mov     rax, [rcx+8]
0x1401a7c16  mov     rcx, [rax]
0x1401a7c19  mov     eax, [rcx+40h]
0x1401a7c1c  test    al, 1
0x1401a7c1e  jnz     short loc_1401A7C27
0x1401a7c20  mov     [rbp+50h+var_CC], 4
0x1401a7c27  mov     eax, [r14+0C8h]
0x1401a7c2e  test    al, 10h
0x1401a7c30  jnz     short loc_1401A7C56
0x1401a7c32  mov     rax, [r14+10h]
0x1401a7c36  mov     rcx, [rax+28h]
0x1401a7c3a  test    byte ptr [rcx+1Bh], 8
0x1401a7c3e  jnz     short loc_1401A7C56
0x1401a7c40  test    r15, r15
0x1401a7c43  jz      loc_1401A8577
0x1401a7c49  movups  xmm0, xmmword ptr [r15]
0x1401a7c4d  movdqu  xmmword ptr [rbx], xmm0
0x1401a7c51  jmp     loc_1401A8577
0x1401a7c56  test    r15, r15
0x1401a7c59  jz      short loc_1401A7C75
0x1401a7c5b  mov     rcx, [r14+18h]
0x1401a7c5f  sub     rcx, [r15]
0x1401a7c62  jnz     short loc_1401A7C6C
0x1401a7c64  mov     rcx, [r14+20h]
0x1401a7c68  sub     rcx, [r15+8]
0x1401a7c6c  test    rcx, rcx
0x1401a7c6f  jz      loc_1401A8577
0x1401a7c75  mov     r12d, r13d
0x1401a7c78  mov     [rbp+50h+var_C4], esi
0x1401a7c7b  and     r12d, 0FFFFFFFh
0x1401a7c82  mov     rdi, r15
0x1401a7c85  test    r15, r15
0x1401a7c88  cmovz   rdi, rbx
0x1401a7c8c  mov     [rbp+50h+var_B0], rdi
0x1401a7c90  movups  xmm0, xmmword ptr [rdi]
0x1401a7c93  movdqu  xmmword ptr [rbp+50h+var_60.left], xmm0
0x1401a7c98  mov     rcx, cs:WPP_GLOBAL_Control
0x1401a7c9f  lea     rax, WPP_GLOBAL_Control
0x1401a7ca6  cmp     rcx, rax
0x1401a7ca9  jz      short loc_1401A7CBA
0x1401a7cab  mov     eax, [rcx+2Ch]
0x1401a7cae  test    al, 1
0x1401a7cb0  jz      short loc_1401A7CBA
0x1401a7cb2  cmp     byte ptr [rcx+29h], 5
0x1401a7cb6  mov     dl, 1
0x1401a7cb8  jnb     short loc_1401A7CBD
0x1401a7cba  mov     dl, sil
0x1401a7cbd  lea     rax, WPP_RECORDER_INITIALIZED
0x1401a7cc4  mov     [rbp+50h+var_CF], dl
0x1401a7cc7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401a7cce  jz      short loc_1401A7CD8
0x1401a7cd0  mov     al, 1
0x1401a7cd2  cmp     [rcx+48h], si
0x1401a7cd6  jnz     short loc_1401A7CDB
0x1401a7cd8  mov     al, sil
0x1401a7cdb  mov     [rbp+50h+var_D0], al
0x1401a7cde  test    dl, dl
0x1401a7ce0  jnz     short loc_1401A7CEA
0x1401a7ce2  test    al, al
0x1401a7ce4  jz      loc_1401A7D93
0x1401a7cea  mov     rsi, qword ptr [rbp+50h+var_60.left]
0x1401a7cee  mov     rdi, qword ptr [rbp+50h+var_60.right]
0x1401a7cf2  mov     rax, rsi
0x1401a7cf5  mov     rbx, rdi
0x1401a7cf8  shr     rax, 20h
0x1401a7cfc  shr     rbx, 20h
0x1401a7d00  sub     edi, esi
0x1401a7d02  sub     ebx, eax
0x1401a7d04  call    cs:__imp_W32GetUserSessionState
0x1401a7d0b  nop     dword ptr [rax+rax+00h]
0x1401a7d10  mov     r8b, [rbp+50h+var_D0]
0x1401a7d14  lea     rcx, aPreview; "Preview"
0x1401a7d1b  mov     dl, [rbp+50h+var_CF]
0x1401a7d1e  test    r13d, r13d
0x1401a7d21  mov     [rsp+150h+var_E0], ebx
0x1401a7d25  mov     r9, [rax+10E20h]
0x1401a7d2c  lea     rax, aDrag; "Drag"
0x1401a7d33  mov     [rsp+150h+var_E8], edi
0x1401a7d37  cmovns  rcx, rax
0x1401a7d3b  mov     eax, [rbp+50h+var_60.bottom]
0x1401a7d3e  mov     [rsp+150h+var_F0], eax
0x1401a7d42  mov     eax, [rbp+50h+var_60.right]
0x1401a7d45  mov     [rsp+150h+var_F8], eax
0x1401a7d49  mov     eax, [rbp+50h+var_60.top]
0x1401a7d4c  mov     [rsp+150h+var_100], eax
0x1401a7d50  lea     rax, WPP_b1ea2d8fe1293d1854b7a8cb55068641_Traceguids
0x1401a7d57  mov     [rsp+150h+var_108], esi
0x1401a7d5b  mov     qword ptr [rsp+150h+var_110], rcx
0x1401a7d60  mov     rcx, cs:WPP_GLOBAL_Control
0x1401a7d67  mov     [rsp+150h+var_118], rax
0x1401a7d6c  mov     word ptr [rsp+150h+var_120], 10h
0x1401a7d73  mov     dword ptr [rsp+150h+var_128], 1
0x1401a7d7b  mov     rcx, [rcx+18h]
0x1401a7d7f  mov     byte ptr [rsp+150h+var_130], 5
0x1401a7d84  call    WPP_RECORDER_AND_TRACE_SF_sdddddd
0x1401a7d89  mov     rbx, [rbp+50h+var_A8]
0x1401a7d8d  xor     esi, esi
0x1401a7d8f  mov     rdi, [rbp+50h+var_B0]
0x1401a7d93  test    r13d, r13d
0x1401a7d96  js      short loc_1401A7DFA
0x1401a7d98  cmp     r12d, 3
0x1401a7d9c  jnz     short loc_1401A7DFA
0x1401a7d9e  lea     rdx, [rbp+50h+var_60]; struct tagRECT *
0x1401a7da2  mov     rcx, r14; this
0x1401a7da5  call    ?xxxDetectNewMonitor@@YAHPEAUMOVESIZEDATA@@PEAUtagRECT@@@Z; xxxDetectNewMonitor(MOVESIZEDATA *,tagRECT *)
0x1401a7daa  test    eax, eax
0x1401a7dac  jz      short loc_1401A7DFA
0x1401a7dae  mov     rax, [r14+10h]
0x1401a7db2  movups  xmm0, xmmword ptr [rbp+50h+var_60.left]
0x1401a7db6  mov     rcx, [rax+28h]
0x1401a7dba  mov     eax, [rcx+120h]
0x1401a7dc0  and     eax, 0Fh
0x1401a7dc3  cmp     eax, 2
0x1401a7dc6  movdqu  xmmword ptr [rbx], xmm0
0x1401a7dca  setnz   sil
0x1401a7dce  mov     [rbp+50h+var_C4], esi
0x1401a7dd1  test    r15, r15
0x1401a7dd4  jz      short loc_1401A7DDB
0x1401a7dd6  movdqu  xmmword ptr [r15], xmm0
0x1401a7ddb  cmp     eax, 2
0x1401a7dde  jz      short loc_1401A7DF5
0x1401a7de0  call    ?xxxMS_FlushWigglies@@YAXXZ; xxxMS_FlushWigglies(void)
0x1401a7de5  xor     ecx, ecx
0x1401a7de7  call    cs:__imp_GenerateMouseMove
0x1401a7dee  nop     dword ptr [rax+rax+00h]
0x1401a7df3  jmp     short loc_1401A7DF8
0x1401a7df5  mov     [rbp+50h+var_C4], esi
0x1401a7df8  xor     esi, esi
0x1401a7dfa  mov     eax, [r14+0C8h]
0x1401a7e01  test    al, 20h
0x1401a7e03  jz      loc_1401A821C
0x1401a7e09  cmp     r12d, 2
0x1401a7e0d  jb      loc_1401A821C
0x1401a7e13  lea     rsi, [r14+10h]
0x1401a7e17  mov     rax, [rsi]
0x1401a7e1a  mov     r13, [rax+10h]
0x1401a7e1e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401a7e23  xor     edi, edi
0x1401a7e25  mov     [rbp+50h+var_70], rax
0x1401a7e29  mov     [rbp+50h+var_78], 0FFFFFFFFFFFFFFFFh
0x1401a7e31  xorps   xmm0, xmm0
0x1401a7e34  mov     [rbp+50h+var_C8], edi
0x1401a7e37  mov     dword ptr [rbp+50h+var_B0], edi
0x1401a7e3a  mov     [rbp+50h+var_CC], edi
0x1401a7e3d  movups  xmmword ptr [rbp+50h+BugCheckParameter2], xmm0
0x1401a7e41  cmp     r13, rax
0x1401a7e44  jz      short loc_1401A7E52
0x1401a7e46  mov     rdx, r13; BugCheckParameter3
0x1401a7e49  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x1401a7e4d  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::ManualLock(_W32THREAD *)
0x1401a7e52  lock or dword ptr [r13+208h], 8000h
0x1401a7e5e  test    r15, r15
0x1401a7e61  jz      short loc_1401A7E6B
0x1401a7e63  movups  xmm0, xmmword ptr [r15]
0x1401a7e67  movdqu  xmmword ptr [rbx], xmm0
0x1401a7e6b  mov     r10, [rsi]
0x1401a7e6e  movups  xmm6, xmmword ptr [rbx]
0x1401a7e71  mov     r9, [r10+68h]
0x1401a7e75  movaps  xmmword ptr [rbp+50h+var_C0.left], xmm6
0x1401a7e79  test    r9, r9
0x1401a7e7c  jz      short loc_1401A7ECA
0x1401a7e7e  mov     rcx, r10
0x1401a7e81  call    _IsTopLevelWindow
0x1401a7e86  test    eax, eax
0x1401a7e88  jnz     short loc_1401A7ECA
0x1401a7e8a  lea     rdx, [rbp+50h+var_C0]
0x1401a7e8e  mov     rcx, r9
0x1401a7e91  call    _ScreenToClient
0x1401a7e96  lea     rdx, [rbp+50h+var_C0.right]
0x1401a7e9a  mov     rcx, r9
0x1401a7e9d  call    _ScreenToClient
0x1401a7ea2  mov     r9, [r9+28h]
0x1401a7ea6  test    byte ptr [r9+1Ah], 40h
0x1401a7eab  jz      short loc_1401A7EBD
0x1401a7ead  mov     ebx, [rbp+50h+var_C0.left]
0x1401a7eb0  mov     r12d, [rbp+50h+var_C0.right]
0x1401a7eb4  mov     [rbp+50h+var_C0.left], r12d
0x1401a7eb8  mov     [rbp+50h+var_C0.right], ebx
0x1401a7ebb  jmp     short loc_1401A7EC4
0x1401a7ebd  mov     ebx, [rbp+50h+var_C0.right]
0x1401a7ec0  mov     r12d, [rbp+50h+var_C0.left]
0x1401a7ec4  movaps  xmm6, xmmword ptr [rbp+50h+var_C0.left]
0x1401a7ec8  jmp     short loc_1401A7EDC
0x1401a7eca  movdqa  xmm0, xmm6
0x1401a7ece  movd    r12d, xmm6
0x1401a7ed3  psrldq  xmm0, 8
0x1401a7ed8  movd    ebx, xmm0
0x1401a7edc  mov     rcx, [r10+28h]
0x1401a7ee0  add     rcx, 58h ; 'X'
0x1401a7ee4  call    cs:__imp_GreCreateRectRgnIndirect
0x1401a7eeb  nop     dword ptr [rax+rax+00h]
0x1401a7ef0  mov     rcx, [rsi]
0x1401a7ef3  mov     rdi, rax
0x1401a7ef6  mov     rdx, [rcx+28h]
0x1401a7efa  mov     r8, [rdx+0A8h]
0x1401a7f01  test    r8, r8
0x1401a7f04  jz      short loc_1401A7F1E
0x1401a7f06  mov     r9d, 1
0x1401a7f0c  mov     rdx, rax
0x1401a7f0f  mov     rcx, rax
0x1401a7f12  call    cs:__imp_GreCombineRgn
0x1401a7f19  nop     dword ptr [rax+rax+00h]
0x1401a7f1e  mov     rdx, [rsi]
0x1401a7f21  lea     rcx, [rbp+50h+BugCheckParameter3]
0x1401a7f25  call    ??0?$Win32HMThreadLockBase@UtagMENU@@$00$0A@@@QEAA@PEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(tagMENU *)
0x1401a7f2a  mov     rax, [rsi]
0x1401a7f2d  sub     ebx, r12d
0x1401a7f30  mov     [rbp+50h+var_A0], rax
0x1401a7f34  mov     rdx, [rax+28h]
0x1401a7f38  mov     ecx, [rdx+60h]
0x1401a7f3b  sub     ecx, [rdx+58h]
0x1401a7f3e  cmp     ecx, ebx
0x1401a7f40  jnz     short loc_1401A7F6E
0x1401a7f42  mov     eax, [rdx+5Ch]
0x1401a7f45  movdqa  xmm0, xmm6
0x1401a7f49  mov     edx, [rdx+64h]
0x1401a7f4c  movdqa  xmm1, xmm6
0x1401a7f50  sub     edx, eax
0x1401a7f52  psrldq  xmm0, 0Ch
0x1401a7f57  psrldq  xmm1, 4
0x1401a7f5c  movd    ecx, xmm0
0x1401a7f60  movd    eax, xmm1
0x1401a7f64  sub     ecx, eax
0x1401a7f66  cmp     edx, ecx
0x1401a7f68  jz      loc_1401A7FFF
0x1401a7f6e  mov     rcx, r14; struct MOVESIZEDATA *
0x1401a7f71  call    ?DoesQualifyForResizeOptimization@@YAHPEAUMOVESIZEDATA@@@Z; DoesQualifyForResizeOptimization(MOVESIZEDATA *)
0x1401a7f76  test    eax, eax
0x1401a7f78  jz      loc_1401A7FFF
0x1401a7f7e  mov     rbx, [rbp+50h+var_A0]
0x1401a7f82  mov     rcx, rbx; struct tagWND *
0x1401a7f85  mov     [rbp+50h+var_C8], 0
0x1401a7f8c  call    ?DoesRequireResizeLayoutSynchronization@@YAHPEAUtagWND@@@Z; DoesRequireResizeLayoutSynchronization(tagWND *)
0x1401a7f91  mov     rbx, [rbx]
0x1401a7f94  mov     r12d, eax
0x1401a7f97  mov     dword ptr [rbp+50h+var_B0], eax
0x1401a7f9a  call    cs:__imp_W32GetUserSessionState
0x1401a7fa1  nop     dword ptr [rax+rax+00h]
0x1401a7fa6  lea     r9, [rbp+50h+var_CC]
0x1401a7faa  mov     r8d, r12d
0x1401a7fad  mov     rdx, rbx
0x1401a7fb0  mov     rcx, [rax+0DDA8h]
0x1401a7fb7  lea     rax, [rbp+50h+var_C8]
0x1401a7fbb  mov     qword ptr [rsp+150h+var_130], rax
0x1401a7fc0  mov     rcx, [rcx+28h]
0x1401a7fc4  call    GreWindowResizeStarted
0x1401a7fc9  mov     r12d, [rbp+50h+var_CC]
0x1401a7fcd  test    eax, eax
0x1401a7fcf  jz      short loc_1401A7FF6
0x1401a7fd1  test    r12d, r12d
0x1401a7fd4  jz      short loc_1401A7FF6
0x1401a7fd6  mov     r8d, [rbp+50h+var_C8]
0x1401a7fda  lea     r9, ?ResizeTimerFunc@@YAXPEAUtagWND@@I_K_J@Z; ResizeTimerFunc(tagWND *,uint,unsigned __int64,__int64)
0x1401a7fe1  mov     rcx, [rsi]
0x1401a7fe4  mov     edx, 0FFF2h
0x1401a7fe9  mov     [rsp+150h+var_130], 1
0x1401a7ff1  call    _SetSystemTimer
0x1401a7ff6  mov     [rbp+50h+var_C8], 1
0x1401a7ffd  jmp     short loc_1401A8003
0x1401a7fff  mov     r12d, [rbp+50h+var_CC]
0x1401a8003  call    Feature_ApplyWindowActionConvergence__private_IsEnabledDeviceUsageNoInline
0x1401a8008  lea     rdx, [rbp+50h+var_C0]; struct tagRECT
0x1401a800c  mov     rcx, r14; struct MOVESIZEDATA *
0x1401a800f  test    eax, eax
0x1401a8011  jz      short loc_1401A801D
0x1401a8013  call    ?xxxMoveSizeSetWindowPos@@YAXPEAUMOVESIZEDATA@@AEBUtagRECT@@@Z; xxxMoveSizeSetWindowPos(MOVESIZEDATA *,tagRECT const &)
0x1401a8018  jmp     loc_1401A80C3
0x1401a801d  movdqa  xmmword ptr [rbp+50h+var_C0.left], xmm6
0x1401a8022  call    ?xxxMoveSizeSetWindowPosOld@@YAXPEAUMOVESIZEDATA@@UtagRECT@@@Z; xxxMoveSizeSetWindowPosOld(MOVESIZEDATA *,tagRECT)
0x1401a8027  test    dword ptr [r14+0C8h], 200000h
0x1401a8032  jz      loc_1401A80C3
0x1401a8038  mov     rax, [rsi]
0x1401a803b  mov     rcx, [rax+28h]
  ... truncated ...
```
