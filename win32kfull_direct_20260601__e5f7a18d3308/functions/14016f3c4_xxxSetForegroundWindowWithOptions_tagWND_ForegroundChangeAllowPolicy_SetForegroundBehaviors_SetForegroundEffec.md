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
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 UserSessionState; // rax
  int v15; // r8d
  int v16; // edx
  struct tagWND *v17; // rax
  __int64 v18; // rdx
  struct MOVESIZEDATA *v19; // rcx
  struct tagWND *v20; // rsi
  bool v21; // r15
  bool v22; // r12
  __int64 v23; // rbx
  __int64 v24; // rdi
  __int64 v25; // rax
  int v26; // r8d
  int v27; // edx
  __int64 v28; // rax
  __int64 v29; // r15
  __int64 v30; // rsi
  bool v31; // bl
  bool v32; // di
  __int64 v33; // rax
  int v34; // r8d
  int v35; // edx
  bool v36; // bl
  bool v37; // di
  __int64 v38; // rax
  int v39; // r8d
  int v40; // edx
  __int64 v41; // r9
  const char *v42; // rax
  char v43; // si
  bool v44; // r15
  __int64 v45; // rdx
  int v46; // esi
  __int16 v47; // r12
  bool v48; // di
  bool v49; // si
  __int64 v50; // rax
  int v51; // r8d
  int v52; // edx
  __int64 v53; // r9
  const char *v54; // rax
  bool v55; // bl
  bool v56; // di
  __int64 v57; // rax
  int v58; // r8d
  int v59; // edx
  ULONG_PTR v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 *v65; // rax
  struct MOVESIZEDATA **v66; // rdx
  bool v67; // r15
  bool v68; // r12
  char ThreadId; // di
  __int64 v70; // rsi
  char v71; // bl
  __int64 v72; // rdx
  __int64 v73; // rcx
  __int64 v74; // rax
  int v75; // r8d
  int v76; // edx
  bool v77; // bl
  bool v78; // di
  __int64 v79; // rax
  int v80; // r8d
  int v81; // edx
  __int64 NonChildAncestor; // rax
  struct tagWND *TopLevelCreatorWindow; // rbx
  struct tagTHREADINFO *v84; // r15
  bool v85; // bl
  bool v86; // di
  __int64 v87; // rax
  int v88; // r8d
  int v89; // edx
  __int64 v90; // rdx
  bool v91; // bl
  bool v92; // di
  __int64 v93; // rax
  int v94; // edx
  int v95; // r8d
  bool v96; // bl
  bool v97; // di
  __int64 v98; // rax
  int v99; // r8d
  int v100; // edx
  bool v101; // bl
  bool v102; // di
  __int64 v103; // rax
  int v104; // r8d
  int v105; // edx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v107; // rdx
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
  bool v118; // bl
  bool v119; // di
  __int64 v120; // rax
  int v121; // r8d
  int v122; // edx
  unsigned int v124; // [rsp+20h] [rbp-C8h]
  int v125; // [rsp+28h] [rbp-C0h]
  int v126; // [rsp+30h] [rbp-B8h]
  __int16 v127; // [rsp+30h] [rbp-B8h]
  int v128; // [rsp+38h] [rbp-B0h]
  bool v129; // [rsp+70h] [rbp-78h]
  char v130; // [rsp+71h] [rbp-77h]
  ULONG_PTR v131[2]; // [rsp+78h] [rbp-70h] BYREF
  struct tagTHREADINFO *v132; // [rsp+88h] [rbp-60h]
  ULONG_PTR BugCheckParameter3[11]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v134; // [rsp+F0h] [rbp+8h]
  bool v135; // [rsp+F0h] [rbp+8h]

  v4 = 1;
  v5 = a1;
  v130 = 1;
  v6 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(a1, a2) + 18968);
  v8 = *((_QWORD *)v5 + 2);
  v131[0] = v7;
  v134 = *(_QWORD *)(v8 + 464);
  v129 = v134 == v7;
  v9 = PtiCurrent();
  v132 = v9;
  v10 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v11 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v10 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(**((PETHREAD **)v5 + 2));
    PsGetThreadId(*(PETHREAD *)v9);
    UserSessionState = W32GetUserSessionState(v13, v12);
    LOBYTE(v15) = v11;
    LOBYTE(v16) = v10;
    WPP_RECORDER_AND_TRACE_SF_DqDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v16,
      v15,
      *(_QWORD *)(UserSessionState + 69152));
    v9 = v132;
  }
  BugCheckParameter3[1] = 0;
  BugCheckParameter3[0] = -1;
  v17 = _GhostWindowFromHungWindow(v5);
  v20 = v17;
  if ( v17 )
  {
    Win32HM_LockIntoThread<0>(v9, v17, BugCheckParameter3);
    v19 = WPP_GLOBAL_Control;
    v21 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v22 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v21 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v23 = *(_QWORD *)v5;
      v24 = *(_QWORD *)v20;
      v25 = W32GetUserSessionState(WPP_GLOBAL_Control, v18);
      LOBYTE(v26) = v22;
      LOBYTE(v27) = v21;
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v27,
        v26,
        *(_QWORD *)(v25 + 69152),
        4,
        2,
        73,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        v24,
        v23);
      v9 = v132;
    }
    v5 = v20;
  }
  if ( v134 == v131[0] )
  {
    v28 = W32GetUserSessionState(v19, v18);
    v29 = *((_QWORD *)v9 + 58);
    v30 = *(_QWORD *)(v28 + 18968);
    v135 = v30 == v29;
    v31 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v32 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v31 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v33 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
      LOBYTE(v34) = v32;
      LOBYTE(v35) = v31;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v35,
        v34,
        *(_QWORD *)(v33 + 69152),
        4,
        2,
        74,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v36 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v37 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v36 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v38 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED);
      LOBYTE(v39) = v37;
      LOBYTE(v40) = v36;
      v41 = *(_QWORD *)(v38 + 69152);
      v42 = "Synchronously";
      if ( v30 != v29 )
        v42 = "Async";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v40,
        v39,
        v41,
        4,
        2,
        75,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        (__int64)v42);
    }
    v43 = v129;
    v44 = v135;
