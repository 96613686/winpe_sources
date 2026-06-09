# xxxSetForegroundWindowWithOptions(tagWND *,ForegroundChangeAllowPolicy,SetForegroundBehaviors,SetForegroundEffects)

- ea: `0x14016f3c4`
- end: `0x140170139`
- name: `?xxxSetForegroundWindowWithOptions@@YA_NPEAUtagWND@@W4ForegroundChangeAllowPolicy@@W4SetForegroundBehaviors@@W4SetForegroundEffects@@@Z`
- size: `3445`
- prototype: ``
- caller_count: `17`
- callee_count: `25`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140082c80`
- `0x1400ebc3c`
- `0x14016cec0`
- `0x14016f330`
- `0x140170140`
- `0x140170590`
- `0x14018597c`
- `0x1401bafd4`
- `0x14021c534`
- `0x14023a36c`
- `0x140271570`
- `0x1402780f0`
- `0x14028a24c`
- `0x14029dd24`
- `0x1402c1e00`
- `0x1402c9150`
- `0x1402e96cc`

## callees

- `0x140007e18`
- `0x14000a36c`
- `0x1400191c8`
- `0x140020840`
- `0x140023570`
- `0x140026ce0`
- `0x140026dbc`
- `0x1400c0e10`
- `0x1400cb390`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x14016ccb4`
- `0x14016e684`
- `0x14016f3c4`
- `0x140172e04`
- `0x14017aef0`
- `0x140189cec`
- `0x1401bbe78`
- `0x1401ff224`
- `0x140241890`
- `0x140246f54`
- `0x1402655e8`
- `0x140271cc4`
- `0x1402938dc`
- `0x1402aadd4`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14016f48b`
- `ntoskrnl!PsGetThreadId` at `0x14016f4a0`
- `ntoskrnl!PsGetThreadId` at `0x14016fa06`
- `ntoskrnl!PsGetThreadId` at `0x14016fa1b`
- `ntoskrnl!PsGetThreadId` at `0x14016f48b`
- `ntoskrnl!PsGetThreadId` at `0x14016f4a0`
- `ntoskrnl!PsGetThreadId` at `0x14016fa06`
- `ntoskrnl!PsGetThreadId` at `0x14016fa1b`
- `win32kbase!UPDWORDPointer` at `0x14016fb84`
- `win32kbase!UPDWORDPointer` at `0x14016fb84`
- `WIN32K!W32GetUserSessionState` at `0x14016f3f5`
- `WIN32K!W32GetUserSessionState` at `0x14016f4af`
- `WIN32K!W32GetUserSessionState` at `0x14016f599`
- `WIN32K!W32GetUserSessionState` at `0x14016f612`
- `WIN32K!W32GetUserSessionState` at `0x14016f67c`
- `WIN32K!W32GetUserSessionState` at `0x14016f70b`
- `WIN32K!W32GetUserSessionState` at `0x14016f7f8`
- `WIN32K!W32GetUserSessionState` at `0x14016f89d`
- `WIN32K!W32GetUserSessionState` at `0x14016f91b`
- `WIN32K!W32GetUserSessionState` at `0x14016fa2a`
- `WIN32K!W32GetUserSessionState` at `0x14016faba`
- `WIN32K!W32GetUserSessionState` at `0x14016fc14`
- `WIN32K!W32GetUserSessionState` at `0x14016fccb`
- `WIN32K!W32GetUserSessionState` at `0x14016fd69`
- `WIN32K!W32GetUserSessionState` at `0x14016fdf9`
- `WIN32K!W32GetUserSessionState` at `0x14016fec2`
- `WIN32K!W32GetUserSessionState` at `0x14016ff67`
- `WIN32K!W32GetUserSessionState` at `0x14016fffb`
- `WIN32K!W32GetUserSessionState` at `0x140170082`
- `WIN32K!W32GetUserSessionState` at `0x14016f3f5`
- `WIN32K!W32GetUserSessionState` at `0x14016f4af`
- `WIN32K!W32GetUserSessionState` at `0x14016f599`
- `WIN32K!W32GetUserSessionState` at `0x14016f612`
- `WIN32K!W32GetUserSessionState` at `0x14016f67c`
- `WIN32K!W32GetUserSessionState` at `0x14016f70b`
- `WIN32K!W32GetUserSessionState` at `0x14016f7f8`
- `WIN32K!W32GetUserSessionState` at `0x14016f89d`
- `WIN32K!W32GetUserSessionState` at `0x14016f91b`
- `WIN32K!W32GetUserSessionState` at `0x14016fa2a`
- `WIN32K!W32GetUserSessionState` at `0x14016faba`
- `WIN32K!W32GetUserSessionState` at `0x14016fc14`
- `WIN32K!W32GetUserSessionState` at `0x14016fccb`
- `WIN32K!W32GetUserSessionState` at `0x14016fd69`
- `WIN32K!W32GetUserSessionState` at `0x14016fdf9`
- `WIN32K!W32GetUserSessionState` at `0x14016fec2`
- `WIN32K!W32GetUserSessionState` at `0x14016ff67`
- `WIN32K!W32GetUserSessionState` at `0x14016fffb`
- `WIN32K!W32GetUserSessionState` at `0x140170082`

## string_xrefs

- `0x14016f81a`: `Remove`

## pseudocode

```c
char __fastcall xxxSetForegroundWindowWithOptions(struct tagWND *a1, __int64 a2, __int16 a3, char a4)
{
  char v4; // bp
  struct tagWND *v5; // r14
  char v6; // r13
  ULONG_PTR v7; // rcx
  __int64 v8; // rax
  struct tagTHREADINFO *v9; // rbx
  bool v10; // r15
  bool v11; // r12
  __int64 v12; // rcx
  __int64 UserSessionState; // rax
  int v14; // r8d
  int v15; // edx
  struct tagWND *v16; // rax
  struct MOVESIZEDATA *v17; // rcx
  __int64 v18; // r9
  struct tagWND *v19; // rsi
  bool v20; // r15
  bool v21; // r12
  __int64 v22; // rbx
  __int64 v23; // rdi
  __int64 v24; // rax
  int v25; // r8d
  int v26; // edx
  __int64 v27; // rax
  __int64 v28; // r15
  __int64 v29; // rsi
  bool v30; // bl
  bool v31; // di
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  bool v35; // bl
  bool v36; // di
  __int64 v37; // rax
  int v38; // r8d
  int v39; // edx
  __int64 v40; // r9
  const char *v41; // rax
  char v42; // si
  bool v43; // r15
  int v44; // esi
  __int16 v45; // r12
  bool v46; // di
  bool v47; // si
  __int64 v48; // rax
  int v49; // r8d
  int v50; // edx
  __int64 v51; // r9
  const char *v52; // rax
  bool v53; // bl
  bool v54; // di
  __int64 v55; // rax
  int v56; // r8d
  int v57; // edx
  ULONG_PTR v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 *v62; // rax
  bool v63; // r15
  bool v64; // r12
  char ThreadId; // di
  __int64 v66; // rsi
  char v67; // bl
  __int64 v68; // rcx
  __int64 v69; // rax
  int v70; // r8d
  int v71; // edx
  bool v72; // bl
  bool v73; // di
  __int64 v74; // rax
  int v75; // r8d
  int v76; // edx
  __int64 NonChildAncestor; // rax
  struct tagWND *TopLevelCreatorWindow; // rbx
  __int64 v79; // r9
  struct tagTHREADINFO *v80; // r15
  bool v81; // bl
  bool v82; // di
  __int64 v83; // rax
  int v84; // r8d
  int v85; // edx
  bool v86; // bl
  bool v87; // di
  __int64 v88; // rax
  int v89; // edx
  int v90; // r8d
  bool v91; // bl
  bool v92; // di
  __int64 v93; // rax
  int v94; // r8d
  int v95; // edx
  bool v96; // bl
  bool v97; // di
  __int64 v98; // rax
  int v99; // r8d
  int v100; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  char v102; // dl
  bool v103; // bl
  bool v104; // di
  __int64 v105; // rax
  int v106; // r8d
  int v107; // edx
  bool v108; // bl
  bool v109; // di
  __int64 v110; // rax
  int v111; // r8d
  int v112; // edx
  bool v113; // bl
  bool v114; // di
  __int64 v115; // rax
  int v116; // r8d
  int v117; // edx
  unsigned int v119; // [rsp+20h] [rbp-C8h]
  int v120; // [rsp+28h] [rbp-C0h]
  int v121; // [rsp+30h] [rbp-B8h]
  __int16 v122; // [rsp+30h] [rbp-B8h]
  int v123; // [rsp+38h] [rbp-B0h]
  bool v124; // [rsp+70h] [rbp-78h]
  char v125; // [rsp+71h] [rbp-77h]
  ULONG_PTR v126[2]; // [rsp+78h] [rbp-70h] BYREF
  struct tagTHREADINFO *v127; // [rsp+88h] [rbp-60h]
  ULONG_PTR BugCheckParameter3[11]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v129; // [rsp+F0h] [rbp+8h]
  bool v130; // [rsp+F0h] [rbp+8h]

  v4 = 1;
  v5 = a1;
  v125 = 1;
  v6 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(a1) + 18968);
  v8 = *((_QWORD *)v5 + 2);
  v126[0] = v7;
  v129 = *(_QWORD *)(v8 + 464);
  v124 = v129 == v7;
  v9 = PtiCurrent();
  v127 = v9;
  v10 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v11 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v10 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(**((PETHREAD **)v5 + 2));
    PsGetThreadId(*(PETHREAD *)v9);
    UserSessionState = W32GetUserSessionState(v12);
    LOBYTE(v14) = v11;
    LOBYTE(v15) = v10;
    WPP_RECORDER_AND_TRACE_SF_DqDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v15,
      v14,
      *(_QWORD *)(UserSessionState + 69152));
    v9 = v127;
  }
  BugCheckParameter3[1] = 0;
  BugCheckParameter3[0] = -1;
  v16 = _GhostWindowFromHungWindow(v5);
  v19 = v16;
  if ( v16 )
  {
    Win32HM_LockIntoThread<0>(v9, v16, BugCheckParameter3, v18);
    v17 = WPP_GLOBAL_Control;
    v20 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v21 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v20 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v22 = *(_QWORD *)v5;
      v23 = *(_QWORD *)v19;
      v24 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v25) = v21;
      LOBYTE(v26) = v20;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v26,
        v25,
        *(_QWORD *)(v24 + 69152),
        4,
        2,
        73,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        v23,
        v22);
      v9 = v127;
    }
    v5 = v19;
  }
  if ( v129 == v126[0] )
  {
    v27 = W32GetUserSessionState(v17);
    v28 = *((_QWORD *)v9 + 58);
    v29 = *(_QWORD *)(v27 + 18968);
    v130 = v29 == v28;
    v30 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v31 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v30 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v32 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v33) = v31;
      LOBYTE(v34) = v30;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v34,
        v33,
        *(_QWORD *)(v32 + 69152),
        4,
        2,
        74,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v35 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v36 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v35 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v37 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v38) = v36;
      LOBYTE(v39) = v35;
      v40 = *(_QWORD *)(v37 + 69152);
      v41 = "Synchronously";
      if ( v29 != v28 )
        v41 = "Async";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v39,
        v38,
        v40,
        4,
        2,
        75,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        (__int64)v41);
    }
    v42 = v124;
    v43 = v130;
