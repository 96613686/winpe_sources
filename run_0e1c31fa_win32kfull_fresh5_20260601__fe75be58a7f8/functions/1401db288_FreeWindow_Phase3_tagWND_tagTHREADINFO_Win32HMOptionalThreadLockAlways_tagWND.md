# FreeWindow_Phase3(tagWND *,tagTHREADINFO *,Win32HMOptionalThreadLockAlways<tagWND> *)

- ea: `0x1401db288`
- end: `0x1401dbc87`
- name: `?FreeWindow_Phase3@@YAXPEAUtagWND@@PEAUtagTHREADINFO@@PEAU?$Win32HMOptionalThreadLockAlways@UtagWND@@@@@Z`
- size: `2559`
- prototype: `__int64 __fastcall(struct tagWND *)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401daa48`

## callees

- `0x140007b44`
- `0x1400150d0`
- `0x14001dbdc`
- `0x1400209c0`
- `0x140023be8`
- `0x14002988c`
- `0x14002fd80`
- `0x140059558`
- `0x14006f19c`
- `0x1400a990c`
- `0x1400b2f10`
- `0x1400b3a70`
- `0x1400b4b44`
- `0x1400c138c`
- `0x1400c8124`
- `0x1400db580`
- `0x1400e1d98`
- `0x14010e720`
- `0x1401488b0`
- `0x140148b90`
- `0x1401695a0`
- `0x140191008`
- `0x140198928`
- `0x140199ef4`
- `0x1401abf44`
- `0x1401bdbc0`
- `0x1401cc6e8`
- `0x1401d40a0`
- `0x1401d742c`
- `0x1401db288`
- `0x1401dd610`
- `0x1401e32a8`
- `0x1401e9acc`
- `0x1401f6d10`
- `0x1401fba60`
- `0x14021e8b0`
- `0x140233ed0`
- `0x1402699fc`
- `0x14028ae90`
- `0x1402913f0`
- `0x1402973d0`
- `0x1402b4fb4`
- `0x1402d1380`

## import_xrefs

