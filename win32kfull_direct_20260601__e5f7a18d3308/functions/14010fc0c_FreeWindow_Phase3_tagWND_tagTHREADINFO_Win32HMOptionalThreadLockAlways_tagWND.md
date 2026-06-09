# FreeWindow_Phase3(tagWND *,tagTHREADINFO *,Win32HMOptionalThreadLockAlways<tagWND> *)

- ea: `0x14010fc0c`
- end: `0x14011060b`
- name: `?FreeWindow_Phase3@@YAXPEAUtagWND@@PEAUtagTHREADINFO@@PEAU?$Win32HMOptionalThreadLockAlways@UtagWND@@@@@Z`
- size: `2559`
- prototype: `__int64 __fastcall(struct tagWND *)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14010f3cc`

## callees

- `0x140005a18`
- `0x14000625c`
- `0x1400080f0`
- `0x14000caf4`
- `0x14001af00`
- `0x14001ea78`
- `0x14002479c`
- `0x1400296e4`
- `0x14002b700`
- `0x140033eb4`
- `0x140096414`
- `0x14009b5e8`
- `0x1400c4a40`
- `0x1400ca844`
- `0x1400d91a0`
- `0x1400d9d00`
- `0x1400dadd4`
- `0x1400e759c`
- `0x1400ee444`
- `0x14010fc0c`
- `0x140111060`
- `0x140124cd0`
- `0x14013e870`
- `0x14013eb50`
- `0x140197978`
- `0x14019be9c`
- `0x1401b59b0`
- `0x1401b9750`
- `0x1401c8af8`
- `0x1401d03b0`
- `0x1401d381c`
- `0x1401da170`
- `0x1401e09d8`
- `0x1401e9f70`
- `0x1401fd010`
- `0x14021feb0`
- `0x1402344a0`
- `0x14026cdec`
- `0x14028d380`
- `0x1402938dc`
- `0x1402998b0`
- `0x1402b6964`
- `0x1402d3240`

## import_xrefs