LABEL_106:
    v45 = a3;
    goto LABEL_107;
  }
  LODWORD(v126[0]) = anonymous_namespace_::CanSetForegroundWindow(v5);
  v44 = v126[0];
  if ( LODWORD(v126[0]) != 2 )
  {
    v125 = 0;
    v63 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v64 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v63 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)v5 + 2));
      v66 = *(_QWORD *)v5;
      v67 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)v9);
      v69 = W32GetUserSessionState(v68);
      LOBYTE(v70) = v64;
      LOBYTE(v71) = v63;
      WPP_RECORDER_AND_TRACE_SF_DqD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v71,
        v70,
        *(_QWORD *)(v69 + 69152),
        v119,
        v120,
        v121,
        v123,
        v67,
        v66,
        ThreadId);
      v44 = v126[0];
    }
    if ( (a4 & 1) != 0 )
    {
      v72 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v73 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v72 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v74 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v75) = v73;
        LOBYTE(v76) = v72;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v76,
          v75,
          *(_QWORD *)(v74 + 69152),
          4,
          2,
          79,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      }
      NonChildAncestor = GetNonChildAncestor(v5);
      TopLevelCreatorWindow = (struct tagWND *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(NonChildAncestor);
      if ( !(unsigned __int8)IsTrayWindow(TopLevelCreatorWindow, 1) )
        TopLevelCreatorWindow = v5;
      if ( *(_DWORD *)(*((_QWORD *)TopLevelCreatorWindow + 5) + 236LL) != 15 )
      {
        if ( !(unsigned int)IsImmersiveBandOrShellManaged(TopLevelCreatorWindow) )
        {
          v80 = v127;
          Win32HM_LockIntoThread<0>(v127, TopLevelCreatorWindow, v126, v79);
          UPDWORDPointer(8196);
          xxxFlashWindow(TopLevelCreatorWindow);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v126);
LABEL_95:
          if ( v44 == 1 )
          {
            v42 = v124;
            v43 = 0;
          }
          else
          {
            v42 = 1;
            v43 = *((_QWORD *)v80 + 58) == *(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL);
            v81 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            v82 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v81 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v83 = W32GetUserSessionState(WPP_GLOBAL_Control);
              LOBYTE(v84) = v82;
              LOBYTE(v85) = v81;
              WPP_RECORDER_AND_TRACE_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v85,
                v84,
                *(_QWORD *)(v83 + 69152),
                4,
                2,
                80,
                (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
            }
          }
          goto LABEL_106;
        }
        PostIAMShellHookMessage(0x22u, *(_QWORD *)TopLevelCreatorWindow);
      }
    }
    v80 = v127;
    goto LABEL_95;
  }
  v45 = a3;
  v46 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v47 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v46 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v48 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v49) = v47;
    LOBYTE(v50) = v46;
    v51 = *(_QWORD *)(v48 + 69152);
    v52 = "Remove";
    if ( (a3 & 0x1000) != 0 )
      v52 = "Preserve";
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v50,
      v49,
      v51,
      4,
      2,
      76,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
      (__int64)v52);
  }
  if ( (a3 & 0x1000) == 0 )
    anonymous_namespace_::RemoveForegroundActivate();
  v53 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v54 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v53 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v55 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v56) = v54;
    LOBYTE(v57) = v53;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v57,
      v56,
      *(_QWORD *)(v55 + 69152),
      4,
      2,
      77,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  v58 = (ULONG_PTR)v127;
  if ( (a3 & 0x400) != 0 )
    v58 = 0;
  if ( (unsigned int)xxxSetForegroundWindow2((ULONG_PTR *)v5, v58, a3 & 0x3FF) )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( *((_QWORD *)v127 + 61) != *(_QWORD *)(W32GetUserSessionState(v59) + 19216) )
    {
      v60 = *((_QWORD *)v5 + 5);
      if ( *(char *)(v60 + 19) >= 0 && *(_DWORD *)(v60 + 236) != 15 && (unsigned int)IsImmersiveBandOrShellManaged(v5) )
      {
        if ( (unsigned int)IAMThreadAccessGranted(v127) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2442);
        v61 = GetNonChildAncestor(v5);
        v62 = (__int64 *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(v61);
        PostIAMShellHookMessage(0x22u, *v62);
      }
    }
  }
  v42 = v124;
  v43 = 0;
