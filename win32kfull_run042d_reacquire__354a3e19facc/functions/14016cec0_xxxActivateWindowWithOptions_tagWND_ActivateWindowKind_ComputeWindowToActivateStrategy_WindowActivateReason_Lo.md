# xxxActivateWindowWithOptions(tagWND *,ActivateWindowKind,ComputeWindowToActivateStrategy,WindowActivateReason,LocalActivationOptions)

- ea: `0x14016cec0`
- end: `0x14016dce0`
- name: `?xxxActivateWindowWithOptions@@YA_NPEAUtagWND@@W4ActivateWindowKind@@W4ComputeWindowToActivateStrategy@@W4WindowActivateReason@@W4LocalActivationOptions@@@Z`
- size: `3616`
- prototype: ``
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
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3906);
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
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3894);
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
      (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
LABEL_81:
    v31 = 0;
    goto LABEL_47;
  }
  v31 = 0;
  ForegroundActivate = 0;
  if ( !v30 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3925);
  v32 = !v28;
  v33 = v114;
  if ( !v32 )
    Win32HM_LockIntoThread<0>(v114, v23, BugCheckParameter3, v10);
  if ( (a5 & 0x100) != 0 && *((PETHREAD **)v23 + 2) != v114 )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3934);
  v34 = (PETHREAD *)*((_QWORD *)v23 + 2);
  if ( v34[58] != v114[58] )
  {
    if ( v34 == v114 )
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 3988);
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
            (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
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
              (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
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
              (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
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
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
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
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
    }
    v75 = v58 | 4;
    v76 = *(_QWORD *)(W32GetUserSessionState(v72) + 18968);
    if ( *(_QWORD *)(*((_QWORD *)v49 + 2) + 464LL) == v76
      && *(PETHREAD *)(W32GetUserSessionState(v76) + 18968) == v64[58] )
    {
      MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4116);
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
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
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
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
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
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids,
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
        (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
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
