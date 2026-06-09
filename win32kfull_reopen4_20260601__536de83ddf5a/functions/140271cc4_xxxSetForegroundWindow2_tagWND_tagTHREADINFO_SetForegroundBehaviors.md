# xxxSetForegroundWindow2(tagWND *,tagTHREADINFO *,SetForegroundBehaviors)

- ea: `0x140271cc4`
- end: `0x140272921`
- name: `?xxxSetForegroundWindow2@@YAHPEAUtagWND@@PEAUtagTHREADINFO@@W4SetForegroundBehaviors@@@Z`
- size: `3165`
- prototype: ``
- caller_count: `7`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140032784`
- `0x1400c7d84`
- `0x14016f3c4`
- `0x1401a8530`
- `0x1401c0f48`
- `0x14021c534`
- `0x1402ab58c`

## callees

- `0x140006824`
- `0x1400073ec`
- `0x1400114a4`
- `0x140019430`
- `0x14001b9c0`
- `0x14001c788`
- `0x140025b90`
- `0x14002e150`
- `0x14002ea00`
- `0x14002eb54`
- `0x1400bb904`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x14013dda8`
- `0x14016e684`
- `0x14017cc14`
- `0x140182d80`
- `0x140188eb8`
- `0x140189124`
- `0x1401895f8`
- `0x140203240`
- `0x1402070b0`
- `0x14020a2b8`
- `0x140213994`
- `0x1402256a0`
- `0x140227c4c`
- `0x140271448`
- `0x1402715ec`
- `0x140271cc4`
- `0x1402aadd4`
- `0x1402ab37c`
- `0x1402aecc4`
- `0x1402b2820`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x140271f72`
- `ntoskrnl!PsGetThreadId` at `0x140271f8e`
- `ntoskrnl!PsGetThreadId` at `0x140272533`
- `ntoskrnl!PsGetThreadId` at `0x1402726b0`
- `ntoskrnl!PsGetThreadId` at `0x14027279c`
- `ntoskrnl!PsGetThreadId` at `0x1402728b3`
- `ntoskrnl!PsGetThreadId` at `0x140271f72`
- `ntoskrnl!PsGetThreadId` at `0x140271f8e`
- `ntoskrnl!PsGetThreadId` at `0x140272533`
- `ntoskrnl!PsGetThreadId` at `0x1402726b0`
- `ntoskrnl!PsGetThreadId` at `0x14027279c`
- `ntoskrnl!PsGetThreadId` at `0x1402728b3`
- `win32kbase!?ClearClip@CCursorClip@@QEAAXXZ` at `0x140272433`
- `win32kbase!?ClearClip@CCursorClip@@QEAAXXZ` at `0x140272433`
- `win32kbase!ClearKeyboardToggleStates` at `0x14027227b`
- `win32kbase!ClearKeyboardToggleStates` at `0x14027227b`
- `win32kbase!SetSystemInputSource` at `0x140271d4c`
- `win32kbase!SetSystemInputSource` at `0x140271d4c`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027226b`
- `win32kbase!?CheckAccess@UIPrivilegeIsolation@@YA_NAEBUtagUIPI_INFO@@0@Z` at `0x14027226b`
- `WIN32K!W32GetUserSessionState` at `0x140271d61`
- `WIN32K!W32GetUserSessionState` at `0x140271def`
- `WIN32K!W32GetUserSessionState` at `0x140271e88`
- `WIN32K!W32GetUserSessionState` at `0x140271fa7`
- `WIN32K!W32GetUserSessionState` at `0x140272034`
- `WIN32K!W32GetUserSessionState` at `0x14027207e`
- `WIN32K!W32GetUserSessionState` at `0x1402720ca`
- `WIN32K!W32GetUserSessionState` at `0x140272108`
- `WIN32K!W32GetUserSessionState` at `0x140272120`
- `WIN32K!W32GetUserSessionState` at `0x140272145`
- `WIN32K!W32GetUserSessionState` at `0x1402721c9`
- `WIN32K!W32GetUserSessionState` at `0x1402721de`
- `WIN32K!W32GetUserSessionState` at `0x1402721fa`
- `WIN32K!W32GetUserSessionState` at `0x140272216`
- `WIN32K!W32GetUserSessionState` at `0x14027222b`
- `WIN32K!W32GetUserSessionState` at `0x140272247`
- `WIN32K!W32GetUserSessionState` at `0x140272287`
- `WIN32K!W32GetUserSessionState` at `0x1402722a7`
- `WIN32K!W32GetUserSessionState` at `0x1402722f4`
- `WIN32K!W32GetUserSessionState` at `0x140272309`
- `WIN32K!W32GetUserSessionState` at `0x14027231c`
- `WIN32K!W32GetUserSessionState` at `0x140272331`
- `WIN32K!W32GetUserSessionState` at `0x14027234a`
- `WIN32K!W32GetUserSessionState` at `0x140272365`
- `WIN32K!W32GetUserSessionState` at `0x140272378`
- `WIN32K!W32GetUserSessionState` at `0x140272391`
- `WIN32K!W32GetUserSessionState` at `0x1402723a6`
- `WIN32K!W32GetUserSessionState` at `0x1402723bf`
- `WIN32K!W32GetUserSessionState` at `0x1402723dd`
- `WIN32K!W32GetUserSessionState` at `0x1402723f2`
- `WIN32K!W32GetUserSessionState` at `0x140272420`
- `WIN32K!W32GetUserSessionState` at `0x140272506`
- `WIN32K!W32GetUserSessionState` at `0x14027251d`
- `WIN32K!W32GetUserSessionState` at `0x1402727b5`
- `WIN32K!W32GetUserSessionState` at `0x140271d61`
- `WIN32K!W32GetUserSessionState` at `0x140271def`
- `WIN32K!W32GetUserSessionState` at `0x140271e88`
- `WIN32K!W32GetUserSessionState` at `0x140271fa7`
- `WIN32K!W32GetUserSessionState` at `0x140272034`
- `WIN32K!W32GetUserSessionState` at `0x14027207e`
- `WIN32K!W32GetUserSessionState` at `0x1402720ca`
- `WIN32K!W32GetUserSessionState` at `0x140272108`
- `WIN32K!W32GetUserSessionState` at `0x140272120`
- `WIN32K!W32GetUserSessionState` at `0x140272145`
- `WIN32K!W32GetUserSessionState` at `0x1402721c9`
- `WIN32K!W32GetUserSessionState` at `0x1402721de`
- `WIN32K!W32GetUserSessionState` at `0x1402721fa`
- `WIN32K!W32GetUserSessionState` at `0x140272216`
- `WIN32K!W32GetUserSessionState` at `0x14027222b`
- `WIN32K!W32GetUserSessionState` at `0x140272247`
- `WIN32K!W32GetUserSessionState` at `0x140272287`
- `WIN32K!W32GetUserSessionState` at `0x1402722a7`
- `WIN32K!W32GetUserSessionState` at `0x1402722f4`
- `WIN32K!W32GetUserSessionState` at `0x140272309`
- `WIN32K!W32GetUserSessionState` at `0x14027231c`
- `WIN32K!W32GetUserSessionState` at `0x140272331`
- `WIN32K!W32GetUserSessionState` at `0x14027234a`
- `WIN32K!W32GetUserSessionState` at `0x140272365`
- `WIN32K!W32GetUserSessionState` at `0x140272378`
- `WIN32K!W32GetUserSessionState` at `0x140272391`
- `WIN32K!W32GetUserSessionState` at `0x1402723a6`
- `WIN32K!W32GetUserSessionState` at `0x1402723bf`
- `WIN32K!W32GetUserSessionState` at `0x1402723dd`
- `WIN32K!W32GetUserSessionState` at `0x1402723f2`
- `WIN32K!W32GetUserSessionState` at `0x140272420`
- `WIN32K!W32GetUserSessionState` at `0x140272506`
- `WIN32K!W32GetUserSessionState` at `0x14027251d`
- `WIN32K!W32GetUserSessionState` at `0x1402727b5`

