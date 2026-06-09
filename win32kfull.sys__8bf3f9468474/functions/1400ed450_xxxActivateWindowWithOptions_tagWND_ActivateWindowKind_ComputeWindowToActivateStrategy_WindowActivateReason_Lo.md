# xxxActivateWindowWithOptions(tagWND *,ActivateWindowKind,ComputeWindowToActivateStrategy,WindowActivateReason,LocalActivationOptions)

- ea: `0x1400ed450`
- end: `0x1400ee270`
- name: `?xxxActivateWindowWithOptions@@YA_NPEAUtagWND@@W4ActivateWindowKind@@W4ComputeWindowToActivateStrategy@@W4WindowActivateReason@@W4LocalActivationOptions@@@Z`
- size: `3616`
- prototype: ``
- caller_count: `12`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140025320`
- `0x1400271f0`
- `0x14005d094`
- `0x1400a78e0`
- `0x1400ecd0c`
- `0x1400ed1c0`
- `0x1400ed350`
- `0x14010a2c0`
- `0x140176874`
- `0x140178b7c`
- `0x1401b0470`
- `0x140222f28`

## callees

- `0x140004c3c`
- `0x1400143c0`
- `0x1400b71ac`
- `0x1400bcaa0`
- `0x1400ec110`
- `0x1400ed244`
- `0x1400ed450`
- `0x1400ee278`
- `0x1400ee36c`
- `0x1400ee48c`
- `0x1400ee51c`
- `0x1400eec14`
- `0x1400ef954`
- `0x1402913f0`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x1400ed4e4`
- `ntoskrnl!PsGetThreadId` at `0x1400ed757`
- `ntoskrnl!PsGetThreadId` at `0x1400ed8f3`
- `ntoskrnl!PsGetThreadId` at `0x1400eda8f`
- `ntoskrnl!PsGetThreadId` at `0x1400edeca`
- `ntoskrnl!PsGetThreadId` at `0x1400ed4e4`
- `ntoskrnl!PsGetThreadId` at `0x1400ed757`
- `ntoskrnl!PsGetThreadId` at `0x1400ed8f3`
- `ntoskrnl!PsGetThreadId` at `0x1400eda8f`
- `ntoskrnl!PsGetThreadId` at `0x1400edeca`
- `win32kbase!?GetForegroundActivate@tagTHREADINFO@@QEBA?AW4AllowForegroundActivateReason@@XZ` at `0x1400eddd7`
- `win32kbase!?GetForegroundActivate@tagTHREADINFO@@QEBA?AW4AllowForegroundActivateReason@@XZ` at `0x1400eddd7`
- `win32kbase!?SetForegroundActivate@tagTHREADINFO@@QEAAXW4AllowForegroundActivateReason@@@Z` at `0x1400edc94`
- `win32kbase!?SetForegroundActivate@tagTHREADINFO@@QEAAXW4AllowForegroundActivateReason@@@Z` at `0x1400edc94`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x1400eda26`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x1400eda26`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4f3`
- `WIN32K!W32GetUserSessionState` at `0x1400ed582`
- `WIN32K!W32GetUserSessionState` at `0x1400ed650`
- `WIN32K!W32GetUserSessionState` at `0x1400ed766`
- `WIN32K!W32GetUserSessionState` at `0x1400ed805`
- `WIN32K!W32GetUserSessionState` at `0x1400ed902`
- `WIN32K!W32GetUserSessionState` at `0x1400ed975`
- `WIN32K!W32GetUserSessionState` at `0x1400ed9da`
- `WIN32K!W32GetUserSessionState` at `0x1400eda9e`
- `WIN32K!W32GetUserSessionState` at `0x1400edb90`
- `WIN32K!W32GetUserSessionState` at `0x1400edc1a`
- `WIN32K!W32GetUserSessionState` at `0x1400edca5`
- `WIN32K!W32GetUserSessionState` at `0x1400edcc4`
- `WIN32K!W32GetUserSessionState` at `0x1400edd8f`
- `WIN32K!W32GetUserSessionState` at `0x1400ede44`
- `WIN32K!W32GetUserSessionState` at `0x1400eded9`
- `WIN32K!W32GetUserSessionState` at `0x1400edfbe`
- `WIN32K!W32GetUserSessionState` at `0x1400ee15a`
- `WIN32K!W32GetUserSessionState` at `0x1400ee17b`
- `WIN32K!W32GetUserSessionState` at `0x1400ee220`
- `WIN32K!W32GetUserSessionState` at `0x1400ed4f3`
- `WIN32K!W32GetUserSessionState` at `0x1400ed582`
- `WIN32K!W32GetUserSessionState` at `0x1400ed650`
- `WIN32K!W32GetUserSessionState` at `0x1400ed766`
- `WIN32K!W32GetUserSessionState` at `0x1400ed805`
- `WIN32K!W32GetUserSessionState` at `0x1400ed902`
- `WIN32K!W32GetUserSessionState` at `0x1400ed975`
- `WIN32K!W32GetUserSessionState` at `0x1400ed9da`
- `WIN32K!W32GetUserSessionState` at `0x1400eda9e`
- `WIN32K!W32GetUserSessionState` at `0x1400edb90`
- `WIN32K!W32GetUserSessionState` at `0x1400edc1a`
- `WIN32K!W32GetUserSessionState` at `0x1400edca5`
- `WIN32K!W32GetUserSessionState` at `0x1400edcc4`
- `WIN32K!W32GetUserSessionState` at `0x1400edd8f`
- `WIN32K!W32GetUserSessionState` at `0x1400ede44`
- `WIN32K!W32GetUserSessionState` at `0x1400eded9`
- `WIN32K!W32GetUserSessionState` at `0x1400edfbe`
- `WIN32K!W32GetUserSessionState` at `0x1400ee15a`
- `WIN32K!W32GetUserSessionState` at `0x1400ee17b`
- `WIN32K!W32GetUserSessionState` at `0x1400ee220`

## pseudocode

```c
char __fastcall xxxActivateWindowWithOptions(struct tagWND *a1, unsigned int a2, unsigned int a3, int a4, __int16 a5)
{
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
  struct tagWND *v26; // rdi
  bool v27; // bl
  __int64 v28; // rax
  int v29; // edx
  int v30; // r8d
  bool v31; // bl
  int v32; // r12d
  int v33; // r14d
  char v34; // r13
  bool v35; // zf
  PETHREAD *v36; // rbx
  PETHREAD *v37; // rcx
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
  __int64 v71; // rdx
  struct _KTHREAD *v72; // rcx
  __int64 v73; // r8
  __int64 v74; // r9
  int v75; // edi
  bool v76; // bl
  bool v77; // r15
  __int64 v78; // rax
  int v79; // r8d
  int v80; // edx
  PETHREAD *v81; // r13
  __int64 v82; // rdx
  bool v83; // r15
  bool v84; // r12
  char ThreadId; // bl
  __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // r8
  __int64 v89; // r9
  __int64 v90; // rax
  int v91; // r8d
  int v92; // edx
  struct MOVESIZEDATA *v93; // rcx
  bool v94; // bl
  bool v95; // r14
  unsigned int v96; // edi
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // r9
  __int64 v101; // r8
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // r9
  bool v105; // bl
  __int64 v106; // rax
  int v107; // r8d
  int v108; // edx
  __int64 v109; // r9
  const char *v110; // rax
  __int64 v111; // rax
  int v112; // r8d
  int v113; // edx
  bool v114; // bl
  bool v115; // r15
  __int64 v116; // rax
  int v117; // r8d
  int v118; // edx
  bool v119; // bl
  bool v120; // di
  __int64 v121; // rax
  int v122; // r8d
  int v123; // edx
  bool v124; // di
  bool v125; // r14
  char v126; // bl
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  __int64 v130; // r9
  __int64 v131; // rax
  int v132; // r8d
  int v133; // edx
  struct tagWND *v134; // rax
  bool v135; // bl
  bool v136; // r14
  __int64 v137; // rax
  int v138; // edx
  int v139; // r8d
  __int16 v140; // [rsp+38h] [rbp-51h]
  __int16 v141; // [rsp+38h] [rbp-51h]
  bool v142; // [rsp+68h] [rbp-21h]
  unsigned int ForegroundActivate; // [rsp+6Ch] [rbp-1Dh]
  PETHREAD *v144; // [rsp+78h] [rbp-11h]
  __int128 v145; // [rsp+80h] [rbp-9h] BYREF
  ULONG_PTR BugCheckParameter3[9]; // [rsp+90h] [rbp+7h] BYREF

  v7 = (PETHREAD *)PtiCurrent();
  v144 = v7;
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
  v26 = a1;
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 0xC0) == 0x40 )
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
    v140 = 100;
    goto LABEL_21;
  }
  if ( a2 )
  {
    v145 = 0;
    if ( !(unsigned __int8)anonymous_namespace_::ComputeWindowToActivate(a1, a2, a3, &v145) )
      goto LABEL_16;
    v134 = (struct tagWND *)v145;
    v142 = 0;
    if ( !(_QWORD)v145 || (v33 = DWORD2(v145)) == 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3901);
      v134 = (struct tagWND *)v145;
      v33 = DWORD2(v145);
    }
    v32 = a4;
    v35 = a1 == v134;
    v26 = v134;
    a1 = v134;
    v31 = !v35;
  }
  else
  {
    v31 = 0;
    if ( a3 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3889);
    v32 = a4;
    v33 = 1;
    v142 = a4 == 1;
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
    v140 = 101;
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
      v140,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
LABEL_81:
    v34 = 0;
    goto LABEL_47;
  }
  v34 = 0;
  ForegroundActivate = 0;
  if ( !v33 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3920);
  v35 = !v31;
  v36 = v144;
  if ( !v35 )
    Win32HM_LockIntoThread<0>(v144, v26, BugCheckParameter3);
  if ( (a5 & 0x100) != 0 && *((PETHREAD **)v26 + 2) != v144 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3929);
  v37 = (PETHREAD *)*((_QWORD *)v26 + 2);
  if ( v37[58] != v144[58] )
  {
    if ( v37 == v144 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3983);
    v59 = &WPP_GLOBAL_Control;
    v61 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v62 = &WPP_RECORDER_INITIALIZED;
    v63 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v61 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      PsGetThreadId(*v144);
      v68 = W32GetUserSessionState(v65, v64, v66, v67);
      LOBYTE(v69) = v63;
      LOBYTE(v70) = v61;
      WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v70, v69, *(_QWORD *)(v68 + 69152));
      v36 = v144;
      v62 = &WPP_RECORDER_INITIALIZED;
      v59 = &WPP_GLOBAL_Control;
    }
    if ( v33 == 5 )
    {
      v75 = 31;
      v135 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v136 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v135 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v137 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, &WPP_GLOBAL_Control, v10);
        v141 = 107;
        goto LABEL_173;
      }
    }
    else
    {
      if ( v33 != 6 )
      {
        v72 = *(struct _KTHREAD **)(W32GetUserSessionState(
                                      (unsigned int)(v33 - 5),
                                      &WPP_RECORDER_INITIALIZED,
                                      &WPP_GLOBAL_Control,
                                      v10)
                                  + 18968);
        if ( v72 != v36[58] && *(_QWORD *)(W32GetUserSessionState(v72, v71, v73, v74) + 18968) )
          goto LABEL_47;
        v75 = 2;
        v76 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v77 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v76 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v78 = W32GetUserSessionState(WPP_GLOBAL_Control, v71, v73, v74);
          LOBYTE(v79) = v77;
          LOBYTE(v80) = v76;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v80,
            v79,
            *(_QWORD *)(v78 + 69152),
            4,
            2,
            109,
            (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        }
        v81 = v144;
        if ( tagTHREADINFO::ComputeAndTestForegroundActivate((tagTHREADINFO *)v144) )
        {
          v114 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v115 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v114 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v116 = W32GetUserSessionState(WPP_GLOBAL_Control, v82, v59, v10);
            LOBYTE(v117) = v115;
            LOBYTE(v118) = v114;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v118,
              v117,
              *(_QWORD *)(v116 + 69152),
              4,
              2,
              110,
              (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
          }
          ForegroundActivate = tagTHREADINFO::GetForegroundActivate(v144);
        }
        else if ( *((_DWORD *)v144 + 234) || v142 )
        {
          v83 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v84 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v83 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            ThreadId = (unsigned __int8)PsGetThreadId(*v144);
            v90 = W32GetUserSessionState(v87, v86, v88, v89);
            LOBYTE(v91) = v84;
            LOBYTE(v92) = v83;
            WPP_RECORDER_AND_TRACE_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v92,
              v91,
              *(_QWORD *)(v90 + 69152),
              4,
              2,
              111,
              (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
              ThreadId);
          }
          ForegroundActivate = 64;
        }
        v58 = a1;
        if ( (unsigned int)(v33 - 3) < 2 )
          v75 = 3;
        goto LABEL_83;
      }
      v75 = 31;
      v135 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v136 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v135 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v137 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, &WPP_GLOBAL_Control, v10);
        v141 = 108;
