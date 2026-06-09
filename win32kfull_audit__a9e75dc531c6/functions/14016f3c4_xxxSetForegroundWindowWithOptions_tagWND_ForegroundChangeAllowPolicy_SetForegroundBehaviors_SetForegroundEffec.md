# xxxSetForegroundWindowWithOptions(tagWND *,ForegroundChangeAllowPolicy,SetForegroundBehaviors,SetForegroundEffects)

- ea: `0x14016f3c4`
- end: `0x140170139`
- name: `?xxxSetForegroundWindowWithOptions@@YA_NPEAUtagWND@@W4ForegroundChangeAllowPolicy@@W4SetForegroundBehaviors@@W4SetForegroundEffects@@@Z`
- size: `3445`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64)`
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
char __fastcall xxxSetForegroundWindowWithOptions(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v4; // bp
  __int64 v5; // r14
  bool v6; // r13
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  struct tagTHREADINFO *v11; // rbx
  __int64 v12; // r8
  __int64 v13; // r9
  bool v14; // r15
  bool v15; // r12
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 UserSessionState; // rax
  int v21; // r8d
  int v22; // edx
  struct tagWND *v23; // rax
  __int64 v24; // rdx
  struct MOVESIZEDATA *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  struct tagWND *v28; // rsi
  char v29; // r15
  char v30; // r12
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r15
  __int64 v36; // rsi
  bool v37; // bl
  bool v38; // di
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  char v42; // bl
  char v43; // di
  __int64 v44; // r9
  const char *v45; // rax
  char v46; // si
  bool v47; // r15
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  int v51; // esi
  __int16 v52; // r12
  char v53; // di
  char v54; // si
  __int64 v55; // r9
  const char *v56; // rax
  bool v57; // bl
  bool v58; // di
  __int64 v59; // rax
  int v60; // r8d
  int v61; // edx
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // r9
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 *v69; // rax
  struct MOVESIZEDATA **v70; // rdx
  bool v71; // r15
  unsigned int *v72; // r8
  bool v73; // r12
  char ThreadId; // di
  __int64 v75; // rsi
  char v76; // bl
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // r8
  __int64 v80; // r9
  __int64 v81; // rax
  int v82; // r8d
  int v83; // edx
  bool v84; // bl
  bool v85; // di
  __int64 v86; // rax
  int v87; // r8d
  int v88; // edx
  __int64 NonChildAncestor; // rax
  struct tagWND *TopLevelCreatorWindow; // rbx
  __int64 v91; // r15
  __int64 v92; // rdx
  bool v93; // bl
  bool v94; // di
  __int64 v95; // rax
  int v96; // r8d
  int v97; // edx
  struct MOVESIZEDATA **v98; // rdx
  __int64 v99; // r8
  __int64 v100; // r9
  bool v101; // bl
  bool v102; // di
  __int64 v103; // rax
  int v104; // edx
  int v105; // r8d
  bool v106; // bl
  bool v107; // di
  __int64 v108; // rax
  int v109; // r8d
  int v110; // edx
  bool v111; // bl
  bool v112; // di
  __int64 v113; // rax
  int v114; // r8d
  int v115; // edx
  __int16 v116; // bx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v118; // r8
  __int64 v119; // r9
  bool v120; // bl
  bool v121; // di
  __int64 v122; // rax
  int v123; // r8d
  int v124; // edx
  bool v125; // bl
  bool v126; // di
  __int64 v127; // rax
  int v128; // r8d
  int v129; // edx
  bool v130; // bl
  bool v131; // di
  __int64 v132; // rax
  int v133; // r8d
  int v134; // edx
  unsigned int v136; // [rsp+20h] [rbp-C8h]
  int v137; // [rsp+28h] [rbp-C0h]
  int v138; // [rsp+30h] [rbp-B8h]
  __int16 v139; // [rsp+30h] [rbp-B8h]
  int v140; // [rsp+38h] [rbp-B0h]
  bool v141; // [rsp+70h] [rbp-78h]
  char v142; // [rsp+71h] [rbp-77h]
  ULONG_PTR v143[2]; // [rsp+78h] [rbp-70h] BYREF
  struct tagTHREADINFO *v144; // [rsp+88h] [rbp-60h]
  ULONG_PTR BugCheckParameter3[11]; // [rsp+90h] [rbp-58h] BYREF
  __int64 v146; // [rsp+F0h] [rbp+8h]
  bool v147; // [rsp+F0h] [rbp+8h]
  __int16 v148; // [rsp+100h] [rbp+18h]
  char v149; // [rsp+108h] [rbp+20h]

  v149 = a4;
  v148 = a3;
  v4 = 1;
  v5 = a1;
  v142 = 1;
  v6 = 0;
  v7 = *(_QWORD *)(W32GetUserSessionState(a1, a2, a3, a4) + 18968);
  v8 = *(_QWORD *)(v5 + 16);
  v143[0] = v7;
  v146 = *(_QWORD *)(v8 + 464);
  v141 = v146 == v7;
  v11 = PtiCurrent(v7, v9);
  v144 = v11;
  v14 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v15 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v14 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(**(PETHREAD **)(v5 + 16));
    PsGetThreadId(*(PETHREAD *)v11);
    UserSessionState = W32GetUserSessionState(v17, v16, v18, v19);
    LOBYTE(v21) = v15;
    LOBYTE(v22) = v14;
    WPP_RECORDER_AND_TRACE_SF_DqDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v22,
      v21,
      *(_QWORD *)(UserSessionState + 69152));
    v11 = v144;
  }
  BugCheckParameter3[1] = 0;
  BugCheckParameter3[0] = -1;
  v23 = _GhostWindowFromHungWindow((const struct tagWND *)v5, v10, v12, v13);
  v28 = v23;
  if ( v23 )
  {
    Win32HM_LockIntoThread<0>((__int64)v11, (__int64)v23, BugCheckParameter3);
    v25 = WPP_GLOBAL_Control;
    v29 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v30 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v29 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v31 = W32GetUserSessionState(WPP_GLOBAL_Control, v24, v26, v27);
      WPP_RECORDER_AND_TRACE_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v29,
        v30,
        *(_QWORD *)(v31 + 69152),
        4u,
        2u,
        0x49u,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      v11 = v144;
    }
    v5 = (__int64)v28;
  }
  if ( v146 == v143[0] )
  {
    v32 = W32GetUserSessionState(v25, v24, v26, v27);
    v35 = *((_QWORD *)v11 + 58);
    v36 = *(_QWORD *)(v32 + 18968);
    v147 = v36 == v35;
    v37 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v38 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v37 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v39 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v33, v34);
      LOBYTE(v40) = v38;
      LOBYTE(v41) = v37;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v41,
        v40,
        *(_QWORD *)(v39 + 69152),
        4,
        2,
        74,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v42 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v43 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v42 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v44 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v33, v34) + 69152);
      v45 = "Synchronously";
      if ( v36 != v35 )
        v45 = "Async";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v42,
        v43,
        v44,
        4u,
        2u,
        0x4Bu,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        v45);
    }
    v46 = v141;
    v47 = v147;
LABEL_106:
    v52 = v148;
    goto LABEL_107;
  }
  LODWORD(v143[0]) = anonymous_namespace_::CanSetForegroundWindow((struct tagWND *)v5);
  v51 = v143[0];
  if ( LODWORD(v143[0]) != 2 )
  {
    v142 = 0;
    v70 = &WPP_GLOBAL_Control;
    v71 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v72 = &WPP_RECORDER_INITIALIZED;
    v73 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v71 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      ThreadId = (unsigned __int8)PsGetThreadId(**(PETHREAD **)(v5 + 16));
      v75 = *(_QWORD *)v5;
      v76 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)v11);
      v81 = W32GetUserSessionState(v78, v77, v79, v80);
      LOBYTE(v82) = v73;
      LOBYTE(v83) = v71;
      WPP_RECORDER_AND_TRACE_SF_DqD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v83,
        v82,
        *(_QWORD *)(v81 + 69152),
        v136,
        v137,
        v138,
        v140,
        v76,
        v75,
        ThreadId);
      v51 = v143[0];
      v70 = &WPP_GLOBAL_Control;
      v72 = &WPP_RECORDER_INITIALIZED;
    }
    if ( (v149 & 1) != 0 )
    {
      v84 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v85 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v84 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v86 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v50);
        LOBYTE(v87) = v85;
        LOBYTE(v88) = v84;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v88,
          v87,
          *(_QWORD *)(v86 + 69152),
          4,
          2,
          79,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      }
      NonChildAncestor = GetNonChildAncestor(v5);
      TopLevelCreatorWindow = (struct tagWND *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(NonChildAncestor);
      if ( !IsTrayWindow(TopLevelCreatorWindow, 1) )
        TopLevelCreatorWindow = (struct tagWND *)v5;
      if ( *(_DWORD *)(*((_QWORD *)TopLevelCreatorWindow + 5) + 236LL) != 15 )
      {
        if ( !(unsigned int)IsImmersiveBandOrShellManaged(TopLevelCreatorWindow) )
        {
          v91 = (__int64)v144;
          Win32HM_LockIntoThread<0>((__int64)v144, (__int64)TopLevelCreatorWindow, v143);
          UPDWORDPointer(8196);
          xxxFlashWindow(TopLevelCreatorWindow);
          Win32HMThreadLockAlways<tagWND>::~Win32HMThreadLockAlways<tagWND>(v143, v92);
LABEL_95:
          if ( v51 == 1 )
          {
            v46 = v141;
            v47 = 0;
          }
          else
          {
            v46 = 1;
            v47 = *(_QWORD *)(v91 + 464) == *(_QWORD *)(*(_QWORD *)(v5 + 16) + 464LL);
            v93 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            v94 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v93 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v95 = W32GetUserSessionState(WPP_GLOBAL_Control, v70, v72, v50);
              LOBYTE(v96) = v94;
              LOBYTE(v97) = v93;
              WPP_RECORDER_AND_TRACE_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v97,
                v96,
                *(_QWORD *)(v95 + 69152),
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
    v91 = (__int64)v144;
    goto LABEL_95;
  }
  v52 = v148;
  v53 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v54 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v53 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v55 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v48, v49, v50) + 69152);
    v56 = "Remove";
    if ( (v148 & 0x1000) != 0 )
      v56 = "Preserve";
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v53,
      v54,
      v55,
      4u,
      2u,
      0x4Cu,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
      v56);
  }
  if ( (v148 & 0x1000) == 0 )
    anonymous_namespace_::RemoveForegroundActivate();
  v57 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v58 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v57 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v59 = W32GetUserSessionState(WPP_GLOBAL_Control, v48, v49, v50);
    LOBYTE(v60) = v58;
    LOBYTE(v61) = v57;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v61,
      v60,
      *(_QWORD *)(v59 + 69152),
      4,
      2,
      77,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  v62 = (__int64)v144;
  if ( (v148 & 0x400) != 0 )
    v62 = 0;
  if ( (unsigned int)xxxSetForegroundWindow2(v5, v62, v148 & 0x3FF) )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( *((_QWORD *)v144 + 61) != *(_QWORD *)(W32GetUserSessionState(v64, v63, v65, v66) + 19216) )
    {
      v67 = *(_QWORD *)(v5 + 40);
      if ( *(char *)(v67 + 19) >= 0 && *(_DWORD *)(v67 + 236) != 15 && (unsigned int)IsImmersiveBandOrShellManaged(v5) )
      {
        if ( (unsigned int)IAMThreadAccessGranted(v144) )
          MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 2442);
        v68 = GetNonChildAncestor(v5);
        v69 = (__int64 *)anonymous_namespace_::DSW_GetTopLevelCreatorWindow(v68);
        PostIAMShellHookMessage(0x22u, *v69);
      }
    }
  }
  v46 = v141;
  v47 = 0;
LABEL_107:
  if ( (unsigned int)Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !v46 )
      goto LABEL_181;
    if ( (v52 & 0x400) != 0 )
    {
      v101 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v102 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v101 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v103 = W32GetUserSessionState(WPP_GLOBAL_Control, v98, v99, v100);
        v139 = 81;
LABEL_118:
        LOBYTE(v105) = v102;
        LOBYTE(v104) = v101;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v104,
          v105,
          *(_QWORD *)(v103 + 69152),
          4,
          2,
          v139,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        goto LABEL_181;
      }
      goto LABEL_181;
    }
  }
  else if ( !v46 )
  {
    goto LABEL_181;
  }
  v98 = &WPP_GLOBAL_Control;
  v106 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v107 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v106 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v108 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v100);
    LOBYTE(v109) = v107;
    LOBYTE(v110) = v106;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v110,
      v109,
      *(_QWORD *)(v108 + 69152),
      4,
      2,
      82,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    v98 = &WPP_GLOBAL_Control;
  }
  if ( !v47 )
  {
    if ( v5 != *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 16) + 464LL) + 128LL) )
    {
      if ( (*(_BYTE *)(*(_QWORD *)(v5 + 40) + 31LL) & 0xC0) == 0x40 )
      {
        v125 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v126 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v125 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v127 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v100);
          LOBYTE(v128) = v126;
          LOBYTE(v129) = v125;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v129,
            v128,
            *(_QWORD *)(v127 + 69152),
            4,
            2,
            86,
            (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        }
      }
      v130 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v131 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v130 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v132 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v100);
        LOBYTE(v133) = v131;
        LOBYTE(v134) = v130;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v134,
          v133,
          *(_QWORD *)(v132 + 69152),
          4,
          2,
          87,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      }
      v6 = (unsigned int)PostEventMessageEx(
                           *(struct tagTHREADINFO **)(v5 + 16),
                           *(struct tagTHREADINFO ***)(*(_QWORD *)(v5 + 16) + 464LL),
                           6,
                           0,
                           0,
                           0,
                           *(_QWORD *)v5,
                           0) != 0;
      goto LABEL_181;
    }
    v120 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v121 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v120 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v122 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v100);
      LOBYTE(v123) = v121;
      LOBYTE(v124) = v120;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v124,
        v123,
        *(_QWORD *)(v122 + 69152),
        4,
        2,
        85,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
LABEL_162:
    v6 = 1;
    goto LABEL_181;
  }
  v111 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v112 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v111 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v113 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v100);
    LOBYTE(v114) = v112;
    LOBYTE(v115) = v111;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v115,
      v114,
      *(_QWORD *)(v113 + 69152),
      4,
      2,
      83,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
  }
  v116 = v52 & 0x100 | 0x82;
  if ( (v52 & 4) == 0 )
    v116 = v52 & 0x100 | 0x80;
  IsEnabledDeviceUsageNoInline = Feature_FixAsyncActivationChildWindowGuard__private_IsEnabledDeviceUsageNoInline();
  LOBYTE(v98) = *(_BYTE *)(*(_QWORD *)(v5 + 40) + 31LL) & 0xC0;
  if ( !IsEnabledDeviceUsageNoInline )
  {
    if ( (_BYTE)v98 == 64 || !anonymous_namespace_::xxxLocalActivateWindow((struct tagWND *)v5, 0, v116) )
    {
      v6 = 0;
      goto LABEL_181;
    }
    goto LABEL_162;
  }
  if ( (_BYTE)v98 != 64 )
  {
    v6 = anonymous_namespace_::xxxLocalActivateWindow((struct tagWND *)v5, 0, v116);
    goto LABEL_181;
  }
  v101 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v102 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v101 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v103 = W32GetUserSessionState(WPP_GLOBAL_Control, v98, v118, v119);
    v139 = 84;
    goto LABEL_118;
  }
LABEL_181:
  if ( !v142 || !v6 )
    v4 = 0;
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3, (__int64)v98);
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