- `ntoskrnl!RtlFreeHeap` at `0x140110063`
- `ntoskrnl!RtlFreeHeap` at `0x1401100b6`
- `ntoskrnl!RtlFreeHeap` at `0x140110063`
- `ntoskrnl!RtlFreeHeap` at `0x1401100b6`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140110528`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140110528`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x140110548`
- `win32kbase!?DwsUnlinkAllProcesses@tagWND@@QEAAXW4DwsLinkSource@@@Z` at `0x140110213`
- `win32kbase!?DwsUnlinkAllProcesses@tagWND@@QEAAXW4DwsLinkSource@@@Z` at `0x140110213`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x1401104c7`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x1401104c7`
- `win32kbase!HandleFullWindowDestruction` at `0x14010fc45`
- `win32kbase!HandleFullWindowDestruction` at `0x14010fc45`
- `win32kbase!DeleteProperties` at `0x140110345`
- `win32kbase!DeleteProperties` at `0x140110345`
- `win32kbase!GreUnlockSprite` at `0x14010ff2f`
- `win32kbase!GreUnlockSprite` at `0x14010ff2f`
- `win32kbase!GreLockSprite` at `0x14010ff01`
- `win32kbase!GreLockSprite` at `0x14010ff01`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14010fd38`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x14010fd38`
- `win32kbase!_HMPheFromObject` at `0x1401101e0`
- `win32kbase!_HMPheFromObject` at `0x1401101e0`
- `win32kbase!GreUnlockVisRgn` at `0x14010fef5`
- `win32kbase!GreUnlockVisRgn` at `0x14010ff7a`
- `win32kbase!GreUnlockVisRgn` at `0x14010fef5`
- `win32kbase!GreUnlockVisRgn` at `0x14010ff7a`
- `win32kbase!GreLockVisRgn` at `0x14010fecf`
- `win32kbase!GreLockVisRgn` at `0x14010ff3b`
- `win32kbase!GreLockVisRgn` at `0x14010fecf`
- `win32kbase!GreLockVisRgn` at `0x14010ff3b`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x1401101f3`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x1401101f3`
- `win32kbase!IsWindowDesktopComposed` at `0x140110192`
- `win32kbase!IsWindowDesktopComposed` at `0x140110475`
- `win32kbase!IsWindowDesktopComposed` at `0x140110192`
- `win32kbase!IsWindowDesktopComposed` at `0x140110475`
- `win32kbase!HMFreeObject` at `0x1401104d6`
- `win32kbase!HMFreeObject` at `0x1401104d6`
- `win32kbase!HMMarkObjectDestroy` at `0x1401101d1`
- `win32kbase!HMMarkObjectDestroy` at `0x1401102a1`
- `win32kbase!HMMarkObjectDestroy` at `0x1401101d1`
- `win32kbase!HMMarkObjectDestroy` at `0x1401102a1`
- `win32kbase!HMAssignmentLock` at `0x140110118`
- `win32kbase!HMAssignmentLock` at `0x140110118`
- `win32kbase!Win32FreePool` at `0x1401102d4`
- `win32kbase!Win32FreePool` at `0x140110302`
- `win32kbase!Win32FreePool` at `0x140110326`
- `win32kbase!Win32FreePool` at `0x140110358`
- `win32kbase!Win32FreePool` at `0x14011044d`
- `win32kbase!Win32FreePool` at `0x1401102d4`
- `win32kbase!Win32FreePool` at `0x140110302`
- `win32kbase!Win32FreePool` at `0x140110326`
- `win32kbase!Win32FreePool` at `0x140110358`
- `win32kbase!Win32FreePool` at `0x14011044d`
- `win32kbase!HMAssignmentUnlock` at `0x14010fc79`
- `win32kbase!HMAssignmentUnlock` at `0x14010fcad`
- `win32kbase!HMAssignmentUnlock` at `0x140110132`
- `win32kbase!HMAssignmentUnlock` at `0x14011014a`
- `win32kbase!HMAssignmentUnlock` at `0x140110162`
- `win32kbase!HMAssignmentUnlock` at `0x140110183`
- `win32kbase!HMAssignmentUnlock` at `0x140110237`
- `win32kbase!HMAssignmentUnlock` at `0x140110250`
- `win32kbase!HMAssignmentUnlock` at `0x140110265`
- `win32kbase!HMAssignmentUnlock` at `0x1401104ab`
- `win32kbase!HMAssignmentUnlock` at `0x14010fc79`
- `win32kbase!HMAssignmentUnlock` at `0x14010fcad`
- `win32kbase!HMAssignmentUnlock` at `0x140110132`
- `win32kbase!HMAssignmentUnlock` at `0x14011014a`
- `win32kbase!HMAssignmentUnlock` at `0x140110162`
- `win32kbase!HMAssignmentUnlock` at `0x140110183`
- `win32kbase!HMAssignmentUnlock` at `0x140110237`
- `win32kbase!HMAssignmentUnlock` at `0x140110250`
- `win32kbase!HMAssignmentUnlock` at `0x140110265`
- `win32kbase!HMAssignmentUnlock` at `0x1401104ab`
- `win32kbase!ReferenceDwmApiPort` at `0x1401101a5`
- `win32kbase!ReferenceDwmApiPort` at `0x140110488`
- `win32kbase!ReferenceDwmApiPort` at `0x1401101a5`
- `win32kbase!ReferenceDwmApiPort` at `0x140110488`
- `WIN32K!W32GetUserSessionState` at `0x14010fc51`
- `WIN32K!W32GetUserSessionState` at `0x14010fc66`
- `WIN32K!W32GetUserSessionState` at `0x14010fc85`
- `WIN32K!W32GetUserSessionState` at `0x14010fc9a`
- `WIN32K!W32GetUserSessionState` at `0x14010fcb9`
- `WIN32K!W32GetUserSessionState` at `0x14010fce7`
- `WIN32K!W32GetUserSessionState` at `0x14010fe94`
- `WIN32K!W32GetUserSessionState` at `0x14010fea9`
- `WIN32K!W32GetUserSessionState` at `0x14010fee3`
- `WIN32K!W32GetUserSessionState` at `0x14010ff10`
- `WIN32K!W32GetUserSessionState` at `0x140110002`
- `WIN32K!W32GetUserSessionState` at `0x1401103dd`
- `WIN32K!W32GetUserSessionState` at `0x1401103f4`
- `WIN32K!W32GetUserSessionState` at `0x140110408`
- `WIN32K!W32GetUserSessionState` at `0x140110552`
- `WIN32K!W32GetUserSessionState` at `0x14010fc51`
- `WIN32K!W32GetUserSessionState` at `0x14010fc66`
- `WIN32K!W32GetUserSessionState` at `0x14010fc85`
- `WIN32K!W32GetUserSessionState` at `0x14010fc9a`
- `WIN32K!W32GetUserSessionState` at `0x14010fcb9`
- `WIN32K!W32GetUserSessionState` at `0x14010fce7`
- `WIN32K!W32GetUserSessionState` at `0x14010fe94`
- `WIN32K!W32GetUserSessionState` at `0x14010fea9`
- `WIN32K!W32GetUserSessionState` at `0x14010fee3`
- `WIN32K!W32GetUserSessionState` at `0x14010ff10`
- `WIN32K!W32GetUserSessionState` at `0x140110002`
- `WIN32K!W32GetUserSessionState` at `0x1401103dd`
- `WIN32K!W32GetUserSessionState` at `0x1401103f4`
- `WIN32K!W32GetUserSessionState` at `0x140110408`
- `WIN32K!W32GetUserSessionState` at `0x140110552`

## pseudocode

```c
void __fastcall FreeWindow_Phase3(struct _LIST_ENTRY *a1, __int64 a2, ULONG_PTR a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 UserSessionState; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  struct _LIST_ENTRY *Blink; // rax
  char v18; // r14
  __int64 v19; // rdx
  __int64 QMsg; // rax
  struct _HEAD *v21; // rbx
  struct _HEAD *Flink; // rbx
  struct _LIST_ENTRY **p_Blink; // rsi
  struct _LIST_ENTRY *v24; // rcx
  struct _LIST_ENTRY *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  struct EWNDOBJ *v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rdx
  bool v37; // r15
  struct _LIST_ENTRY *v38; // rbx
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  struct _LIST_ENTRY *v42; // r8
  struct tagWND *v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  void *v50; // rax
  __int64 v51; // rax
  __int64 ProcessWindowStation; // rax
  __int64 v53; // rbx
  __int64 v54; // rdx
  struct _LIST_ENTRY *v55; // rax
  struct _LIST_ENTRY *v56; // rcx
  struct _LIST_ENTRY *v57; // rax
  struct _LIST_ENTRY *v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // r14
  __int64 v64; // rbx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rdx
  __int64 v69; // rcx
  __int64 v70; // rax
  struct _LIST_ENTRY *v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // r8
  void *v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rsi
  __int64 CurrentProcessWin32Process; // rax
  __int64 v79; // rax
  _QWORD *ClassPtr; // rax
  __int64 v81; // rcx
  __int128 v82; // [rsp+50h] [rbp-29h] BYREF
  char v83[8]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v84; // [rsp+68h] [rbp-11h]
  _BYTE v85[16]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v86; // [rsp+80h] [rbp+7h]

  v83[0] = 0;
  v84 = 0;
  AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v83);
  HandleFullWindowDestruction(a1);
  if ( a1 == *(struct _LIST_ENTRY **)(W32GetUserSessionState(v7, v6) + 36088) )
  {
    UserSessionState = W32GetUserSessionState(v9, v8);
    HMAssignmentUnlock(UserSessionState + 36088);
  }
  if ( a1 == *(struct _LIST_ENTRY **)(W32GetUserSessionState(v9, v8) + 36096) )
  {
    v13 = W32GetUserSessionState(v12, v11);
    HMAssignmentUnlock(v13 + 36096);
  }
  v14 = W32GetUserSessionState(v12, v11);
  MagpDestroyLensContext(v14 + 65808, a2, a1);
  DestroyWindowsTimers(a1);
  DestroyWindowsHotKeys(a1);
  if ( !*(_DWORD *)(W32GetUserSessionState(v16, v15) + 69068) )
    ClearSendMessages(a1);
  CleanupWindowRedirection(a1);
  Blink = a1[2].Blink;
  v18 = 1;
  if ( Blink[8].Blink || (BYTE1(Blink[1].Flink) & 0x10) != 0 )
  {
    DecPaintCount(a1);
    DeleteMaybeSpecialRgn(a1[2].Blink[8].Blink);
    a1[2].Blink[8].Blink = 0;
    SetOrClrWF(0, a1, 272, 1);
  }
  if ( (BYTE1(a1[2].Blink[1].Flink) & 0xA) != 0 )
  {
    SetOrClrWF(0, a1, 264, 1);
    SetOrClrWF(0, a1, 258, 1);
  }
  v19 = a2 + 840;
  if ( *(_QWORD *)(a2 + 840) )
  {
    QMsg = FindQMsg(a2, v19, (_DWORD)a1, 18, 18, 1);
    if ( QMsg )
      PostQuitMessage(*(unsigned int *)(QMsg + 32));
  }
  if ( (HIBYTE(a1[2].Blink[1].Blink) & 0xC0) == 0x40 && a1[10].Blink )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 5134);
  if ( (HIBYTE(a1[2].Blink[1].Blink) & 0xC0) != 0x40 )
  {
    v21 = (struct _HEAD *)a1[10].Blink;
    if ( v21 )
    {
      if ( UnlockWndMenuWorker((struct tagWND *)a1, 0) )
        DestroyMenu(v21);
    }
  }
  Flink = (struct _HEAD *)a1[10].Flink;
  p_Blink = &a1[1].Blink;
  if ( Flink )
  {
    if ( Flink == (struct _HEAD *)(*p_Blink)[4].Flink )
    {
      UnlockWndMenuWorker((struct tagWND *)a1, 1);
    }
    else if ( UnlockWndMenuWorker((struct tagWND *)a1, 1) )
    {
      DestroyMenu(Flink);
    }
  }
  v24 = *p_Blink;
  if ( *p_Blink )
  {
    v25 = v24[3].Blink;
    if ( v25 && a1 == v25[5].Flink )
    {
      v24 = v24[3].Blink;
LABEL_33:
      UnlockNotifyWindow((struct tagMENU *)v24);
      goto LABEL_34;
    }
    v24 = v24[4].Flink;
    if ( v24 && a1 == v24[5].Flink )
      goto LABEL_33;
  }