LABEL_173:
        LOBYTE(v139) = v136;
        LOBYTE(v138) = v135;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v138,
          v139,
          *(_QWORD *)(v137 + 69152),
          4,
          2,
          v141,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        v81 = v144;
        v58 = a1;
        goto LABEL_83;
      }
    }
    v81 = v144;
    v58 = a1;
LABEL_84:
    v93 = WPP_GLOBAL_Control;
    v94 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v95 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v94 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v111 = W32GetUserSessionState(WPP_GLOBAL_Control, &WPP_RECORDER_INITIALIZED, v59, v10);
      LOBYTE(v112) = v95;
      LOBYTE(v113) = v94;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v113,
        v112,
        *(_QWORD *)(v111 + 69152),
        4,
        2,
        112,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v96 = v75 | 4;
    v98 = *(_QWORD *)(W32GetUserSessionState(v93, v62, v59, v10) + 18968);
    if ( *(_QWORD *)(*((_QWORD *)v58 + 2) + 464LL) == v98
      && *(PETHREAD *)(W32GetUserSessionState(v98, v97, v99, v100) + 18968) == v81[58] )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4111);
    }
    v101 = a5 & 0x100 | 4u;
    if ( (a5 & 2) == 0 )
      v101 = a5 & 0x100;
    v34 = xxxSetForegroundWindowWithOptions(v58, v96, v101, v142);
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v9 = 0;
    }
    v105 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v106 = W32GetUserSessionState(WPP_GLOBAL_Control, v102, v103, v104);
      LOBYTE(v107) = v105;
      LOBYTE(v108) = v9;
      v109 = *(_QWORD *)(v106 + 69152);
      v110 = "Success";
      if ( !v34 )
        v110 = "Failure";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v108,
        v107,
        v109,
        4,
        2,
        113,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
        (__int64)v110);
    }
    if ( v34 && ForegroundActivate )
      tagTHREADINFO::SetForegroundActivate(v144, ForegroundActivate);
    goto LABEL_47;
  }
  v38 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v39 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v38 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(*v144);
    v44 = W32GetUserSessionState(v41, v40, v42, v43);
    LOBYTE(v45) = v39;
    LOBYTE(v46) = v38;
    WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v46, v45, *(_QWORD *)(v44 + 69152));
    v26 = a1;
  }
  v51 = anonymous_namespace_::FAllowForegroundActivate(v26, v12, v8, v10);
  if ( v51 )
  {
    v10 = (__int64)&WPP_GLOBAL_Control;
    v119 = 0;
    if ( WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control )
    {
      v48 = *((unsigned int *)WPP_GLOBAL_Control + 11);
      if ( (v48 & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
        v119 = 1;
    }
    v120 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v119 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v121 = W32GetUserSessionState(v48, &WPP_RECORDER_INITIALIZED, v49, &WPP_GLOBAL_Control);
      LOBYTE(v122) = v120;
      LOBYTE(v123) = v119;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v123,
        v122,
        *(_QWORD *)(v121 + 69152),
        4,
        2,
        103,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
      v10 = (__int64)&WPP_GLOBAL_Control;
    }
    v59 = v144;
    if ( !*((_DWORD *)v144 + 234) )
    {
      ForegroundActivate = 32;
      v124 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v125 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v124 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v126 = (unsigned __int8)PsGetThreadId(*v144);
        v131 = W32GetUserSessionState(v128, v127, v129, v130);
        LOBYTE(v132) = v125;
        LOBYTE(v133) = v124;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v133,
          v132,
          *(_QWORD *)(v131 + 69152),
          4,
          2,
          104,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
          v126);
      }
    }
    v58 = a1;
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
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v57 = v32 != 0;
    v58 = a1;
    a5 |= 129 - v57;
    v34 = anonymous_namespace_::xxxLocalActivateWindow(a1);
  }
  if ( v51 )
  {
    v81 = v144;
    v75 = 2;
LABEL_83:
    v62 = &WPP_RECORDER_INITIALIZED;
    goto LABEL_84;
  }
