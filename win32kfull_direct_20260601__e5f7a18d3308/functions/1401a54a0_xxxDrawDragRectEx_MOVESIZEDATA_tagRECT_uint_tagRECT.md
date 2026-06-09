# xxxDrawDragRectEx(MOVESIZEDATA *,tagRECT *,uint,tagRECT *)

- ea: `0x1401a54a0`
- end: `0x1401a5e94`
- name: `?xxxDrawDragRectEx@@YAXPEAUMOVESIZEDATA@@PEAUtagRECT@@I1@Z`
- size: `2548`
- prototype: `void __fastcall(struct MOVESIZEDATA *, struct tagRECT *, unsigned int, struct tagRECT *)`
- caller_count: `3`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1401a5484`
- `0x14027d004`
- `0x14027e3d0`

## callees

- `0x140011ab0`
- `0x140012790`
- `0x14001b230`
- `0x1400241fc`
- `0x1400bbd30`
- `0x1400c636c`
- `0x1400e2cb0`
- `0x1400e648c`
- `0x14011a908`
- `0x14011ae80`
- `0x14013eb50`
- `0x140177728`
- `0x1401a54a0`
- `0x1401a5e9c`
- `0x1401a7600`
- `0x1401db6d4`
- `0x14020a2b8`
- `0x140210158`
- `0x140215554`
- `0x14021afe4`
- `0x14021de8c`
- `0x140222810`
- `0x14022b7e8`
- `0x14022d430`
- `0x140243c90`
- `0x140252024`
- `0x1402576a0`
- `0x1402cb4bc`
- `0x140342fa0`

## import_xrefs

- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a57d4`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a59d4`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a57d4`
- `win32kbase!GreCreateRectRgnIndirect` at `0x1401a59d4`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401a5db0`
- `win32kbase!PhysicalToLogicalDPIPoint` at `0x1401a5db0`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x1401a5ba5`
- `win32kbase!LogicalToPhysicalDPIRect` at `0x1401a5ba5`
- `win32kbase!GenerateMouseMove` at `0x1401a56d7`
- `win32kbase!GenerateMouseMove` at `0x1401a56d7`
- `win32kbase!GreCombineRgn` at `0x1401a5802`
- `win32kbase!GreCombineRgn` at `0x1401a5a02`
- `win32kbase!GreCombineRgn` at `0x1401a5a37`
- `win32kbase!GreCombineRgn` at `0x1401a5802`
- `win32kbase!GreCombineRgn` at `0x1401a5a02`
- `win32kbase!GreCombineRgn` at `0x1401a5a37`
- `win32kbase!GreDeleteObject` at `0x1401a5a1b`
- `win32kbase!GreDeleteObject` at `0x1401a5acc`
- `win32kbase!GreDeleteObject` at `0x1401a5adb`
- `win32kbase!GreDeleteObject` at `0x1401a5a1b`
- `win32kbase!GreDeleteObject` at `0x1401a5acc`
- `win32kbase!GreDeleteObject` at `0x1401a5adb`
- `win32kbase!ValidateHmonitor` at `0x1401a5936`
- `win32kbase!ValidateHmonitor` at `0x1401a5936`
- `WIN32K!W32GetUserSessionState` at `0x1401a55f4`
- `WIN32K!W32GetUserSessionState` at `0x1401a588a`
- `WIN32K!W32GetUserSessionState` at `0x1401a5a7f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5b18`
- `WIN32K!W32GetUserSessionState` at `0x1401a5bb7`
- `WIN32K!W32GetUserSessionState` at `0x1401a5bff`
- `WIN32K!W32GetUserSessionState` at `0x1401a5c1f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5c7f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5cbc`
- `WIN32K!W32GetUserSessionState` at `0x1401a5ce1`
- `WIN32K!W32GetUserSessionState` at `0x1401a5d1f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5d3f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5e17`
- `WIN32K!W32GetUserSessionState` at `0x1401a55f4`
- `WIN32K!W32GetUserSessionState` at `0x1401a588a`
- `WIN32K!W32GetUserSessionState` at `0x1401a5a7f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5b18`
- `WIN32K!W32GetUserSessionState` at `0x1401a5bb7`
- `WIN32K!W32GetUserSessionState` at `0x1401a5bff`
- `WIN32K!W32GetUserSessionState` at `0x1401a5c1f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5c7f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5cbc`
- `WIN32K!W32GetUserSessionState` at `0x1401a5ce1`
- `WIN32K!W32GetUserSessionState` at `0x1401a5d1f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5d3f`
- `WIN32K!W32GetUserSessionState` at `0x1401a5e17`

## pseudocode

