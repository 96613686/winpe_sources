# CForegroundLaunch::_CheckAllowForeground(tagPROCESSINFO const *)

- ea: `0x1402750dc`
- end: `0x140275bd2`
- name: `?_CheckAllowForeground@CForegroundLaunch@@AEBA_NPEBUtagPROCESSINFO@@@Z`
- size: `2806`
- prototype: `bool __fastcall(CForegroundLaunch *__hidden this, const struct tagPROCESSINFO *)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ec5a4`
- `0x14017a7c4`
- `0x140213ab4`

## callees

- `0x140077cc8`
- `0x1400b71ac`
- `0x1400e89a4`
- `0x1400eaad0`
- `0x1400eb130`
- `0x1400eb774`
- `0x1400ebeb8`
- `0x1400ec110`
- `0x1400f39a4`
- `0x1402750dc`
- `0x1402913f0`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1402754a7`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1402754a7`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140275141`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x1402753d6`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x140275141`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x1402753d6`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140275483`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140275483`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140275226`
- `ntoskrnl!PsGetProcessWin32Process` at `0x140275226`
- `win32kbase!?IsTimeFromLastInputEvent@CInputGlobals@@QEBA_NK@Z` at `0x140275765`
- `win32kbase!?IsTimeFromLastInputEvent@CInputGlobals@@QEBA_NK@Z` at `0x140275765`
- `win32kbase!luidSystem` at `0x1402754bb`
- `win32kbase!UPDWORDPointer` at `0x140275754`
- `win32kbase!UPDWORDPointer` at `0x140275754`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x140275297`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x140275297`
- `WIN32K!W32GetUserSessionState` at `0x1402751a0`
- `WIN32K!W32GetUserSessionState` at `0x1402752f3`
- `WIN32K!W32GetUserSessionState` at `0x14027538a`
- `WIN32K!W32GetUserSessionState` at `0x140275434`
- `WIN32K!W32GetUserSessionState` at `0x140275524`
- `WIN32K!W32GetUserSessionState` at `0x1402755ee`
- `WIN32K!W32GetUserSessionState` at `0x14027568a`
- `WIN32K!W32GetUserSessionState` at `0x1402756f7`
- `WIN32K!W32GetUserSessionState` at `0x14027573c`
- `WIN32K!W32GetUserSessionState` at `0x1402757b5`
- `WIN32K!W32GetUserSessionState` at `0x14027582b`
- `WIN32K!W32GetUserSessionState` at `0x1402758b8`
- `WIN32K!W32GetUserSessionState` at `0x140275944`
- `WIN32K!W32GetUserSessionState` at `0x140275a02`
- `WIN32K!W32GetUserSessionState` at `0x140275a47`
- `WIN32K!W32GetUserSessionState` at `0x140275a61`
- `WIN32K!W32GetUserSessionState` at `0x140275ac3`
- `WIN32K!W32GetUserSessionState` at `0x140275b58`
- `WIN32K!W32GetUserSessionState` at `0x1402751a0`
- `WIN32K!W32GetUserSessionState` at `0x1402752f3`
- `WIN32K!W32GetUserSessionState` at `0x14027538a`
- `WIN32K!W32GetUserSessionState` at `0x140275434`
- `WIN32K!W32GetUserSessionState` at `0x140275524`
- `WIN32K!W32GetUserSessionState` at `0x1402755ee`
- `WIN32K!W32GetUserSessionState` at `0x14027568a`
- `WIN32K!W32GetUserSessionState` at `0x1402756f7`
- `WIN32K!W32GetUserSessionState` at `0x14027573c`
- `WIN32K!W32GetUserSessionState` at `0x1402757b5`
- `WIN32K!W32GetUserSessionState` at `0x14027582b`
- `WIN32K!W32GetUserSessionState` at `0x1402758b8`
- `WIN32K!W32GetUserSessionState` at `0x140275944`
- `WIN32K!W32GetUserSessionState` at `0x140275a02`
- `WIN32K!W32GetUserSessionState` at `0x140275a47`
- `WIN32K!W32GetUserSessionState` at `0x140275a61`
- `WIN32K!W32GetUserSessionState` at `0x140275ac3`
- `WIN32K!W32GetUserSessionState` at `0x140275b58`

## pseudocode

```c
bool __fastcall CForegroundLaunch::_CheckAllowForeground(CForegroundLaunch *this, const struct tagPROCESSINFO *a2)
{
  unsigned int v3; // r12d
  char v4; // di
  bool v5; // si
  char v6; // r13
  __int64 v7; // rcx
  __int64 ProcessInheritedFromUniqueProcessId; // rbx
  bool v9; // r14
  bool v10; // r15
  int v11; // ebx
  __int64 UserSessionState; // rax
  int v13; // r8d
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rcx
  int v17; // ebx
  const struct tagPROCESSINFO *ProcessWin32Process; // rax
  const struct tagPROCESSINFO *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // rax
  tagTHREADINFO *v22; // rcx
  bool v23; // si
  bool v24; // r15
  int v25; // ebx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // edx
  bool v29; // bl
  bool v30; // r15
  __int64 v31; // rax
  int v32; // r8d
  int v33; // edx
  bool v34; // bl
  bool v35; // r15
  __int64 v36; // rax
  int v37; // r8d
  int v38; // edx
  PACCESS_TOKEN v39; // rax
  bool v40; // r15
  bool v41; // r12
  int v42; // ebx
  __int64 v43; // rax
  int v44; // r8d
  int v45; // edx
  bool v46; // bl
  bool v47; // si
  __int64 v48; // rax
  int v49; // r8d
  int v50; // edx
  bool v51; // bl
  bool v52; // r14
  __int64 v53; // rax
  int v54; // edx
  int v55; // r8d
  struct MOVESIZEDATA *v56; // rcx
  bool v57; // bl
  bool v58; // r14
  __int64 v59; // rax
  int v60; // r8d
  int v61; // edx
  CInputGlobals *v62; // rbx
  unsigned int *v63; // rax
  bool v64; // bl
  bool v65; // si
  __int64 v66; // rax
  int v67; // edx
  int v68; // r8d
  bool v69; // bl
  bool v70; // r14
  __int64 v71; // rax
  int v72; // r8d
  int v73; // edx
  struct MOVESIZEDATA *v74; // rcx
  bool v75; // bl
  bool v76; // si
  __int64 v77; // rax
  int v78; // r8d
  int v79; // edx
  __int64 v80; // rcx
  __int64 v81; // rax
  bool v82; // bl
  bool v83; // si
  __int64 v84; // rax
  int v85; // r8d
  int v86; // edx
  bool v87; // r14
  int v88; // ebx
  __int64 v89; // rax
  int v90; // r8d
  int v91; // edx
  __int64 v92; // r9
  const char *v93; // rax
  int v95; // [rsp+20h] [rbp-79h]
  __int16 v96; // [rsp+30h] [rbp-69h]
  __int16 v97; // [rsp+30h] [rbp-69h]
  struct _LUID AuthenticationId; // [rsp+50h] [rbp-49h] BYREF
  char v99[8]; // [rsp+60h] [rbp-39h] BYREF
  int v100; // [rsp+68h] [rbp-31h]
  PEPROCESS Process; // [rsp+78h] [rbp-21h]
  int v102; // [rsp+88h] [rbp-11h]
  unsigned int v105; // [rsp+110h] [rbp+77h]
  __int64 v106; // [rsp+118h] [rbp+7Fh]

  if ( *((_BYTE *)this + 440) )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1254);
  v3 = 0;
  v4 = 1;
  v105 = 0;
  v5 = 0;
  v6 = 1;
  ProcessInheritedFromUniqueProcessId = PsGetProcessInheritedFromUniqueProcessId(*(_QWORD *)a2);
  v106 = ProcessInheritedFromUniqueProcessId;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control )
  {
    v7 = *((unsigned int *)WPP_GLOBAL_Control + 11);
    if ( (v7 & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u )
      v9 = 1;
  }
  v10 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v9 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v11 = *((_DWORD *)a2 + 14);
    UserSessionState = W32GetUserSessionState(v7);
    LOBYTE(v13) = v10;
    LOBYTE(v14) = v9;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v14,
      v13,
      *(_QWORD *)(UserSessionState + 69152),
      4,
      2,
      55,
      (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids,
      v11);
    ProcessInheritedFromUniqueProcessId = v106;
  }
  while ( 1 )
  {
    v95 = 0;
    CLockProcessByPid::CLockProcessByPid(v99, ProcessInheritedFromUniqueProcessId, 0);
    if ( v100 < 0 )
    {
      v51 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v52 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v51 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v53 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v96 = 60;
LABEL_128:
        LOBYTE(v55) = v52;
        LOBYTE(v54) = v51;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v54,
          v55,
          *(_QWORD *)(v53 + 69152),
          4,
          2,
          v96,
          (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
      }
LABEL_129:
      if ( CForegroundLaunch::_HasLegacyForegroundActivateRight(this, *(struct _EPROCESS **)a2) )
        v5 = 1;
      goto LABEL_131;
    }
    v17 = v102;
    if ( (unsigned int)W32GetCurrentWin32kSessionId(v16, v15) != v17 )
      break;
    ProcessWin32Process = (const struct tagPROCESSINFO *)PsGetProcessWin32Process(Process);
    v19 = ProcessWin32Process;
    if ( !ProcessWin32Process || !*(_QWORD *)ProcessWin32Process )
    {
      v51 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v52 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v51 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v53 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v96 = 61;
        goto LABEL_128;
      }
      goto LABEL_129;
    }
    if ( !v6
      && ((unsigned int)IsShellProcess(ProcessWin32Process)
       || (v21 = *(_QWORD *)(v20 + 656)) != 0 && (*(_DWORD *)(v21 + 32) & 4) != 0) )
    {
      v46 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v47 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v46 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v48 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v49) = v47;
        LOBYTE(v50) = v46;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v50,
          v49,
          *(_QWORD *)(v48 + 69152),
          4,
          2,
          62,
          (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
      }
      CLockProcessByPid::~CLockProcessByPid((CLockProcessByPid *)v99);
      goto LABEL_132;
    }
    v5 = CanForceForeground(v19);
    if ( v5 )
      goto LABEL_62;
    v22 = (tagTHREADINFO *)*((_QWORD *)v19 + 41);
    if ( v22 && tagTHREADINFO::ComputeAndTestForegroundActivate(v22) )
    {
      v23 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v24 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v23 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v25 = *((_DWORD *)v19 + 14);
        v26 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v27) = v24;
        LOBYTE(v28) = v23;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v28,
          v27,
          *(_QWORD *)(v26 + 69152),
          4,
          2,
          63,
          (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids,
          v25);
      }
      v5 = 1;
