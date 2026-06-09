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
  __int64 v14; // rcx
  __int64 UserSessionState; // rax
  int v16; // r8d
  int v17; // edx
  bool v18; // bl
  bool v19; // di
  __int64 v20; // rax
  int v21; // r8d
  int v22; // edx
  struct tagWND *v23; // rdi
  bool v24; // bl
  __int64 v25; // rax
  int v26; // edx
  int v27; // r8d
  bool v28; // bl
  int v29; // r12d
  int v30; // r14d
  char v31; // r13
  bool v32; // zf
  PETHREAD *v33; // rbx
  PETHREAD *v34; // rcx
  bool v35; // r14
  bool v36; // r15
  __int64 v37; // rcx
  __int64 v38; // rax
  int v39; // r8d
  int v40; // edx
  __int64 v41; // rcx
  char v42; // r15
  bool v43; // bl
  bool v44; // di
  __int64 v45; // rax
  int v46; // r8d
  int v47; // edx
  bool v48; // cf
  struct tagWND *v49; // r12
  bool v51; // r15
  bool v52; // r12
  __int64 v53; // rcx
  __int64 v54; // rax
  int v55; // r8d
  int v56; // edx
  struct _KTHREAD *v57; // rcx
  int v58; // edi
  bool v59; // bl
  bool v60; // r15
  __int64 v61; // rax
  int v62; // r8d
  int v63; // edx
  PETHREAD *v64; // r13
  bool v65; // r15
  bool v66; // r12
  char ThreadId; // bl
  __int64 v68; // rcx
  __int64 v69; // rax
  int v70; // r8d
  int v71; // edx
  struct MOVESIZEDATA *v72; // rcx
  bool v73; // bl
  bool v74; // r14
  unsigned int v75; // edi
  __int64 v76; // rcx
  __int64 v77; // r8
  bool v78; // bl
  __int64 v79; // rax
  int v80; // r8d
  int v81; // edx
  __int64 v82; // r9
  const char *v83; // rax
  __int64 v84; // rax
  int v85; // r8d
  int v86; // edx
  bool v87; // bl
  bool v88; // r15
  __int64 v89; // rax
  int v90; // r8d
  int v91; // edx
  bool v92; // bl
  bool v93; // di
  __int64 v94; // rax
  int v95; // r8d
  int v96; // edx
  bool v97; // di
  bool v98; // r14
  char v99; // bl
  __int64 v100; // rcx
  __int64 v101; // rax
  int v102; // r8d
  int v103; // edx
  struct tagWND *v104; // rax
  bool v105; // bl
  bool v106; // r14
  __int64 v107; // rax
  int v108; // edx
  int v109; // r8d
  __int16 v110; // [rsp+38h] [rbp-51h]
  __int16 v111; // [rsp+38h] [rbp-51h]
  bool v112; // [rsp+68h] [rbp-21h]
  unsigned int ForegroundActivate; // [rsp+6Ch] [rbp-1Dh]
  PETHREAD *v114; // [rsp+78h] [rbp-11h]
  __int128 v115; // [rsp+80h] [rbp-9h] BYREF
  ULONG_PTR BugCheckParameter3[9]; // [rsp+90h] [rbp+7h] BYREF

  v7 = (PETHREAD *)PtiCurrent();
  v114 = v7;
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
    UserSessionState = W32GetUserSessionState(v14);
    LOBYTE(v16) = v13;
    LOBYTE(v17) = v11;
    WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v17, v16, *(_QWORD *)(UserSessionState + 69152));
    v10 = 2;
    v12 = &WPP_RECORDER_INITIALIZED;
  }
  v18 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v19 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v18 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v20 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v21) = v19;
    LOBYTE(v22) = v18;
    WPP_RECORDER_AND_TRACE_SF_DDdD(*((_QWORD *)WPP_GLOBAL_Control + 3), v22, v21, *(_QWORD *)(v20 + 69152));
    v12 = &WPP_RECORDER_INITIALIZED;
  }
  v23 = a1;
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 5) + 31LL) & 0xC0) == 0x40 )
  {
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v9 = 0;
    }
    v24 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( !v9 && *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_81;
    v25 = W32GetUserSessionState(WPP_GLOBAL_Control);
    v110 = 100;
    goto LABEL_21;
  }
  if ( a2 )
  {
    v115 = 0;
    if ( !(unsigned __int8)anonymous_namespace_::ComputeWindowToActivate(a1, a2, a3, &v115) )
      goto LABEL_16;
    v104 = (struct tagWND *)v115;
    v112 = 0;
    if ( !(_QWORD)v115 || (v30 = DWORD2(v115)) == 0 )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3901);
      v104 = (struct tagWND *)v115;
      v30 = DWORD2(v115);
    }
    v29 = a4;
    v32 = a1 == v104;
    v23 = v104;
    a1 = v104;
    v28 = !v32;
  }
  else
  {
    v28 = 0;
    if ( a3 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3889);
    v29 = a4;
    v30 = 1;
    v112 = a4 == 1;
  }
  if ( !v23 )
  {
LABEL_16:
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v9 = 0;
    }
    v24 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( !v9 && *(unsigned int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
      goto LABEL_81;
    v25 = W32GetUserSessionState(WPP_GLOBAL_Control);
    v110 = 101;
LABEL_21:
    LOBYTE(v27) = v24;
    LOBYTE(v26) = v9;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v26,
      v27,
      *(_QWORD *)(v25 + 69152),
      4,
      2,
      v110,
      (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
LABEL_81:
    v31 = 0;
    goto LABEL_47;
  }
  v31 = 0;
  ForegroundActivate = 0;
  if ( !v30 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3920);
  v32 = !v28;
  v33 = v114;
  if ( !v32 )
    Win32HM_LockIntoThread<0>(v114, v23, BugCheckParameter3, v10);
  if ( (a5 & 0x100) != 0 && *((PETHREAD **)v23 + 2) != v114 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3929);
  v34 = (PETHREAD *)*((_QWORD *)v23 + 2);
  if ( v34[58] != v114[58] )
  {
    if ( v34 == v114 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3983);
    v51 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v52 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v51 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      PsGetThreadId(*v114);
      v54 = W32GetUserSessionState(v53);
      LOBYTE(v55) = v52;
      LOBYTE(v56) = v51;
      WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v56, v55, *(_QWORD *)(v54 + 69152));
      v33 = v114;
    }
    if ( v30 == 5 )
    {
      v58 = 31;
      v105 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v106 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v105 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v107 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v111 = 107;
        goto LABEL_172;
      }
    }
    else
    {
      if ( v30 != 6 )
      {
        v57 = *(struct _KTHREAD **)(W32GetUserSessionState((unsigned int)(v30 - 5)) + 18968);
        if ( v57 != v33[58] && *(_QWORD *)(W32GetUserSessionState(v57) + 18968) )
          goto LABEL_47;
        v58 = 2;
        v59 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v60 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v59 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v61 = W32GetUserSessionState(WPP_GLOBAL_Control);
          LOBYTE(v62) = v60;
          LOBYTE(v63) = v59;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v63,
            v62,
            *(_QWORD *)(v61 + 69152),
            4,
            2,
            109,
            (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        }
        v64 = v114;
        if ( tagTHREADINFO::ComputeAndTestForegroundActivate((tagTHREADINFO *)v114) )
        {
          v87 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v88 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v87 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v89 = W32GetUserSessionState(WPP_GLOBAL_Control);
            LOBYTE(v90) = v88;
            LOBYTE(v91) = v87;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v91,
              v90,
              *(_QWORD *)(v89 + 69152),
              4,
              2,
              110,
              (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
          }
          ForegroundActivate = tagTHREADINFO::GetForegroundActivate(v114);
        }
        else if ( *((_DWORD *)v114 + 234) || v112 )
        {
          v65 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v66 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v65 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            ThreadId = (unsigned __int8)PsGetThreadId(*v114);
            v69 = W32GetUserSessionState(v68);
            LOBYTE(v70) = v66;
            LOBYTE(v71) = v65;
            WPP_RECORDER_AND_TRACE_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v71,
              v70,
              *(_QWORD *)(v69 + 69152),
              4,
              2,
              111,
              (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
              ThreadId);
          }
          ForegroundActivate = 64;
        }
        v49 = a1;
        if ( (unsigned int)(v30 - 3) < 2 )
          v58 = 3;
        goto LABEL_83;
      }
      v58 = 31;
      v105 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v106 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v105 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v107 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v111 = 108;