## pseudocode

```c
__int64 __fastcall xxxSetForegroundWindow2(ULONG_PTR *a1, ULONG_PTR a2, unsigned int a3)
{
  __int64 v5; // rcx
  bool v6; // bl
  bool v7; // si
  __int64 UserSessionState; // rax
  int v9; // r8d
  int v10; // edx
  bool v11; // bl
  bool v12; // si
  __int64 v13; // rax
  int v14; // r8d
  int v15; // edx
  bool v17; // al
  ULONG_PTR v18; // rcx
  __int64 v19; // rax
  int v20; // r8d
  int v21; // edx
  struct MOVESIZEDATA *v22; // rcx
  bool v23; // al
  __int64 v24; // rax
  int v25; // r8d
  int v26; // edx
  struct MOVESIZEDATA *v27; // rcx
  bool v28; // bl
  bool v29; // r14
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // r13
  ULONG_PTR v35; // r14
  struct tagTHREADINFO *v36; // rcx
  struct tagWND *v37; // rdx
  _QWORD *v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  const struct tagUIPI_INFO *v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rcx
  _QWORD *v45; // rdx
  __m128i si128; // xmm0
  __m128i *v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rbx
  __int64 v50; // rcx
  __int64 v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rcx
  ULONG_PTR v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rbx
  unsigned int v61; // ebx
  unsigned __int64 v62; // r13
  const struct tagWND *TopLevelWindow; // rax
  __int64 v64; // rcx
  __int64 v65; // rcx
  __int64 v66; // rax
  HANDLE ThreadId; // rax
  const struct tagWND *v68; // rcx
  __int64 v69; // rbx
  ULONG_PTR v70; // r8
  __int64 v71; // r13
  int v72; // eax
  bool v73; // zf
  char v74; // r13
  __int64 v75; // r12
  void *v76; // rdx
  unsigned int v77; // ecx
  unsigned __int64 v78; // r9
  unsigned int v79; // eax
  const struct tagWND *v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rdx
  __int64 v83; // rax
  BOOL v84; // ebx
  const struct tagWND *v85; // rax
  const struct tagWND *v86; // r15
  unsigned int v87; // eax
  bool v88; // [rsp+70h] [rbp-90h]
  bool v89; // [rsp+70h] [rbp-90h]
  bool v90; // [rsp+71h] [rbp-8Fh]
  bool v91; // [rsp+71h] [rbp-8Fh]
  struct tagWND *v93; // [rsp+80h] [rbp-80h]
  struct tagWND *v94; // [rsp+80h] [rbp-80h]
  unsigned int v95; // [rsp+80h] [rbp-80h]
  unsigned int v96; // [rsp+80h] [rbp-80h]
  struct tagQMSG *v98; // [rsp+90h] [rbp-70h]
  struct tagQMSG *v99; // [rsp+90h] [rbp-70h]
  ULONG_PTR v100; // [rsp+98h] [rbp-68h]
  __int64 v101; // [rsp+A0h] [rbp-60h] BYREF
  ULONG_PTR v102[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v103; // [rsp+B8h] [rbp-48h]
  ULONG_PTR v104[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v105; // [rsp+D0h] [rbp-30h]
  ULONG_PTR BugCheckParameter2[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v107; // [rsp+E8h] [rbp-18h]
  __int64 v108; // [rsp+F0h] [rbp-10h] BYREF
  int v109; // [rsp+F8h] [rbp-8h]
  __int64 v110; // [rsp+100h] [rbp+0h] BYREF
  int v111; // [rsp+108h] [rbp+8h]

  *(_OWORD *)BugCheckParameter2 = 0;
  *(_OWORD *)v104 = 0;
  v107 = -1;
  v105 = -1;
  *(_OWORD *)v102 = 0;
  v103 = -1;
  v93 = PtiCurrent();
  v110 = 0;
  v111 = 0;
  v108 = 0;
  v109 = 0;
  v101 = 0;
  Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  SetSystemInputSource(&v101);
  if ( !a1 )
    goto LABEL_22;
  if ( a1[3] == *(_QWORD *)(W32GetUserSessionState(v5) + 19216) && *(char *)(a1[5] + 19) >= 0 )
  {
    if ( (unsigned int)IsWindowUnderActiveLockScreen(a1) )
    {
      v6 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v7 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v6 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v9) = v7;
        LOBYTE(v10) = v6;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v10,
          v9,
          *(_QWORD *)(UserSessionState + 69152),
          4,
          2,
          91,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      }
      goto LABEL_89;
    }
LABEL_22:
    if ( a2 )
      Win32RawLockedW32Thread::ManualLock((ULONG_PTR)BugCheckParameter2, a2);
    v17 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v88 = v17;
    v90 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v17 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      PsGetThreadId(*(PETHREAD *)v93);
      v18 = a2;
      if ( a2 )
        PsGetThreadId(*(PETHREAD *)a2);
      v19 = W32GetUserSessionState(v18);
      LOBYTE(v20) = v90;
      LOBYTE(v21) = v88;
      WPP_RECORDER_AND_TRACE_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v21, v20, *(_QWORD *)(v19 + 69152));
    }
    v22 = WPP_GLOBAL_Control;
    v23 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v89 = v23;
    LOBYTE(v22) = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    v91 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v23 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v24 = W32GetUserSessionState(v22);
      LOBYTE(v25) = v91;
      LOBYTE(v26) = v89;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v26,
        v25,
        *(_QWORD *)(v24 + 69152),
        4,
        2,
        93,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        a3);
    }
    *(_QWORD *)(W32GetUserSessionState(v22) + 18928) = 0;
    v27 = WPP_GLOBAL_Control;
    v28 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v29 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v28 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v30 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v31) = v29;
      LOBYTE(v32) = v28;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v32,
        v31,
        *(_QWORD *)(v30 + 69152),
        4,
        2,
        94,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v34 = 0;
    if ( !*(_QWORD *)(W32GetUserSessionState(v27) + 18984)
      || (_InterlockedCompareExchange(
            (volatile signed __int32 *)(*(_QWORD *)(W32GetUserSessionState(v33) + 18984) + 520LL),
            0,
            0)
        & 1) != 0 )
    {
      v35 = 0;
    }
    else
    {
      v35 = *(_QWORD *)(W32GetUserSessionState(0) + 18984);
      Win32RawLockedW32Thread::ManualLock((ULONG_PTR)v104, v35);
    }
    if ( a1 )
    {
      v100 = a1[2];
      SetNewForegroundQueue(*(_QWORD *)(v100 + 464), (a3 & 0x200 | 0x100) >> 8);
      Win32RawLockedW32Thread::ManualLock((ULONG_PTR)v102, v100);
      v36 = (struct tagTHREADINFO *)a1[2];
      v37 = (struct tagWND *)a1;
    }
    else
    {
      v100 = 0;
      ResetForegroundQueue(1);
      v36 = 0;
      v37 = 0;
    }
    xxxSetForegroundThreadWithWindowHint(v36, v37);
    if ( (a3 & 0x20) == 0 )
    {
      if ( *(_QWORD *)(W32GetUserSessionState(v38) + 18968) )
      {
        v40 = *(_QWORD *)(W32GetUserSessionState(v39) + 18968);
        LODWORD(v110) = *(_DWORD *)(v40 + 544);
        v39 = *(_QWORD *)(W32GetUserSessionState(v40) + 18968);
        HIDWORD(v110) = *(_DWORD *)(v39 + 548);
      }
      if ( *(_QWORD *)(W32GetUserSessionState(v39) + 18976) )
      {
        v43 = *(_QWORD *)(W32GetUserSessionState(v41) + 18976);
        LODWORD(v108) = *(_DWORD *)(v43 + 544);
        HIDWORD(v108) = *(_DWORD *)(*(_QWORD *)(W32GetUserSessionState(v43) + 18976) + 548LL);
      }
      if ( !UIPrivilegeIsolation::CheckAccess((UIPrivilegeIsolation *)&v110, (const struct tagUIPI_INFO *)&v108, v42) )
      {
        ClearKeyboardToggleStates();
        v38 = *(_QWORD **)(W32GetUserSessionState(v44) + 19216);
        if ( *((_QWORD **)v93 + 61) == v38 )
        {
          v45 = (_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v38) + 19216) + 176LL);
          v38 = (_QWORD *)*v45;
          if ( (_QWORD *)*v45 != v45 )
          {
            si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            do
            {
              v47 = (__m128i *)*(v38 - 38);
              v47[20] = si128;
              v47[21] = si128;
              v47[31].m128i_i32[3] |= 1u;
              v38 = (_QWORD *)*v38;
            }
            while ( v38 != v45 );
          }
        }
      }
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v38) + 18968) )
    {
      v49 = *(_QWORD *)(W32GetUserSessionState(v48) + 18968);
      if ( v49 != *(_QWORD *)(W32GetUserSessionState(v50) + 18976) )
      {
        v48 = *(_QWORD *)(W32GetUserSessionState(v48) + 18968);
        if ( *(_QWORD *)(v48 + 120) )
        {
          v48 = *(unsigned int *)(W32GetUserSessionState(v48) + 66792);
          if ( (v48 & 0x80u) == 0LL )
            xxxApplyGlobalInputSettings(v48);
        }
      }
    }
    v51 = *(_QWORD *)(W32GetUserSessionState(v48) + 18968);
    if ( v51 == *(_QWORD *)(W32GetUserSessionState(v52) + 18976) )
      goto LABEL_153;
    if ( *(_QWORD *)(W32GetUserSessionState(v53) + 18976) )
    {
      v54 = *(_QWORD *)(W32GetUserSessionState(v54) + 18976);
      if ( *(_QWORD *)(v54 + 120) )
      {
        v55 = W32GetUserSessionState(v54);
        zzzInputFocusLostWindowEvent(*(_QWORD *)(*(_QWORD *)(v55 + 18976) + 120LL), 1);
      }
    }
    if ( *(_QWORD *)(W32GetUserSessionState(v54) + 18968)
      && *(_QWORD *)(*(_QWORD *)(W32GetUserSessionState(v56) + 18968) + 120LL) )
    {
      zzzInputFocusReceivedWindowEvent(1);
    }
    v57 = a2;
    if ( a2 )
    {
      xxxCancelTracking();
      v59 = W32GetUserSessionState(v58);
      CCursorClip::ClearClip(*(CCursorClip **)(v59 + 36072));
      v57 = a2;
    }
    v60 = 0;
    if ( v35 && (_InterlockedCompareExchange((volatile signed __int32 *)(v35 + 520), 0, 0) & 1) == 0 )
      v60 = *(_QWORD *)(v35 + 464);
    if ( v57 )
      v34 = *(_QWORD *)(v57 + 464);
    v98 = 0;
    if ( v60 )
    {
      if ( v60 != v34 )
      {
        v98 = (struct tagQMSG *)AllocQEntryEx(v60 + 24, 0, 1);
        if ( !v98 )
          goto LABEL_89;
      }
      if ( v60 != v34 )
      {
        v62 = 0;
        if ( a1 )
        {
          TopLevelWindow = (const struct tagWND *)GetTopLevelWindow(a1);
          v94 = TopLevelWindow;
          if ( TopLevelWindow )
          {
            if ( (unsigned int)CoreWindowProp::IsComponent(TopLevelWindow) )
              v62 = CoreWindowProp::IsHostThreadOf((const struct tagTHREADINFO *)v35, v94) != 0;
          }
        }
        v64 = *(_QWORD *)(PtiKbdFromQ(v60) + 456);
        v95 = *(_DWORD *)(v64 + 268);
        if ( *(_QWORD *)(W32GetUserSessionState(v64) + 18984) )
        {
          v66 = W32GetUserSessionState(v65);
          ThreadId = PsGetThreadId(**(PETHREAD **)(v66 + 18984));
        }
        else
        {
          ThreadId = 0;
        }
        StoreQMessage(
          v98,
          0,
          0,
          (unsigned __int64)ThreadId,
          0,
          0,
          0,
          5u,
          v62,
          0,
          (const struct tagINPUT_MESSAGE_SOURCE *)&v101,
          v95,
          0,
          0);
        if ( v35 )
        {
          *((_QWORD *)v98 + 13) = v35;
          SetWakeBit(v35, 8256);
        }
        v68 = *(const struct tagWND **)(v60 + 128);
        if ( v68 && IsHungWindow(v68) )
          ProcessHungWindow(*(struct tagWND **)(v60 + 128));
      }
    }
    v69 = 0;
    if ( v100 && (_InterlockedCompareExchange((volatile signed __int32 *)(v100 + 520), 0, 0) & 1) == 0 )
      v69 = *(_QWORD *)(v100 + 464);
    v70 = a2;
    v71 = 0;
    if ( a2 )
      v71 = *(_QWORD *)(a2 + 464);
    if ( v69 )
    {
      v99 = 0;
      if ( v69 != v71 )
      {
        v99 = (struct tagQMSG *)AllocQEntryEx(v69 + 24, 0, 1);
        if ( !v99 )
        {
LABEL_89:
          v61 = 0;
LABEL_154:
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v102);
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v104);
          Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
          return v61;
        }
      }
      v72 = anonymous_namespace_::RemoveEventMessage(v69, 5);
      if ( v69 == v71 )
      {
        if ( a1 == *(ULONG_PTR **)(v71 + 128) )
        {
          anonymous_namespace_::xxxSendNCActivateMessage((struct tagWND *)a1);
          anonymous_namespace_::xxxUpdateTray((struct tagWND *)a1);
          v74 = a3;
          if ( (a3 & 4) == 0 )
            xxxSetWindowPos((struct tagWND *)a1, 0, 0, 3);
        }
        else
        {
          v74 = a3;
          if ( (a3 & 1) == 0 )
          {
            if ( v35 )
              PsGetThreadId(*(PETHREAD *)v35);
            anonymous_namespace_::xxxLocalActivateWindow((struct tagWND *)a1);
            if ( (*(_DWORD *)(W32GetUserSessionState(v81) + 66788) & 1) != 0 )
              zzzActiveCursorTracking(a1);
            goto LABEL_153;
          }
        }
      }
      else
      {
        v73 = v71 == 0;
        v74 = a3;
        if ( !v73 || (a3 & 2) != 0 )
        {
          v75 = 0;
          if ( a1 )
            v75 = *a1;
        }
        else
        {
          v75 = 0;
        }
        if ( v72 )
          *(_DWORD *)(v69 + 508) |= 0x8000u;
        v77 = *(_DWORD *)(*(_QWORD *)(PtiKbdFromQ(v69) + 456) + 268LL);
        v96 = v77;
        if ( (a3 & 1) != 0 )
        {
          v78 = (unsigned __int64)v76;
        }
        else
        {
          if ( v35 )
          {
            v79 = (unsigned int)PsGetThreadId(*(PETHREAD *)v35);
            v77 = v96;
            v76 = 0;
          }
          else
          {
            v79 = (unsigned int)v76;
          }
          v78 = v79;
        }
        StoreQMessage(
          v99,
          0,
          (a3 >> 2) & 1,
          v78,
          v75,
          (unsigned int)v76,
          (unsigned __int64)v76,
          6u,
          (unsigned __int64)v76,
          (unsigned int)v76,
          (const struct tagINPUT_MESSAGE_SOURCE *)&v101,
          v77,
          v76,
          (struct tagUIPI_INFO *)v76);
        *((_QWORD *)v99 + 13) = v100;
        SetWakeBit(v100, 8256);
        v80 = *(const struct tagWND **)(v69 + 128);
        if ( v80 && IsHungWindow(v80) )
          ProcessHungWindow(*(struct tagWND **)(v69 + 128));
      }
      if ( (v74 & 0x40) == 0 )
        xxxDeliverRestoreFocusMessage((struct tagWND *)a1);
      v70 = a2;
    }
    v82 = 0;
    if ( v35 && (_InterlockedCompareExchange((volatile signed __int32 *)(v35 + 520), 0, 0) & 1) == 0 )
      v82 = *(_QWORD *)(v35 + 464);
    v83 = 0;
    if ( v70 )
      v83 = *(_QWORD *)(v70 + 464);
    if ( v82 && v82 == v83 )
    {
      v84 = 0;
      if ( a1 )
      {
        v85 = (const struct tagWND *)GetTopLevelWindow(a1);
        v86 = v85;
        if ( v85 && (unsigned int)CoreWindowProp::IsComponent(v85) )
          v84 = CoreWindowProp::IsHostThreadOf((const struct tagTHREADINFO *)v35, v86) != 0;
        v87 = (unsigned int)PsGetThreadId(*(PETHREAD *)a1[2]);
      }
      else
      {
        v87 = 0;
      }
      xxxDeactivate(a2, v87, v84);
    }
LABEL_153:
    v61 = 1;
    goto LABEL_154;
  }
  v11 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v12 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v11 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v13 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v14) = v12;
    LOBYTE(v15) = v11;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v15,
      v14,
      *(_QWORD *)(v13 + 69152),
      4,
      2,
      90,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v102);
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)v104);
  Win32RawLockedItemBase<_W32THREAD,0,1,1,1>::UnlockWorker((ULONG_PTR)BugCheckParameter2);
  return 0;
}

```