LABEL_106:
    v47 = a3;
    goto LABEL_107;
  }
  LODWORD(v131[0]) = anonymous_namespace_::CanSetForegroundWindow(v5);
  v46 = v131[0];
  if ( LODWORD(v131[0]) != 2 )
  {
    v130 = 0;
    v66 = &WPP_GLOBAL_Control;
    v67 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v68 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v67 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ThreadId = (unsigned __int8)PsGetThreadId(**((PETHREAD **)v5 + 2));
      v70 = *(_QWORD *)v5;
      v71 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)v9);
      v74 = W32GetUserSessionState(v73, v72);
      LOBYTE(v75) = v68;
      LOBYTE(v76) = v67;
      WPP_RECORDER_AND_TRACE_SF_DqD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v76,
        v75,
        *(_QWORD *)(v74 + 69152),
        v124,
        v125,
        v126,
        v128,
        v71,
        v70,
        ThreadId);
      v46 = v131[0];
      v66 = &WPP_GLOBAL_Control;
    }
    if ( (a4 & 1) != 0 )
    {
      v77 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v78 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v77 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v79 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
        LOBYTE(v80) = v78;
        LOBYTE(v81) = v77;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v81,
          v80,
          *(_QWORD *)(v79 + 69152),
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
          v84 = v132;
          Win32HM_LockIntoThread<0>(v132, TopLevelCreatorWindow, v131);
          UPDWORDPointer(8196);
          xxxFlashWindow(TopLevelCreatorWindow);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>((ULONG_PTR)v131);
LABEL_95:
          if ( v46 == 1 )
          {
            v43 = v129;
            v44 = 0;
          }
          else
          {
            v43 = 1;
            v44 = *((_QWORD *)v84 + 58) == *(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL);
            v85 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            v86 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v85 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v87 = W32GetUserSessionState(WPP_GLOBAL_Control, v66);
              LOBYTE(v88) = v86;
              LOBYTE(v89) = v85;
              WPP_RECORDER_AND_TRACE_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v89,
                v88,
                *(_QWORD *)(v87 + 69152),
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
    v84 = v132;
    goto LABEL_95;
  }
  v47 = a3;
  v48 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v49 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v48 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v50 = W32GetUserSessionState(WPP_GLOBAL_Control, v45);
    LOBYTE(v51) = v49;
    LOBYTE(v52) = v48;
    v53 = *(_QWORD *)(v50 + 69152);
    v54 = "Remove";
    if ( (a3 & 0x1000) != 0 )
      v54 = "Preserve";
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v52,
      v51,
      v53,
      4,
      2,
      76,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
      (__int64)v54);
  }
  if ( (a3 & 0x1000) == 0 )
    anonymous_namespace_::RemoveForegroundActivate();
  v55 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v56 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v55 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v57 = W32GetUserSessionState(WPP_GLOBAL_Control, v45);
    LOBYTE(v58) = v56;
    LOBYTE(v59) = v55;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v59,
      v58,
      *(_QWORD *)(v57 + 69152),
      4,
      2,
      77,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  v60 = (ULONG_PTR)v132;
  if ( (a3 & 0x400) != 0 )
    v60 = 0;
  if ( (unsigned int)xxxSetForegroundWindow2((ULONG_PTR *)v5, v60, a3 & 0x3FF) )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( *((_QWORD *)v132 + 61) != *(_QWORD *)(W32GetUserSessionState(v62, v61) + 19216) )
    {
      v63 = *((_QWORD *)v5 + 5);
      if ( *(char *)(v63 + 19) >= 0 && *(_DWORD *)(v63 + 236) != 15 && (unsigned int)IsImmersiveBandOrShellManaged(v5) )
      {
        if ( (unsigned int)IAMThreadAccessGranted(v132) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2442);
        v64 = GetNonChildAncestor(v5);
        v65 = (__int64 *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(v64);
        PostIAMShellHookMessage(0x22u, *v65);
      }
    }
  }
  v43 = v129;
  v44 = 0;