LABEL_62:
      ProcessInheritedFromUniqueProcessId = v106;
      goto LABEL_63;
    }
    v29 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v30 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v29 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v31 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v32) = v30;
      LOBYTE(v33) = v29;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v33,
        v32,
        *(_QWORD *)(v31 + 69152),
        4,
        2,
        64,
        (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
    }
    v106 = PsGetProcessInheritedFromUniqueProcessId(Process);
    ProcessInheritedFromUniqueProcessId = v106;
    if ( v6 )
    {
      v34 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v35 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v34 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v36 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v37) = v35;
        LOBYTE(v38) = v34;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v38,
          v37,
          *(_QWORD *)(v36 + 69152),
          4,
          2,
          65,
          (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
      }
      v6 = 0;
      v39 = PsReferencePrimaryToken(Process);
      if ( v39 )
      {
        AuthenticationId = 0;
        if ( SeQueryAuthenticationIdToken(v39, &AuthenticationId) >= 0 )
        {
          if ( AuthenticationId.LowPart == luidSystem[0] && AuthenticationId.HighPart == luidSystem[1] )
          {
            v5 = 1;
            v40 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            v41 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v40 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v42 = *((_DWORD *)v19 + 14);
              v43 = W32GetUserSessionState(WPP_GLOBAL_Control);
              LOBYTE(v44) = v41;
              LOBYTE(v45) = v40;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v45,
                v44,
                *(_QWORD *)(v43 + 69152),
                4,
                2,
                66,
                (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids,
                v42);
            }
            *((_DWORD *)v19 + 3) |= 0x80000u;
            v3 = v105;
          }
          else
          {
            v5 = 0;
          }
        }
      }
      goto LABEL_62;
    }