LABEL_47:
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  return v34;
}

```

## disassembly

```asm
0x1400ed450  mov     rax, rsp
0x1400ed453  mov     [rax+10h], rbx
0x1400ed457  mov     [rax+20h], r9d
0x1400ed45b  mov     [rax+8], rcx
0x1400ed45f  push    rbp
0x1400ed460  push    rsi
0x1400ed461  push    rdi
0x1400ed462  push    r12
0x1400ed464  push    r13
0x1400ed466  push    r14
0x1400ed468  push    r15
0x1400ed46a  lea     rbp, [rax-57h]
0x1400ed46e  sub     rsp, 0A0h
0x1400ed475  mov     r13d, r8d
0x1400ed478  mov     r12d, edx
0x1400ed47b  mov     rbx, rcx
0x1400ed47e  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x1400ed483  mov     [rbp+4Fh+var_60], rax
0x1400ed487  mov     [rbp+4Fh+var_40], 0
0x1400ed48f  mov     [rbp+4Fh+BugCheckParameter3], 0FFFFFFFFFFFFFFFFh
0x1400ed497  mov     rdx, cs:WPP_GLOBAL_Control
0x1400ed49e  lea     r10, WPP_GLOBAL_Control
0x1400ed4a5  mov     esi, 1
0x1400ed4aa  lea     r9d, [rsi+1]
0x1400ed4ae  cmp     rdx, r10
0x1400ed4b1  jz      short loc_1400ED4BF
0x1400ed4b3  mov     ecx, [rdx+2Ch]
0x1400ed4b6  test    r9b, cl
0x1400ed4b9  jnz     loc_1400EDF80
0x1400ed4bf  xor     r14b, r14b
0x1400ed4c2  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400ed4c9  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400ed4d0  setnz   r15b
0x1400ed4d4  test    r14b, r14b
0x1400ed4d7  jnz     short loc_1400ED4DE
0x1400ed4d9  test    r15b, r15b
0x1400ed4dc  jz      short loc_1400ED554
0x1400ed4de  mov     rcx, [rax]; Thread
0x1400ed4e1  mov     rdi, [rbx]
0x1400ed4e4  call    cs:__imp_PsGetThreadId
0x1400ed4eb  nop     dword ptr [rax+rax+00h]
0x1400ed4f0  mov     rbx, rax
0x1400ed4f3  call    cs:__imp_W32GetUserSessionState
0x1400ed4fa  nop     dword ptr [rax+rax+00h]
0x1400ed4ff  mov     qword ptr [rsp+0D0h+var_88], rdi
0x1400ed504  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400ed50b  mov     dword ptr [rsp+0D0h+var_90], ebx
0x1400ed50f  mov     r8b, r15b
0x1400ed512  mov     [rsp+0D0h+var_98], rcx
0x1400ed517  mov     dl, r14b
0x1400ed51a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed521  mov     r9, [rax+10E20h]
0x1400ed528  mov     word ptr [rsp+0D0h+var_A0], 62h ; 'b'
0x1400ed52f  mov     dword ptr [rsp+0D0h+var_A8], 2
0x1400ed537  mov     rcx, [rcx+18h]
0x1400ed53b  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x1400ed540  mov     r9d, 2
0x1400ed546  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400ed54d  lea     r10, WPP_GLOBAL_Control
0x1400ed554  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed55b  cmp     rcx, r10
0x1400ed55e  jz      short loc_1400ED56C
0x1400ed560  mov     eax, [rcx+2Ch]
0x1400ed563  test    r9b, al
0x1400ed566  jnz     loc_1400EDF92
0x1400ed56c  xor     bl, bl
0x1400ed56e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400ed575  setnz   dil
0x1400ed579  test    bl, bl
0x1400ed57b  jnz     short loc_1400ED582
0x1400ed57d  test    dil, dil
0x1400ed580  jz      short loc_1400ED5D7
0x1400ed582  call    cs:__imp_W32GetUserSessionState
0x1400ed589  nop     dword ptr [rax+rax+00h]
0x1400ed58e  mov     ecx, [rbp+4Fh+arg_20]
0x1400ed591  mov     r8b, dil
0x1400ed594  mov     [rsp+58h], ecx
0x1400ed598  mov     dl, bl
0x1400ed59a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed5a1  mov     r9, [rax+10E20h]
0x1400ed5a8  mov     eax, [rbp+4Fh+arg_18]
0x1400ed5ab  mov     [rsp+0D0h+var_80], eax
0x1400ed5af  mov     rcx, [rcx+18h]
0x1400ed5b3  mov     [rsp+0D0h+var_88], r13d
0x1400ed5b8  mov     dword ptr [rsp+0D0h+var_90], r12d
0x1400ed5bd  mov     word ptr [rsp+0D0h+var_A0], 63h ; 'c'
0x1400ed5c4  call    WPP_RECORDER_AND_TRACE_SF_DDdD
0x1400ed5c9  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400ed5d0  lea     r10, WPP_GLOBAL_Control
0x1400ed5d7  mov     rdi, [rbp+4Fh+arg_0]
0x1400ed5db  mov     rax, [rdi+28h]
0x1400ed5df  mov     cl, [rax+1Fh]
0x1400ed5e2  and     cl, 0C0h
0x1400ed5e5  cmp     cl, 40h ; '@'
0x1400ed5e8  jz      loc_1400EDB0E
0x1400ed5ee  test    r12d, r12d
0x1400ed5f1  jz      loc_1400ED69E
0x1400ed5f7  xorps   xmm0, xmm0
0x1400ed5fa  lea     r9, [rbp+4Fh+var_58]
0x1400ed5fe  mov     r8d, r13d
0x1400ed601  mov     edx, r12d
0x1400ed604  mov     rcx, rdi
0x1400ed607  movups  [rbp+4Fh+var_58], xmm0
0x1400ed60b  call    _anonymous_namespace___ComputeWindowToActivate
0x1400ed610  test    al, al
0x1400ed612  jnz     loc_1400EDF45
0x1400ed618  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed61f  lea     rax, WPP_GLOBAL_Control
0x1400ed626  cmp     rcx, rax
0x1400ed629  jnz     loc_1400EDD2C
0x1400ed62f  xor     sil, sil
0x1400ed632  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ed639  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ed640  setnz   bl
0x1400ed643  test    sil, sil
0x1400ed646  jnz     short loc_1400ED650
0x1400ed648  test    bl, bl
0x1400ed64a  jz      loc_1400EDB3C
0x1400ed650  call    cs:__imp_W32GetUserSessionState
0x1400ed657  nop     dword ptr [rax+rax+00h]
0x1400ed65c  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400ed663  mov     [rsp+0D0h+var_98], rcx
0x1400ed668  mov     word ptr [rsp+0D0h+var_A0], 65h ; 'e'
0x1400ed66f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed676  mov     r8b, bl
0x1400ed679  mov     r9, [rax+10E20h]
0x1400ed680  mov     dl, sil
0x1400ed683  mov     dword ptr [rsp+0D0h+var_A8], 2
0x1400ed68b  mov     byte ptr [rsp+0D0h+var_B0], 4
0x1400ed690  mov     rcx, [rcx+18h]
0x1400ed694  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ed699  jmp     loc_1400EDB3C
0x1400ed69e  xor     bl, bl
0x1400ed6a0  lea     r15, aIxptelassert; "IXPTelAssert"
0x1400ed6a7  test    r13d, r13d
0x1400ed6aa  jnz     loc_1400EDFE2
0x1400ed6b0  mov     r12d, [rbp+4Fh+arg_18]
0x1400ed6b4  mov     r14d, esi
0x1400ed6b7  cmp     r12d, esi
0x1400ed6ba  setz    [rbp+4Fh+var_70]
0x1400ed6be  test    rdi, rdi
0x1400ed6c1  jz      loc_1400ED618
0x1400ed6c7  xor     eax, eax
0x1400ed6c9  xor     r13b, r13b
0x1400ed6cc  mov     [rbp+4Fh+var_6C], eax
0x1400ed6cf  test    r14d, r14d
0x1400ed6d2  jz      loc_1400EDF28
0x1400ed6d8  test    bl, bl
0x1400ed6da  mov     rbx, [rbp+4Fh+var_60]
0x1400ed6de  jz      short loc_1400ED6EF
0x1400ed6e0  lea     r8, [rbp+4Fh+BugCheckParameter3]
0x1400ed6e4  mov     rdx, rdi
0x1400ed6e7  mov     rcx, rbx
0x1400ed6ea  call    ??$Win32HM_LockIntoThread@$0A@@@YAXPEAUtagTHREADINFO@@PEAU_HEAD@@PEAU_Win32HMThreadLockItem@@@Z; Win32HM_LockIntoThread<0>(tagTHREADINFO *,_HEAD *,_Win32HMThreadLockItem *)
0x1400ed6ef  test    [rbp+4Fh+arg_20], 100h
0x1400ed6f6  jnz     loc_1400EE024
0x1400ed6fc  mov     rcx, [rdi+10h]
0x1400ed700  mov     rax, [rbx+1D0h]
0x1400ed707  cmp     [rcx+1D0h], rax
0x1400ed70e  jnz     loc_1400ED8A0
0x1400ed714  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed71b  lea     rax, WPP_GLOBAL_Control
0x1400ed722  cmp     rcx, rax
0x1400ed725  jz      short loc_1400ED732
0x1400ed727  mov     eax, [rcx+2Ch]
0x1400ed72a  test    al, 2
0x1400ed72c  jnz     loc_1400EE04B
0x1400ed732  xor     r14b, r14b
0x1400ed735  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ed73c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ed743  setnz   r15b
0x1400ed747  test    r14b, r14b
0x1400ed74a  jnz     short loc_1400ED751
0x1400ed74c  test    r15b, r15b
0x1400ed74f  jz      short loc_1400ED7B7
0x1400ed751  mov     rcx, [rbx]; Thread
0x1400ed754  mov     rdi, [rdi]
0x1400ed757  call    cs:__imp_PsGetThreadId
0x1400ed75e  nop     dword ptr [rax+rax+00h]
0x1400ed763  mov     rbx, rax
0x1400ed766  call    cs:__imp_W32GetUserSessionState
0x1400ed76d  nop     dword ptr [rax+rax+00h]
0x1400ed772  mov     qword ptr [rsp+0D0h+var_88], rdi
0x1400ed777  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400ed77e  mov     dword ptr [rsp+0D0h+var_90], ebx
0x1400ed782  mov     r8b, r15b
0x1400ed785  mov     [rsp+0D0h+var_98], rcx
0x1400ed78a  mov     dl, r14b
0x1400ed78d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed794  mov     r9, [rax+10E20h]
0x1400ed79b  mov     word ptr [rsp+0D0h+var_A0], 66h ; 'f'
0x1400ed7a2  mov     dword ptr [rsp+0D0h+var_A8], 2
0x1400ed7aa  mov     rcx, [rcx+18h]
0x1400ed7ae  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x1400ed7b3  mov     rdi, [rbp+4Fh+arg_0]
0x1400ed7b7  mov     rcx, rdi
0x1400ed7ba  call    _anonymous_namespace___FAllowForegroundActivate
0x1400ed7bf  mov     r15b, al
0x1400ed7c2  test    al, al
0x1400ed7c4  jnz     loc_1400EDDEB
0x1400ed7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed7d1  lea     rax, WPP_GLOBAL_Control
0x1400ed7d8  cmp     rcx, rax
0x1400ed7db  jz      short loc_1400ED7E8
0x1400ed7dd  mov     eax, [rcx+2Ch]
0x1400ed7e0  test    al, 2
0x1400ed7e2  jnz     loc_1400EE09B
0x1400ed7e8  xor     bl, bl
0x1400ed7ea  lea     rax, WPP_RECORDER_INITIALIZED
0x1400ed7f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ed7f8  setnz   dil
0x1400ed7fc  test    bl, bl
0x1400ed7fe  jnz     short loc_1400ED805
0x1400ed800  test    dil, dil
0x1400ed803  jz      short loc_1400ED84D
0x1400ed805  call    cs:__imp_W32GetUserSessionState
0x1400ed80c  nop     dword ptr [rax+rax+00h]
0x1400ed811  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400ed818  mov     r8b, dil
0x1400ed81b  mov     [rsp+0D0h+var_98], rcx
0x1400ed820  mov     dl, bl
0x1400ed822  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed829  mov     r9, [rax+10E20h]
0x1400ed830  mov     word ptr [rsp+0D0h+var_A0], 69h ; 'i'
0x1400ed837  mov     dword ptr [rsp+0D0h+var_A8], 2
0x1400ed83f  mov     rcx, [rcx+18h]
0x1400ed843  mov     byte ptr [rsp+0D0h+var_B0], 4
0x1400ed848  call    WPP_RECORDER_AND_TRACE_SF_
0x1400ed84d  neg     r12d
0x1400ed850  mov     r12, [rbp+4Fh+arg_0]
0x1400ed854  sbb     eax, eax
0x1400ed856  mov     rcx, r12; struct tagWND *
0x1400ed859  add     eax, 81h
0x1400ed85e  xor     edx, edx
0x1400ed860  or      [rbp+4Fh+arg_20], eax
0x1400ed863  mov     r8d, [rbp+4Fh+arg_20]
0x1400ed867  call    _anonymous_namespace___xxxLocalActivateWindow
0x1400ed86c  mov     r13b, al
0x1400ed86f  test    r15b, r15b
0x1400ed872  jnz     loc_1400EDB44
0x1400ed878  lea     rcx, [rbp+4Fh+BugCheckParameter3]; BugCheckParameter3
0x1400ed87c  call    ??1?$Win32HMOptionalThreadLockAlways@UtagMENU@@@@QEAA@XZ; Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>(void)
0x1400ed881  mov     rbx, [rsp+0D0h+arg_8]
0x1400ed889  mov     al, r13b
0x1400ed88c  add     rsp, 0A0h
0x1400ed893  pop     r15
0x1400ed895  pop     r14
0x1400ed897  pop     r13
0x1400ed899  pop     r12
0x1400ed89b  pop     rdi
0x1400ed89c  pop     rsi
0x1400ed89d  pop     rbp
0x1400ed89e  retn
0x1400ed8a0  cmp     rcx, rbx
0x1400ed8a3  jz      loc_1400EE0AD
0x1400ed8a9  mov     r12d, 2
0x1400ed8af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed8b6  lea     r8, WPP_GLOBAL_Control
0x1400ed8bd  cmp     rcx, r8
0x1400ed8c0  jz      short loc_1400ED8CE
0x1400ed8c2  mov     eax, [rcx+2Ch]
0x1400ed8c5  test    r12b, al
0x1400ed8c8  jnz     loc_1400EE0D0
0x1400ed8ce  xor     r15b, r15b
0x1400ed8d1  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400ed8d8  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400ed8df  setnz   r12b
0x1400ed8e3  test    r15b, r15b
0x1400ed8e6  jnz     short loc_1400ED8ED
0x1400ed8e8  test    r12b, r12b
0x1400ed8eb  jz      short loc_1400ED961
0x1400ed8ed  mov     rcx, [rbx]; Thread
0x1400ed8f0  mov     rdi, [rdi]
0x1400ed8f3  call    cs:__imp_PsGetThreadId
0x1400ed8fa  nop     dword ptr [rax+rax+00h]
0x1400ed8ff  mov     rbx, rax
0x1400ed902  call    cs:__imp_W32GetUserSessionState
0x1400ed909  nop     dword ptr [rax+rax+00h]
0x1400ed90e  mov     qword ptr [rsp+0D0h+var_88], rdi
0x1400ed913  lea     rcx, WPP_dad220efef7b365d279206ae321641e5_Traceguids
0x1400ed91a  mov     dword ptr [rsp+0D0h+var_90], ebx
0x1400ed91e  mov     r8b, r12b
0x1400ed921  mov     [rsp+0D0h+var_98], rcx
0x1400ed926  mov     dl, r15b
0x1400ed929  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ed930  mov     r9, [rax+10E20h]
0x1400ed937  mov     word ptr [rsp+0D0h+var_A0], 6Ah ; 'j'
0x1400ed93e  mov     dword ptr [rsp+0D0h+var_A8], 2
0x1400ed946  mov     rcx, [rcx+18h]
0x1400ed94a  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x1400ed94f  mov     rbx, [rbp+4Fh+var_60]
0x1400ed953  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400ed95a  lea     r8, WPP_GLOBAL_Control
0x1400ed961  mov     ecx, r14d
0x1400ed964  sub     ecx, 5
0x1400ed967  jz      loc_1400EE1CD
0x1400ed96d  cmp     ecx, esi
0x1400ed96f  jz      loc_1400EE118
0x1400ed975  call    cs:__imp_W32GetUserSessionState
0x1400ed97c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