LABEL_107:
  if ( (unsigned int)Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !v42 )
      goto LABEL_179;
    if ( (v45 & 0x400) != 0 )
    {
      v86 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v87 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v86 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v88 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v122 = 81;
LABEL_118:
        LOBYTE(v90) = v87;
        LOBYTE(v89) = v86;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v89,
          v90,
          *(_QWORD *)(v88 + 69152),
          4,
          2,
          v122,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        goto LABEL_179;
      }
      goto LABEL_179;
    }
  }
  else if ( !v42 )
  {
    goto LABEL_179;
  }
  v91 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v92 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v91 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v93 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v94) = v92;
    LOBYTE(v95) = v91;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v95,
      v94,
      *(_QWORD *)(v93 + 69152),
      4,
      2,
      82,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  if ( !v43 )
  {
    if ( v5 != *(struct tagWND **)(*(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL) + 128LL) )
    {
      if ( (*(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0) == 0x40 )
      {
        v108 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v109 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v108 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v110 = W32GetUserSessionState(WPP_GLOBAL_Control);
          LOBYTE(v111) = v109;
          LOBYTE(v112) = v108;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v112,
            v111,
            *(_QWORD *)(v110 + 69152),
            4,
            2,
            86,
            (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        }
      }
      v113 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v114 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v113 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v115 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v116) = v114;
        LOBYTE(v117) = v113;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v117,
          v116,
          *(_QWORD *)(v115 + 69152),
          4,
          2,
          87,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      }
      v6 = (unsigned int)PostEventMessageEx(
                           *((struct tagTHREADINFO **)v5 + 2),
                           *(struct tagQ **)(*((_QWORD *)v5 + 2) + 464LL),
                           6u,
                           0,
                           0,
                           0,
                           *(_QWORD *)v5,
                           0) != 0;
      goto LABEL_179;
    }
    v103 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v104 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v103 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v105 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v106) = v104;
      LOBYTE(v107) = v103;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v107,
        v106,
        *(_QWORD *)(v105 + 69152),
        4,
        2,
        85,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