```c
void __fastcall xxxDrawDragRectEx(struct MOVESIZEDATA *a1, struct tagRECT *a2, int a3, struct tagRECT *a4)
{
  struct tagRECT *v4; // rbx
  __int64 v5; // r13
  __int64 v8; // rdx
  int v9; // esi
  __int64 v10; // rcx
  unsigned int v11; // r12d
  struct tagRECT *v12; // rdi
  struct MOVESIZEDATA *v13; // rcx
  char v14; // al
  __int64 UserSessionState; // rax
  int v16; // r8d
  const char *v17; // rcx
  int v18; // edx
  struct tagRECT v19; // xmm0
  int v20; // eax
  struct tagWND **v21; // rsi
  ULONG_PTR v22; // r13
  struct tagWND *v23; // r10
  __m128i v24; // xmm6
  __int64 v25; // r9
  __int64 v26; // r9
  __int64 v27; // r9
  __int64 v28; // r9
  int left; // ebx
  LONG right; // r12d
  __int64 RectRgnIndirect; // rax
  HRGN v32; // rdi
  __int64 v33; // r8
  _DWORD *v34; // rdx
  struct tagWND *v35; // rbx
  unsigned int v36; // eax
  __int64 v37; // rbx
  unsigned int v38; // r12d
  __int64 v39; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  int v42; // eax
  int v43; // r12d
  __int64 v44; // rax
  struct tagWND *v45; // rcx
  struct tagWND *v46; // r9
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // r15
  __int64 v50; // rdx
  __int64 v51; // r8
  struct tagWND *v52; // rbx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rbx
  __int64 v56; // rax
  struct tagRECT v57; // xmm0
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 WindowMargins; // rax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // rbx
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rcx
  struct tagWND *v78; // rax
  __int64 v79; // rdx
  int v80; // edi
  char v81; // si
  bool v82; // bl
  bool v83; // r14
  __int64 v84; // rax
  int v85; // r8d
  int v86; // edx
  char v87; // [rsp+88h] [rbp-80h]
  char v88; // [rsp+89h] [rbp-7Fh]
  int v89; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v90; // [rsp+90h] [rbp-78h] BYREF
  int v91; // [rsp+94h] [rbp-74h]
  struct tagRECT v92; // [rsp+98h] [rbp-70h] BYREF
  struct tagRECT *v93; // [rsp+A8h] [rbp-60h] BYREF
  struct tagRECT *v94; // [rsp+B0h] [rbp-58h] BYREF
  struct tagWND *v95; // [rsp+B8h] [rbp-50h]
  ULONG_PTR BugCheckParameter3[2]; // [rsp+C0h] [rbp-48h] BYREF
  ULONG_PTR BugCheckParameter2[2]; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v98; // [rsp+E0h] [rbp-28h]
  struct tagTHREADINFO *v99[2]; // [rsp+E8h] [rbp-20h] BYREF
  struct tagRECT v100; // [rsp+F8h] [rbp-10h] BYREF

  v4 = a4;
  v5 = a3;
  v94 = a4;
  v9 = 0;
  if ( !*((_QWORD *)PtiCurrent() + 61)
    || (v89 = 5, (*(_DWORD *)(**(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL) + 64LL) & 1) == 0) )
  {
    v89 = 4;
  }
  if ( (*((_DWORD *)a1 + 50) & 0x10) == 0 && (*(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 40LL) + 27LL) & 8) == 0 )
  {
    if ( a2 )
      *v4 = *a2;
    return;
  }
  if ( !a2 )
    goto LABEL_12;
  v10 = *((_QWORD *)a1 + 3) - *(_QWORD *)&a2->left;
  if ( !v10 )
    v10 = *((_QWORD *)a1 + 4) - *(_QWORD *)&a2->right;
  if ( v10 )
  {
LABEL_12:
    v91 = 0;
    v11 = v5 & 0xFFFFFFF;
    v12 = a2;
    if ( !a2 )
      v12 = v4;
    v93 = v12;
    v100 = *v12;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (LOBYTE(v8) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 5u) )
    {
      LOBYTE(v8) = 0;
    }
    v88 = v8;
    if ( *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED
      || (v14 = 1, !*((_WORD *)WPP_GLOBAL_Control + 36)) )
    {
      v14 = 0;
    }
    v87 = v14;
    if ( (_BYTE)v8 || v14 )
    {
      UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, v8);
      LOBYTE(v16) = v87;
      v17 = "Preview";
      LOBYTE(v18) = v88;
      if ( (int)v5 >= 0 )
        v17 = "Drag";
      WPP_RECORDER_AND_TRACE_SF_sdddddd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v18,
        v16,
        *(_QWORD *)(UserSessionState + 69152),
        5,
        1,
        16,
        (__int64)WPP_b1ea2d8fe1293d1854b7a8cb55068641_Traceguids,
        (__int64)v17,
        v100.left,
        v100.top,
        v100.right,
        v100.bottom,
        LOBYTE(v100.right) - LOBYTE(v100.left),
        LOBYTE(v100.bottom) - LOBYTE(v100.top));
      v4 = v94;
      v9 = 0;
      v12 = v93;
    }
    if ( (int)v5 >= 0 && v11 == 3 && (unsigned int)xxxDetectNewMonitor(a1, &v100) )
    {
      v19 = v100;
      v13 = *(struct MOVESIZEDATA **)(*((_QWORD *)a1 + 2) + 40LL);
      v20 = *((_DWORD *)v13 + 72) & 0xF;
      *v4 = v100;
      LOBYTE(v9) = v20 != 2;
      v91 = v9;
      if ( a2 )
        *a2 = v19;
      if ( v20 == 2 )
      {
        v91 = v9;
      }
      else
      {
        xxxMS_FlushWigglies();
        GenerateMouseMove(0);
      }
    }
    if ( (*((_DWORD *)a1 + 50) & 0x20) != 0 && v11 >= 2 )
    {
      v21 = (struct tagWND **)((char *)a1 + 16);
      v22 = *(_QWORD *)(*((_QWORD *)a1 + 2) + 16LL);
      v99[0] = PtiCurrent();
      v98 = -1;
      v90 = 0;
      LODWORD(v93) = 0;
      v89 = 0;
      *(_OWORD *)BugCheckParameter2 = 0;
      if ( (struct tagTHREADINFO *)v22 != v99[0] )
        Win32RawLockedW32Thread::ManualLock((ULONG_PTR)BugCheckParameter2, v22);
      _InterlockedOr((volatile signed __int32 *)(v22 + 520), 0x8000u);
      if ( a2 )
        *v4 = *a2;
      v23 = *v21;
      v24 = *(__m128i *)v4;
      v25 = *((_QWORD *)*v21 + 13);
      v92 = *v4;
      if ( !v25 || (unsigned int)IsTopLevelWindow(v23) )
      {
        right = _mm_cvtsi128_si32(v24);
        left = _mm_cvtsi128_si32(_mm_srli_si128(v24, 8));
      }
      else
      {
        ScreenToClient(v26, &v92);
        ScreenToClient(v27, &v92.right);
        if ( (*(_BYTE *)(*(_QWORD *)(v28 + 40) + 26LL) & 0x40) != 0 )
        {
          left = v92.left;
          right = v92.right;
          v92.left = v92.right;
          v92.right = left;
        }
        else
        {
          left = v92.right;
          right = v92.left;
        }
        v24 = (__m128i)v92;
      }
      RectRgnIndirect = GreCreateRectRgnIndirect(*((_QWORD *)v23 + 5) + 88LL);
      v32 = (HRGN)RectRgnIndirect;
      v33 = *(_QWORD *)(*((_QWORD *)*v21 + 5) + 168LL);
      if ( v33 )
        GreCombineRgn(RectRgnIndirect, RectRgnIndirect, v33, 1);
      Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, *v21);
      v95 = *v21;
      v34 = (_DWORD *)*((_QWORD *)v95 + 5);
      if ( v34[24] - v34[22] == left - right
        && v34[25] - v34[23] == _mm_cvtsi128_si32(_mm_srli_si128(v24, 12)) - _mm_cvtsi128_si32(_mm_srli_si128(v24, 4))
        || !(unsigned int)DoesQualifyForResizeOptimization(a1) )
      {
        v43 = v89;
      }
      else
      {
        v35 = v95;
        v90 = 0;
        v36 = DoesRequireResizeLayoutSynchronization(v95);
        v37 = *(_QWORD *)v35;
        v38 = v36;
        LODWORD(v93) = v36;
        v41 = W32GetUserSessionState(v40, v39);
        v42 = GreWindowResizeStarted(*(_QWORD *)(*(_QWORD *)(v41 + 56744) + 40LL), v37, v38, &v89, &v90);
        v43 = v89;
        if ( v42 && v89 )
          SetSystemTimer((unsigned int)*v21, 65522, v90, (unsigned int)ResizeTimerFunc, 1);
        v90 = 1;
      }
      if ( (unsigned int)Feature_ApplyWindowActionConvergence__private_IsEnabledDeviceUsageNoInline() )
      {
        xxxMoveSizeSetWindowPos(a1, &v92);
      }
      else
      {
        v92 = (struct tagRECT)v24;
        xxxMoveSizeSetWindowPosOld(a1, &v92);
        if ( (*((_DWORD *)a1 + 50) & 0x200000) != 0 )
        {
          v44 = ValidateHmonitor(*(_QWORD *)(*((_QWORD *)*v21 + 5) + 256LL));
          v45 = *v21;
          *((_QWORD *)a1 + 27) = v44;
          if ( (unsigned int)IsTopLevelWindow(v45) )
          {
            v47 = *((_QWORD *)v46 + 5);
            if ( (*(_DWORD *)(v47 + 288) & 0xF) == 2 && (*(_DWORD *)(*((_QWORD *)v46 + 2) + 680LL) & 0x2000000) == 0 )
            {
              if ( a2 )
              {
                *a2 = *(struct tagRECT *)(v47 + 88);
                v46 = *v21;
              }
              *v94 = *(struct tagRECT *)(*((_QWORD *)v46 + 5) + 88LL);
              *(_OWORD *)((char *)a1 + 120) = *(_OWORD *)(*((_QWORD *)*v21 + 5) + 88LL);
            }
          }
          *((_DWORD *)a1 + 50) &= ~0x200000u;
        }
      }
      Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
      if ( *(struct MOVESIZEDATA **)(v22 + 704) == a1 )
      {
        v48 = GreCreateRectRgnIndirect(*((_QWORD *)*v21 + 5) + 88LL);
        v49 = v48;
        v50 = *((_QWORD *)*v21 + 5);
        v51 = *(_QWORD *)(v50 + 168);
        if ( v51 )
          GreCombineRgn(v48, v48, v51, 1);
        if ( v32 )
        {
          if ( v49 )
          {
            GreCombineRgn(v32, v32, v49, 4);
          }
          else
          {
            GreDeleteObject(v32);
            v32 = 0;
          }
        }
        v52 = *(struct tagWND **)(GetDesktopWindow(*v21, v50, v51) + 112);
        Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(BugCheckParameter3, v52);
        xxxUpdateThreadsWindows(v99[0], v52, v32);
        Win32HMThreadLock<tagCURSOR>::~Win32HMThreadLock<tagCURSOR>((ULONG_PTR)BugCheckParameter3);
        if ( v90 )
        {
          v55 = *(_QWORD *)*v21;
          v56 = W32GetUserSessionState(v54, v53);
          GreWindowResizeComplete(*(_QWORD *)(*(_QWORD *)(v56 + 56744) + 40LL), v55);
          if ( v43 )
          {
            if ( !(_DWORD)v93 )
              FindTimer((unsigned int)*v21, 65522, 2, 1, 0);
          }
        }
        GreDeleteObject(v49);
      }
      GreDeleteObject(v32);
      _InterlockedAnd((volatile signed __int32 *)(v22 + 520), 0xFFFF7FFF);
      if ( v98 != -1 )
        PopAndFreeW32ThreadLock(BugCheckParameter2);
      goto LABEL_99;
    }
    v57 = *v12;
    v93 = 0;
    *(struct tagRECT *)v99 = v57;
    v58 = W32GetUserSessionState(v13, v8);
    v21 = (struct tagWND **)((char *)a1 + 16);
    v59 = *((_QWORD *)a1 + 2);
    v92 = *(struct tagRECT *)(**(_QWORD **)(v58 + 56744) + 24LL);
    v93 = *(struct tagRECT **)((char *)a1 + ((v5 >> 63) & 0x18) + 216);
    WindowMargins = WindowMargins::_anonymous_namespace_::GetWindowMargins(
                      v59,
                      *(unsigned __int16 *)(*(_QWORD *)&v93[2].right + 60LL));
    LODWORD(v99[0]) = (__int16)WindowMargins + v57.left;
    HIDWORD(v99[0]) = SWORD2(WindowMargins) + v57.top;
    LODWORD(v99[1]) = v57.right - SWORD1(WindowMargins);
    HIDWORD(v99[1]) = v57.bottom - SHIWORD(WindowMargins);
    LogicalToPhysicalDPIRect(v99, v99, *(unsigned int *)(*(_QWORD *)(*((_QWORD *)a1 + 2) + 40LL) + 288LL), &v93);
    if ( v91 )
    {
      v63 = W32GetUserSessionState(v62, v61);
      bSetDevDragRect(*(HDEV *)(*(_QWORD *)(v63 + 56744) + 40LL));
    }
    if ( a2 )
    {
      if ( (int)v5 < 0 && (*((_DWORD *)a1 + 50) & 0x20) != 0 )
      {
        v64 = *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v62, v61) + 19704) + 4960LL);
        v67 = W32GetUserSessionState(v66, v65);
        bMoveDevPreviewRect(*(HDEV *)(*(_QWORD *)(v67 + 56744) + 40LL), v64);
      }
      else
      {
        if ( *((_QWORD *)PtiCurrent() + 61) )
          v69 = **(_QWORD **)(*((_QWORD *)PtiCurrent() + 61) + 8LL);
        v70 = W32GetUserSessionState(v69, v68);
        bMoveDevDragRect(*(HDEV *)(*(_QWORD *)(v70 + 56744) + 40LL));
      }
      *v94 = *a2;
      goto LABEL_99;
    }
    if ( v11 )
    {
      if ( v11 == 1 && (int)v5 < 0 )
      {
        v74 = *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v62, v61) + 19704) + 4960LL);
        v75 = W32GetUserSessionState(v77, v76);
        goto LABEL_98;
      }
    }
    else
    {
      v71 = W32GetUserSessionState(v62, v61);
      if ( (int)v5 < 0 )
      {
        v74 = *(_QWORD *)(*(_QWORD *)(v71 + 19704) + 4960LL);
        v75 = W32GetUserSessionState(v73, v72);
LABEL_98:
        bSetDevPreviewRect(*(HDEV *)(*(_QWORD *)(v75 + 56744) + 40LL), v74);
        goto LABEL_99;
      }
      bSetDevDragRect(*(HDEV *)(*(_QWORD *)(v71 + 56744) + 40LL));
    }
LABEL_99:
    if ( v91 && *((_DWORD *)a1 + 44) == 9 )
    {
      v99[0] = *((struct tagTHREADINFO **)a1 + 27);
      v78 = *v21;
      v94 = 0;
      PhysicalToLogicalDPIPoint(&v94, (char *)a1 + 260, *(unsigned int *)(*((_QWORD *)v78 + 5) + 288LL), v99);
      v80 = v100.left - (_DWORD)v94;
      v81 = LOBYTE(v100.top) - BYTE4(v94);
      *((_DWORD *)a1 + 43) = v100.top - HIDWORD(v94);
      *((_DWORD *)a1 + 42) = v80;
      v82 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v83 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v82 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v84 = W32GetUserSessionState(WPP_GLOBAL_Control, v79);
        LOBYTE(v85) = v83;
        LOBYTE(v86) = v82;
        WPP_RECORDER_AND_TRACE_SF_DD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v86,
          v85,
          *(_QWORD *)(v84 + 69152),
          4,
          1,
          17,
          (__int64)WPP_b1ea2d8fe1293d1854b7a8cb55068641_Traceguids,
          v80,
          v81);
      }
    }
  }
}

```