LABEL_63:
    CLockProcessByPid::~CLockProcessByPid((CLockProcessByPid *)v99);
    if ( v5 )
      goto LABEL_153;
    if ( v3 >= 5 )
      goto LABEL_132;
    v105 = ++v3;
  }
  v56 = WPP_GLOBAL_Control;
  v57 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v58 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v57 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v59 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v60) = v58;
    LOBYTE(v61) = v57;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v61,
      v60,
      *(_QWORD *)(v59 + 69152),
      4,
      2,
      56,
      (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
  }
  v62 = *(CInputGlobals **)(W32GetUserSessionState(v56) + 3008);
  v63 = (unsigned int *)UPDWORDPointer(0x2000);
  if ( CInputGlobals::IsTimeFromLastInputEvent(v62, *v63) )
  {
    v64 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v65 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v64 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v66 = W32GetUserSessionState(WPP_GLOBAL_Control);
      v97 = 57;
      goto LABEL_110;
    }
    goto LABEL_111;
  }
  if ( !v6 )
    goto LABEL_131;
  if ( (*((_DWORD *)a2 + 3) & 1) != 0 )
  {
    v64 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v65 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v64 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v66 = W32GetUserSessionState(WPP_GLOBAL_Control);
      v97 = 58;
LABEL_110:
      LOBYTE(v68) = v65;
      LOBYTE(v67) = v64;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v67,
        v68,
        *(_QWORD *)(v66 + 69152),
        4,
        2,
        v97,
        (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
    }
LABEL_111:
    v5 = 1;
    goto LABEL_131;
  }
  v69 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v70 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v69 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v71 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v72) = v70;
    LOBYTE(v73) = v69;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v73,
      v72,
      *(_QWORD *)(v71 + 69152),
      4,
      2,
      59,
      (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
  }