## disassembly

```asm
0x140271cc4  mov     [rsp-8+arg_10], rbx
0x140271cc9  push    rbp
0x140271cca  push    rsi
0x140271ccb  push    rdi
0x140271ccc  push    r12
0x140271cce  push    r13
0x140271cd0  push    r14
0x140271cd2  push    r15
0x140271cd4  lea     rbp, [rsp-20h]
0x140271cd9  sub     rsp, 120h
0x140271ce0  mov     rax, cs:__security_cookie
0x140271ce7  xor     rax, rsp
0x140271cea  mov     [rbp+50h+var_40], rax
0x140271cee  xorps   xmm0, xmm0
0x140271cf1  mov     [rsp+150h+var_DC], r8d
0x140271cf6  movups  xmmword ptr [rbp+50h+BugCheckParameter2], xmm0
0x140271cfa  mov     [rbp+50h+var_C8], rdx
0x140271cfe  mov     rsi, rcx
0x140271d01  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140271d05  xorps   xmm0, xmm0
0x140271d08  movups  xmmword ptr [rbp+50h+var_90], xmm0
0x140271d0c  mov     [rbp+50h+var_68], rcx
0x140271d10  mov     rbx, rdx
0x140271d13  xorps   xmm0, xmm0
0x140271d16  mov     [rbp+50h+var_80], rcx
0x140271d1a  movups  xmmword ptr [rbp+50h+var_A8], xmm0
0x140271d1e  mov     [rbp+50h+var_98], rcx
0x140271d22  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ
0x140271d27  mov     [rbp+50h+var_D0], rax
0x140271d2b  xor     eax, eax
0x140271d2d  mov     [rbp+50h+var_50], rax
0x140271d31  mov     [rbp+50h+var_48], eax
0x140271d34  mov     [rbp+50h+var_60], rax
0x140271d38  mov     [rbp+50h+var_58], eax
0x140271d3b  mov     [rbp+50h+var_B0], 0
0x140271d43  call    Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline
0x140271d48  lea     rcx, [rbp+50h+var_B0]
0x140271d4c  call    cs:__imp_SetSystemInputSource
0x140271d53  nop     dword ptr [rax+rax+00h]
0x140271d58  test    rsi, rsi
0x140271d5b  jz      loc_140271EF8
0x140271d61  call    cs:__imp_W32GetUserSessionState
0x140271d68  nop     dword ptr [rax+rax+00h]
0x140271d6d  mov     rcx, [rax+4B10h]
0x140271d74  cmp     [rsi+18h], rcx
0x140271d78  jnz     loc_140271E39
0x140271d7e  mov     rax, [rsi+28h]
0x140271d82  cmp     byte ptr [rax+13h], 0
0x140271d86  jl      loc_140271E39
0x140271d8c  mov     rcx, rsi
0x140271d8f  call    IsWindowUnderActiveLockScreen
0x140271d94  test    eax, eax
0x140271d96  jz      loc_140271EF8
0x140271d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140271da3  lea     rbx, WPP_GLOBAL_Control
0x140271daa  mov     edi, 1
0x140271daf  mov     r12b, 4
0x140271db2  lea     r15d, [rdi+1]
0x140271db6  cmp     rcx, rbx
0x140271db9  jz      short loc_140271DCE
0x140271dbb  mov     eax, [rcx+2Ch]
0x140271dbe  test    r15b, al
0x140271dc1  jz      short loc_140271DCE
0x140271dc3  cmp     [rcx+29h], r12b
0x140271dc7  jb      short loc_140271DCE
0x140271dc9  mov     bl, dil
0x140271dcc  jmp     short loc_140271DD0
0x140271dce  xor     bl, bl
0x140271dd0  lea     r14, WPP_RECORDER_INITIALIZED
0x140271dd7  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140271dde  setnz   sil
0x140271de2  test    bl, bl
0x140271de4  jnz     short loc_140271DEF
0x140271de6  test    sil, sil
0x140271de9  jz      loc_14027249E
0x140271def  call    cs:__imp_W32GetUserSessionState
0x140271df6  nop     dword ptr [rax+rax+00h]
0x140271dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140271e02  lea     r13, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271e09  mov     qword ptr [rsp+150h+var_118], r13
0x140271e0e  mov     r8b, sil
0x140271e11  mov     word ptr [rsp+150h+var_120], 5Bh ; '['
0x140271e18  mov     dl, bl
0x140271e1a  mov     r9, [rax+10E20h]
0x140271e21  mov     rcx, [rcx+18h]
0x140271e25  mov     [rsp+150h+var_128], r15d
0x140271e2a  mov     byte ptr [rsp+150h+var_130], r12b
0x140271e2f  call    WPP_RECORDER_AND_TRACE_SF_
0x140271e34  jmp     loc_14027249E
0x140271e39  mov     rcx, cs:WPP_GLOBAL_Control
0x140271e40  lea     rbx, WPP_GLOBAL_Control
0x140271e47  mov     edi, 1
0x140271e4c  mov     r12b, 4
0x140271e4f  lea     r15d, [rdi+1]
0x140271e53  cmp     rcx, rbx
0x140271e56  jz      short loc_140271E6B
0x140271e58  mov     eax, [rcx+2Ch]
0x140271e5b  test    r15b, al
0x140271e5e  jz      short loc_140271E6B
0x140271e60  cmp     [rcx+29h], r12b
0x140271e64  jb      short loc_140271E6B
0x140271e66  mov     bl, dil
0x140271e69  jmp     short loc_140271E6D
0x140271e6b  xor     bl, bl
0x140271e6d  lea     r14, WPP_RECORDER_INITIALIZED
0x140271e74  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140271e7b  setnz   sil
0x140271e7f  test    bl, bl
0x140271e81  jnz     short loc_140271E88
0x140271e83  test    sil, sil
0x140271e86  jz      short loc_140271ECD
0x140271e88  call    cs:__imp_W32GetUserSessionState
0x140271e8f  nop     dword ptr [rax+rax+00h]
0x140271e94  mov     rcx, cs:WPP_GLOBAL_Control
0x140271e9b  lea     r13, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271ea2  mov     qword ptr [rsp+150h+var_118], r13
0x140271ea7  mov     r8b, sil
0x140271eaa  mov     word ptr [rsp+150h+var_120], 5Ah ; 'Z'
0x140271eb1  mov     dl, bl
0x140271eb3  mov     r9, [rax+10E20h]
0x140271eba  mov     rcx, [rcx+18h]
0x140271ebe  mov     [rsp+150h+var_128], r15d
0x140271ec3  mov     byte ptr [rsp+150h+var_130], r12b
0x140271ec8  call    WPP_RECORDER_AND_TRACE_SF_
0x140271ecd  mov     dl, dil
0x140271ed0  lea     rcx, [rbp+50h+var_A8]; BugCheckParameter2
0x140271ed4  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x140271ed9  mov     dl, dil
0x140271edc  lea     rcx, [rbp+50h+var_90]; BugCheckParameter2
0x140271ee0  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x140271ee5  mov     dl, dil
0x140271ee8  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x140271eec  call    ?UnlockWorker@?$Win32RawLockedItemBase@U_W32THREAD@@$0A@$00$00$00@@AEAAX_N0@Z
0x140271ef1  xor     eax, eax
0x140271ef3  jmp     loc_1402728F9
0x140271ef8  mov     edi, 1
0x140271efd  test    rbx, rbx
0x140271f00  jz      short loc_140271F0E
0x140271f02  mov     rdx, rbx; BugCheckParameter3
0x140271f05  lea     rcx, [rbp+50h+BugCheckParameter2]; BugCheckParameter2
0x140271f09  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x140271f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140271f15  lea     rbx, WPP_GLOBAL_Control
0x140271f1c  mov     r12b, 4
0x140271f1f  mov     r15d, 2
0x140271f25  cmp     rcx, rbx
0x140271f28  jz      short loc_140271F3D
0x140271f2a  mov     eax, [rcx+2Ch]
0x140271f2d  test    r15b, al
0x140271f30  jz      short loc_140271F3D
0x140271f32  cmp     [rcx+29h], r12b
0x140271f36  jb      short loc_140271F3D
0x140271f38  mov     al, dil
0x140271f3b  jmp     short loc_140271F3F
0x140271f3d  xor     al, al
0x140271f3f  lea     r14, WPP_RECORDER_INITIALIZED
0x140271f46  mov     [rsp+150h+var_E0], al
0x140271f4a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140271f51  lea     r13, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x140271f58  setnz   cl
0x140271f5b  mov     [rsp+150h+var_DF], cl
0x140271f5f  test    al, al
0x140271f61  jnz     short loc_140271F6B
0x140271f63  test    cl, cl
0x140271f65  jz      loc_140271FF9
0x140271f6b  mov     rcx, [rbp+50h+var_D0]
0x140271f6f  mov     rcx, [rcx]; Thread
0x140271f72  call    cs:__imp_PsGetThreadId
0x140271f79  nop     dword ptr [rax+rax+00h]
0x140271f7e  mov     rcx, [rbp+50h+var_C8]
0x140271f82  mov     [rbp+50h+var_C0], rax
0x140271f86  test    rcx, rcx
0x140271f89  jz      short loc_140271FA0
0x140271f8b  mov     rcx, [rcx]; Thread
0x140271f8e  call    cs:__imp_PsGetThreadId
0x140271f95  nop     dword ptr [rax+rax+00h]
0x140271f9a  mov     [rbp+50h+var_B8], rax
0x140271f9e  jmp     short loc_140271FA7
0x140271fa0  mov     dword ptr [rbp+50h+var_B8], 0
0x140271fa7  call    cs:__imp_W32GetUserSessionState
0x140271fae  nop     dword ptr [rax+rax+00h]
0x140271fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140271fba  mov     r8b, [rsp+150h+var_DF]
0x140271fbf  mov     dl, [rsp+150h+var_E0]
0x140271fc3  mov     r9, [rax+10E20h]
0x140271fca  mov     rax, [rbp+50h+var_C0]
0x140271fce  mov     rcx, [rcx+18h]
0x140271fd2  mov     dword ptr [rsp+150h+var_100], eax
0x140271fd6  mov     rax, [rbp+50h+var_B8]
0x140271fda  mov     [rsp+150h+var_108], eax
0x140271fde  mov     [rsp+150h+var_110], rsi
0x140271fe3  mov     qword ptr [rsp+150h+var_118], r13
0x140271fe8  mov     word ptr [rsp+150h+var_120], 5Ch ; '\'
0x140271fef  mov     [rsp+150h+var_128], r15d
0x140271ff4  call    WPP_RECORDER_AND_TRACE_SF_qDD
0x140271ff9  mov     rcx, cs:WPP_GLOBAL_Control
0x140272000  cmp     rcx, rbx
0x140272003  jz      short loc_140272018
0x140272005  mov     eax, [rcx+2Ch]
0x140272008  test    r15b, al
0x14027200b  jz      short loc_140272018
0x14027200d  cmp     [rcx+29h], r12b
0x140272011  jb      short loc_140272018
0x140272013  mov     al, dil
0x140272016  jmp     short loc_14027201A
0x140272018  xor     al, al
0x14027201a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140272021  mov     [rsp+150h+var_E0], al
0x140272025  setnz   cl
0x140272028  mov     [rsp+150h+var_DF], cl
0x14027202c  test    al, al
0x14027202e  jnz     short loc_140272034
0x140272030  test    cl, cl
0x140272032  jz      short loc_14027207E
0x140272034  call    cs:__imp_W32GetUserSessionState
0x14027203b  nop     dword ptr [rax+rax+00h]
0x140272040  mov     rcx, cs:WPP_GLOBAL_Control
0x140272047  mov     r8b, [rsp+150h+var_DF]
0x14027204c  mov     dl, [rsp+150h+var_E0]
0x140272050  mov     r9, [rax+10E20h]
0x140272057  mov     eax, [rsp+150h+var_DC]
0x14027205b  mov     rcx, [rcx+18h]
0x14027205f  mov     dword ptr [rsp+150h+var_110], eax
0x140272063  mov     qword ptr [rsp+150h+var_118], r13
0x140272068  mov     word ptr [rsp+150h+var_120], 5Dh ; ']'
0x14027206f  mov     [rsp+150h+var_128], r15d
0x140272074  mov     byte ptr [rsp+150h+var_130], r12b
0x140272079  call    WPP_RECORDER_AND_TRACE_SF_D
0x14027207e  call    cs:__imp_W32GetUserSessionState
0x140272085  nop     dword ptr [rax+rax+00h]
0x14027208a  mov     qword ptr [rax+49F0h], 0
0x140272095  mov     rcx, cs:WPP_GLOBAL_Control
0x14027209c  cmp     rcx, rbx
0x14027209f  jz      short loc_1402720B4
0x1402720a1  mov     eax, [rcx+2Ch]
0x1402720a4  test    r15b, al
0x1402720a7  jz      short loc_1402720B4
0x1402720a9  cmp     [rcx+29h], r12b
0x1402720ad  jb      short loc_1402720B4
0x1402720af  mov     bl, dil
0x1402720b2  jmp     short loc_1402720B6
0x1402720b4  xor     bl, bl
0x1402720b6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1402720bd  setnz   r14b
0x1402720c1  test    bl, bl
0x1402720c3  jnz     short loc_1402720CA
0x1402720c5  test    r14b, r14b
0x1402720c8  jz      short loc_140272108
0x1402720ca  call    cs:__imp_W32GetUserSessionState
0x1402720d1  nop     dword ptr [rax+rax+00h]
0x1402720d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1402720dd  mov     r8b, r14b
0x1402720e0  mov     qword ptr [rsp+150h+var_118], r13
0x1402720e5  mov     dl, bl
0x1402720e7  mov     word ptr [rsp+150h+var_120], 5Eh ; '^'
0x1402720ee  mov     r9, [rax+10E20h]
0x1402720f5  mov     rcx, [rcx+18h]
0x1402720f9  mov     [rsp+150h+var_128], r15d
0x1402720fe  mov     byte ptr [rsp+150h+var_130], r12b
0x140272103  call    WPP_RECORDER_AND_TRACE_SF_
0x140272108  call    cs:__imp_W32GetUserSessionState
0x14027210f  nop     dword ptr [rax+rax+00h]
0x140272114  xor     r13d, r13d
0x140272117  cmp     [rax+4A28h], r13
0x14027211e  jz      short loc_140272166
0x140272120  call    cs:__imp_W32GetUserSessionState
0x140272127  nop     dword ptr [rax+rax+00h]
0x14027212c  mov     ecx, r13d
0x14027212f  mov     rdx, [rax+4A28h]
0x140272136  xor     eax, eax
0x140272138  lock cmpxchg [rdx+208h], ecx
0x140272140  test    dil, al
0x140272143  jnz     short loc_140272166
0x140272145  call    cs:__imp_W32GetUserSessionState
0x14027214c  nop     dword ptr [rax+rax+00h]
0x140272151  lea     rcx, [rbp+50h+var_90]; BugCheckParameter2
0x140272155  mov     r14, [rax+4A28h]
0x14027215c  mov     rdx, r14; BugCheckParameter3
0x14027215f  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x140272164  jmp     short loc_140272169
0x140272166  mov     r14, r13
0x140272169  test    rsi, rsi
0x14027216c  jz      short loc_1402721A8
0x14027216e  mov     rbx, [rsi+10h]
0x140272172  mov     edx, [rsp+150h+var_DC]
0x140272176  and     edx, 200h
0x14027217c  mov     [rbp+50h+var_B8], rbx
0x140272180  bts     edx, 8
0x140272184  mov     rcx, [rbx+1D0h]
0x14027218b  shr     edx, 8
0x14027218e  call    ?SetNewForegroundQueue@@YAXPEAUtagQ@@W4SetFgQueueOption@@@Z
0x140272193  mov     rdx, rbx; BugCheckParameter3
0x140272196  lea     rcx, [rbp+50h+var_A8]; BugCheckParameter2
0x14027219a  call    ?ManualLock@Win32RawLockedW32Thread@@QEAAXPEAU_W32THREAD@@@Z
0x14027219f  mov     rcx, [rsi+10h]
0x1402721a3  mov     rdx, rsi
0x1402721a6  jmp     short loc_1402721B9
0x1402721a8  mov     ecx, edi
0x1402721aa  mov     [rbp+50h+var_B8], r13
0x1402721ae  call    ?ResetForegroundQueue@@YAXW4SetFgQueueOption@@@Z
  ... truncated ...
```