- `ntoskrnl!RtlFreeHeap` at `0x1401db6df`
- `ntoskrnl!RtlFreeHeap` at `0x1401db732`
- `ntoskrnl!RtlFreeHeap` at `0x1401db6df`
- `ntoskrnl!RtlFreeHeap` at `0x1401db732`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401dbba4`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1401dbba4`
- `win32kbase!?hModuleWin@@3PEAXEA` at `0x1401dbbc4`
- `win32kbase!?DwsUnlinkAllProcesses@tagWND@@QEAAXW4DwsLinkSource@@@Z` at `0x1401db88f`
- `win32kbase!?DwsUnlinkAllProcesses@tagWND@@QEAAXW4DwsLinkSource@@@Z` at `0x1401db88f`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x1401dbb43`
- `win32kbase!?LockUnInitializeThreadCreator@tagObjLock@@QEBAXXZ` at `0x1401dbb43`
- `win32kbase!HandleFullWindowDestruction` at `0x1401db2c1`
- `win32kbase!HandleFullWindowDestruction` at `0x1401db2c1`
- `win32kbase!DeleteProperties` at `0x1401db9c1`
- `win32kbase!DeleteProperties` at `0x1401db9c1`
- `win32kbase!GreUnlockSprite` at `0x1401db5ab`
- `win32kbase!GreUnlockSprite` at `0x1401db5ab`
- `win32kbase!GreLockSprite` at `0x1401db57d`
- `win32kbase!GreLockSprite` at `0x1401db57d`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1401db3b4`
- `win32kbase!DeleteMaybeSpecialRgn` at `0x1401db3b4`
- `win32kbase!_HMPheFromObject` at `0x1401db85c`
- `win32kbase!_HMPheFromObject` at `0x1401db85c`
- `win32kbase!GreUnlockVisRgn` at `0x1401db571`
- `win32kbase!GreUnlockVisRgn` at `0x1401db5f6`
- `win32kbase!GreUnlockVisRgn` at `0x1401db571`
- `win32kbase!GreUnlockVisRgn` at `0x1401db5f6`
- `win32kbase!GreLockVisRgn` at `0x1401db54b`
- `win32kbase!GreLockVisRgn` at `0x1401db5b7`
- `win32kbase!GreLockVisRgn` at `0x1401db54b`
- `win32kbase!GreLockVisRgn` at `0x1401db5b7`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x1401db86f`
- `win32kbase!?ComputeDominantState@tagWND@@QEAAXXZ` at `0x1401db86f`
- `win32kbase!IsWindowDesktopComposed` at `0x1401db80e`
- `win32kbase!IsWindowDesktopComposed` at `0x1401dbaf1`
- `win32kbase!IsWindowDesktopComposed` at `0x1401db80e`
- `win32kbase!IsWindowDesktopComposed` at `0x1401dbaf1`
- `win32kbase!HMFreeObject` at `0x1401dbb52`
- `win32kbase!HMFreeObject` at `0x1401dbb52`
- `win32kbase!HMMarkObjectDestroy` at `0x1401db84d`
- `win32kbase!HMMarkObjectDestroy` at `0x1401db91d`
- `win32kbase!HMMarkObjectDestroy` at `0x1401db84d`
- `win32kbase!HMMarkObjectDestroy` at `0x1401db91d`
- `win32kbase!HMAssignmentLock` at `0x1401db794`
- `win32kbase!HMAssignmentLock` at `0x1401db794`
- `win32kbase!Win32FreePool` at `0x1401db950`
- `win32kbase!Win32FreePool` at `0x1401db97e`
- `win32kbase!Win32FreePool` at `0x1401db9a2`
- `win32kbase!Win32FreePool` at `0x1401db9d4`
- `win32kbase!Win32FreePool` at `0x1401dbac9`
- `win32kbase!Win32FreePool` at `0x1401db950`
- `win32kbase!Win32FreePool` at `0x1401db97e`
- `win32kbase!Win32FreePool` at `0x1401db9a2`
- `win32kbase!Win32FreePool` at `0x1401db9d4`
- `win32kbase!Win32FreePool` at `0x1401dbac9`
- `win32kbase!HMAssignmentUnlock` at `0x1401db2f5`
- `win32kbase!HMAssignmentUnlock` at `0x1401db329`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7ae`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7c6`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7de`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7ff`
- `win32kbase!HMAssignmentUnlock` at `0x1401db8b3`
- `win32kbase!HMAssignmentUnlock` at `0x1401db8cc`
- `win32kbase!HMAssignmentUnlock` at `0x1401db8e1`
- `win32kbase!HMAssignmentUnlock` at `0x1401dbb27`
- `win32kbase!HMAssignmentUnlock` at `0x1401db2f5`
- `win32kbase!HMAssignmentUnlock` at `0x1401db329`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7ae`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7c6`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7de`
- `win32kbase!HMAssignmentUnlock` at `0x1401db7ff`
- `win32kbase!HMAssignmentUnlock` at `0x1401db8b3`
- `win32kbase!HMAssignmentUnlock` at `0x1401db8cc`
- `win32kbase!HMAssignmentUnlock` at `0x1401db8e1`
- `win32kbase!HMAssignmentUnlock` at `0x1401dbb27`
- `win32kbase!ReferenceDwmApiPort` at `0x1401db821`
- `win32kbase!ReferenceDwmApiPort` at `0x1401dbb04`
- `win32kbase!ReferenceDwmApiPort` at `0x1401db821`
- `win32kbase!ReferenceDwmApiPort` at `0x1401dbb04`
- `WIN32K!W32GetUserSessionState` at `0x1401db2cd`
- `WIN32K!W32GetUserSessionState` at `0x1401db2e2`
- `WIN32K!W32GetUserSessionState` at `0x1401db301`
- `WIN32K!W32GetUserSessionState` at `0x1401db316`
- `WIN32K!W32GetUserSessionState` at `0x1401db335`
- `WIN32K!W32GetUserSessionState` at `0x1401db363`
- `WIN32K!W32GetUserSessionState` at `0x1401db510`
- `WIN32K!W32GetUserSessionState` at `0x1401db525`
- `WIN32K!W32GetUserSessionState` at `0x1401db55f`
- `WIN32K!W32GetUserSessionState` at `0x1401db58c`
- `WIN32K!W32GetUserSessionState` at `0x1401db67e`
- `WIN32K!W32GetUserSessionState` at `0x1401dba59`
- `WIN32K!W32GetUserSessionState` at `0x1401dba70`
- `WIN32K!W32GetUserSessionState` at `0x1401dba84`
- `WIN32K!W32GetUserSessionState` at `0x1401dbbce`
- `WIN32K!W32GetUserSessionState` at `0x1401db2cd`
- `WIN32K!W32GetUserSessionState` at `0x1401db2e2`
- `WIN32K!W32GetUserSessionState` at `0x1401db301`
- `WIN32K!W32GetUserSessionState` at `0x1401db316`
- `WIN32K!W32GetUserSessionState` at `0x1401db335`
- `WIN32K!W32GetUserSessionState` at `0x1401db363`
- `WIN32K!W32GetUserSessionState` at `0x1401db510`
- `WIN32K!W32GetUserSessionState` at `0x1401db525`
- `WIN32K!W32GetUserSessionState` at `0x1401db55f`
- `WIN32K!W32GetUserSessionState` at `0x1401db58c`
- `WIN32K!W32GetUserSessionState` at `0x1401db67e`
- `WIN32K!W32GetUserSessionState` at `0x1401dba59`
- `WIN32K!W32GetUserSessionState` at `0x1401dba70`
- `WIN32K!W32GetUserSessionState` at `0x1401dba84`
- `WIN32K!W32GetUserSessionState` at `0x1401dbbce`

## pseudocode