LABEL_131:
  CLockProcessByPid::~CLockProcessByPid((CLockProcessByPid *)v99);
  if ( v5 )
    goto LABEL_153;
LABEL_132:
  v74 = WPP_GLOBAL_Control;
  v75 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v76 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v75 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v77 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v78) = v76;
    LOBYTE(v79) = v75;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v79,
      v78,
      *(_QWORD *)(v77 + 69152),
      4,
      2,
      67,
      (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v74) + 18984)
    && (v81 = *(_QWORD *)(W32GetUserSessionState(v80) + 18984), *(_DWORD *)(v81 + 664) <= 0x400u)
    && (*(_DWORD *)(v81 + 680) & 0x40) != 0 )
  {
    v82 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v83 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v82 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v84 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v85) = v83;
      LOBYTE(v86) = v82;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v86,
        v85,
        *(_QWORD *)(v84 + 69152),
        4,
        2,
        116,
        (__int64)WPP_dad220efef7b365d279206ae321641e5_Traceguids);
    }
    v5 = 1;
  }
  else
  {
    v5 = 0;
  }
LABEL_153:
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v4 = 0;
  }
  v87 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v4 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v88 = *((_DWORD *)a2 + 14);
    v89 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v90) = v87;
    LOBYTE(v91) = v4;
    v92 = *(_QWORD *)(v89 + 69152);
    v93 = "Yes";
    if ( !v5 )
      v93 = "No";
    WPP_RECORDER_AND_TRACE_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v91,
      v90,
      v92,
      v95,
      2,
      68,
      (__int64)WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids,
      (__int64)v93,
      v88);
  }
  return v5;
}