LABEL_34:
  if ( *(_DWORD *)(W32GetUserSessionState(v24, v19) + 43048) )
  {
    v28 = W32GetUserSessionState(v27, v26);
    v29 = (struct EWNDOBJ *)InternalRemoveProp(a1, *(unsigned __int16 *)(v28 + 41182), 1);
    if ( v29 )
    {
      GreLockVisRgn();
      GreDeleteWnd(v29);
      v32 = W32GetUserSessionState(v31, v30);
      --*(_DWORD *)(v32 + 43048);
      GreUnlockVisRgn();
    }
  }
  GreLockSprite();
  v35 = W32GetUserSessionState(v34, v33);
  GreDeleteSpriteOverlapPresent(*(HDEV *)(*(_QWORD *)(v35 + 56744) + 40LL));
  GreUnlockSprite();
  GreLockVisRgn();
  _ClearPwndDceList(a1 + 20, 0x68u);
  _ClearPwndDceList(a1 + 21, 0x78u);
  _ClearPwndDceList(a1 + 22, 0x88u);
  GreUnlockVisRgn();
  if ( (WORD1(a1[2].Blink[2].Blink) & 0x2FFF) != 0x29D )
    tagWND::ClearClipRgnOrMaxClip((tagWND *)a1);
  if ( !(unsigned int)Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline() && a1[9].Blink )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x100) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v18 = 0;
    }
    v37 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v18 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v38 = a1->Flink;
      v39 = W32GetUserSessionState(WPP_GLOBAL_Control, v36);
      LOBYTE(v40) = v37;
      LOBYTE(v41) = v18;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v41,
        v40,
        *(_QWORD *)(v39 + 69152),
        4,
        9,
        11,
        (__int64)WPP_486a5556d82b3fd2406559f49d2a7b57_Traceguids,
        (char)v38);
    }
    RtlFreeHeap((*p_Blink)[8].Blink, 0, a1[9].Blink);
    a1[2].Blink[9].Flink = 0;
    a1[9].Blink = 0;
  }
  if ( (HIDWORD(a1[23].Blink) & 0x10000) != 0 )
    NotifyOverlayWindow((struct tagWND *)a1);
  v42 = a1[11].Blink;
  if ( v42 )
  {
    RtlFreeHeap((*p_Blink)[8].Blink, 0, v42);
    a1[2].Blink[12].Flink = 0;
    a1[11].Blink = 0;
    LODWORD(a1[2].Blink[11].Blink) = 0;
  }
  ResetWindowTransform(a1);
  if ( !*p_Blink || (v43 = (struct tagWND *)(*p_Blink)->Blink[1].Blink, a1 == (struct _LIST_ENTRY *)v43) )
  {
    a1[2].Blink[3].Flink = 0;
    HMAssignmentUnlock(&a1[6].Blink);
  }
  else
  {
    v82 = *(_OWORD *)LockPointer(v85, &a1[6].Blink, v43);
    HMAssignmentLock(&v82, 1);
  }
  a1[2].Blink[3].Blink = 0;
  HMAssignmentUnlock(&a1[7]);
  a1[2].Blink[4].Flink = 0;
  HMAssignmentUnlock(&a1[7].Blink);
  a1[2].Blink[11].Flink = 0;
  HMAssignmentUnlock(&a1[12].Blink);
  if ( (unsigned int)IsWindowDesktopComposed(a1, v44, v45, v46) )
  {
    v50 = (void *)ReferenceDwmApiPort(v48, v47, v49);
    DwmAsyncOwnerChange(v50);
  }
  DereferenceClass(*(_QWORD *)(a2 + 456), a1);
  HMMarkObjectDestroy(a1);
  v51 = _HMPheFromObject(a1);
  *(_BYTE *)(v51 + 25) |= 2u;
  tagWND::ComputeDominantState((tagWND *)a1);
  if ( (HIDWORD(a1[23].Blink) & 0x8000000) != 0 )
    tagWND::DwsUnlinkAllProcesses(a1, 3);
  ProcessWindowStation = GetProcessWindowStation(0);
  v53 = ProcessWindowStation;
  if ( ProcessWindowStation )
  {
    if ( *(struct _LIST_ENTRY **)(ProcessWindowStation + 64) == a1 )
    {
      HMAssignmentUnlock(ProcessWindowStation + 64);
      *(_QWORD *)(v53 + 48) = 0;
    }
    if ( *(struct _LIST_ENTRY **)(v53 + 80) == a1 )
      HMAssignmentUnlock(v53 + 80);
    if ( *(struct _LIST_ENTRY **)(v53 + 72) == a1 )
      HMAssignmentUnlock(v53 + 72);
  }
  if ( (HIDWORD(a1[23].Blink) & 0x800000) != 0 )
    _RemoveClipboardFormatListener((struct tagWND *)a1);
  if ( Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>(a3) )
  {
    FreeClientOnWindowDestruction(a1);
    if ( (unsigned int)HMMarkObjectDestroy(a1) )
    {
      v55 = a1[18].Flink;
      if ( v55 )
      {
        --LODWORD(v55->Flink);
        v56 = a1[18].Flink;
        if ( !LODWORD(v56->Flink) )
          Win32FreePool(v56);
        a1[18].Flink = 0;
      }
      v57 = a1[18].Blink;
      if ( v57 )
      {
        --LODWORD(v57->Flink);
        v58 = a1[18].Blink;
        if ( !LODWORD(v58->Flink) )
          Win32FreePool(v58);
        a1[18].Blink = 0;
      }
      UpdateWindowMonitorAndDpiInfoHelper((struct tagWND *)a1, 0);
      Win32FreePool(a1[23].Flink);
      a1[23].Flink = 0;
      if ( a1[9].Flink )
      {
        DeleteProperties(a1);
        Win32FreePool(a1[9].Flink);
        a1[9].Flink = 0;
      }
      if ( (WORD1(a1[2].Blink[2].Blink) & 0x2FFF) == 0x2A0 )
        MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 5385);
      v59 = safe_cast_fnid_to_PMENUWND(a1);
      v63 = v59;
      if ( v59 )
      {
        v60 = *(_QWORD *)(v59 + 16);
        if ( v60 )
        {
          SmartObjStackRefBase<tagPOPUPMENU>::Init(&v82, v60);
          if ( (**(_DWORD **)v82 & 0x20000000) != 0 )
          {
            **(_DWORD **)v82 &= ~0x40000000u;
          }
          else
          {
            v64 = *(_QWORD *)v82;
            if ( v64 == W32GetUserSessionState(v82, *(_QWORD *)v82) + 65560 )
            {
              v67 = W32GetUserSessionState(v66, v65);
              *(_DWORD *)(v67 + 66784) &= ~0x800000u;
              v70 = W32GetUserSessionState(v69, v68);
              NullifyLookasideRef(*(_QWORD *)(v70 + 65648));
            }
            else
            {
              FreeIsolatedTypeAndClearStackReferences<tagPOPUPMENU>(&v82);
              *(_QWORD *)(v63 + 16) = 0;
            }
          }
          SmartObjStackRefBase<tagPOPUPMENU>::~SmartObjStackRefBase<tagPOPUPMENU>(&v82);
        }
      }
      v71 = a1[17].Blink;
      if ( v71 )
      {
        Win32FreePool(v71);
        a1[17].Blink = 0;
      }
      LODWORD(a1[2].Blink[15].Blink) = 0;
      --*(_DWORD *)(a2 + 932);
      if ( (unsigned int)IsWindowDesktopComposed(a1, v60, v61, v62) )
      {
        v75 = (void *)ReferenceDwmApiPort(v73, v72, v74);
        DwmAsyncChildDestroy(v75);
      }
      a1[2].Blink[3].Flink = 0;
      HMAssignmentUnlock(&a1[6].Blink);
      Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v85, *p_Blink);
      tagObjLock::LockUnInitializeThreadCreator((tagObjLock *)&a1[3].Blink);
      HMFreeObject(a1);
      if ( v86 != -1 )
      {
        PopAndFreeW32ThreadLock(v85);
        v86 = -1;
      }
    }
    else
    {
      a1[2].Blink[7].Blink = 0;
      if ( *p_Blink )
      {
        v76 = (__int64)(*p_Blink)[2].Blink[1].Blink;
        v77 = *(_QWORD *)(*(_QWORD *)(v76 + 16) + 456LL);
      }
      else
      {
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
        v77 = CurrentProcessWin32Process;
        if ( CurrentProcessWin32Process )
        {
          v76 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
          v77 = v76 & CurrentProcessWin32Process;
        }
      }
      v79 = W32GetUserSessionState(v76, v54);
      ClassPtr = (_QWORD *)GetClassPtr(*(unsigned __int16 *)(*(_QWORD *)(v79 + 19704) + 910LL), v77, hModuleWin);
      tagWND::SharedMixedObjectPointerFieldpcls<tagCLS>::operator=(&a1[8].Blink, *ClassPtr);
      ++*(_DWORD *)(*(_QWORD *)v81 + 72LL);
      SetOrClrWF(1, a1, 516, 1);
      SetOrClrWF(0, a1, 544, 1);
      SetOrClrWF(0, a1, 4032, 1);
      SetOrClrWF(1, a1, 3840, 1);
      a1[2].Blink[9].Blink = 0;
      a1[10].Blink = 0;
    }
  }
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v83);
}