```c
void __fastcall FreeWindow_Phase3(struct _LIST_ENTRY *a1, __int64 a2, ULONG_PTR a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 UserSessionState; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  struct _LIST_ENTRY *Blink; // rax
  char v14; // r14
  __int64 QMsg; // rax
  struct _HEAD *v16; // rbx
  struct _HEAD *Flink; // rbx
  struct _LIST_ENTRY **p_Blink; // rsi
  struct _LIST_ENTRY *v19; // rcx
  struct _LIST_ENTRY *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  struct EWNDOBJ *v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rax
  bool v28; // r15
  struct _LIST_ENTRY *v29; // rbx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  struct _LIST_ENTRY *v33; // r8
  struct tagWND *v34; // r8
  void *v35; // rax
  __int64 v36; // rax
  __int64 ProcessWindowStation; // rax
  __int64 v38; // rbx
  struct _LIST_ENTRY *v39; // rax
  struct _LIST_ENTRY *v40; // rcx
  struct _LIST_ENTRY *v41; // rax
  struct _LIST_ENTRY *v42; // rcx
  __int64 v43; // rax
  __int64 v44; // r14
  __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rax
  struct _LIST_ENTRY *v50; // rcx
  void *v51; // rax
  __int64 v52; // rcx
  __int64 v53; // rsi
  __int64 CurrentProcessWin32Process; // rax
  __int64 v55; // rax
  _QWORD *ClassPtr; // rax
  __int64 v57; // rcx
  __int128 v58; // [rsp+50h] [rbp-29h] BYREF
  char v59[8]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v60; // [rsp+68h] [rbp-11h]
  _BYTE v61[16]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v62; // [rsp+80h] [rbp+7h]

  v59[0] = 0;
  v60 = 0;
  AtomicExecutionCheck::Arm((AtomicExecutionCheck *)v59);
  HandleFullWindowDestruction(a1);
  if ( a1 == *(struct _LIST_ENTRY **)(W32GetUserSessionState(v6) + 36088) )
  {
    UserSessionState = W32GetUserSessionState(v7);
    HMAssignmentUnlock(UserSessionState + 36088);
  }
  if ( a1 == *(struct _LIST_ENTRY **)(W32GetUserSessionState(v7) + 36096) )
  {
    v10 = W32GetUserSessionState(v9);
    HMAssignmentUnlock(v10 + 36096);
  }
  v11 = W32GetUserSessionState(v9);
  MagpDestroyLensContext(v11 + 65808, a2, a1);
  DestroyWindowsTimers(a1);
  DestroyWindowsHotKeys(a1);
  if ( !*(_DWORD *)(W32GetUserSessionState(v12) + 69068) )
    ClearSendMessages(a1);
  CleanupWindowRedirection(a1);
  Blink = a1[2].Blink;
  v14 = 1;
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
  if ( *(_QWORD *)(a2 + 840) )
  {
    QMsg = FindQMsg(a2, (int)a2 + 840, (_DWORD)a1, 18, 18, 1);
    if ( QMsg )
      PostQuitMessage(*(unsigned int *)(QMsg + 32));
  }
  if ( (HIBYTE(a1[2].Blink[1].Blink) & 0xC0) == 0x40 && a1[10].Blink )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 5134);
  if ( (HIBYTE(a1[2].Blink[1].Blink) & 0xC0) != 0x40 )
  {
    v16 = (struct _HEAD *)a1[10].Blink;
    if ( v16 )
    {
      if ( UnlockWndMenuWorker((struct tagWND *)a1, 0) )
        DestroyMenu(v16);
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
  v19 = *p_Blink;
  if ( *p_Blink )
  {
    v20 = v19[3].Blink;
    if ( v20 && a1 == v20[5].Flink )
    {
      v19 = v19[3].Blink;
LABEL_33:
      UnlockNotifyWindow((struct tagMENU *)v19);
      goto LABEL_34;
    }
    v19 = v19[4].Flink;
    if ( v19 && a1 == v19[5].Flink )
      goto LABEL_33;
  }
LABEL_34:
  if ( *(_DWORD *)(W32GetUserSessionState(v19) + 43048) )
  {
    v22 = W32GetUserSessionState(v21);
    v23 = (struct EWNDOBJ *)InternalRemoveProp(a1, *(unsigned __int16 *)(v22 + 41182), 1);
    if ( v23 )
    {
      GreLockVisRgn();
      GreDeleteWnd(v23);
      v25 = W32GetUserSessionState(v24);
      --*(_DWORD *)(v25 + 43048);
      GreUnlockVisRgn();
    }
  }
  GreLockSprite();
  v27 = W32GetUserSessionState(v26);
  GreDeleteSpriteOverlapPresent(*(HDEV *)(*(_QWORD *)(v27 + 56744) + 40LL));
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
      v14 = 0;
    }
    v28 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v29 = a1->Flink;
      v30 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v31) = v28;
      LOBYTE(v32) = v14;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v32,
        v31,
        *(_QWORD *)(v30 + 69152),
        4,
        9,
        11,
        (__int64)WPP_486a5556d82b3fd2406559f49d2a7b57_Traceguids,
        (char)v29);
    }
    RtlFreeHeap((*p_Blink)[8].Blink, 0, a1[9].Blink);
    a1[2].Blink[9].Flink = 0;
    a1[9].Blink = 0;
  }
  if ( (HIDWORD(a1[23].Blink) & 0x10000) != 0 )
    NotifyOverlayWindow((struct tagWND *)a1);
  v33 = a1[11].Blink;
  if ( v33 )
  {
    RtlFreeHeap((*p_Blink)[8].Blink, 0, v33);
    a1[2].Blink[12].Flink = 0;
    a1[11].Blink = 0;
    LODWORD(a1[2].Blink[11].Blink) = 0;
  }
  ResetWindowTransform(a1);
  if ( !*p_Blink || (v34 = (struct tagWND *)(*p_Blink)->Blink[1].Blink, a1 == (struct _LIST_ENTRY *)v34) )
  {
    a1[2].Blink[3].Flink = 0;
    HMAssignmentUnlock(&a1[6].Blink);
  }
  else
  {
    v58 = *(_OWORD *)LockPointer(v61, &a1[6].Blink, v34);
    HMAssignmentLock(&v58, 1);
  }
  a1[2].Blink[3].Blink = 0;
  HMAssignmentUnlock(&a1[7]);
  a1[2].Blink[4].Flink = 0;
  HMAssignmentUnlock(&a1[7].Blink);
  a1[2].Blink[11].Flink = 0;
  HMAssignmentUnlock(&a1[12].Blink);
  if ( (unsigned int)IsWindowDesktopComposed(a1) )
  {
    v35 = (void *)ReferenceDwmApiPort();
    DwmAsyncOwnerChange(v35);
  }
  DereferenceClass(*(_QWORD *)(a2 + 456), a1);
  HMMarkObjectDestroy(a1);
  v36 = _HMPheFromObject(a1);
  *(_BYTE *)(v36 + 25) |= 2u;
  tagWND::ComputeDominantState((tagWND *)a1);
  if ( (HIDWORD(a1[23].Blink) & 0x8000000) != 0 )
    tagWND::DwsUnlinkAllProcesses(a1, 3);
  ProcessWindowStation = GetProcessWindowStation(0);
  v38 = ProcessWindowStation;
  if ( ProcessWindowStation )
  {
    if ( *(struct _LIST_ENTRY **)(ProcessWindowStation + 64) == a1 )
    {
      HMAssignmentUnlock(ProcessWindowStation + 64);
      *(_QWORD *)(v38 + 48) = 0;
    }
    if ( *(struct _LIST_ENTRY **)(v38 + 80) == a1 )
      HMAssignmentUnlock(v38 + 80);
    if ( *(struct _LIST_ENTRY **)(v38 + 72) == a1 )
      HMAssignmentUnlock(v38 + 72);
  }
  if ( (HIDWORD(a1[23].Blink) & 0x800000) != 0 )
    _RemoveClipboardFormatListener((struct tagWND *)a1);
  if ( Win32HMThreadLockBase<tagMENU,0,1>::ManualUnlock<void>(a3) )
  {
    FreeClientOnWindowDestruction(a1);
    if ( (unsigned int)HMMarkObjectDestroy(a1) )
    {
      v39 = a1[18].Flink;
      if ( v39 )
      {
        --LODWORD(v39->Flink);
        v40 = a1[18].Flink;
        if ( !LODWORD(v40->Flink) )
          Win32FreePool(v40);
        a1[18].Flink = 0;
      }
      v41 = a1[18].Blink;
      if ( v41 )
      {
        --LODWORD(v41->Flink);
        v42 = a1[18].Blink;
        if ( !LODWORD(v42->Flink) )
          Win32FreePool(v42);
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
      v43 = safe_cast_fnid_to_PMENUWND(a1);
      v44 = v43;
      if ( v43 && *(_QWORD *)(v43 + 16) )
      {
        SmartObjStackRefBase<tagPOPUPMENU>::Init(&v58);
        if ( (**(_DWORD **)v58 & 0x20000000) != 0 )
        {
          **(_DWORD **)v58 &= ~0x40000000u;
        }
        else
        {
          v45 = *(_QWORD *)v58;
          if ( v45 == W32GetUserSessionState(v58) + 65560 )
          {
            v47 = W32GetUserSessionState(v46);
            *(_DWORD *)(v47 + 66784) &= ~0x800000u;
            v49 = W32GetUserSessionState(v48);
            NullifyLookasideRef(*(_QWORD *)(v49 + 65648));
          }
          else
          {
            FreeIsolatedTypeAndClearStackReferences<tagPOPUPMENU>(&v58);
            *(_QWORD *)(v44 + 16) = 0;
          }
        }
        SmartObjStackRefBase<tagPOPUPMENU>::~SmartObjStackRefBase<tagPOPUPMENU>(&v58);
      }
      v50 = a1[17].Blink;
      if ( v50 )
      {
        Win32FreePool(v50);
        a1[17].Blink = 0;
      }
      LODWORD(a1[2].Blink[15].Blink) = 0;
      --*(_DWORD *)(a2 + 932);
      if ( (unsigned int)IsWindowDesktopComposed(a1) )
      {
        v51 = (void *)ReferenceDwmApiPort();
        DwmAsyncChildDestroy(v51);
      }
      a1[2].Blink[3].Flink = 0;
      HMAssignmentUnlock(&a1[6].Blink);
      Win32RawLockedNtObject<tagDESKTOP>::Win32RawLockedNtObject<tagDESKTOP>(v61, *p_Blink);
      tagObjLock::LockUnInitializeThreadCreator((tagObjLock *)&a1[3].Blink);
      HMFreeObject(a1);
      if ( v62 != -1 )
      {
        PopAndFreeW32ThreadLock(v61);
        v62 = -1;
      }
    }
    else
    {
      a1[2].Blink[7].Blink = 0;
      if ( *p_Blink )
      {
        v52 = (__int64)(*p_Blink)[2].Blink[1].Blink;
        v53 = *(_QWORD *)(*(_QWORD *)(v52 + 16) + 456LL);
      }
      else
      {
        CurrentProcessWin32Process = PsGetCurrentProcessWin32Process();
        v53 = CurrentProcessWin32Process;
        if ( CurrentProcessWin32Process )
        {
          v52 = -(__int64)(*(_QWORD *)CurrentProcessWin32Process != 0);
          v53 = v52 & CurrentProcessWin32Process;
        }
      }
      v55 = W32GetUserSessionState(v52);
      ClassPtr = (_QWORD *)GetClassPtr(*(unsigned __int16 *)(*(_QWORD *)(v55 + 19704) + 910LL), v53, hModuleWin);
      tagWND::SharedMixedObjectPointerFieldpcls<tagCLS>::operator=(&a1[8].Blink, *ClassPtr);
      ++*(_DWORD *)(*(_QWORD *)v57 + 72LL);
      SetOrClrWF(1, a1, 516, 1);
      SetOrClrWF(0, a1, 544, 1);
      SetOrClrWF(0, a1, 4032, 1);
      SetOrClrWF(1, a1, 3840, 1);
      a1[2].Blink[9].Blink = 0;
      a1[10].Blink = 0;
    }
  }
  AtomicExecutionCheck::Disarm((AtomicExecutionCheck *)v59);
}

```

