# xxxActivateWindowWithOptions(tagWND *,ActivateWindowKind,ComputeWindowToActivateStrategy,WindowActivateReason,LocalActivationOptions)

- ea: `0x14016cec0`
- end: `0x14016dce0`
- name: `?xxxActivateWindowWithOptions@@YA_NPEAUtagWND@@W4ActivateWindowKind@@W4ComputeWindowToActivateStrategy@@W4WindowActivateReason@@W4LocalActivationOptions@@@Z`
- size: `3616`
- prototype: `char __fastcall(__int64, __int64, unsigned int, int, __int16)`
- caller_count: `12`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140006574`
- `0x14000ab10`
- `0x140020230`
- `0x140022100`
- `0x140082c80`
- `0x140098244`
- `0x14016c77c`
- `0x14016cc30`
- `0x14016cdc0`
- `0x140183674`
- `0x14018597c`
- `0x1401ab990`

## callees

- `0x14000a36c`
- `0x1400c0e10`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x14016ccb4`
- `0x14016cec0`
- `0x14016dce8`
- `0x14016dddc`
- `0x14016defc`
- `0x14016df8c`
- `0x14016e684`
- `0x14016f3c4`
- `0x14017cc14`
- `0x1402938dc`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14016cf54`
- `ntoskrnl!PsGetThreadId` at `0x14016d1c7`
- `ntoskrnl!PsGetThreadId` at `0x14016d363`
- `ntoskrnl!PsGetThreadId` at `0x14016d4ff`
- `ntoskrnl!PsGetThreadId` at `0x14016d93a`
- `ntoskrnl!PsGetThreadId` at `0x14016cf54`
- `ntoskrnl!PsGetThreadId` at `0x14016d1c7`
- `ntoskrnl!PsGetThreadId` at `0x14016d363`
- `ntoskrnl!PsGetThreadId` at `0x14016d4ff`
- `ntoskrnl!PsGetThreadId` at `0x14016d93a`
- `win32kbase!?GetForegroundActivate@tagTHREADINFO@@QEBA?AW4AllowForegroundActivateReason@@XZ` at `0x14016d847`
- `win32kbase!?GetForegroundActivate@tagTHREADINFO@@QEBA?AW4AllowForegroundActivateReason@@XZ` at `0x14016d847`
- `win32kbase!?SetForegroundActivate@tagTHREADINFO@@QEAAXW4AllowForegroundActivateReason@@@Z` at `0x14016d704`
- `win32kbase!?SetForegroundActivate@tagTHREADINFO@@QEAAXW4AllowForegroundActivateReason@@@Z` at `0x14016d704`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x14016d496`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x14016d496`
- `WIN32K!W32GetUserSessionState` at `0x14016cf63`
- `WIN32K!W32GetUserSessionState` at `0x14016cff2`
- `WIN32K!W32GetUserSessionState` at `0x14016d0c0`
- `WIN32K!W32GetUserSessionState` at `0x14016d1d6`
- `WIN32K!W32GetUserSessionState` at `0x14016d275`
- `WIN32K!W32GetUserSessionState` at `0x14016d372`
- `WIN32K!W32GetUserSessionState` at `0x14016d3e5`
- `WIN32K!W32GetUserSessionState` at `0x14016d44a`
- `WIN32K!W32GetUserSessionState` at `0x14016d50e`
- `WIN32K!W32GetUserSessionState` at `0x14016d600`
- `WIN32K!W32GetUserSessionState` at `0x14016d68a`
- `WIN32K!W32GetUserSessionState` at `0x14016d715`
- `WIN32K!W32GetUserSessionState` at `0x14016d734`
- `WIN32K!W32GetUserSessionState` at `0x14016d7ff`
- `WIN32K!W32GetUserSessionState` at `0x14016d8b4`
- `WIN32K!W32GetUserSessionState` at `0x14016d949`
- `WIN32K!W32GetUserSessionState` at `0x14016da2e`
- `WIN32K!W32GetUserSessionState` at `0x14016dbca`
- `WIN32K!W32GetUserSessionState` at `0x14016dbeb`
- `WIN32K!W32GetUserSessionState` at `0x14016dc90`
- `WIN32K!W32GetUserSessionState` at `0x14016cf63`
- `WIN32K!W32GetUserSessionState` at `0x14016cff2`
- `WIN32K!W32GetUserSessionState` at `0x14016d0c0`
- `WIN32K!W32GetUserSessionState` at `0x14016d1d6`
- `WIN32K!W32GetUserSessionState` at `0x14016d275`
- `WIN32K!W32GetUserSessionState` at `0x14016d372`
- `WIN32K!W32GetUserSessionState` at `0x14016d3e5`
- `WIN32K!W32GetUserSessionState` at `0x14016d44a`
- `WIN32K!W32GetUserSessionState` at `0x14016d50e`
- `WIN32K!W32GetUserSessionState` at `0x14016d600`
- `WIN32K!W32GetUserSessionState` at `0x14016d68a`
- `WIN32K!W32GetUserSessionState` at `0x14016d715`
- `WIN32K!W32GetUserSessionState` at `0x14016d734`
- `WIN32K!W32GetUserSessionState` at `0x14016d7ff`
- `WIN32K!W32GetUserSessionState` at `0x14016d8b4`
- `WIN32K!W32GetUserSessionState` at `0x14016d949`
- `WIN32K!W32GetUserSessionState` at `0x14016da2e`
- `WIN32K!W32GetUserSessionState` at `0x14016dbca`
- `WIN32K!W32GetUserSessionState` at `0x14016dbeb`
- `WIN32K!W32GetUserSessionState` at `0x14016dc90`

## pseudocode

```c
char __fastcall xxxActivateWindowWithOptions(__int64 a1, __int64 a2, unsigned int a3, int a4, __int16 a5)
{
  unsigned int v6; // r12d
  PETHREAD *v7; // rax
  __int64 v8; // r8
  char v9; // si
  __int64 v10; // r9
  bool v11; // r14
  unsigned int *v12; // rdx
  bool v13; // r15
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 UserSessionState; // rax
  int v19; // r8d
  int v20; // edx
  bool v21; // bl
  bool v22; // di
  __int64 v23; // rax
  int v24; // r8d
  int v25; // edx
  __int64 v26; // rdi
  bool v27; // bl
  __int64 v28; // rax
  int v29; // edx
  int v30; // r8d
  bool v31; // bl
  int v32; // r12d
  int v33; // r14d
  char v34; // r13
  bool v35; // zf
  __int64 v36; // rbx
  __int64 v37; // rcx
  bool v38; // r14
  bool v39; // r15
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rax
  int v45; // r8d
  int v46; // edx
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  __int64 v50; // r9
  char v51; // r15
  bool v52; // bl
  bool v53; // di
  __int64 v54; // rax
  int v55; // r8d
  int v56; // edx
  bool v57; // cf
  struct tagWND *v58; // r12
  struct MOVESIZEDATA **v59; // r8
  bool v61; // r15
  unsigned int *v62; // rdx
  bool v63; // r12
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rax
  int v69; // r8d
  int v70; // edx
  __int64 v71; // rcx
  __int64 v72; // r8
  __int64 v73; // r9
  int v74; // edi
  bool v75; // bl
  bool v76; // r15
  __int64 v77; // rax
  int v78; // r8d
  int v79; // edx
  __int64 v80; // r13
  __int64 v81; // rdx
  bool v82; // r15
  bool v83; // r12
  char ThreadId; // bl
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  __int64 v88; // r9
  __int64 v89; // rax
  int v90; // r8d
  int v91; // edx
  struct MOVESIZEDATA *v92; // rcx
  bool v93; // bl
  bool v94; // r14
  unsigned int v95; // edi
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // r8
  __int64 v101; // r8
  __int64 v102; // r9
  char v103; // bl
  __int64 v104; // r9
  const char *v105; // rax
  __int64 v106; // rax
  int v107; // r8d
  int v108; // edx
  bool v109; // bl
  bool v110; // r15
  __int64 v111; // rax
  int v112; // r8d
  int v113; // edx
  bool v114; // bl
  bool v115; // di
  __int64 v116; // rax
  int v117; // r8d
  int v118; // edx
  bool v119; // di
  bool v120; // r14
  char v121; // bl
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // r8
  __int64 v125; // r9
  __int64 v126; // rax
  int v127; // r8d
  int v128; // edx
  struct tagWND *v129; // rax
  bool v130; // bl
  bool v131; // r14
  __int64 v132; // rax
  int v133; // edx
  int v134; // r8d
  __int16 v135; // [rsp+38h] [rbp-51h]
  __int16 v136; // [rsp+38h] [rbp-51h]
  bool v137; // [rsp+68h] [rbp-21h]
  unsigned int ForegroundActivate; // [rsp+6Ch] [rbp-1Dh]
  __int64 v139; // [rsp+78h] [rbp-11h]
  __int128 v140; // [rsp+80h] [rbp-9h] BYREF
  ULONG_PTR BugCheckParameter3[9]; // [rsp+90h] [rbp+7h] BYREF
  struct tagWND *v142; // [rsp+E8h] [rbp+5Fh]

  v142 = (struct tagWND *)a1;
  v6 = a2;
  v7 = (PETHREAD *)PtiCurrent(a1, a2);
  v139 = (__int64)v7;
  BugCheckParameter3[1] = 0;
  BugCheckParameter3[0] = -1;
  v9 = 1;
  v10 = 2;
  v11 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v12 = &WPP_RECORDER_INITIALIZED;
  v13 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v11 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(*v7);
    UserSessionState = W32GetUserSessionState(v15, v14, v16, v17);
    LOBYTE(v19) = v13;
    LOBYTE(v20) = v11;
    WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v20, v19, *(_QWORD *)(UserSessionState + 69152));
    v10 = 2;
    v12 = &WPP_RECORDER_INITIALIZED;
  }
  v21 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v22 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v21 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v23 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v8, 2);
    LOBYTE(v24) = v22;
    LOBYTE(v25) = v21;
    WPP_RECORDER_AND_TRACE_SF_DDdD(*((_QWORD *)WPP_GLOBAL_Control + 3), v25, v24, *(_QWORD *)(v23 + 69152));
    v12 = &WPP_RECORDER_INITIALIZED;
  }
  v26 = (__int64)v142;
  if ( (*(_BYTE *)(*((_QWORD *)v142 + 5) + 31LL) & 0xC0) == 0x40 )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v9 = 0;
    }
    v27 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( !v9 && *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_81;
    v28 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v8, v10);
    v135 = 100;
    goto LABEL_21;
  }
  if ( v6 )
  {
    v140 = 0;
    if ( !(unsigned __int8)anonymous_namespace_::ComputeWindowToActivate(v142, v6, a3, &v140) )
      goto LABEL_16;
    v129 = (struct tagWND *)v140;
    v137 = 0;
    if ( !(_QWORD)v140 || (v33 = DWORD2(v140)) == 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3906);
      v129 = (struct tagWND *)v140;
      v33 = DWORD2(v140);
    }
    v32 = a4;
    v35 = v142 == v129;
    v26 = (__int64)v129;
    v142 = v129;
    v31 = !v35;
  }
  else
  {
    v31 = 0;
    if ( a3 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3894);
    v32 = a4;
    v33 = 1;
    v137 = a4 == 1;
  }
  if ( !v26 )
  {
LABEL_16:
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v9 = 0;
    }
    v27 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( !v9 && *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_81;
    v28 = W32GetUserSessionState(WPP_GLOBAL_Control, v12, v8, v10);
    v135 = 101;
LABEL_21:
    LOBYTE(v30) = v27;
    LOBYTE(v29) = v9;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v29,
      v30,
      *(_QWORD *)(v28 + 69152),
      4,
      2,
      v135,
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
LABEL_81:
    v34 = 0;
    goto LABEL_47;
  }
  v34 = 0;
  ForegroundActivate = 0;
  if ( !v33 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3925);
  v35 = !v31;
  v36 = v139;
  if ( !v35 )
    Win32HM_LockIntoThread<0>(v139, v26, BugCheckParameter3);
  if ( (a5 & 0x100) != 0 && *(_QWORD *)(v26 + 16) != v139 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3934);
  v37 = *(_QWORD *)(v26 + 16);
  if ( *(_QWORD *)(v37 + 464) != *(_QWORD *)(v139 + 464) )
  {
    if ( v37 == v139 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3988);
    v59 = &WPP_GLOBAL_Control;
    v61 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v62 = &WPP_RECORDER_INITIALIZED;
    v63 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v61 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      PsGetThreadId(*(PETHREAD *)v139);
      v68 = W32GetUserSessionState(v65, v64, v66, v67);
      LOBYTE(v69) = v63;
      LOBYTE(v70) = v61;
      WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v70, v69, *(_QWORD *)(v68 + 69152));
      v36 = v139;
      v62 = &WPP_RECORDER_INITIALIZED;
      v59 = &WPP_GLOBAL_Control;
    }
    if ( v33 == 5 )
    {
      v74 = 31;
      v130 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v131 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v130 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v132 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, &WPP_GLOBAL_Control, v10);
        v136 = 107;
        goto LABEL_173;
      }
    }
    else
    {
      if ( v33 != 6 )
      {
        v71 = *(_QWORD *)(W32GetUserSessionState(
                            (unsigned int)(v33 - 5),
                            &WPP_RECORDER_INITIALIZED,
                            &WPP_GLOBAL_Control,
                            v10)
                        + 18968);
        if ( v71 != *(_QWORD *)(v36 + 464) && *(_QWORD *)(W32GetUserSessionState(v71, v12, v72, v73) + 18968) )
          goto LABEL_47;
        v74 = 2;
        v75 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v76 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v75 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v77 = W32GetUserSessionState(WPP_GLOBAL_Control, v12, v72, v73);
          LOBYTE(v78) = v76;
          LOBYTE(v79) = v75;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v79,
            v78,
            *(_QWORD *)(v77 + 69152),
            4,
            2,
            109,
            (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        }
        v80 = v139;
        if ( tagTHREADINFO::ComputeAndTestForegroundActivate((tagTHREADINFO *)v139) )
        {
          v109 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v110 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v109 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v111 = W32GetUserSessionState(WPP_GLOBAL_Control, v81, v59, v10);
            LOBYTE(v112) = v110;
            LOBYTE(v113) = v109;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v113,
              v112,
              *(_QWORD *)(v111 + 69152),
              4,
              2,
              110,
              (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
          }
          ForegroundActivate = tagTHREADINFO::GetForegroundActivate(v139);
        }
        else if ( *(_DWORD *)(v139 + 936) || v137 )
        {
          v82 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v83 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v82 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            ThreadId = (unsigned __int8)PsGetThreadId(*(PETHREAD *)v139);
            v89 = W32GetUserSessionState(v86, v85, v87, v88);
            LOBYTE(v90) = v83;
            LOBYTE(v91) = v82;
            WPP_RECORDER_AND_TRACE_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v91,
              v90,
              *(_QWORD *)(v89 + 69152),
              4,
              2,
              111,
              (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
              ThreadId);
          }
          ForegroundActivate = 64;
        }
        v58 = v142;
        if ( (unsigned int)(v33 - 3) < 2 )
          v74 = 3;
        goto LABEL_83;
      }
      v74 = 31;
      v130 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v131 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v130 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v132 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, &WPP_GLOBAL_Control, v10);
        v136 = 108;