## disassembly

```asm
0x1401a54a0  mov     rax, rsp
0x1401a54a3  mov     [rax+18h], rbx
0x1401a54a7  push    rbp
0x1401a54a8  push    rsi
0x1401a54a9  push    rdi
0x1401a54aa  push    r12
0x1401a54ac  push    r13
0x1401a54ae  push    r14
0x1401a54b0  push    r15
0x1401a54b2  lea     rbp, [rax-58h]
0x1401a54b6  sub     rsp, 120h
0x1401a54bd  movaps  xmmword ptr [rax-48h], xmm6
0x1401a54c1  mov     rax, cs:__security_cookie
0x1401a54c8  xor     rax, rsp
0x1401a54cb  mov     [rbp+50h+var_50], rax
0x1401a54cf  mov     rbx, r9
0x1401a54d2  movsxd  r13, r8d
0x1401a54d5  mov     [rbp+50h+var_A8], rbx
0x1401a54d9  mov     r15, rdx
0x1401a54dc  mov     r14, rcx
0x1401a54df  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401a54e4  xor     esi, esi
0x1401a54e6  cmp     [rax+1E8h], rsi
0x1401a54ed  jz      short loc_1401A5510
0x1401a54ef  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401a54f4  mov     [rbp+50h+var_CC], 5
0x1401a54fb  mov     rcx, [rax+1E8h]
0x1401a5502  mov     rax, [rcx+8]
0x1401a5506  mov     rcx, [rax]
0x1401a5509  mov     eax, [rcx+40h]
0x1401a550c  test    al, 1
0x1401a550e  jnz     short loc_1401A5517
0x1401a5510  mov     [rbp+50h+var_CC], 4
0x1401a5517  mov     eax, [r14+0C8h]
0x1401a551e  test    al, 10h
0x1401a5520  jnz     short loc_1401A5546
0x1401a5522  mov     rax, [r14+10h]
0x1401a5526  mov     rcx, [rax+28h]
0x1401a552a  test    byte ptr [rcx+1Bh], 8
0x1401a552e  jnz     short loc_1401A5546
0x1401a5530  test    r15, r15
0x1401a5533  jz      loc_1401A5E67
0x1401a5539  movups  xmm0, xmmword ptr [r15]
0x1401a553d  movdqu  xmmword ptr [rbx], xmm0
0x1401a5541  jmp     loc_1401A5E67
0x1401a5546  test    r15, r15
0x1401a5549  jz      short loc_1401A5565
0x1401a554b  mov     rcx, [r14+18h]
0x1401a554f  sub     rcx, [r15]
0x1401a5552  jnz     short loc_1401A555C
0x1401a5554  mov     rcx, [r14+20h]
0x1401a5558  sub     rcx, [r15+8]
0x1401a555c  test    rcx, rcx
0x1401a555f  jz      loc_1401A5E67
0x1401a5565  mov     r12d, r13d
0x1401a5568  mov     [rbp+50h+var_C4], esi
0x1401a556b  and     r12d, 0FFFFFFFh
0x1401a5572  mov     rdi, r15
0x1401a5575  test    r15, r15
0x1401a5578  cmovz   rdi, rbx
0x1401a557c  mov     [rbp+50h+var_B0], rdi
0x1401a5580  movups  xmm0, xmmword ptr [rdi]
0x1401a5583  movdqu  xmmword ptr [rbp+50h+var_60.left], xmm0
0x1401a5588  mov     rcx, cs:WPP_GLOBAL_Control
0x1401a558f  lea     rax, WPP_GLOBAL_Control
0x1401a5596  cmp     rcx, rax
0x1401a5599  jz      short loc_1401A55AA
0x1401a559b  mov     eax, [rcx+2Ch]
0x1401a559e  test    al, 1
0x1401a55a0  jz      short loc_1401A55AA
0x1401a55a2  cmp     byte ptr [rcx+29h], 5
0x1401a55a6  mov     dl, 1
0x1401a55a8  jnb     short loc_1401A55AD
0x1401a55aa  mov     dl, sil
0x1401a55ad  lea     rax, WPP_RECORDER_INITIALIZED
0x1401a55b4  mov     [rbp+50h+var_CF], dl
0x1401a55b7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401a55be  jz      short loc_1401A55C8
0x1401a55c0  mov     al, 1
0x1401a55c2  cmp     [rcx+48h], si
0x1401a55c6  jnz     short loc_1401A55CB
0x1401a55c8  mov     al, sil
0x1401a55cb  mov     [rbp+50h+var_D0], al
0x1401a55ce  test    dl, dl
0x1401a55d0  jnz     short loc_1401A55DA
0x1401a55d2  test    al, al
0x1401a55d4  jz      loc_1401A5683
0x1401a55da  mov     rsi, qword ptr [rbp+50h+var_60.left]
0x1401a55de  mov     rdi, qword ptr [rbp+50h+var_60.right]
0x1401a55e2  mov     rax, rsi
0x1401a55e5  mov     rbx, rdi
0x1401a55e8  shr     rax, 20h
0x1401a55ec  shr     rbx, 20h
0x1401a55f0  sub     edi, esi
0x1401a55f2  sub     ebx, eax
0x1401a55f4  call    cs:__imp_W32GetUserSessionState
0x1401a55fb  nop     dword ptr [rax+rax+00h]
0x1401a5600  mov     r8b, [rbp+50h+var_D0]
0x1401a5604  lea     rcx, aPreview; "Preview"
0x1401a560b  mov     dl, [rbp+50h+var_CF]
0x1401a560e  test    r13d, r13d
0x1401a5611  mov     [rsp+150h+var_E0], ebx
0x1401a5615  mov     r9, [rax+10E20h]
0x1401a561c  lea     rax, aDrag; "Drag"
0x1401a5623  mov     [rsp+150h+var_E8], edi
0x1401a5627  cmovns  rcx, rax
0x1401a562b  mov     eax, [rbp+50h+var_60.bottom]
0x1401a562e  mov     [rsp+150h+var_F0], eax
0x1401a5632  mov     eax, [rbp+50h+var_60.right]
0x1401a5635  mov     [rsp+150h+var_F8], eax
0x1401a5639  mov     eax, [rbp+50h+var_60.top]
0x1401a563c  mov     [rsp+150h+var_100], eax
0x1401a5640  lea     rax, WPP_b1ea2d8fe1293d1854b7a8cb55068641_Traceguids
0x1401a5647  mov     [rsp+150h+var_108], esi
0x1401a564b  mov     qword ptr [rsp+150h+var_110], rcx
0x1401a5650  mov     rcx, cs:WPP_GLOBAL_Control
0x1401a5657  mov     [rsp+150h+var_118], rax
0x1401a565c  mov     word ptr [rsp+150h+var_120], 10h
0x1401a5663  mov     dword ptr [rsp+150h+var_128], 1
0x1401a566b  mov     rcx, [rcx+18h]
0x1401a566f  mov     byte ptr [rsp+150h+var_130], 5
0x1401a5674  call    WPP_RECORDER_AND_TRACE_SF_sdddddd
0x1401a5679  mov     rbx, [rbp+50h+var_A8]
0x1401a567d  xor     esi, esi
0x1401a567f  mov     rdi, [rbp+50h+var_B0]
0x1401a5683  test    r13d, r13d
0x1401a5686  js      short loc_1401A56EA
0x1401a5688  cmp     r12d, 3
0x1401a568c  jnz     short loc_1401A56EA
0x1401a568e  lea     rdx, [rbp+50h+var_60]; struct tagRECT *
0x1401a5692  mov     rcx, r14; this
0x1401a5695  call    ?xxxDetectNewMonitor@@YAHPEAUMOVESIZEDATA@@PEAUtagRECT@@@Z; xxxDetectNewMonitor(MOVESIZEDATA *,tagRECT *)
0x1401a569a  test    eax, eax
0x1401a569c  jz      short loc_1401A56EA
0x1401a569e  mov     rax, [r14+10h]
0x1401a56a2  movups  xmm0, xmmword ptr [rbp+50h+var_60.left]
0x1401a56a6  mov     rcx, [rax+28h]
0x1401a56aa  mov     eax, [rcx+120h]
0x1401a56b0  and     eax, 0Fh
0x1401a56b3  cmp     eax, 2
0x1401a56b6  movdqu  xmmword ptr [rbx], xmm0
0x1401a56ba  setnz   sil
0x1401a56be  mov     [rbp+50h+var_C4], esi
0x1401a56c1  test    r15, r15
0x1401a56c4  jz      short loc_1401A56CB
0x1401a56c6  movdqu  xmmword ptr [r15], xmm0
0x1401a56cb  cmp     eax, 2
0x1401a56ce  jz      short loc_1401A56E5
0x1401a56d0  call    ?xxxMS_FlushWigglies@@YAXXZ; xxxMS_FlushWigglies(void)
0x1401a56d5  xor     ecx, ecx
0x1401a56d7  call    cs:__imp_GenerateMouseMove
0x1401a56de  nop     dword ptr [rax+rax+00h]
0x1401a56e3  jmp     short loc_1401A56E8
0x1401a56e5  mov     [rbp+50h+var_C4], esi
0x1401a56e8  xor     esi, esi
0x1401a56ea  mov     eax, [r14+0C8h]
0x1401a56f1  test    al, 20h
0x1401a56f3  jz      loc_1401A5B0C
0x1401a56f9  cmp     r12d, 2
0x1401a56fd  jb      loc_1401A5B0C
0x1401a5703  lea     rsi, [r14+10h]
0x1401a5707  mov     rax, [rsi]
0x1401a570a  mov     r13, [rax+10h]
0x1401a570e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1401a5713  xor     edi, edi
0x1401a5715  mov     [rbp+50h+var_70], rax
0x1401a5719  mov     [rbp+50h+var_78], 0FFFFFFFFFFFFFFFFh
0x1401a5721  xorps   xmm0, xmm0
0x1401a5724  mov     [rbp+50h+var_C8], edi
0x1401a5727  mov     dword ptr [rbp+50h+var_B0], edi
0x1401a572a  mov     [rbp+50h+var_CC], edi
0x1401a572d  movups  xmmword ptr [rbp+50h+BugCheckParameter2], xmm0
0x1401a5731  cmp     r13, rax
0x1401a5734  jz      short loc_1401A5742
0x1401a5736  mov     rdx, r13; BugCheckParameter3
0x1401a5739  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x1401a573d  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z; Win32RawLockedW32Thread::ManualLock(_W32THREAD *)
0x1401a5742  lock or dword ptr [r13+208h], 8000h
0x1401a574e  test    r15, r15
0x1401a5751  jz      short loc_1401A575B
0x1401a5753  movups  xmm0, xmmword ptr [r15]
0x1401a5757  movdqu  xmmword ptr [rbx], xmm0
0x1401a575b  mov     r10, [rsi]
0x1401a575e  movups  xmm6, xmmword ptr [rbx]
0x1401a5761  mov     r9, [r10+68h]
0x1401a5765  movaps  xmmword ptr [rbp+50h+var_C0.left], xmm6
0x1401a5769  test    r9, r9
0x1401a576c  jz      short loc_1401A57BA
0x1401a576e  mov     rcx, r10
0x1401a5771  call    _IsTopLevelWindow
0x1401a5776  test    eax, eax
0x1401a5778  jnz     short loc_1401A57BA
0x1401a577a  lea     rdx, [rbp+50h+var_C0]
0x1401a577e  mov     rcx, r9
0x1401a5781  call    _ScreenToClient
0x1401a5786  lea     rdx, [rbp+50h+var_C0.right]
0x1401a578a  mov     rcx, r9
0x1401a578d  call    _ScreenToClient
0x1401a5792  mov     r9, [r9+28h]
0x1401a5796  test    byte ptr [r9+1Ah], 40h
0x1401a579b  jz      short loc_1401A57AD
0x1401a579d  mov     ebx, [rbp+50h+var_C0.left]
0x1401a57a0  mov     r12d, [rbp+50h+var_C0.right]
0x1401a57a4  mov     [rbp+50h+var_C0.left], r12d
0x1401a57a8  mov     [rbp+50h+var_C0.right], ebx
0x1401a57ab  jmp     short loc_1401A57B4
0x1401a57ad  mov     ebx, [rbp+50h+var_C0.right]
0x1401a57b0  mov     r12d, [rbp+50h+var_C0.left]
0x1401a57b4  movaps  xmm6, xmmword ptr [rbp+50h+var_C0.left]
0x1401a57b8  jmp     short loc_1401A57CC
0x1401a57ba  movdqa  xmm0, xmm6
0x1401a57be  movd    r12d, xmm6
0x1401a57c3  psrldq  xmm0, 8
0x1401a57c8  movd    ebx, xmm0
0x1401a57cc  mov     rcx, [r10+28h]
0x1401a57d0  add     rcx, 58h ; 'X'
0x1401a57d4  call    cs:__imp_GreCreateRectRgnIndirect
0x1401a57db  nop     dword ptr [rax+rax+00h]
0x1401a57e0  mov     rcx, [rsi]
0x1401a57e3  mov     rdi, rax
0x1401a57e6  mov     rdx, [rcx+28h]
0x1401a57ea  mov     r8, [rdx+0A8h]
0x1401a57f1  test    r8, r8
0x1401a57f4  jz      short loc_1401A580E
0x1401a57f6  mov     r9d, 1
0x1401a57fc  mov     rdx, rax
0x1401a57ff  mov     rcx, rax
0x1401a5802  call    cs:__imp_GreCombineRgn
0x1401a5809  nop     dword ptr [rax+rax+00h]
0x1401a580e  mov     rdx, [rsi]
0x1401a5811  lea     rcx, [rbp+50h+BugCheckParameter3]
0x1401a5815  call    ??0?$Win32HMThreadLockBase@UtagMENU@@$00$0A@@@QEAA@PEAUtagMENU@@@Z; Win32HMThreadLockBase<tagMENU,1,0>::Win32HMThreadLockBase<tagMENU,1,0>(tagMENU *)
0x1401a581a  mov     rax, [rsi]
0x1401a581d  sub     ebx, r12d
0x1401a5820  mov     [rbp+50h+var_A0], rax
0x1401a5824  mov     rdx, [rax+28h]
0x1401a5828  mov     ecx, [rdx+60h]
0x1401a582b  sub     ecx, [rdx+58h]
0x1401a582e  cmp     ecx, ebx
0x1401a5830  jnz     short loc_1401A585E
0x1401a5832  mov     eax, [rdx+5Ch]
0x1401a5835  movdqa  xmm0, xmm6
0x1401a5839  mov     edx, [rdx+64h]
0x1401a583c  movdqa  xmm1, xmm6
0x1401a5840  sub     edx, eax
0x1401a5842  psrldq  xmm0, 0Ch
0x1401a5847  psrldq  xmm1, 4
0x1401a584c  movd    ecx, xmm0
0x1401a5850  movd    eax, xmm1
0x1401a5854  sub     ecx, eax
0x1401a5856  cmp     edx, ecx
0x1401a5858  jz      loc_1401A58EF
0x1401a585e  mov     rcx, r14; struct MOVESIZEDATA *
0x1401a5861  call    ?DoesQualifyForResizeOptimization@@YAHPEAUMOVESIZEDATA@@@Z; DoesQualifyForResizeOptimization(MOVESIZEDATA *)
0x1401a5866  test    eax, eax
0x1401a5868  jz      loc_1401A58EF
0x1401a586e  mov     rbx, [rbp+50h+var_A0]
0x1401a5872  mov     rcx, rbx; struct tagWND *
0x1401a5875  mov     [rbp+50h+var_C8], 0
0x1401a587c  call    ?DoesRequireResizeLayoutSynchronization@@YAHPEAUtagWND@@@Z; DoesRequireResizeLayoutSynchronization(tagWND *)
0x1401a5881  mov     rbx, [rbx]
0x1401a5884  mov     r12d, eax
0x1401a5887  mov     dword ptr [rbp+50h+var_B0], eax
0x1401a588a  call    cs:__imp_W32GetUserSessionState
0x1401a5891  nop     dword ptr [rax+rax+00h]
0x1401a5896  lea     r9, [rbp+50h+var_CC]
0x1401a589a  mov     r8d, r12d
0x1401a589d  mov     rdx, rbx
0x1401a58a0  mov     rcx, [rax+0DDA8h]
0x1401a58a7  lea     rax, [rbp+50h+var_C8]
0x1401a58ab  mov     [rsp+150h+var_130], rax
0x1401a58b0  mov     rcx, [rcx+28h]
0x1401a58b4  call    GreWindowResizeStarted
0x1401a58b9  mov     r12d, [rbp+50h+var_CC]
0x1401a58bd  test    eax, eax
0x1401a58bf  jz      short loc_1401A58E6
0x1401a58c1  test    r12d, r12d
0x1401a58c4  jz      short loc_1401A58E6
0x1401a58c6  mov     r8d, [rbp+50h+var_C8]
0x1401a58ca  lea     r9, ?ResizeTimerFunc@@YAXPEAUtagWND@@I_K_J@Z; ResizeTimerFunc(tagWND *,uint,unsigned __int64,__int64)
0x1401a58d1  mov     rcx, [rsi]
0x1401a58d4  mov     edx, 0FFF2h
0x1401a58d9  mov     dword ptr [rsp+150h+var_130], 1
0x1401a58e1  call    _SetSystemTimer
0x1401a58e6  mov     [rbp+50h+var_C8], 1
0x1401a58ed  jmp     short loc_1401A58F3
0x1401a58ef  mov     r12d, [rbp+50h+var_CC]
0x1401a58f3  call    Feature_ApplyWindowActionConvergence__private_IsEnabledDeviceUsageNoInline
0x1401a58f8  lea     rdx, [rbp+50h+var_C0]; struct tagRECT
0x1401a58fc  mov     rcx, r14; struct MOVESIZEDATA *
0x1401a58ff  test    eax, eax
0x1401a5901  jz      short loc_1401A590D
0x1401a5903  call    ?xxxMoveSizeSetWindowPos@@YAXPEAUMOVESIZEDATA@@AEBUtagRECT@@@Z; xxxMoveSizeSetWindowPos(MOVESIZEDATA *,tagRECT const &)
0x1401a5908  jmp     loc_1401A59B3
0x1401a590d  movdqa  xmmword ptr [rbp+50h+var_C0.left], xmm6
0x1401a5912  call    ?xxxMoveSizeSetWindowPosOld@@YAXPEAUMOVESIZEDATA@@UtagRECT@@@Z; xxxMoveSizeSetWindowPosOld(MOVESIZEDATA *,tagRECT)
0x1401a5917  test    dword ptr [r14+0C8h], 200000h
0x1401a5922  jz      loc_1401A59B3
0x1401a5928  mov     rax, [rsi]
0x1401a592b  mov     rcx, [rax+28h]
  ... truncated ...
```