```

## disassembly

```asm
0x1402750dc  mov     [rsp-8+arg_8], rdx
0x1402750e1  mov     [rsp-8+arg_0], rcx
0x1402750e6  push    rbp
0x1402750e7  push    rbx
0x1402750e8  push    rsi
0x1402750e9  push    rdi
0x1402750ea  push    r12
0x1402750ec  push    r13
0x1402750ee  push    r14
0x1402750f0  push    r15
0x1402750f2  lea     rbp, [rsp-1Fh]
0x1402750f7  sub     rsp, 0B8h
0x1402750fe  cmp     byte ptr [rcx+1B8h], 0
0x140275105  mov     rbx, rdx
0x140275108  mov     r14d, 2
0x14027510e  jz      short loc_14027512C
0x140275110  mov     [rbp+57h+arg_10], 20000h
0x140275117  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14027511e  mov     edx, [rbp+57h+arg_10]
0x140275121  mov     r8d, 4E6h
0x140275127  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14027512c  mov     rcx, [rbx]
0x14027512f  xor     r12d, r12d
0x140275132  mov     edi, 1
0x140275137  mov     [rbp+57h+arg_10], r12d
0x14027513b  xor     sil, sil
0x14027513e  mov     r13b, dil
0x140275141  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x140275148  nop     dword ptr [rax+rax+00h]
0x14027514d  mov     rbx, rax
0x140275150  mov     [rbp+57h+arg_18], rax
0x140275154  mov     rdx, cs:WPP_GLOBAL_Control
0x14027515b  lea     rax, WPP_GLOBAL_Control
0x140275162  cmp     rdx, rax
0x140275165  jz      short loc_14027517A
0x140275167  mov     ecx, [rdx+2Ch]
0x14027516a  test    r14b, cl
0x14027516d  jz      short loc_14027517A
0x14027516f  cmp     byte ptr [rdx+29h], 4
0x140275173  jb      short loc_14027517A
0x140275175  mov     r14b, dil
0x140275178  jmp     short loc_14027517D
0x14027517a  xor     r14b, r14b
0x14027517d  lea     rax, WPP_RECORDER_INITIALIZED
0x140275184  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14027518b  setnz   r15b
0x14027518f  test    r14b, r14b
0x140275192  jnz     short loc_140275199
0x140275194  test    r15b, r15b
0x140275197  jz      short loc_1402751F1
0x140275199  mov     rbx, [rbp+57h+arg_8]
0x14027519d  mov     ebx, [rbx+38h]
0x1402751a0  call    cs:__imp_W32GetUserSessionState
0x1402751a7  nop     dword ptr [rax+rax+00h]
0x1402751ac  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x1402751b0  lea     rcx, WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids
0x1402751b7  mov     [rsp+0F0h+var_B8], rcx
0x1402751bc  mov     r8b, r15b
0x1402751bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1402751c6  mov     dl, r14b
0x1402751c9  mov     r9, [rax+10E20h]
0x1402751d0  mov     [rsp+0F0h+var_C0], 37h ; '7'
0x1402751d7  mov     [rsp+0F0h+var_C8], 2
0x1402751df  mov     rcx, [rcx+18h]
0x1402751e3  mov     byte ptr [rsp+0F0h+var_D0], 4
0x1402751e8  call    WPP_RECORDER_AND_TRACE_SF_D
0x1402751ed  mov     rbx, [rbp+57h+arg_18]
0x1402751f1  xor     r8d, r8d
0x1402751f4  mov     [rsp+0F0h+var_D0], 0
0x1402751fc  mov     rdx, rbx
0x1402751ff  lea     rcx, [rbp+57h+var_90]
0x140275203  call    ??0CLockProcessByPid@@QEAA@PEAXKKW4LockProcessOptions@@_K@Z; CLockProcessByPid::CLockProcessByPid(void *,ulong,ulong,LockProcessOptions,unsigned __int64)
0x140275208  cmp     [rbp+57h+var_88], 0
0x14027520c  jl      loc_140275902
0x140275212  mov     ebx, [rbp+57h+var_68]
0x140275215  call    W32GetCurrentWin32kSessionId
0x14027521a  cmp     eax, ebx
0x14027521c  jnz     loc_1402756AE
0x140275222  mov     rcx, [rbp+57h+Process]
0x140275226  call    cs:__imp_PsGetProcessWin32Process
0x14027522d  nop     dword ptr [rax+rax+00h]
0x140275232  mov     r14, rax
0x140275235  test    rax, rax
0x140275238  jz      loc_140275644
0x14027523e  cmp     qword ptr [rax], 0
0x140275242  jz      loc_140275644
0x140275248  test    r13b, r13b
0x14027524b  jnz     short loc_140275274
0x14027524d  mov     rcx, rax
0x140275250  call    IsShellProcess
0x140275255  test    eax, eax
0x140275257  jnz     loc_1402755AC
0x14027525d  mov     rax, [rcx+290h]
0x140275264  test    rax, rax
0x140275267  jz      short loc_140275274
0x140275269  mov     eax, [rax+20h]
0x14027526c  test    al, 4
0x14027526e  jnz     loc_1402755AC
0x140275274  mov     rcx, r14; struct tagPROCESSINFO *
0x140275277  call    ?CanForceForeground@@YA_NPEBUtagPROCESSINFO@@@Z; CanForceForeground(tagPROCESSINFO const *)
0x14027527c  mov     sil, al
0x14027527f  test    al, al
0x140275281  jnz     loc_140275580
0x140275287  mov     rcx, [r14+148h]
0x14027528e  test    rcx, rcx
0x140275291  jz      loc_140275348
0x140275297  call    cs:__imp_?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ; tagTHREADINFO::ComputeAndTestForegroundActivate(void)
0x14027529e  nop     dword ptr [rax+rax+00h]
0x1402752a3  test    al, al
0x1402752a5  jz      loc_140275348
0x1402752ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1402752b2  lea     rax, WPP_GLOBAL_Control
0x1402752b9  cmp     rcx, rax
0x1402752bc  jz      short loc_1402752D0
0x1402752be  mov     eax, [rcx+2Ch]
0x1402752c1  test    al, 2
0x1402752c3  jz      short loc_1402752D0
0x1402752c5  cmp     byte ptr [rcx+29h], 4
0x1402752c9  jb      short loc_1402752D0
0x1402752cb  mov     sil, dil
0x1402752ce  jmp     short loc_1402752D3
0x1402752d0  xor     sil, sil
0x1402752d3  lea     rax, WPP_RECORDER_INITIALIZED
0x1402752da  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1402752e1  setnz   r15b
0x1402752e5  test    sil, sil
0x1402752e8  jnz     short loc_1402752EF
0x1402752ea  test    r15b, r15b
0x1402752ed  jz      short loc_140275340
0x1402752ef  mov     ebx, [r14+38h]
0x1402752f3  call    cs:__imp_W32GetUserSessionState
0x1402752fa  nop     dword ptr [rax+rax+00h]
0x1402752ff  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x140275303  lea     rcx, WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids
0x14027530a  mov     [rsp+0F0h+var_B8], rcx
0x14027530f  mov     r8b, r15b
0x140275312  mov     rcx, cs:WPP_GLOBAL_Control
0x140275319  mov     dl, sil
0x14027531c  mov     r9, [rax+10E20h]
0x140275323  mov     [rsp+0F0h+var_C0], 3Fh ; '?'
0x14027532a  mov     [rsp+0F0h+var_C8], 2
0x140275332  mov     rcx, [rcx+18h]
0x140275336  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14027533b  call    WPP_RECORDER_AND_TRACE_SF_D
0x140275340  mov     sil, dil
0x140275343  jmp     loc_140275580
0x140275348  mov     rcx, cs:WPP_GLOBAL_Control
0x14027534f  lea     rax, WPP_GLOBAL_Control
0x140275356  cmp     rcx, rax
0x140275359  jz      short loc_14027536D
0x14027535b  mov     eax, [rcx+2Ch]
0x14027535e  test    al, 2
0x140275360  jz      short loc_14027536D
0x140275362  cmp     byte ptr [rcx+29h], 4
0x140275366  jb      short loc_14027536D
0x140275368  mov     bl, dil
0x14027536b  jmp     short loc_14027536F
0x14027536d  xor     bl, bl
0x14027536f  lea     rax, WPP_RECORDER_INITIALIZED
0x140275376  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14027537d  setnz   r15b
0x140275381  test    bl, bl
0x140275383  jnz     short loc_14027538A
0x140275385  test    r15b, r15b
0x140275388  jz      short loc_1402753D2
0x14027538a  call    cs:__imp_W32GetUserSessionState
0x140275391  nop     dword ptr [rax+rax+00h]
0x140275396  mov     rcx, cs:WPP_GLOBAL_Control
0x14027539d  mov     r8b, r15b
0x1402753a0  mov     dl, bl
0x1402753a2  mov     r9, [rax+10E20h]
0x1402753a9  lea     rax, WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids
0x1402753b0  mov     rcx, [rcx+18h]
0x1402753b4  mov     [rsp+0F0h+var_B8], rax
0x1402753b9  mov     [rsp+0F0h+var_C0], 40h ; '@'
0x1402753c0  mov     [rsp+0F0h+var_C8], 2
0x1402753c8  mov     byte ptr [rsp+0F0h+var_D0], 4
0x1402753cd  call    WPP_RECORDER_AND_TRACE_SF_
0x1402753d2  mov     rcx, [rbp+57h+Process]
0x1402753d6  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x1402753dd  nop     dword ptr [rax+rax+00h]
0x1402753e2  mov     [rbp+57h+arg_18], rax
0x1402753e6  mov     rbx, rax
0x1402753e9  test    r13b, r13b
0x1402753ec  jz      loc_140275584
0x1402753f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1402753f9  lea     rax, WPP_GLOBAL_Control
0x140275400  cmp     rcx, rax
0x140275403  jz      short loc_140275417
0x140275405  mov     eax, [rcx+2Ch]
0x140275408  test    al, 2
0x14027540a  jz      short loc_140275417
0x14027540c  cmp     byte ptr [rcx+29h], 4
0x140275410  jb      short loc_140275417
0x140275412  mov     bl, dil
0x140275415  jmp     short loc_140275419
0x140275417  xor     bl, bl
0x140275419  lea     rax, WPP_RECORDER_INITIALIZED
0x140275420  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140275427  setnz   r15b
0x14027542b  test    bl, bl
0x14027542d  jnz     short loc_140275434
0x14027542f  test    r15b, r15b
0x140275432  jz      short loc_14027547C
0x140275434  call    cs:__imp_W32GetUserSessionState
0x14027543b  nop     dword ptr [rax+rax+00h]
0x140275440  lea     rcx, WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids
0x140275447  mov     r8b, r15b
0x14027544a  mov     [rsp+0F0h+var_B8], rcx
0x14027544f  mov     dl, bl
0x140275451  mov     rcx, cs:WPP_GLOBAL_Control
0x140275458  mov     r9, [rax+10E20h]
0x14027545f  mov     [rsp+0F0h+var_C0], 41h ; 'A'
0x140275466  mov     [rsp+0F0h+var_C8], 2
0x14027546e  mov     rcx, [rcx+18h]
0x140275472  mov     byte ptr [rsp+0F0h+var_D0], 4
0x140275477  call    WPP_RECORDER_AND_TRACE_SF_
0x14027547c  mov     rcx, [rbp+57h+Process]; Process
0x140275480  xor     r13b, r13b
0x140275483  call    cs:__imp_PsReferencePrimaryToken
0x14027548a  nop     dword ptr [rax+rax+00h]
0x14027548f  test    rax, rax
0x140275492  jz      loc_140275580
0x140275498  lea     rdx, [rbp+57h+AuthenticationId]; AuthenticationId
0x14027549c  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 0
0x1402754a4  mov     rcx, rax; Token
0x1402754a7  call    cs:__imp_SeQueryAuthenticationIdToken
0x1402754ae  nop     dword ptr [rax+rax+00h]
0x1402754b3  test    eax, eax
0x1402754b5  js      loc_140275580
0x1402754bb  mov     rax, cs:__imp_luidSystem
0x1402754c2  mov     ecx, [rax]
0x1402754c4  cmp     [rbp+57h+AuthenticationId.LowPart], ecx
0x1402754c7  jnz     loc_14027557D
0x1402754cd  mov     ecx, [rax+4]
0x1402754d0  cmp     [rbp+57h+AuthenticationId.HighPart], ecx
0x1402754d3  jnz     loc_14027557D
0x1402754d9  mov     sil, dil
0x1402754dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1402754e3  lea     rax, WPP_GLOBAL_Control
0x1402754ea  cmp     rcx, rax
0x1402754ed  jz      short loc_140275501
0x1402754ef  mov     eax, [rcx+2Ch]
0x1402754f2  test    al, 2
0x1402754f4  jz      short loc_140275501
0x1402754f6  cmp     byte ptr [rcx+29h], 4
0x1402754fa  jb      short loc_140275501
0x1402754fc  mov     r15b, dil
0x1402754ff  jmp     short loc_140275504
0x140275501  xor     r15b, r15b
0x140275504  lea     rax, WPP_RECORDER_INITIALIZED
0x14027550b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140275512  setnz   r12b
0x140275516  test    r15b, r15b
0x140275519  jnz     short loc_140275520
0x14027551b  test    r12b, r12b
0x14027551e  jz      short loc_140275571
0x140275520  mov     ebx, [r14+38h]
0x140275524  call    cs:__imp_W32GetUserSessionState
0x14027552b  nop     dword ptr [rax+rax+00h]
0x140275530  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x140275534  lea     rcx, WPP_20bc2a7dd0683241c0e422dae7433fa9_Traceguids
0x14027553b  mov     [rsp+0F0h+var_B8], rcx
0x140275540  mov     r8b, r12b
0x140275543  mov     rcx, cs:WPP_GLOBAL_Control
0x14027554a  mov     dl, r15b
0x14027554d  mov     r9, [rax+10E20h]
0x140275554  mov     [rsp+0F0h+var_C0], 42h ; 'B'
0x14027555b  mov     [rsp+0F0h+var_C8], 2
0x140275563  mov     rcx, [rcx+18h]
0x140275567  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14027556c  call    WPP_RECORDER_AND_TRACE_SF_D
0x140275571  bts     dword ptr [r14+0Ch], 13h
0x140275577  mov     r12d, [rbp+57h+arg_10]
0x14027557b  jmp     short loc_140275580
0x14027557d  xor     sil, sil
0x140275580  mov     rbx, [rbp+57h+arg_18]
0x140275584  lea     rcx, [rbp+57h+var_90]; this
0x140275588  call    ??1CLockProcessByPid@@QEAA@XZ; CLockProcessByPid::~CLockProcessByPid(void)
0x14027558d  test    sil, sil
0x140275590  jnz     loc_140275B12
0x140275596  cmp     r12d, 5
0x14027559a  jnb     loc_1402759B9
0x1402755a0  add     r12d, edi
0x1402755a3  mov     [rbp+57h+arg_10], r12d
0x1402755a7  jmp     loc_1402751F1
0x1402755ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1402755b3  lea     r12, WPP_GLOBAL_Control
0x1402755ba  cmp     rcx, r12
0x1402755bd  jz      short loc_1402755D1
0x1402755bf  mov     eax, [rcx+2Ch]
0x1402755c2  test    al, 2
0x1402755c4  jz      short loc_1402755D1
0x1402755c6  cmp     byte ptr [rcx+29h], 4
0x1402755ca  jb      short loc_1402755D1
0x1402755cc  mov     bl, dil
0x1402755cf  jmp     short loc_1402755D3
0x1402755d1  xor     bl, bl
0x1402755d3  lea     r15, WPP_RECORDER_INITIALIZED
0x1402755da  cmp     cs:WPP_RECORDER_INITIALIZED, r15
  ... truncated ...
```