LABEL_173:
        LOBYTE(v134) = v131;
        LOBYTE(v133) = v130;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v133,
          v134,
          *(_QWORD *)(v132 + 69152),
          4,
          2,
          v136,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        v80 = v139;
        v58 = v142;
        goto LABEL_83;
      }
    }
    v80 = v139;
    v58 = v142;
LABEL_84:
    v92 = WPP_GLOBAL_Control;
    v93 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v94 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v93 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v106 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v59, v10);
      LOBYTE(v107) = v94;
      LOBYTE(v108) = v93;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v108,
        v107,
        *(_QWORD *)(v106 + 69152),
        4,
        2,
        112,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v95 = v74 | 4;
    v97 = *(_QWORD *)(W32GetUserSessionState(v92, v62, v59, v10) + 18968);
    if ( *(_QWORD *)(*((_QWORD *)v58 + 2) + 464LL) == v97
      && *(_QWORD *)(W32GetUserSessionState(v97, v96, v98, v99) + 18968) == *(_QWORD *)(v80 + 464) )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4116);
    }
    v100 = a5 & 0x100 | 4u;
    if ( (a5 & 2) == 0 )
      v100 = a5 & 0x100;
    v34 = xxxSetForegroundWindowWithOptions(v58, v95, v100);
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v9 = 0;
    }
    v103 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v104 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control, v12, v101, v102) + 69152);
      v105 = "Success";
      if ( !v34 )
        v105 = "Failure";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v9,
        v103,
        v104,
        4u,
        2u,
        0x71u,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
        v105);
    }
    if ( v34 && ForegroundActivate )
      tagTHREADINFO::SetForegroundActivate(v139, ForegroundActivate);
    goto LABEL_47;
  }
  v38 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v39 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v38 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(*(PETHREAD *)v139);
    v44 = W32GetUserSessionState(v41, v40, v42, v43);
    LOBYTE(v45) = v39;
    LOBYTE(v46) = v38;
    WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v46, v45, *(_QWORD *)(v44 + 69152));
    v26 = (__int64)v142;
  }
  v51 = anonymous_namespace_::FAllowForegroundActivate(v26);
  if ( v51 )
  {
    v10 = (__int64)&WPP_GLOBAL_Control;
    v114 = 0;
    if ( WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control )
    {
      v48 = *((unsigned int *)WPP_GLOBAL_Control + 11);
      if ( (v48 & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
        v114 = 1;
    }
    v12 = &WPP_RECORDER_INITIALIZED;
    v115 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v114 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v116 = W32GetUserSessionState(v48, &WPP_RECORDER_INITIALIZED, v49, &WPP_GLOBAL_Control);
      LOBYTE(v117) = v115;
      LOBYTE(v118) = v114;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v118,
        v117,
        *(_QWORD *)(v116 + 69152),
        4,
        2,
        103,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      v12 = &WPP_RECORDER_INITIALIZED;
      v10 = (__int64)&WPP_GLOBAL_Control;
    }
    v59 = (struct MOVESIZEDATA **)v139;
    if ( !*(_DWORD *)(v139 + 936) )
    {
      ForegroundActivate = 32;
      v119 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v120 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v119 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v121 = (unsigned __int8)PsGetThreadId(*(PETHREAD *)v139);
        v126 = W32GetUserSessionState(v123, v122, v124, v125);
        LOBYTE(v127) = v120;
        LOBYTE(v128) = v119;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v128,
          v127,
          *(_QWORD *)(v126 + 69152),
          4,
          2,
          104,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
          v121);
      }
    }
    v58 = v142;
  }
  else
  {
    v52 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v53 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v52 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v54 = W32GetUserSessionState(WPP_GLOBAL_Control, v47, v49, v50);
      LOBYTE(v55) = v53;
      LOBYTE(v56) = v52;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v56,
        v55,
        *(_QWORD *)(v54 + 69152),
        4,
        2,
        105,
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v57 = v32 != 0;
    v58 = v142;
    a5 |= 129 - v57;
    v34 = anonymous_namespace_::xxxLocalActivateWindow(v142);
  }
  if ( v51 )
  {
    v80 = v139;
    v74 = 2;
LABEL_83:
    v62 = &WPP_RECORDER_INITIALIZED;
    goto LABEL_84;
  }