LABEL_107:
  if ( (unsigned int)Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !v43 )
      goto LABEL_179;
    if ( (v47 & 0x400) != 0 )
    {
      v91 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v92 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v91 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v93 = W32GetUserSessionState(WPP_GLOBAL_Control, v90);
        v127 = 81;
LABEL_118:
        LOBYTE(v95) = v92;
        LOBYTE(v94) = v91;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v94,
          v95,
          *(_QWORD *)(v93 + 69152),
          4,
          2,
          v127,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        goto LABEL_179;
      }
      goto LABEL_179;
    }
  }
  else if ( !v43 )
  {
    goto LABEL_179;
  }
  v96 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v97 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v96 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v98 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
    LOBYTE(v99) = v97;
    LOBYTE(v100) = v96;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v100,
      v99,
      *(_QWORD *)(v98 + 69152),
      4,
      2,
      82,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  if ( !v44 )
  {
    if ( v5 != *(struct tagWND **)(*(_QWORD *)(*((_QWORD *)v5 + 2) + 464LL) + 128LL) )
    {
      if ( (*(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0) == 0x40 )
      {
        v113 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v114 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v113 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v115 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
          LOBYTE(v116) = v114;
          LOBYTE(v117) = v113;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v117,
            v116,
            *(_QWORD *)(v115 + 69152),
            4,
            2,
            86,
            (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        }
      }
      v118 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v119 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v118 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v120 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
        LOBYTE(v121) = v119;
        LOBYTE(v122) = v118;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v122,
          v121,
          *(_QWORD *)(v120 + 69152),
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
    v108 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v109 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v108 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v110 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
      LOBYTE(v111) = v109;
      LOBYTE(v112) = v108;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v112,
        v111,
        *(_QWORD *)(v110 + 69152),
        4,
        2,
        85,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
LABEL_160:
    v6 = 1;
    goto LABEL_179;
  }
  v101 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v102 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v101 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v103 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control);
    LOBYTE(v104) = v102;
    LOBYTE(v105) = v101;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v105,
      v104,
      *(_QWORD *)(v103 + 69152),
      4,
      2,
      83,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  IsEnabledDeviceUsageNoInline = Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  LOBYTE(v107) = *(_BYTE *)(*((_QWORD *)v5 + 5) + 31LL) & 0xC0;
  if ( !IsEnabledDeviceUsageNoInline )
  {
    if ( (_BYTE)v107 == 64 || !(unsigned __int8)anonymous_namespace_::xxxLocalActivateWindow(v5) )
    {
      v6 = 0;
      goto LABEL_179;
    }
    goto LABEL_160;
  }
  if ( (_BYTE)v107 != 64 )
  {
    v6 = anonymous_namespace_::xxxLocalActivateWindow(v5);
    goto LABEL_179;
  }
  v91 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v92 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v91 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v93 = W32GetUserSessionState(WPP_GLOBAL_Control, v107);
    v127 = 84;
    goto LABEL_118;
  }
LABEL_179:
  if ( !v130 || !v6 )
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