## disassembly

```asm
0x1401db288  push    rbp
0x1401db28a  push    rbx
0x1401db28b  push    rsi
0x1401db28c  push    rdi
0x1401db28d  push    r12
0x1401db28f  push    r13
0x1401db291  push    r14
0x1401db293  push    r15
0x1401db295  lea     rbp, [rsp-1Fh]
0x1401db29a  sub     rsp, 98h
0x1401db2a1  mov     rdi, rcx
0x1401db2a4  xor     r15d, r15d
0x1401db2a7  lea     rcx, [rbp+57h+var_70]; this
0x1401db2ab  mov     [rbp+57h+var_70], r15b
0x1401db2af  mov     [rbp+57h+var_68], r15
0x1401db2b3  mov     r12, r8
0x1401db2b6  mov     r13, rdx
0x1401db2b9  call    ?Arm@AtomicExecutionCheck@@QEAAXXZ; AtomicExecutionCheck::Arm(void)
0x1401db2be  mov     rcx, rdi
0x1401db2c1  call    cs:__imp_HandleFullWindowDestruction
0x1401db2c8  nop     dword ptr [rax+rax+00h]
0x1401db2cd  call    cs:__imp_W32GetUserSessionState
0x1401db2d4  nop     dword ptr [rax+rax+00h]
0x1401db2d9  cmp     rdi, [rax+8CF8h]
0x1401db2e0  jnz     short loc_1401DB301
0x1401db2e2  call    cs:__imp_W32GetUserSessionState
0x1401db2e9  nop     dword ptr [rax+rax+00h]
0x1401db2ee  lea     rcx, [rax+8CF8h]
0x1401db2f5  call    cs:__imp_HMAssignmentUnlock
0x1401db2fc  nop     dword ptr [rax+rax+00h]
0x1401db301  call    cs:__imp_W32GetUserSessionState
0x1401db308  nop     dword ptr [rax+rax+00h]
0x1401db30d  cmp     rdi, [rax+8D00h]
0x1401db314  jnz     short loc_1401DB335
0x1401db316  call    cs:__imp_W32GetUserSessionState
0x1401db31d  nop     dword ptr [rax+rax+00h]
0x1401db322  lea     rcx, [rax+8D00h]
0x1401db329  call    cs:__imp_HMAssignmentUnlock
0x1401db330  nop     dword ptr [rax+rax+00h]
0x1401db335  call    cs:__imp_W32GetUserSessionState
0x1401db33c  nop     dword ptr [rax+rax+00h]
0x1401db341  mov     r8, rdi
0x1401db344  mov     rdx, r13
0x1401db347  lea     rcx, [rax+10110h]
0x1401db34e  call    MagpDestroyLensContext
0x1401db353  mov     rcx, rdi
0x1401db356  call    DestroyWindowsTimers
0x1401db35b  mov     rcx, rdi
0x1401db35e  call    DestroyWindowsHotKeys
0x1401db363  call    cs:__imp_W32GetUserSessionState
0x1401db36a  nop     dword ptr [rax+rax+00h]
0x1401db36f  cmp     [rax+10DCCh], r15d
0x1401db376  jnz     short loc_1401DB380
0x1401db378  mov     rcx, rdi
0x1401db37b  call    ClearSendMessages
0x1401db380  mov     rcx, rdi
0x1401db383  call    CleanupWindowRedirection
0x1401db388  mov     rax, [rdi+28h]
0x1401db38c  mov     r14d, 1
0x1401db392  cmp     [rax+88h], r15
0x1401db399  jnz     short loc_1401DB3A1
0x1401db39b  test    byte ptr [rax+11h], 10h
0x1401db39f  jz      short loc_1401DB3DE
0x1401db3a1  mov     rcx, rdi
0x1401db3a4  call    DecPaintCount
0x1401db3a9  mov     rcx, [rdi+28h]
0x1401db3ad  mov     rcx, [rcx+88h]
0x1401db3b4  call    cs:__imp_DeleteMaybeSpecialRgn
0x1401db3bb  nop     dword ptr [rax+rax+00h]
0x1401db3c0  mov     rax, [rdi+28h]
0x1401db3c4  mov     r8d, 110h
0x1401db3ca  mov     r9d, r14d
0x1401db3cd  mov     rdx, rdi
0x1401db3d0  xor     ecx, ecx
0x1401db3d2  mov     [rax+88h], r15
0x1401db3d9  call    SetOrClrWF
0x1401db3de  mov     rax, [rdi+28h]
0x1401db3e2  test    byte ptr [rax+11h], 0Ah
0x1401db3e6  jz      short loc_1401DB40E
0x1401db3e8  mov     r8d, 108h
0x1401db3ee  mov     r9d, r14d
0x1401db3f1  mov     rdx, rdi
0x1401db3f4  xor     ecx, ecx
0x1401db3f6  call    SetOrClrWF
0x1401db3fb  mov     r8d, 102h
0x1401db401  mov     r9d, r14d
0x1401db404  mov     rdx, rdi
0x1401db407  xor     ecx, ecx
0x1401db409  call    SetOrClrWF
0x1401db40e  lea     rdx, [r13+348h]
0x1401db415  cmp     [rdx], r15
0x1401db418  jz      short loc_1401DB442
0x1401db41a  mov     r9d, 12h
0x1401db420  mov     [rsp+0D0h+var_A8], r14d
0x1401db425  mov     r8, rdi
0x1401db428  mov     [rsp+0D0h+var_B0], r9d
0x1401db42d  mov     rcx, r13
0x1401db430  call    FindQMsg
0x1401db435  test    rax, rax
0x1401db438  jz      short loc_1401DB442
0x1401db43a  mov     ecx, [rax+20h]
0x1401db43d  call    _PostQuitMessage
0x1401db442  mov     rax, [rdi+28h]
0x1401db446  mov     cl, [rax+1Fh]
0x1401db449  and     cl, 0C0h
0x1401db44c  cmp     cl, 40h ; '@'
0x1401db44f  jnz     short loc_1401DB476
0x1401db451  cmp     [rdi+0A8h], r15
0x1401db458  jz      short loc_1401DB476
0x1401db45a  mov     [rbp+57h+arg_0], 20000h
0x1401db461  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401db468  mov     edx, [rbp+57h+arg_0]
0x1401db46b  mov     r8d, 140Eh
0x1401db471  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401db476  mov     rax, [rdi+28h]
0x1401db47a  mov     cl, [rax+1Fh]
0x1401db47d  and     cl, 0C0h
0x1401db480  cmp     cl, 40h ; '@'
0x1401db483  jz      short loc_1401DB4A8
0x1401db485  mov     rbx, [rdi+0A8h]
0x1401db48c  test    rbx, rbx
0x1401db48f  jz      short loc_1401DB4A8
0x1401db491  xor     edx, edx; bool
0x1401db493  mov     rcx, rdi; struct tagWND *
0x1401db496  call    ?UnlockWndMenuWorker@@YAPEAXPEAUtagWND@@_N@Z; UnlockWndMenuWorker(tagWND *,bool)
0x1401db49b  test    rax, rax
0x1401db49e  jz      short loc_1401DB4A8
0x1401db4a0  mov     rcx, rbx; struct _HEAD *
0x1401db4a3  call    _DestroyMenu
0x1401db4a8  mov     rbx, [rdi+0A0h]
0x1401db4af  lea     rsi, [rdi+18h]
0x1401db4b3  test    rbx, rbx
0x1401db4b6  jz      short loc_1401DB4E0
0x1401db4b8  mov     rax, [rsi]
0x1401db4bb  mov     dl, r14b; bool
0x1401db4be  mov     rcx, rdi; struct tagWND *
0x1401db4c1  cmp     rbx, [rax+40h]
0x1401db4c5  jz      short loc_1401DB4DB
0x1401db4c7  call    ?UnlockWndMenuWorker@@YAPEAXPEAUtagWND@@_N@Z; UnlockWndMenuWorker(tagWND *,bool)
0x1401db4cc  test    rax, rax
0x1401db4cf  jz      short loc_1401DB4E0
0x1401db4d1  mov     rcx, rbx; struct _HEAD *
0x1401db4d4  call    _DestroyMenu
0x1401db4d9  jmp     short loc_1401DB4E0
0x1401db4db  call    ?UnlockWndMenuWorker@@YAPEAXPEAUtagWND@@_N@Z; UnlockWndMenuWorker(tagWND *,bool)
0x1401db4e0  mov     rcx, [rsi]
0x1401db4e3  test    rcx, rcx
0x1401db4e6  jz      short loc_1401DB510
0x1401db4e8  mov     rax, [rcx+38h]
0x1401db4ec  test    rax, rax
0x1401db4ef  jz      short loc_1401DB4FC
0x1401db4f1  cmp     rdi, [rax+50h]
0x1401db4f5  jnz     short loc_1401DB4FC
0x1401db4f7  mov     rcx, rax
0x1401db4fa  jmp     short loc_1401DB50B
0x1401db4fc  mov     rcx, [rcx+40h]; struct tagMENU *
0x1401db500  test    rcx, rcx
0x1401db503  jz      short loc_1401DB510
0x1401db505  cmp     rdi, [rcx+50h]
0x1401db509  jnz     short loc_1401DB510
0x1401db50b  call    ?UnlockNotifyWindow@@YAXPEAUtagMENU@@@Z; UnlockNotifyWindow(tagMENU *)
0x1401db510  call    cs:__imp_W32GetUserSessionState
0x1401db517  nop     dword ptr [rax+rax+00h]
0x1401db51c  cmp     [rax+0A828h], r15d
0x1401db523  jz      short loc_1401DB57D
0x1401db525  call    cs:__imp_W32GetUserSessionState
0x1401db52c  nop     dword ptr [rax+rax+00h]
0x1401db531  mov     r8d, r14d
0x1401db534  mov     rcx, rdi
0x1401db537  movzx   edx, word ptr [rax+0A0DEh]
0x1401db53e  call    InternalRemoveProp
0x1401db543  mov     rbx, rax
0x1401db546  test    rax, rax
0x1401db549  jz      short loc_1401DB57D
0x1401db54b  call    cs:__imp_GreLockVisRgn
0x1401db552  nop     dword ptr [rax+rax+00h]
0x1401db557  mov     rcx, rbx; struct EWNDOBJ *
0x1401db55a  call    GreDeleteWnd
0x1401db55f  call    cs:__imp_W32GetUserSessionState
0x1401db566  nop     dword ptr [rax+rax+00h]
0x1401db56b  dec     dword ptr [rax+0A828h]
0x1401db571  call    cs:__imp_GreUnlockVisRgn
0x1401db578  nop     dword ptr [rax+rax+00h]
0x1401db57d  call    cs:__imp_GreLockSprite
0x1401db584  nop     dword ptr [rax+rax+00h]
0x1401db589  mov     rbx, [rdi]
0x1401db58c  call    cs:__imp_W32GetUserSessionState
0x1401db593  nop     dword ptr [rax+rax+00h]
0x1401db598  mov     rdx, rbx
0x1401db59b  mov     rcx, [rax+0DDA8h]
0x1401db5a2  mov     rcx, [rcx+28h]; HDEV
0x1401db5a6  call    GreDeleteSpriteOverlapPresent
0x1401db5ab  call    cs:__imp_GreUnlockSprite
0x1401db5b2  nop     dword ptr [rax+rax+00h]
0x1401db5b7  call    cs:__imp_GreLockVisRgn
0x1401db5be  nop     dword ptr [rax+rax+00h]
0x1401db5c3  lea     rcx, [rdi+140h]; struct _LIST_ENTRY *
0x1401db5ca  mov     edx, 68h ; 'h'; unsigned __int64
0x1401db5cf  call    ?_ClearPwndDceList@@YAXPEAU_LIST_ENTRY@@_K@Z; _ClearPwndDceList(_LIST_ENTRY *,unsigned __int64)
0x1401db5d4  lea     rcx, [rdi+150h]; struct _LIST_ENTRY *
0x1401db5db  mov     edx, 78h ; 'x'; unsigned __int64
0x1401db5e0  call    ?_ClearPwndDceList@@YAXPEAU_LIST_ENTRY@@_K@Z; _ClearPwndDceList(_LIST_ENTRY *,unsigned __int64)
0x1401db5e5  lea     rcx, [rdi+160h]; struct _LIST_ENTRY *
0x1401db5ec  mov     edx, 88h; unsigned __int64
0x1401db5f1  call    ?_ClearPwndDceList@@YAXPEAU_LIST_ENTRY@@_K@Z; _ClearPwndDceList(_LIST_ENTRY *,unsigned __int64)
0x1401db5f6  call    cs:__imp_GreUnlockVisRgn
0x1401db5fd  nop     dword ptr [rax+rax+00h]
0x1401db602  mov     rax, [rdi+28h]
0x1401db606  movzx   ecx, word ptr [rax+2Ah]
0x1401db60a  and     ecx, 0FFFF2FFFh
0x1401db610  cmp     ecx, 29Dh
0x1401db616  jz      short loc_1401DB620
0x1401db618  mov     rcx, rdi; this
0x1401db61b  call    ?ClearClipRgnOrMaxClip@tagWND@@QEAAXXZ; tagWND::ClearClipRgnOrMaxClip(void)
0x1401db620  call    Feature_UserModeNonClientScrollBars2__private_IsEnabledDeviceUsageNoInline
0x1401db625  test    eax, eax
0x1401db627  jnz     loc_1401DB704
0x1401db62d  cmp     [rdi+98h], r15
0x1401db634  jz      loc_1401DB704
0x1401db63a  mov     rcx, cs:WPP_GLOBAL_Control
0x1401db641  lea     rax, WPP_GLOBAL_Control
0x1401db648  cmp     rcx, rax
0x1401db64b  jz      short loc_1401DB65C
0x1401db64d  test    dword ptr [rcx+2Ch], 100h
0x1401db654  jz      short loc_1401DB65C
0x1401db656  cmp     byte ptr [rcx+29h], 4
0x1401db65a  jnb     short loc_1401DB65F
0x1401db65c  mov     r14b, r15b
0x1401db65f  lea     rax, WPP_RECORDER_INITIALIZED
0x1401db666  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401db66d  setnz   r15b
0x1401db671  test    r14b, r14b
0x1401db674  jnz     short loc_1401DB67B
0x1401db676  test    r15b, r15b
0x1401db679  jz      short loc_1401DB6CC
0x1401db67b  mov     rbx, [rdi]
0x1401db67e  call    cs:__imp_W32GetUserSessionState
0x1401db685  nop     dword ptr [rax+rax+00h]
0x1401db68a  mov     rcx, cs:WPP_GLOBAL_Control
0x1401db691  mov     r8b, r15b
0x1401db694  mov     [rsp+0D0h+var_90], rbx
0x1401db699  mov     dl, r14b
0x1401db69c  mov     r9, [rax+10E20h]
0x1401db6a3  lea     rax, WPP_486a5556d82b3fd2406559f49d2a7b57_Traceguids
0x1401db6aa  mov     rcx, [rcx+18h]
0x1401db6ae  mov     [rsp+0D0h+var_98], rax
0x1401db6b3  mov     [rsp+0D0h+var_A0], 0Bh
0x1401db6ba  mov     [rsp+0D0h+var_A8], 9
0x1401db6c2  mov     byte ptr [rsp+0D0h+var_B0], 4
0x1401db6c7  call    WPP_RECORDER_AND_TRACE_SF_q
0x1401db6cc  mov     rcx, [rsi]
0x1401db6cf  xor     edx, edx; Flags
0x1401db6d1  mov     r8, [rdi+98h]; BaseAddress
0x1401db6d8  mov     rcx, [rcx+88h]; HeapHandle
0x1401db6df  call    cs:__imp_RtlFreeHeap
0x1401db6e6  nop     dword ptr [rax+rax+00h]
0x1401db6eb  mov     rax, [rdi+28h]
0x1401db6ef  xor     r15d, r15d
0x1401db6f2  mov     [rax+90h], r15
0x1401db6f9  lea     r14d, [r15+1]
0x1401db6fd  mov     [rdi+98h], r15
0x1401db704  test    dword ptr [rdi+17Ch], 10000h
0x1401db70e  jz      short loc_1401DB71A
0x1401db710  xor     edx, edx
0x1401db712  mov     rcx, rdi; struct tagWND *
0x1401db715  call    _NotifyOverlayWindow
0x1401db71a  mov     r8, [rdi+0B8h]; BaseAddress
0x1401db721  test    r8, r8
0x1401db724  jz      short loc_1401DB75B
0x1401db726  mov     rcx, [rsi]
0x1401db729  xor     edx, edx; Flags
0x1401db72b  mov     rcx, [rcx+88h]; HeapHandle
0x1401db732  call    cs:__imp_RtlFreeHeap
0x1401db739  nop     dword ptr [rax+rax+00h]
0x1401db73e  mov     rax, [rdi+28h]
0x1401db742  mov     [rax+0C0h], r15
0x1401db749  mov     [rdi+0B8h], r15
0x1401db750  mov     rax, [rdi+28h]
0x1401db754  mov     [rax+0B8h], r15d
0x1401db75b  mov     rcx, rdi
0x1401db75e  call    ResetWindowTransform
0x1401db763  mov     rax, [rsi]
0x1401db766  test    rax, rax
0x1401db769  jz      short loc_1401DB7A2
0x1401db76b  mov     rax, [rax+8]
0x1401db76f  mov     r8, [rax+18h]
0x1401db773  cmp     rdi, r8
0x1401db776  jz      short loc_1401DB7A2
0x1401db778  lea     rdx, [rdi+68h]
0x1401db77c  lea     rcx, [rbp+57h+var_60]
0x1401db780  call    ?LockPointer@@YA?AU_LOCKASSIGNPAIR@@PEAV?$SharedUserObjPointerFieldspwndParent@UtagWND@@@tagWND@@PEAU_HEAD@@@Z; LockPointer(tagWND::SharedUserObjPointerFieldspwndParent<tagWND> *,_HEAD *)
0x1401db785  mov     edx, r14d
0x1401db788  lea     rcx, [rbp+57h+var_80]
0x1401db78c  movups  xmm0, xmmword ptr [rax]
0x1401db78f  movdqu  [rbp+57h+var_80], xmm0
0x1401db794  call    cs:__imp_HMAssignmentLock
0x1401db79b  nop     dword ptr [rax+rax+00h]
0x1401db7a0  jmp     short loc_1401DB7BA
0x1401db7a2  lea     rcx, [rdi+68h]
0x1401db7a6  mov     rax, [rcx-40h]
  ... truncated ...
```