LABEL_47:
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>(BugCheckParameter3, (__int64)v12);
  return v34;
}

```

## disassembly

```asm
0x14016cec0  mov     rax, rsp
0x14016cec3  mov     [rax+10h], rbx
0x14016cec7  mov     [rax+20h], r9d
0x14016cecb  mov     [rax+8], rcx
0x14016cecf  push    rbp
0x14016ced0  push    rsi
0x14016ced1  push    rdi
0x14016ced2  push    r12
0x14016ced4  push    r13
0x14016ced6  push    r14
0x14016ced8  push    r15
0x14016ceda  lea     rbp, [rax-57h]
0x14016cede  sub     rsp, 0A0h
0x14016cee5  mov     r13d, r8d
0x14016cee8  mov     r12d, edx
0x14016ceeb  mov     rbx, rcx
0x14016ceee  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14016cef3  mov     [rbp+4Fh+var_60], rax
0x14016cef7  mov     [rbp+4Fh+var_40], 0
0x14016ceff  mov     [rbp+4Fh+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x14016cf07  mov     rdx, cs:WPP_GLOBAL_Control
0x14016cf0e  lea     r10, WPP_GLOBAL_Control
0x14016cf15  mov     esi, 1
0x14016cf1a  lea     r9d, [rsi+1]
0x14016cf1e  cmp     rdx, r10
0x14016cf21  jz      short loc_14016CF2F
0x14016cf23  mov     ecx, [rdx+2Ch]
0x14016cf26  test    r9b, cl
0x14016cf29  jnz     loc_14016D9F0
0x14016cf2f  xor     r14b, r14b
0x14016cf32  lea     rdx, WPP_RECORDER_INITIALIZED
0x14016cf39  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14016cf40  setnz   r15b
0x14016cf44  test    r14b, r14b
0x14016cf47  jnz     short loc_14016CF4E
0x14016cf49  test    r15b, r15b
0x14016cf4c  jz      short loc_14016CFC4
0x14016cf4e  mov     rcx, [rax]; Thread
0x14016cf51  mov     rdi, [rbx]
0x14016cf54  call    cs:__imp_PsGetThreadId
0x14016cf5b  nop     dword ptr [rax+rax+00h]
0x14016cf60  mov     rbx, rax
0x14016cf63  call    cs:__imp_W32GetUserSessionState
0x14016cf6a  nop     dword ptr [rax+rax+00h]
0x14016cf6f  mov     qword ptr [rsp+0D0h+var_88], rdi
0x14016cf74  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016cf7b  mov     dword ptr [rsp+0D0h+var_90], ebx
0x14016cf7f  mov     r8b, r15b
0x14016cf82  mov     [rsp+0D0h+var_98], rcx
0x14016cf87  mov     dl, r14b
0x14016cf8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14016cf91  mov     r9, [rax+10E20h]
0x14016cf98  mov     word ptr [rsp+0D0h+var_A0], 62h ; 'b'
0x14016cf9f  mov     dword ptr [rsp+0D0h+var_A8], 2
0x14016cfa7  mov     rcx, [rcx+18h]
0x14016cfab  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14016cfb0  mov     r9d, 2
0x14016cfb6  lea     rdx, WPP_RECORDER_INITIALIZED
0x14016cfbd  lea     r10, WPP_GLOBAL_Control
0x14016cfc4  mov     rcx, cs:WPP_GLOBAL_Control
0x14016cfcb  cmp     rcx, r10
0x14016cfce  jz      short loc_14016CFDC
0x14016cfd0  mov     eax, [rcx+2Ch]
0x14016cfd3  test    r9b, al
0x14016cfd6  jnz     loc_14016DA02
0x14016cfdc  xor     bl, bl
0x14016cfde  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14016cfe5  setnz   dil
0x14016cfe9  test    bl, bl
0x14016cfeb  jnz     short loc_14016CFF2
0x14016cfed  test    dil, dil
0x14016cff0  jz      short loc_14016D047
0x14016cff2  call    cs:__imp_W32GetUserSessionState
0x14016cff9  nop     dword ptr [rax+rax+00h]
0x14016cffe  mov     ecx, [rbp+4Fh+arg_20]
0x14016d001  mov     r8b, dil
0x14016d004  mov     [rsp+58h], ecx
0x14016d008  mov     dl, bl
0x14016d00a  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d011  mov     r9, [rax+10E20h]
0x14016d018  mov     eax, [rbp+4Fh+arg_18]
0x14016d01b  mov     [rsp+0D0h+var_80], eax
0x14016d01f  mov     rcx, [rcx+18h]
0x14016d023  mov     [rsp+0D0h+var_88], r13d
0x14016d028  mov     dword ptr [rsp+0D0h+var_90], r12d
0x14016d02d  mov     word ptr [rsp+0D0h+var_A0], 63h ; 'c'
0x14016d034  call    WPP_RECORDER_AND_TRACE_SF_DDdD
0x14016d039  lea     rdx, WPP_RECORDER_INITIALIZED
0x14016d040  lea     r10, WPP_GLOBAL_Control
0x14016d047  mov     rdi, [rbp+4Fh+arg_0]
0x14016d04b  mov     rax, [rdi+28h]
0x14016d04f  mov     cl, [rax+1Fh]
0x14016d052  and     cl, 0C0h
0x14016d055  cmp     cl, 40h ; '@'
0x14016d058  jz      loc_14016D57E
0x14016d05e  test    r12d, r12d
0x14016d061  jz      loc_14016D10E
0x14016d067  xorps   xmm0, xmm0
0x14016d06a  lea     r9, [rbp+4Fh+var_58]
0x14016d06e  mov     r8d, r13d
0x14016d071  mov     edx, r12d
0x14016d074  mov     rcx, rdi
0x14016d077  movups  [rbp+4Fh+var_58], xmm0
0x14016d07b  call    _anonymous_namespace___ComputeWindowToActivate
0x14016d080  test    al, al
0x14016d082  jnz     loc_14016D9B5
0x14016d088  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d08f  lea     rax, WPP_GLOBAL_Control
0x14016d096  cmp     rcx, rax
0x14016d099  jnz     loc_14016D79C
0x14016d09f  xor     sil, sil
0x14016d0a2  lea     rax, WPP_RECORDER_INITIALIZED
0x14016d0a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14016d0b0  setnz   bl
0x14016d0b3  test    sil, sil
0x14016d0b6  jnz     short loc_14016D0C0
0x14016d0b8  test    bl, bl
0x14016d0ba  jz      loc_14016D5AC
0x14016d0c0  call    cs:__imp_W32GetUserSessionState
0x14016d0c7  nop     dword ptr [rax+rax+00h]
0x14016d0cc  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016d0d3  mov     [rsp+0D0h+var_98], rcx
0x14016d0d8  mov     word ptr [rsp+0D0h+var_A0], 65h ; 'e'
0x14016d0df  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d0e6  mov     r8b, bl
0x14016d0e9  mov     r9, [rax+10E20h]
0x14016d0f0  mov     dl, sil
0x14016d0f3  mov     dword ptr [rsp+0D0h+var_A8], 2
0x14016d0fb  mov     byte ptr [rsp+0D0h+var_B0], 4
0x14016d100  mov     rcx, [rcx+18h]
0x14016d104  call    WPP_RECORDER_AND_TRACE_SF_
0x14016d109  jmp     loc_14016D5AC
0x14016d10e  xor     bl, bl
0x14016d110  lea     r15, aIxptelassert; "IXPTelAssert"
0x14016d117  test    r13d, r13d
0x14016d11a  jnz     loc_14016DA52
0x14016d120  mov     r12d, [rbp+4Fh+arg_18]
0x14016d124  mov     r14d, esi
0x14016d127  cmp     r12d, esi
0x14016d12a  setz    [rbp+4Fh+var_70]
0x14016d12e  test    rdi, rdi
0x14016d131  jz      loc_14016D088
0x14016d137  xor     eax, eax
0x14016d139  xor     r13b, r13b
0x14016d13c  mov     [rbp+4Fh+var_6C], eax
0x14016d13f  test    r14d, r14d
0x14016d142  jz      loc_14016D998
0x14016d148  test    bl, bl
0x14016d14a  mov     rbx, [rbp+4Fh+var_60]
0x14016d14e  jz      short loc_14016D15F
0x14016d150  lea     r8, [rbp+4Fh+BugCheckParameter3]
0x14016d154  mov     rdx, rdi
0x14016d157  mov     rcx, rbx
0x14016d15a  call    ??$Win32HM_LockIntoThread@$0A@@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<0>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x14016d15f  test    [rbp+4Fh+arg_20], 100h
0x14016d166  jnz     loc_14016DA94
0x14016d16c  mov     rcx, [rdi+10h]
0x14016d170  mov     rax, [rbx+1D0h]
0x14016d177  cmp     [rcx+1D0h], rax
0x14016d17e  jnz     loc_14016D310
0x14016d184  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d18b  lea     rax, WPP_GLOBAL_Control
0x14016d192  cmp     rcx, rax
0x14016d195  jz      short loc_14016D1A2
0x14016d197  mov     eax, [rcx+2Ch]
0x14016d19a  test    al, 2
0x14016d19c  jnz     loc_14016DABB
0x14016d1a2  xor     r14b, r14b
0x14016d1a5  lea     rax, WPP_RECORDER_INITIALIZED
0x14016d1ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14016d1b3  setnz   r15b
0x14016d1b7  test    r14b, r14b
0x14016d1ba  jnz     short loc_14016D1C1
0x14016d1bc  test    r15b, r15b
0x14016d1bf  jz      short loc_14016D227
0x14016d1c1  mov     rcx, [rbx]; Thread
0x14016d1c4  mov     rdi, [rdi]
0x14016d1c7  call    cs:__imp_PsGetThreadId
0x14016d1ce  nop     dword ptr [rax+rax+00h]
0x14016d1d3  mov     rbx, rax
0x14016d1d6  call    cs:__imp_W32GetUserSessionState
0x14016d1dd  nop     dword ptr [rax+rax+00h]
0x14016d1e2  mov     qword ptr [rsp+0D0h+var_88], rdi
0x14016d1e7  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016d1ee  mov     dword ptr [rsp+0D0h+var_90], ebx
0x14016d1f2  mov     r8b, r15b
0x14016d1f5  mov     [rsp+0D0h+var_98], rcx
0x14016d1fa  mov     dl, r14b
0x14016d1fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d204  mov     r9, [rax+10E20h]
0x14016d20b  mov     word ptr [rsp+0D0h+var_A0], 66h ; 'f'
0x14016d212  mov     dword ptr [rsp+0D0h+var_A8], 2
0x14016d21a  mov     rcx, [rcx+18h]
0x14016d21e  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14016d223  mov     rdi, [rbp+4Fh+arg_0]
0x14016d227  mov     rcx, rdi
0x14016d22a  call    _anonymous_namespace___FAllowForegroundActivate
0x14016d22f  mov     r15b, al
0x14016d232  test    al, al
0x14016d234  jnz     loc_14016D85B
0x14016d23a  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d241  lea     rax, WPP_GLOBAL_Control
0x14016d248  cmp     rcx, rax
0x14016d24b  jz      short loc_14016D258
0x14016d24d  mov     eax, [rcx+2Ch]
0x14016d250  test    al, 2
0x14016d252  jnz     loc_14016DB0B
0x14016d258  xor     bl, bl
0x14016d25a  lea     rax, WPP_RECORDER_INITIALIZED
0x14016d261  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14016d268  setnz   dil
0x14016d26c  test    bl, bl
0x14016d26e  jnz     short loc_14016D275
0x14016d270  test    dil, dil
0x14016d273  jz      short loc_14016D2BD
0x14016d275  call    cs:__imp_W32GetUserSessionState
0x14016d27c  nop     dword ptr [rax+rax+00h]
0x14016d281  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016d288  mov     r8b, dil
0x14016d28b  mov     [rsp+0D0h+var_98], rcx
0x14016d290  mov     dl, bl
0x14016d292  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d299  mov     r9, [rax+10E20h]
0x14016d2a0  mov     word ptr [rsp+0D0h+var_A0], 69h ; 'i'
0x14016d2a7  mov     dword ptr [rsp+0D0h+var_A8], 2
0x14016d2af  mov     rcx, [rcx+18h]
0x14016d2b3  mov     byte ptr [rsp+0D0h+var_B0], 4
0x14016d2b8  call    WPP_RECORDER_AND_TRACE_SF_
0x14016d2bd  neg     r12d
0x14016d2c0  mov     r12, [rbp+4Fh+arg_0]
0x14016d2c4  sbb     eax, eax
0x14016d2c6  mov     rcx, r12; struct tagWND *
0x14016d2c9  add     eax, 81h
0x14016d2ce  xor     edx, edx
0x14016d2d0  or      [rbp+4Fh+arg_20], eax
0x14016d2d3  mov     r8d, [rbp+4Fh+arg_20]
0x14016d2d7  call    _anonymous_namespace___xxxLocalActivateWindow
0x14016d2dc  mov     r13b, al
0x14016d2df  test    r15b, r15b
0x14016d2e2  jnz     loc_14016D5B4
0x14016d2e8  lea     rcx, [rbp+4Fh+BugCheckParameter3]; BugCheckParameter3
0x14016d2ec  call    ??1?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x14016d2f1  mov     rbx, [rsp+0D0h+arg_8]
0x14016d2f9  mov     al, r13b
0x14016d2fc  add     rsp, 0A0h
0x14016d303  pop     r15
0x14016d305  pop     r14
0x14016d307  pop     r13
0x14016d309  pop     r12
0x14016d30b  pop     rdi
0x14016d30c  pop     rsi
0x14016d30d  pop     rbp
0x14016d30e  retn
0x14016d310  cmp     rcx, rbx
0x14016d313  jz      loc_14016DB1D
0x14016d319  mov     r12d, 2
0x14016d31f  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d326  lea     r8, WPP_GLOBAL_Control
0x14016d32d  cmp     rcx, r8
0x14016d330  jz      short loc_14016D33E
0x14016d332  mov     eax, [rcx+2Ch]
0x14016d335  test    r12b, al
0x14016d338  jnz     loc_14016DB40
0x14016d33e  xor     r15b, r15b
0x14016d341  lea     rdx, WPP_RECORDER_INITIALIZED
0x14016d348  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14016d34f  setnz   r12b
0x14016d353  test    r15b, r15b
0x14016d356  jnz     short loc_14016D35D
0x14016d358  test    r12b, r12b
0x14016d35b  jz      short loc_14016D3D1
0x14016d35d  mov     rcx, [rbx]; Thread
0x14016d360  mov     rdi, [rdi]
0x14016d363  call    cs:__imp_PsGetThreadId
0x14016d36a  nop     dword ptr [rax+rax+00h]
0x14016d36f  mov     rbx, rax
0x14016d372  call    cs:__imp_W32GetUserSessionState
0x14016d379  nop     dword ptr [rax+rax+00h]
0x14016d37e  mov     qword ptr [rsp+0D0h+var_88], rdi
0x14016d383  lea     rcx, WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids
0x14016d38a  mov     dword ptr [rsp+0D0h+var_90], ebx
0x14016d38e  mov     r8b, r12b
0x14016d391  mov     [rsp+0D0h+var_98], rcx
0x14016d396  mov     dl, r15b
0x14016d399  mov     rcx, cs:WPP_GLOBAL_Control
0x14016d3a0  mov     r9, [rax+10E20h]
0x14016d3a7  mov     word ptr [rsp+0D0h+var_A0], 6Ah ; 'j'
0x14016d3ae  mov     dword ptr [rsp+0D0h+var_A8], 2
0x14016d3b6  mov     rcx, [rcx+18h]
0x14016d3ba  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14016d3bf  mov     rbx, [rbp+4Fh+var_60]
0x14016d3c3  lea     rdx, WPP_RECORDER_INITIALIZED
0x14016d3ca  lea     r8, WPP_GLOBAL_Control
0x14016d3d1  mov     ecx, r14d
0x14016d3d4  sub     ecx, 5
0x14016d3d7  jz      loc_14016DC3D
0x14016d3dd  cmp     ecx, esi
0x14016d3df  jz      loc_14016DB88
0x14016d3e5  call    cs:__imp_W32GetUserSessionState
0x14016d3ec  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