LABEL_172:
        LOBYTE(v109) = v106;
        LOBYTE(v108) = v105;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v108,
          v109,
          *(_QWORD *)(v107 + 69152),
          4,
          2,
          v111,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
        v64 = v114;
        v49 = a1;
        goto LABEL_83;
      }
    }
    v64 = v114;
    v49 = a1;
LABEL_83:
    v72 = WPP_GLOBAL_Control;
    v73 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v74 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v73 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v84 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v85) = v74;
      LOBYTE(v86) = v73;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v86,
        v85,
        *(_QWORD *)(v84 + 69152),
        4,
        2,
        112,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v75 = v58 | 4;
    v76 = *(_QWORD *)(W32GetUserSessionState(v72) + 18968);
    if ( *(_QWORD *)(*((_QWORD *)v49 + 2) + 464LL) == v76
      && *(PETHREAD *)(W32GetUserSessionState(v76) + 18968) == v64[58] )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4111);
    }
    v77 = a5 & 0x100 | 4u;
    if ( (a5 & 2) == 0 )
      v77 = a5 & 0x100;
    v31 = xxxSetForegroundWindowWithOptions(v49, v75, v77, v112);
    if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
    {
      v9 = 0;
    }
    v78 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v79 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v80) = v78;
      LOBYTE(v81) = v9;
      v82 = *(_QWORD *)(v79 + 69152);
      v83 = "Success";
      if ( !v31 )
        v83 = "Failure";
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v81,
        v80,
        v82,
        4,
        2,
        113,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
        (__int64)v83);
    }
    if ( v31 && ForegroundActivate )
      tagTHREADINFO::SetForegroundActivate(v114, ForegroundActivate);
    goto LABEL_47;
  }
  v35 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v36 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v35 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    PsGetThreadId(*v114);
    v38 = W32GetUserSessionState(v37);
    LOBYTE(v39) = v36;
    LOBYTE(v40) = v35;
    WPP_RECORDER_AND_TRACE_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 3), v40, v39, *(_QWORD *)(v38 + 69152));
    v23 = a1;
  }
  v42 = anonymous_namespace_::FAllowForegroundActivate(v23, v12, v8, v10);
  if ( v42 )
  {
    v92 = 0;
    if ( WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control )
    {
      v41 = *((unsigned int *)WPP_GLOBAL_Control + 11);
      if ( (v41 & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
        v92 = 1;
    }
    v93 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v92 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v94 = W32GetUserSessionState(v41);
      LOBYTE(v95) = v93;
      LOBYTE(v96) = v92;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v96,
        v95,
        *(_QWORD *)(v94 + 69152),
        4,
        2,
        103,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    if ( !*((_DWORD *)v114 + 234) )
    {
      ForegroundActivate = 32;
      v97 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v98 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v97 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v99 = (unsigned __int8)PsGetThreadId(*v114);
        v101 = W32GetUserSessionState(v100);
        LOBYTE(v102) = v98;
        LOBYTE(v103) = v97;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v103,
          v102,
          *(_QWORD *)(v101 + 69152),
          4,
          2,
          104,
          (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids,
          v99);
      }
    }
    v49 = a1;
  }
  else
  {
    v43 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v44 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v43 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v45 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v46) = v44;
      LOBYTE(v47) = v43;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v47,
        v46,
        *(_QWORD *)(v45 + 69152),
        4,
        2,
        105,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v48 = v29 != 0;
    v49 = a1;
    a5 |= 129 - v48;
    v31 = anonymous_namespace_::xxxLocalActivateWindow(a1);
  }
  if ( v42 )
  {
    v64 = v114;
    v58 = 2;
    goto LABEL_83;
  }
LABEL_47:
  Win32HMOptionalThreadLockAlways<tagMENU>::~Win32HMOptionalThreadLockAlways<tagMENU>((ULONG_PTR)BugCheckParameter3);
  return v31;
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