LABEL_160:
    v6 = 1;
    goto LABEL_179;
  }
  v96 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v97 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v96 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v98 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v99) = v97;
    LOBYTE(v100) = v96;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v100,
      v99,
      *(_QWORD *)(v98 + 69152),
      4,
      2,
      83,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  IsEnabledDeviceUsageNoInline = Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  v102 = *(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0;
  if ( !IsEnabledDeviceUsageNoInline )
  {
    if ( v102 == 64 || !(unsigned __int8)anonymous_namespace_::xxxLocalActivateWindow(v5) )
    {
      v6 = 0;
      goto LABEL_179;
    }
    goto LABEL_160;
  }
  if ( v102 != 64 )
  {
    v6 = anonymous_namespace_::xxxLocalActivateWindow(v5);
    goto LABEL_179;
  }
  v86 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v87 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v86 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v88 = W32GetUserSessionState(WPP_GLOBAL_Control);
    v122 = 84;
    goto LABEL_118;
  }
LABEL_179:
  if ( !v125 || !v6 )
    v4 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  return v4;
}

```

## disassembly

```asm
0x14016f3c4  mov     [rsp+arg_18], r9d
0x14016f3c9  mov     [rsp+arg_10], r8d
0x14016f3ce  mov     [rsp+arg_8], edx
0x14016f3d2  push    rbx
0x14016f3d3  push    rbp
0x14016f3d4  push    rsi
0x14016f3d5  push    rdi
0x14016f3d6  push    r12
0x14016f3d8  push    r13
0x14016f3da  push    r14
0x14016f3dc  push    r15
0x14016f3de  sub     rsp, 0A8h
0x14016f3e5  mov     ebp, 1
0x14016f3ea  mov     r14, rcx
0x14016f3ed  mov     [rsp+0E8h+var_77], bpl
0x14016f3f2  xor     r13b, r13b
0x14016f3f5  call    cs:__imp_W32GetUserSessionState
0x14016f3fc  nop     dword ptr [rax+rax+00h]
0x14016f401  mov     rcx, [rax+4A18h]
0x14016f408  mov     rax, [r14+10h]
0x14016f40c  mov     [rsp+0E8h+var_70], rcx
0x14016f411  mov     rax, [rax+1D0h]
0x14016f418  cmp     rax, rcx
0x14016f41b  mov     [rsp+0E8h+arg_0], rax
0x14016f423  setz    [rsp+0E8h+var_78]
0x14016f428  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14016f42d  mov     rbx, rax
0x14016f430  mov     [rsp+0E8h+var_60], rax
0x14016f438  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f43f  lea     rax, WPP_GLOBAL_Control
0x14016f446  lea     edi, [rbp+1]
0x14016f449  cmp     rcx, rax
0x14016f44c  jz      short loc_14016F461
0x14016f44e  mov     eax, [rcx+2Ch]
0x14016f451  test    dil, al
0x14016f454  jz      short loc_14016F461
0x14016f456  cmp     byte ptr [rcx+29h], 4
0x14016f45a  jb      short loc_14016F461
0x14016f45c  mov     r15b, bpl
0x14016f45f  jmp     short loc_14016F464
0x14016f461  xor     r15b, r15b
0x14016f464  lea     rax, WPP_RECORDER_INITIALIZED
0x14016f46b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14016f472  setnz   r12b
0x14016f476  test    r15b, r15b
0x14016f479  jnz     short loc_14016F484
0x14016f47b  test    r12b, r12b
0x14016f47e  jz      loc_14016F508
0x14016f484  mov     rcx, [r14+10h]
0x14016f488  mov     rcx, [rcx]; Thread
0x14016f48b  call    cs:__imp_PsGetThreadId
0x14016f492  nop     dword ptr [rax+rax+00h]
0x14016f497  mov     rcx, [rbx]; Thread
0x14016f49a  mov     rdi, rax
0x14016f49d  mov     rsi, [r14]
0x14016f4a0  call    cs:__imp_PsGetThreadId
0x14016f4a7  nop     dword ptr [rax+rax+00h]
0x14016f4ac  mov     rbx, rax
0x14016f4af  call    cs:__imp_W32GetUserSessionState
0x14016f4b6  nop     dword ptr [rax+rax+00h]
0x14016f4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f4c2  mov     r8b, r12b
0x14016f4c5  mov     dl, r15b
0x14016f4c8  mov     r9, [rax+10E20h]
0x14016f4cf  mov     eax, [rsp+0E8h+arg_10]
0x14016f4d6  mov     rcx, [rcx+18h]
0x14016f4da  mov     [rsp+0E8h+var_88], eax
0x14016f4de  mov     eax, [rsp+0E8h+arg_8]
0x14016f4e5  mov     [rsp+0E8h+var_90], eax
0x14016f4e9  mov     [rsp+0E8h+var_98], edi
0x14016f4ed  mov     [rsp+0E8h+var_A0], rsi
0x14016f4f2  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x14016f4f6  call    WPP_RECORDER_AND_TRACE_SF_DqDDD
0x14016f4fb  mov     rbx, [rsp+0E8h+var_60]
0x14016f503  mov     edi, 2
0x14016f508  mov     rcx, r14; struct tagWND *
0x14016f50b  mov     [rsp+0E8h+var_50], 0
0x14016f517  mov     [rsp+0E8h+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x14016f523  call    ?_GhostWindowFromHungWindow@@YAPEAUtagWND@@PEBU1@@Z; _GhostWindowFromHungWindow(tagWND const *)
0x14016f528  lea     r12, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016f52f  mov     rsi, rax
0x14016f532  test    rax, rax
0x14016f535  jz      loc_14016F5FF
0x14016f53b  lea     r8, [rsp+0E8h+BugCheckParameter3]
0x14016f543  mov     rdx, rax
0x14016f546  mov     rcx, rbx
0x14016f549  call    ??$Win32HM_LockIntoThread@$0A@@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<0>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x14016f54e  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f555  lea     rax, WPP_GLOBAL_Control
0x14016f55c  cmp     rcx, rax
0x14016f55f  jz      short loc_14016F574
0x14016f561  mov     eax, [rcx+2Ch]
0x14016f564  test    dil, al
0x14016f567  jz      short loc_14016F574
0x14016f569  cmp     byte ptr [rcx+29h], 4
0x14016f56d  jb      short loc_14016F574
0x14016f56f  mov     r15b, bpl
0x14016f572  jmp     short loc_14016F577
0x14016f574  xor     r15b, r15b
0x14016f577  lea     rax, WPP_RECORDER_INITIALIZED
0x14016f57e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14016f585  setnz   r12b
0x14016f589  test    r15b, r15b
0x14016f58c  jnz     short loc_14016F593
0x14016f58e  test    r12b, r12b
0x14016f591  jz      short loc_14016F5F5
0x14016f593  mov     rbx, [r14]
0x14016f596  mov     rdi, [rsi]
0x14016f599  call    cs:__imp_W32GetUserSessionState
0x14016f5a0  nop     dword ptr [rax+rax+00h]
0x14016f5a5  mov     [rsp+0E8h+var_A0], rbx
0x14016f5aa  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016f5b1  mov     [rsp+0E8h+var_A8], rdi
0x14016f5b6  mov     r8b, r12b
0x14016f5b9  mov     [rsp+0E8h+var_B0], rcx
0x14016f5be  mov     edi, 2
0x14016f5c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f5ca  mov     dl, r15b
0x14016f5cd  mov     r9, [rax+10E20h]
0x14016f5d4  mov     word ptr [rsp+0E8h+var_B8], 49h ; 'I'
0x14016f5db  mov     dword ptr [rsp+0E8h+var_C0], edi
0x14016f5df  mov     rcx, [rcx+18h]
0x14016f5e3  mov     byte ptr [rsp+0E8h+var_C8], 4
0x14016f5e8  call    WPP_RECORDER_AND_TRACE_SF_qq
0x14016f5ed  mov     rbx, [rsp+0E8h+var_60]
0x14016f5f5  mov     r14, rsi
0x14016f5f8  lea     r12, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016f5ff  mov     rax, [rsp+0E8h+arg_0]
0x14016f607  cmp     rax, [rsp+0E8h+var_70]
0x14016f60c  jnz     loc_14016F77C
0x14016f612  call    cs:__imp_W32GetUserSessionState
0x14016f619  nop     dword ptr [rax+rax+00h]
0x14016f61e  mov     r15, [rbx+1D0h]
0x14016f625  mov     rsi, [rax+4A18h]
0x14016f62c  cmp     rsi, r15
0x14016f62f  setz    al
0x14016f632  mov     byte ptr [rsp+0E8h+arg_0], al
0x14016f639  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f640  lea     rax, WPP_GLOBAL_Control
0x14016f647  cmp     rcx, rax
0x14016f64a  jz      short loc_14016F65F
0x14016f64c  mov     eax, [rcx+2Ch]
0x14016f64f  test    dil, al
0x14016f652  jz      short loc_14016F65F
0x14016f654  cmp     byte ptr [rcx+29h], 4
0x14016f658  jb      short loc_14016F65F
0x14016f65a  mov     bl, bpl
0x14016f65d  jmp     short loc_14016F661
0x14016f65f  xor     bl, bl
0x14016f661  lea     rdx, WPP_RECORDER_INITIALIZED
0x14016f668  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14016f66f  setnz   dil
0x14016f673  test    bl, bl
0x14016f675  jnz     short loc_14016F67C
0x14016f677  test    dil, dil
0x14016f67a  jz      short loc_14016F6C9
0x14016f67c  call    cs:__imp_W32GetUserSessionState
0x14016f683  nop     dword ptr [rax+rax+00h]
0x14016f688  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f68f  mov     r8b, dil
0x14016f692  mov     [rsp+0E8h+var_B0], r12
0x14016f697  mov     dl, bl
0x14016f699  mov     word ptr [rsp+0E8h+var_B8], 4Ah ; 'J'
0x14016f6a0  mov     r12d, 2
0x14016f6a6  mov     r9, [rax+10E20h]
0x14016f6ad  mov     rcx, [rcx+18h]
0x14016f6b1  mov     dword ptr [rsp+0E8h+var_C0], r12d
0x14016f6b6  mov     byte ptr [rsp+0E8h+var_C8], 4
0x14016f6bb  call    WPP_RECORDER_AND_TRACE_SF_
0x14016f6c0  lea     rdx, WPP_RECORDER_INITIALIZED
0x14016f6c7  jmp     short loc_14016F6CF
0x14016f6c9  mov     r12d, 2
0x14016f6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f6d6  lea     rax, WPP_GLOBAL_Control
0x14016f6dd  cmp     rcx, rax
0x14016f6e0  jz      short loc_14016F6F5
0x14016f6e2  mov     eax, [rcx+2Ch]
0x14016f6e5  test    r12b, al
0x14016f6e8  jz      short loc_14016F6F5
0x14016f6ea  cmp     byte ptr [rcx+29h], 4
0x14016f6ee  jb      short loc_14016F6F5
0x14016f6f0  mov     bl, bpl
0x14016f6f3  jmp     short loc_14016F6F7
0x14016f6f5  xor     bl, bl
0x14016f6f7  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14016f6fe  setnz   dil
0x14016f702  test    bl, bl
0x14016f704  jnz     short loc_14016F70B
0x14016f706  test    dil, dil
0x14016f709  jz      short loc_14016F76A
0x14016f70b  call    cs:__imp_W32GetUserSessionState
0x14016f712  nop     dword ptr [rax+rax+00h]
0x14016f717  cmp     rsi, r15
0x14016f71a  lea     rcx, aAsync_0; "Async"
0x14016f721  mov     r8b, dil
0x14016f724  mov     dl, bl
0x14016f726  mov     r9, [rax+10E20h]
0x14016f72d  lea     rax, aSynchronously; "Synchronously"
0x14016f734  cmovnz  rax, rcx
0x14016f738  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f73f  mov     [rsp+0E8h+var_A8], rax
0x14016f744  lea     rax, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016f74b  mov     [rsp+0E8h+var_B0], rax
0x14016f750  mov     word ptr [rsp+0E8h+var_B8], 4Bh ; 'K'
0x14016f757  mov     rcx, [rcx+18h]
0x14016f75b  mov     dword ptr [rsp+0E8h+var_C0], r12d
0x14016f760  mov     byte ptr [rsp+0E8h+var_C8], 4
0x14016f765  call    WPP_RECORDER_AND_TRACE_SF_s
0x14016f76a  mov     sil, [rsp+0E8h+var_78]
0x14016f76f  mov     r15b, byte ptr [rsp+0E8h+arg_0]
0x14016f777  jmp     loc_14016FC5C
0x14016f77c  mov     edx, [rsp+0E8h+arg_8]
0x14016f783  xor     al, al
0x14016f785  mov     rcx, r14; struct tagWND *
0x14016f788  mov     byte ptr [rsp+0E8h+arg_0], al
0x14016f78f  call    _anonymous_namespace___CanSetForegroundWindow
0x14016f794  mov     dword ptr [rsp+0E8h+var_70], eax
0x14016f798  mov     esi, eax
0x14016f79a  cmp     eax, edi
0x14016f79c  jnz     loc_14016F9B5
0x14016f7a2  mov     r12d, [rsp+0E8h+arg_10]
0x14016f7aa  mov     ebx, r12d
0x14016f7ad  and     ebx, 1000h
0x14016f7b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f7ba  lea     r15, WPP_GLOBAL_Control
0x14016f7c1  cmp     rcx, r15
0x14016f7c4  jz      short loc_14016F7D9
0x14016f7c6  mov     eax, [rcx+2Ch]
0x14016f7c9  test    dil, al
0x14016f7cc  jz      short loc_14016F7D9
0x14016f7ce  cmp     byte ptr [rcx+29h], 4
0x14016f7d2  jb      short loc_14016F7D9
0x14016f7d4  mov     dil, bpl
0x14016f7d7  jmp     short loc_14016F7DC
0x14016f7d9  xor     dil, dil
0x14016f7dc  lea     r13, WPP_RECORDER_INITIALIZED
0x14016f7e3  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14016f7ea  setnz   sil
0x14016f7ee  test    dil, dil
0x14016f7f1  jnz     short loc_14016F7F8
0x14016f7f3  test    sil, sil
0x14016f7f6  jz      short loc_14016F85A
0x14016f7f8  call    cs:__imp_W32GetUserSessionState
0x14016f7ff  nop     dword ptr [rax+rax+00h]
0x14016f804  test    ebx, ebx
0x14016f806  lea     rcx, aPreserve; "Preserve"
0x14016f80d  mov     r8b, sil
0x14016f810  mov     dl, dil
0x14016f813  mov     r9, [rax+10E20h]
0x14016f81a  lea     rax, aRemove; "Remove"
0x14016f821  cmovnz  rax, rcx
0x14016f825  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f82c  mov     [rsp+0E8h+var_A8], rax
0x14016f831  lea     rax, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016f838  mov     [rsp+0E8h+var_B0], rax
0x14016f83d  mov     word ptr [rsp+0E8h+var_B8], 4Ch ; 'L'
0x14016f844  mov     rcx, [rcx+18h]
0x14016f848  mov     dword ptr [rsp+0E8h+var_C0], 2
0x14016f850  mov     byte ptr [rsp+0E8h+var_C8], 4
0x14016f855  call    WPP_RECORDER_AND_TRACE_SF_s
0x14016f85a  test    ebx, ebx
0x14016f85c  jnz     short loc_14016F863
0x14016f85e  call    _anonymous_namespace___RemoveForegroundActivate
0x14016f863  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f86a  mov     esi, 2
0x14016f86f  cmp     rcx, r15
0x14016f872  jz      short loc_14016F887
0x14016f874  mov     eax, [rcx+2Ch]
0x14016f877  test    sil, al
0x14016f87a  jz      short loc_14016F887
0x14016f87c  cmp     byte ptr [rcx+29h], 4
0x14016f880  jb      short loc_14016F887
0x14016f882  mov     bl, bpl
0x14016f885  jmp     short loc_14016F889
0x14016f887  xor     bl, bl
0x14016f889  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14016f890  setnz   dil
0x14016f894  test    bl, bl
0x14016f896  jnz     short loc_14016F89D
0x14016f898  test    dil, dil
0x14016f89b  jz      short loc_14016F8E1
0x14016f89d  call    cs:__imp_W32GetUserSessionState
0x14016f8a4  nop     dword ptr [rax+rax+00h]
0x14016f8a9  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016f8b0  mov     r8b, dil
0x14016f8b3  mov     [rsp+0E8h+var_B0], rcx
0x14016f8b8  mov     dl, bl
0x14016f8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x14016f8c1  mov     r9, [rax+10E20h]
0x14016f8c8  mov     word ptr [rsp+0E8h+var_B8], 4Dh ; 'M'
0x14016f8cf  mov     dword ptr [rsp+0E8h+var_C0], esi
0x14016f8d3  mov     rcx, [rcx+18h]
0x14016f8d7  mov     byte ptr [rsp+0E8h+var_C8], 4
0x14016f8dc  call    WPP_RECORDER_AND_TRACE_SF_
0x14016f8e1  mov     r15, [rsp+0E8h+var_60]
0x14016f8e9  mov     eax, 0
0x14016f8ee  mov     r8d, r12d
0x14016f8f1  bt      r12d, 0Ah
0x14016f8f6  mov     rdx, r15
0x14016f8f9  mov     rcx, r14
  ... truncated ...
```