```

## disassembly

```asm
0x14010fc0c  push    rbp
0x14010fc0e  push    rbx
0x14010fc0f  push    rsi
0x14010fc10  push    rdi
0x14010fc11  push    r12
0x14010fc13  push    r13
0x14010fc15  push    r14
0x14010fc17  push    r15
0x14010fc19  lea     rbp, [rsp-1Fh]
0x14010fc1e  sub     rsp, 98h
0x14010fc25  mov     rdi, rcx
0x14010fc28  xor     r15d, r15d
0x14010fc2b  lea     rcx, [rbp+57h+var_70]; this
0x14010fc2f  mov     [rbp+57h+var_70], r15b
0x14010fc33  mov     [rbp+57h+var_68], r15
0x14010fc37  mov     r12, r8
0x14010fc3a  mov     r13, rdx
0x14010fc3d  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Arm(void)
0x14010fc42  mov     rcx, rdi
0x14010fc45  call    cs:__imp_HandleFullWindowDestruction
0x14010fc4c  nop     dword ptr [rax+rax+00h]
0x14010fc51  call    cs:__imp_W32GetUserSessionState
0x14010fc58  nop     dword ptr [rax+rax+00h]
0x14010fc5d  cmp     rdi, [rax+8CF8h]
0x14010fc64  jnz     short loc_14010FC85
0x14010fc66  call    cs:__imp_W32GetUserSessionState
0x14010fc6d  nop     dword ptr [rax+rax+00h]
0x14010fc72  lea     rcx, [rax+8CF8h]
0x14010fc79  call    cs:__imp_HMAssignmentUnlock
0x14010fc80  nop     dword ptr [rax+rax+00h]
0x14010fc85  call    cs:__imp_W32GetUserSessionState
0x14010fc8c  nop     dword ptr [rax+rax+00h]
0x14010fc91  cmp     rdi, [rax+8D00h]
0x14010fc98  jnz     short loc_14010FCB9
0x14010fc9a  call    cs:__imp_W32GetUserSessionState
0x14010fca1  nop     dword ptr [rax+rax+00h]
0x14010fca6  lea     rcx, [rax+8D00h]
0x14010fcad  call    cs:__imp_HMAssignmentUnlock
0x14010fcb4  nop     dword ptr [rax+rax+00h]
0x14010fcb9  call    cs:__imp_W32GetUserSessionState
0x14010fcc0  nop     dword ptr [rax+rax+00h]
0x14010fcc5  mov     r8, rdi
0x14010fcc8  mov     rdx, r13
0x14010fccb  lea     rcx, [rax+10110h]
0x14010fcd2  call    MagpDestroyLensContext
0x14010fcd7  mov     rcx, rdi
0x14010fcda  call    DestroyWindowsTimers
0x14010fcdf  mov     rcx, rdi
0x14010fce2  call    DestroyWindowsHotKeys
0x14010fce7  call    cs:__imp_W32GetUserSessionState
0x14010fcee  nop     dword ptr [rax+rax+00h]
0x14010fcf3  cmp     [rax+10DCCh], r15d
0x14010fcfa  jnz     short loc_14010FD04
0x14010fcfc  mov     rcx, rdi
0x14010fcff  call    ClearSendMessages
0x14010fd04  mov     rcx, rdi
0x14010fd07  call    CleanupWindowRedirection
0x14010fd0c  mov     rax, [rdi+28h]
0x14010fd10  mov     r14d, 1
0x14010fd16  cmp     [rax+88h], r15
0x14010fd1d  jnz     short loc_14010FD25
0x14010fd1f  test    byte ptr [rax+11h], 10h
0x14010fd23  jz      short loc_14010FD62
0x14010fd25  mov     rcx, rdi
0x14010fd28  call    DecPaintCount
0x14010fd2d  mov     rcx, [rdi+28h]
0x14010fd31  mov     rcx, [rcx+88h]
0x14010fd38  call    cs:__imp_DeleteMaybeSpecialRgn
0x14010fd3f  nop     dword ptr [rax+rax+00h]
0x14010fd44  mov     rax, [rdi+28h]
0x14010fd48  mov     r8d, 110h
0x14010fd4e  mov     r9d, r14d
0x14010fd51  mov     rdx, rdi
0x14010fd54  xor     ecx, ecx
0x14010fd56  mov     [rax+88h], r15
0x14010fd5d  call    SetOrClrWF
0x14010fd62  mov     rax, [rdi+28h]
0x14010fd66  test    byte ptr [rax+11h], 0Ah
0x14010fd6a  jz      short loc_14010FD92
0x14010fd6c  mov     r8d, 108h
0x14010fd72  mov     r9d, r14d
0x14010fd75  mov     rdx, rdi
0x14010fd78  xor     ecx, ecx
0x14010fd7a  call    SetOrClrWF
0x14010fd7f  mov     r8d, 102h
0x14010fd85  mov     r9d, r14d
0x14010fd88  mov     rdx, rdi
0x14010fd8b  xor     ecx, ecx
0x14010fd8d  call    SetOrClrWF
0x14010fd92  lea     rdx, [r13+348h]
0x14010fd99  cmp     [rdx], r15
0x14010fd9c  jz      short loc_14010FDC6
0x14010fd9e  mov     r9d, 12h
0x14010fda4  mov     [rsp+0D0h+var_A8], r14d
0x14010fda9  mov     r8, rdi
0x14010fdac  mov     [rsp+0D0h+var_B0], r9d
0x14010fdb1  mov     rcx, r13
0x14010fdb4  call    FindQMsg
0x14010fdb9  test    rax, rax
0x14010fdbc  jz      short loc_14010FDC6
0x14010fdbe  mov     ecx, [rax+20h]
0x14010fdc1  call    _PostQuitMessage
0x14010fdc6  mov     rax, [rdi+28h]
0x14010fdca  mov     cl, [rax+1Fh]
0x14010fdcd  and     cl, 0C0h
0x14010fdd0  cmp     cl, 40h ; '@'
0x14010fdd3  jnz     short loc_14010FDFA
0x14010fdd5  cmp     [rdi+0A8h], r15
0x14010fddc  jz      short loc_14010FDFA
0x14010fdde  mov     [rbp+57h+arg_0], 20000h
0x14010fde5  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14010fdec  mov     edx, [rbp+57h+arg_0]
0x14010fdef  mov     r8d, 140Eh
0x14010fdf5  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14010fdfa  mov     rax, [rdi+28h]
0x14010fdfe  mov     cl, [rax+1Fh]
0x14010fe01  and     cl, 0C0h
0x14010fe04  cmp     cl, 40h ; '@'
0x14010fe07  jz      short loc_14010FE2C
0x14010fe09  mov     rbx, [rdi+0A8h]
0x14010fe10  test    rbx, rbx
0x14010fe13  jz      short loc_14010FE2C
0x14010fe15  xor     edx, edx; bool
0x14010fe17  mov     rcx, rdi; struct tagWND *
0x14010fe1a  call    ?UnlockWndMenuWorker@@YAPEAXPEAUtagWND@@_N@Z; UnlockWndMenuWorker(tagWND *,bool)
0x14010fe1f  test    rax, rax
0x14010fe22  jz      short loc_14010FE2C
0x14010fe24  mov     rcx, rbx; struct _HEAD *
0x14010fe27  call    _DestroyMenu
0x14010fe2c  mov     rbx, [rdi+0A0h]
0x14010fe33  lea     rsi, [rdi+18h]
0x14010fe37  test    rbx, rbx
0x14010fe3a  jz      short loc_14010FE64
0x14010fe3c  mov     rax, [rsi]
0x14010fe3f  mov     dl, r14b; bool
0x14010fe42  mov     rcx, rdi; struct tagWND *
0x14010fe45  cmp     rbx, [rax+40h]
0x14010fe49  jz      short loc_14010FE5F
0x14010fe4b  call    ?UnlockWndMenuWorker@@YAPEAXPEAUtagWND@@_N@Z; UnlockWndMenuWorker(tagWND *,bool)
0x14010fe50  test    rax, rax
0x14010fe53  jz      short loc_14010FE64
0x14010fe55  mov     rcx, rbx; struct _HEAD *
0x14010fe58  call    _DestroyMenu
0x14010fe5d  jmp     short loc_14010FE64
0x14010fe5f  call    ?UnlockWndMenuWorker@@YAPEAXPEAUtagWND@@_N@Z; UnlockWndMenuWorker(tagWND *,bool)
0x14010fe64  mov     rcx, [rsi]
0x14010fe67  test    rcx, rcx
0x14010fe6a  jz      short loc_14010FE94
0x14010fe6c  mov     rax, [rcx+38h]
0x14010fe70  test    rax, rax
0x14010fe73  jz      short loc_14010FE80
0x14010fe75  cmp     rdi, [rax+50h]
0x14010fe79  jnz     short loc_14010FE80
0x14010fe7b  mov     rcx, rax
0x14010fe7e  jmp     short loc_14010FE8F
0x14010fe80  mov     rcx, [rcx+40h]; struct tagMENU *
0x14010fe84  test    rcx, rcx
0x14010fe87  jz      short loc_14010FE94
0x14010fe89  cmp     rdi, [rcx+50h]
0x14010fe8d  jnz     short loc_14010FE94
0x14010fe8f  call    ?UnlockNotifyWindow@@YAXPEAUtagMENU@@@Z; UnlockNotifyWindow(tagMENU *)
0x14010fe94  call    cs:__imp_W32GetUserSessionState
0x14010fe9b  nop     dword ptr [rax+rax+00h]
0x14010fea0  cmp     [rax+0A828h], r15d
0x14010fea7  jz      short loc_14010FF01
0x14010fea9  call    cs:__imp_W32GetUserSessionState
0x14010feb0  nop     dword ptr [rax+rax+00h]
0x14010feb5  mov     r8d, r14d
0x14010feb8  mov     rcx, rdi
0x14010febb  movzx   edx, word ptr [rax+0A0DEh]
0x14010fec2  call    InternalRemoveProp
0x14010fec7  mov     rbx, rax
0x14010feca  test    rax, rax
0x14010fecd  jz      short loc_14010FF01
0x14010fecf  call    cs:__imp_GreLockVisRgn
0x14010fed6  nop     dword ptr [rax+rax+00h]
0x14010fedb  mov     rcx, rbx; struct EWNDOBJ *
0x14010fede  call    GreDeleteWnd
0x14010fee3  call    cs:__imp_W32GetUserSessionState
0x14010feea  nop     dword ptr [rax+rax+00h]
0x14010feef  dec     dword ptr [rax+0A828h]
0x14010fef5  call    cs:__imp_GreUnlockVisRgn
0x14010fefc  nop     dword ptr [rax+rax+00h]
0x14010ff01  call    cs:__imp_GreLockSprite
0x14010ff08  nop     dword ptr [rax+rax+00h]
0x14010ff0d  mov     rbx, [rdi]
0x14010ff10  call    cs:__imp_W32GetUserSessionState
0x14010ff17  nop     dword ptr [rax+rax+00h]
0x14010ff1c  mov     rdx, rbx
0x14010ff1f  mov     rcx, [rax+0DDA8h]
0x14010ff26  mov     rcx, [rcx+28h]; HDEV
0x14010ff2a  call    GreDeleteSpriteOverlapPresent
0x14010ff2f  call    cs:__imp_GreUnlockSprite
0x14010ff36  nop     dword ptr [rax+rax+00h]
0x14010ff3b  call    cs:__imp_GreLockVisRgn
0x14010ff42  nop     dword ptr [rax+rax+00h]
0x14010ff47  lea     rcx, [rdi+140h]; struct _LIST_ENTRY *
0x14010ff4e  mov     edx, 68h ; 'h'; unsigned __int64
0x14010ff53  call    ?_ClearPwndDceList@@YAXPEAU_LIST_ENTRY@@_K@Z; _ClearPwndDceList(_LIST_ENTRY *,unsigned __int64)
0x14010ff58  lea     rcx, [rdi+150h]; struct _LIST_ENTRY *
0x14010ff5f  mov     edx, 78h ; 'x'; unsigned __int64
0x14010ff64  call    ?_ClearPwndDceList@@YAXPEAU_LIST_ENTRY@@_K@Z; _ClearPwndDceList(_LIST_ENTRY *,unsigned __int64)
0x14010ff69  lea     rcx, [rdi+160h]; struct _LIST_ENTRY *
0x14010ff70  mov     edx, 88h; unsigned __int64
0x14010ff75  call    ?_ClearPwndDceList@@YAXPEAU_LIST_ENTRY@@_K@Z; _ClearPwndDceList(_LIST_ENTRY *,unsigned __int64)
0x14010ff7a  call    cs:__imp_GreUnlockVisRgn
0x14010ff81  nop     dword ptr [rax+rax+00h]
0x14010ff86  mov     rax, [rdi+28h]
0x14010ff8a  movzx   ecx, word ptr [rax+2Ah]
0x14010ff8e  and     ecx, 0FFFF2FFFh
0x14010ff94  cmp     ecx, 29Dh
0x14010ff9a  jz      short loc_14010FFA4
0x14010ff9c  mov     rcx, rdi; this
0x14010ff9f  call    ?ClearClipRgnOrMaxClip@tagWND@@QEAAXXZ; tagWND::ClearClipRgnOrMaxClip(void)
0x14010ffa4  call    Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline
0x14010ffa9  test    eax, eax
0x14010ffab  jnz     loc_140110088
0x14010ffb1  cmp     [rdi+98h], r15
0x14010ffb8  jz      loc_140110088
0x14010ffbe  mov     rcx, cs:WPP_GLOBAL_Control
0x14010ffc5  lea     rax, WPP_GLOBAL_Control
0x14010ffcc  cmp     rcx, rax
0x14010ffcf  jz      short loc_14010FFE0
0x14010ffd1  test    dword ptr [rcx+2Ch], 100h
0x14010ffd8  jz      short loc_14010FFE0
0x14010ffda  cmp     byte ptr [rcx+29h], 4
0x14010ffde  jnb     short loc_14010FFE3
0x14010ffe0  mov     r14b, r15b
0x14010ffe3  lea     rax, WPP_RECORDER_INITIALIZED
0x14010ffea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14010fff1  setnz   r15b
0x14010fff5  test    r14b, r14b
0x14010fff8  jnz     short loc_14010FFFF
0x14010fffa  test    r15b, r15b
0x14010fffd  jz      short loc_140110050
0x14010ffff  mov     rbx, [rdi]
0x140110002  call    cs:__imp_W32GetUserSessionState
0x140110009  nop     dword ptr [rax+rax+00h]
0x14011000e  mov     rcx, cs:WPP_GLOBAL_Control
0x140110015  mov     r8b, r15b
0x140110018  mov     [rsp+0D0h+var_90], rbx
0x14011001d  mov     dl, r14b
0x140110020  mov     r9, [rax+10E20h]
0x140110027  lea     rax, WPP_486a5556d82b3fd2406559f49d2a7b57_Traceguids
0x14011002e  mov     rcx, [rcx+18h]
0x140110032  mov     [rsp+0D0h+var_98], rax
0x140110037  mov     [rsp+0D0h+var_A0], 0Bh
0x14011003e  mov     [rsp+0D0h+var_A8], 9
0x140110046  mov     byte ptr [rsp+0D0h+var_B0], 4
0x14011004b  call    WPP_RECORDER_AND_TRACE_SF_q
0x140110050  mov     rcx, [rsi]
0x140110053  xor     edx, edx; Flags
0x140110055  mov     r8, [rdi+98h]; BaseAddress
0x14011005c  mov     rcx, [rcx+88h]; HeapHandle
0x140110063  call    cs:__imp_RtlFreeHeap
0x14011006a  nop     dword ptr [rax+rax+00h]
0x14011006f  mov     rax, [rdi+28h]
0x140110073  xor     r15d, r15d
0x140110076  mov     [rax+90h], r15
0x14011007d  lea     r14d, [r15+1]
0x140110081  mov     [rdi+98h], r15
0x140110088  test    dword ptr [rdi+17Ch], 10000h
0x140110092  jz      short loc_14011009E
0x140110094  xor     edx, edx
0x140110096  mov     rcx, rdi; struct tagWND *
0x140110099  call    _NotifyOverlayWindow
0x14011009e  mov     r8, [rdi+0B8h]; BaseAddress
0x1401100a5  test    r8, r8
0x1401100a8  jz      short loc_1401100DF
0x1401100aa  mov     rcx, [rsi]
0x1401100ad  xor     edx, edx; Flags
0x1401100af  mov     rcx, [rcx+88h]; HeapHandle
0x1401100b6  call    cs:__imp_RtlFreeHeap
0x1401100bd  nop     dword ptr [rax+rax+00h]
0x1401100c2  mov     rax, [rdi+28h]
0x1401100c6  mov     [rax+0C0h], r15
0x1401100cd  mov     [rdi+0B8h], r15
0x1401100d4  mov     rax, [rdi+28h]
0x1401100d8  mov     [rax+0B8h], r15d
0x1401100df  mov     rcx, rdi
0x1401100e2  call    ResetWindowTransform
0x1401100e7  mov     rax, [rsi]
0x1401100ea  test    rax, rax
0x1401100ed  jz      short loc_140110126
0x1401100ef  mov     rax, [rax+8]
0x1401100f3  mov     r8, [rax+18h]
0x1401100f7  cmp     rdi, r8
0x1401100fa  jz      short loc_140110126
0x1401100fc  lea     rdx, [rdi+68h]
0x140110100  lea     rcx, [rbp+57h+var_60]
0x140110104  call    ?LockPointer@@YA?AU_LOCKASSIGNPAIR@@PEAV?$SharedUserObjPointerFieldspwndParent@UtagWND@@@tagWND@@PEAU_HEAD@@@Z; LockPointer(tagWND::SharedUserObjPointerFieldspwndParent<tagWND> *,_HEAD *)
0x140110109  mov     edx, r14d
0x14011010c  lea     rcx, [rbp+57h+var_80]
0x140110110  movups  xmm0, xmmword ptr [rax]
0x140110113  movdqu  [rbp+57h+var_80], xmm0
0x140110118  call    cs:__imp_HMAssignmentLock
0x14011011f  nop     dword ptr [rax+rax+00h]
0x140110124  jmp     short loc_14011013E
0x140110126  lea     rcx, [rdi+68h]
0x14011012a  mov     rax, [rcx-40h]
  ... truncated ...
```
