# CForegroundLaunch::_CheckAllowForeground2(tagPROCESSINFO const *)

- ea: `0x14017d534`
- end: `0x14017e063`
- name: `?_CheckAllowForeground2@CForegroundLaunch@@AEBA_NPEBUtagPROCESSINFO@@@Z`
- size: `2863`
- prototype: `bool __fastcall(CForegroundLaunch *__hidden this, const struct tagPROCESSINFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017e99c`

## callees

- `0x1400a4a38`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x140179c44`
- `0x14017b6a0`
- `0x14017bc34`
- `0x14017c278`
- `0x14017c9bc`
- `0x14017cbc4`
- `0x14017cc14`
- `0x14017d534`
- `0x1401d1fc4`
- `0x1402938dc`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14017d8ff`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14017d8ff`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017d599`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017d82e`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017d599`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017d82e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14017d8db`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14017d8db`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14017d67e`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14017d67e`
- `win32kbase!?IsTimeFromLastInputEvent@CInputGlobals@@QEBA_NK@Z` at `0x14017dbda`
- `win32kbase!?IsTimeFromLastInputEvent@CInputGlobals@@QEBA_NK@Z` at `0x14017dbda`
- `win32kbase!luidSystem` at `0x14017d913`
- `win32kbase!UPDWORDPointer` at `0x14017dbc9`
- `win32kbase!UPDWORDPointer` at `0x14017dbc9`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x14017d6ef`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x14017d6ef`
- `WIN32K!W32GetUserSessionState` at `0x14017d5f8`
- `WIN32K!W32GetUserSessionState` at `0x14017d74b`
- `WIN32K!W32GetUserSessionState` at `0x14017d7e2`
- `WIN32K!W32GetUserSessionState` at `0x14017d88c`
- `WIN32K!W32GetUserSessionState` at `0x14017d97c`
- `WIN32K!W32GetUserSessionState` at `0x14017da63`
- `WIN32K!W32GetUserSessionState` at `0x14017daff`
- `WIN32K!W32GetUserSessionState` at `0x14017db6c`
- `WIN32K!W32GetUserSessionState` at `0x14017dbb1`
- `WIN32K!W32GetUserSessionState` at `0x14017dc2a`
- `WIN32K!W32GetUserSessionState` at `0x14017dca0`
- `WIN32K!W32GetUserSessionState` at `0x14017dd2d`
- `WIN32K!W32GetUserSessionState` at `0x14017ddb9`
- `WIN32K!W32GetUserSessionState` at `0x14017de93`
- `WIN32K!W32GetUserSessionState` at `0x14017ded8`
- `WIN32K!W32GetUserSessionState` at `0x14017def2`
- `WIN32K!W32GetUserSessionState` at `0x14017df54`
- `WIN32K!W32GetUserSessionState` at `0x14017dfe9`
- `WIN32K!W32GetUserSessionState` at `0x14017d5f8`
- `WIN32K!W32GetUserSessionState` at `0x14017d74b`
- `WIN32K!W32GetUserSessionState` at `0x14017d7e2`
- `WIN32K!W32GetUserSessionState` at `0x14017d88c`
- `WIN32K!W32GetUserSessionState` at `0x14017d97c`
- `WIN32K!W32GetUserSessionState` at `0x14017da63`
- `WIN32K!W32GetUserSessionState` at `0x14017daff`
- `WIN32K!W32GetUserSessionState` at `0x14017db6c`
- `WIN32K!W32GetUserSessionState` at `0x14017dbb1`
- `WIN32K!W32GetUserSessionState` at `0x14017dc2a`
- `WIN32K!W32GetUserSessionState` at `0x14017dca0`
- `WIN32K!W32GetUserSessionState` at `0x14017dd2d`
- `WIN32K!W32GetUserSessionState` at `0x14017ddb9`
- `WIN32K!W32GetUserSessionState` at `0x14017de93`
- `WIN32K!W32GetUserSessionState` at `0x14017ded8`
- `WIN32K!W32GetUserSessionState` at `0x14017def2`
- `WIN32K!W32GetUserSessionState` at `0x14017df54`
- `WIN32K!W32GetUserSessionState` at `0x14017dfe9`

## pseudocode

```c
bool __fastcall CForegroundLaunch::_CheckAllowForeground2(CForegroundLaunch *this, const struct tagPROCESSINFO *a2)
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
  _LUID AuthenticationId; // [rsp+50h] [rbp-49h] BYREF
  char v99[8]; // [rsp+60h] [rbp-39h] BYREF
  int v100; // [rsp+68h] [rbp-31h]
  char v101; // [rsp+74h] [rbp-25h]
  PEPROCESS Process; // [rsp+78h] [rbp-21h]
  int v103; // [rsp+88h] [rbp-11h]
  __int64 v104; // [rsp+90h] [rbp-9h]
  unsigned int v107; // [rsp+110h] [rbp+77h]
  __int64 v108; // [rsp+118h] [rbp+7Fh]

  if ( *((_BYTE *)this + 440) )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1256);
  v3 = 0;
  v4 = 1;
  v107 = 0;
  v5 = 0;
  v6 = 1;
  ProcessInheritedFromUniqueProcessId = PsGetProcessInheritedFromUniqueProcessId(*(_QWORD *)a2);
  v108 = ProcessInheritedFromUniqueProcessId;
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
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
      v11);
    ProcessInheritedFromUniqueProcessId = v108;
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
LABEL_132:
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
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
LABEL_133:
      if ( CForegroundLaunch::_HasLegacyForegroundActivateRight(this, *(struct _EPROCESS **)a2) )
        v5 = 1;
      goto LABEL_135;
    }
    v17 = v103;
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
        goto LABEL_132;
      }
      goto LABEL_133;
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
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      CLockProcessByPid::~CLockProcessByPid((CLockProcessByPid *)v99);
LABEL_140:
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
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
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
            (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
        }
        v5 = 1;
      }
      else
      {
        v5 = 0;
      }
      goto LABEL_161;
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
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
          v25);
      }
      v5 = 1;
LABEL_62:
      ProcessInheritedFromUniqueProcessId = v108;
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
        (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
    }
    v108 = PsGetProcessInheritedFromUniqueProcessId(Process);
    ProcessInheritedFromUniqueProcessId = v108;
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
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
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
                (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
                v42);
            }
            *((_DWORD *)v19 + 3) |= 0x80000u;
            v3 = v107;
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
    if ( Process )
    {
      if ( (v101 & 8) != 0 )
        *((_QWORD *)PtiCurrent() + 47) = v104;
      CLockProcessByPid::_Cleanup((CLockProcessByPid *)v99);
    }
    if ( v5 )
      goto LABEL_161;
    if ( v3 >= 5 )
      goto LABEL_140;
    v107 = ++v3;
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
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
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
      goto LABEL_114;
    }
    goto LABEL_115;
  }
  if ( !v6 )
    goto LABEL_135;
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
LABEL_114:
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
        (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
    }
LABEL_115:
    v5 = 1;
    goto LABEL_135;
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
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
  }
LABEL_135:
  if ( Process )
  {
    if ( (v101 & 8) != 0 )
      *((_QWORD *)PtiCurrent() + 47) = v104;
    CLockProcessByPid::_Cleanup((CLockProcessByPid *)v99);
  }
  if ( !v5 )
    goto LABEL_140;
LABEL_161:
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
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
      (__int64)v93,
      v88);
  }
  return v5;
}

```

## disassembly

```asm
0x14017d534  mov     [rsp-8+arg_8], rdx
0x14017d539  mov     [rsp-8+arg_0], rcx
0x14017d53e  push    rbp
0x14017d53f  push    rbx
0x14017d540  push    rsi
0x14017d541  push    rdi
0x14017d542  push    r12
0x14017d544  push    r13
0x14017d546  push    r14
0x14017d548  push    r15
0x14017d54a  lea     rbp, [rsp-1Fh]
0x14017d54f  sub     rsp, 0B8h
0x14017d556  cmp     byte ptr [rcx+1B8h], 0
0x14017d55d  mov     rbx, rdx
0x14017d560  mov     r14d, 2
0x14017d566  jz      short loc_14017D584
0x14017d568  mov     [rbp+57h+arg_10], 20000h
0x14017d56f  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14017d576  mov     edx, [rbp+57h+arg_10]
0x14017d579  mov     r8d, 4E8h
0x14017d57f  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14017d584  mov     rcx, [rbx]
0x14017d587  xor     r12d, r12d
0x14017d58a  mov     edi, 1
0x14017d58f  mov     [rbp+57h+arg_10], r12d
0x14017d593  xor     sil, sil
0x14017d596  mov     r13b, dil
0x14017d599  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x14017d5a0  nop     dword ptr [rax+rax+00h]
0x14017d5a5  mov     rbx, rax
0x14017d5a8  mov     [rbp+57h+arg_18], rax
0x14017d5ac  mov     rdx, cs:WPP_GLOBAL_Control
0x14017d5b3  lea     rax, WPP_GLOBAL_Control
0x14017d5ba  cmp     rdx, rax
0x14017d5bd  jz      short loc_14017D5D2
0x14017d5bf  mov     ecx, [rdx+2Ch]
0x14017d5c2  test    r14b, cl
0x14017d5c5  jz      short loc_14017D5D2
0x14017d5c7  cmp     byte ptr [rdx+29h], 4
0x14017d5cb  jb      short loc_14017D5D2
0x14017d5cd  mov     r14b, dil
0x14017d5d0  jmp     short loc_14017D5D5
0x14017d5d2  xor     r14b, r14b
0x14017d5d5  lea     rax, WPP_RECORDER_INITIALIZED
0x14017d5dc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017d5e3  setnz   r15b
0x14017d5e7  test    r14b, r14b
0x14017d5ea  jnz     short loc_14017D5F1
0x14017d5ec  test    r15b, r15b
0x14017d5ef  jz      short loc_14017D649
0x14017d5f1  mov     rbx, [rbp+57h+arg_8]
0x14017d5f5  mov     ebx, [rbx+38h]
0x14017d5f8  call    cs:__imp_W32GetUserSessionState
0x14017d5ff  nop     dword ptr [rax+rax+00h]
0x14017d604  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x14017d608  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017d60f  mov     [rsp+0F0h+var_B8], rcx
0x14017d614  mov     r8b, r15b
0x14017d617  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d61e  mov     dl, r14b
0x14017d621  mov     r9, [rax+10E20h]
0x14017d628  mov     [rsp+0F0h+var_C0], 37h ; '7'
0x14017d62f  mov     [rsp+0F0h+var_C8], 2
0x14017d637  mov     rcx, [rcx+18h]
0x14017d63b  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14017d640  call    WPP_RECORDER_AND_TRACE_SF_D
0x14017d645  mov     rbx, [rbp+57h+arg_18]
0x14017d649  xor     r8d, r8d
0x14017d64c  mov     [rsp+0F0h+var_D0], 0
0x14017d654  mov     rdx, rbx
0x14017d657  lea     rcx, [rbp+57h+var_90]
0x14017d65b  call    ??0CLockProcessByPid@@QEAA@PEAXKKW4LockProcessOptions@@_K@Z; CLockProcessByPid::CLockProcessByPid(void *,ulong,ulong,LockProcessOptions,unsigned __int64)
0x14017d660  cmp     [rbp+57h+var_88], 0
0x14017d664  jl      loc_14017DD77
0x14017d66a  mov     ebx, [rbp+57h+var_68]
0x14017d66d  call    W32GetCurrentWin32kSessionId
0x14017d672  cmp     eax, ebx
0x14017d674  jnz     loc_14017DB23
0x14017d67a  mov     rcx, [rbp+57h+Process]
0x14017d67e  call    cs:__imp_PsGetProcessWin32Process
0x14017d685  nop     dword ptr [rax+rax+00h]
0x14017d68a  mov     r14, rax
0x14017d68d  test    rax, rax
0x14017d690  jz      loc_14017DAB9
0x14017d696  cmp     qword ptr [rax], 0
0x14017d69a  jz      loc_14017DAB9
0x14017d6a0  test    r13b, r13b
0x14017d6a3  jnz     short loc_14017D6CC
0x14017d6a5  mov     rcx, rax
0x14017d6a8  call    IsShellProcess
0x14017d6ad  test    eax, eax
0x14017d6af  jnz     loc_14017DA21
0x14017d6b5  mov     rax, [rcx+290h]
0x14017d6bc  test    rax, rax
0x14017d6bf  jz      short loc_14017D6CC
0x14017d6c1  mov     eax, [rax+20h]
0x14017d6c4  test    al, 4
0x14017d6c6  jnz     loc_14017DA21
0x14017d6cc  mov     rcx, r14; struct tagPROCESSINFO *
0x14017d6cf  call    ?CanForceForeground@@YA_NPEBUtagPROCESSINFO@@@Z; CanForceForeground(tagPROCESSINFO const *)
0x14017d6d4  mov     sil, al
0x14017d6d7  test    al, al
0x14017d6d9  jnz     loc_14017D9D8
0x14017d6df  mov     rcx, [r14+148h]
0x14017d6e6  test    rcx, rcx
0x14017d6e9  jz      loc_14017D7A0
0x14017d6ef  call    cs:__imp_?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ; tagTHREADINFO::ComputeAndTestForegroundActivate(void)
0x14017d6f6  nop     dword ptr [rax+rax+00h]
0x14017d6fb  test    al, al
0x14017d6fd  jz      loc_14017D7A0
0x14017d703  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d70a  lea     rax, WPP_GLOBAL_Control
0x14017d711  cmp     rcx, rax
0x14017d714  jz      short loc_14017D728
0x14017d716  mov     eax, [rcx+2Ch]
0x14017d719  test    al, 2
0x14017d71b  jz      short loc_14017D728
0x14017d71d  cmp     byte ptr [rcx+29h], 4
0x14017d721  jb      short loc_14017D728
0x14017d723  mov     sil, dil
0x14017d726  jmp     short loc_14017D72B
0x14017d728  xor     sil, sil
0x14017d72b  lea     rax, WPP_RECORDER_INITIALIZED
0x14017d732  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017d739  setnz   r15b
0x14017d73d  test    sil, sil
0x14017d740  jnz     short loc_14017D747
0x14017d742  test    r15b, r15b
0x14017d745  jz      short loc_14017D798
0x14017d747  mov     ebx, [r14+38h]
0x14017d74b  call    cs:__imp_W32GetUserSessionState
0x14017d752  nop     dword ptr [rax+rax+00h]
0x14017d757  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x14017d75b  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017d762  mov     [rsp+0F0h+var_B8], rcx
0x14017d767  mov     r8b, r15b
0x14017d76a  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d771  mov     dl, sil
0x14017d774  mov     r9, [rax+10E20h]
0x14017d77b  mov     [rsp+0F0h+var_C0], 3Fh ; '?'
0x14017d782  mov     [rsp+0F0h+var_C8], 2
0x14017d78a  mov     rcx, [rcx+18h]
0x14017d78e  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14017d793  call    WPP_RECORDER_AND_TRACE_SF_D
0x14017d798  mov     sil, dil
0x14017d79b  jmp     loc_14017D9D8
0x14017d7a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d7a7  lea     rax, WPP_GLOBAL_Control
0x14017d7ae  cmp     rcx, rax
0x14017d7b1  jz      short loc_14017D7C5
0x14017d7b3  mov     eax, [rcx+2Ch]
0x14017d7b6  test    al, 2
0x14017d7b8  jz      short loc_14017D7C5
0x14017d7ba  cmp     byte ptr [rcx+29h], 4
0x14017d7be  jb      short loc_14017D7C5
0x14017d7c0  mov     bl, dil
0x14017d7c3  jmp     short loc_14017D7C7
0x14017d7c5  xor     bl, bl
0x14017d7c7  lea     rax, WPP_RECORDER_INITIALIZED
0x14017d7ce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017d7d5  setnz   r15b
0x14017d7d9  test    bl, bl
0x14017d7db  jnz     short loc_14017D7E2
0x14017d7dd  test    r15b, r15b
0x14017d7e0  jz      short loc_14017D82A
0x14017d7e2  call    cs:__imp_W32GetUserSessionState
0x14017d7e9  nop     dword ptr [rax+rax+00h]
0x14017d7ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d7f5  mov     r8b, r15b
0x14017d7f8  mov     dl, bl
0x14017d7fa  mov     r9, [rax+10E20h]
0x14017d801  lea     rax, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017d808  mov     rcx, [rcx+18h]
0x14017d80c  mov     [rsp+0F0h+var_B8], rax
0x14017d811  mov     [rsp+0F0h+var_C0], 40h ; '@'
0x14017d818  mov     [rsp+0F0h+var_C8], 2
0x14017d820  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14017d825  call    WPP_RECORDER_AND_TRACE_SF_
0x14017d82a  mov     rcx, [rbp+57h+Process]
0x14017d82e  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x14017d835  nop     dword ptr [rax+rax+00h]
0x14017d83a  mov     [rbp+57h+arg_18], rax
0x14017d83e  mov     rbx, rax
0x14017d841  test    r13b, r13b
0x14017d844  jz      loc_14017D9DC
0x14017d84a  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d851  lea     rax, WPP_GLOBAL_Control
0x14017d858  cmp     rcx, rax
0x14017d85b  jz      short loc_14017D86F
0x14017d85d  mov     eax, [rcx+2Ch]
0x14017d860  test    al, 2
0x14017d862  jz      short loc_14017D86F
0x14017d864  cmp     byte ptr [rcx+29h], 4
0x14017d868  jb      short loc_14017D86F
0x14017d86a  mov     bl, dil
0x14017d86d  jmp     short loc_14017D871
0x14017d86f  xor     bl, bl
0x14017d871  lea     rax, WPP_RECORDER_INITIALIZED
0x14017d878  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017d87f  setnz   r15b
0x14017d883  test    bl, bl
0x14017d885  jnz     short loc_14017D88C
0x14017d887  test    r15b, r15b
0x14017d88a  jz      short loc_14017D8D4
0x14017d88c  call    cs:__imp_W32GetUserSessionState
0x14017d893  nop     dword ptr [rax+rax+00h]
0x14017d898  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017d89f  mov     r8b, r15b
0x14017d8a2  mov     [rsp+0F0h+var_B8], rcx
0x14017d8a7  mov     dl, bl
0x14017d8a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d8b0  mov     r9, [rax+10E20h]
0x14017d8b7  mov     [rsp+0F0h+var_C0], 41h ; 'A'
0x14017d8be  mov     [rsp+0F0h+var_C8], 2
0x14017d8c6  mov     rcx, [rcx+18h]
0x14017d8ca  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14017d8cf  call    WPP_RECORDER_AND_TRACE_SF_
0x14017d8d4  mov     rcx, [rbp+57h+Process]; Process
0x14017d8d8  xor     r13b, r13b
0x14017d8db  call    cs:__imp_PsReferencePrimaryToken
0x14017d8e2  nop     dword ptr [rax+rax+00h]
0x14017d8e7  test    rax, rax
0x14017d8ea  jz      loc_14017D9D8
0x14017d8f0  lea     rdx, [rbp+57h+AuthenticationId]; AuthenticationId
0x14017d8f4  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 0
0x14017d8fc  mov     rcx, rax; Token
0x14017d8ff  call    cs:__imp_SeQueryAuthenticationIdToken
0x14017d906  nop     dword ptr [rax+rax+00h]
0x14017d90b  test    eax, eax
0x14017d90d  js      loc_14017D9D8
0x14017d913  mov     rax, cs:__imp_luidSystem
0x14017d91a  mov     ecx, [rax]
0x14017d91c  cmp     [rbp+57h+AuthenticationId.LowPart], ecx
0x14017d91f  jnz     loc_14017D9D5
0x14017d925  mov     ecx, [rax+4]
0x14017d928  cmp     [rbp+57h+AuthenticationId.HighPart], ecx
0x14017d92b  jnz     loc_14017D9D5
0x14017d931  mov     sil, dil
0x14017d934  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d93b  lea     rax, WPP_GLOBAL_Control
0x14017d942  cmp     rcx, rax
0x14017d945  jz      short loc_14017D959
0x14017d947  mov     eax, [rcx+2Ch]
0x14017d94a  test    al, 2
0x14017d94c  jz      short loc_14017D959
0x14017d94e  cmp     byte ptr [rcx+29h], 4
0x14017d952  jb      short loc_14017D959
0x14017d954  mov     r15b, dil
0x14017d957  jmp     short loc_14017D95C
0x14017d959  xor     r15b, r15b
0x14017d95c  lea     rax, WPP_RECORDER_INITIALIZED
0x14017d963  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017d96a  setnz   r12b
0x14017d96e  test    r15b, r15b
0x14017d971  jnz     short loc_14017D978
0x14017d973  test    r12b, r12b
0x14017d976  jz      short loc_14017D9C9
0x14017d978  mov     ebx, [r14+38h]
0x14017d97c  call    cs:__imp_W32GetUserSessionState
0x14017d983  nop     dword ptr [rax+rax+00h]
0x14017d988  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x14017d98c  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017d993  mov     [rsp+0F0h+var_B8], rcx
0x14017d998  mov     r8b, r12b
0x14017d99b  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d9a2  mov     dl, r15b
0x14017d9a5  mov     r9, [rax+10E20h]
0x14017d9ac  mov     [rsp+0F0h+var_C0], 42h ; 'B'
0x14017d9b3  mov     [rsp+0F0h+var_C8], 2
0x14017d9bb  mov     rcx, [rcx+18h]
0x14017d9bf  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14017d9c4  call    WPP_RECORDER_AND_TRACE_SF_D
0x14017d9c9  bts     dword ptr [r14+0Ch], 13h
0x14017d9cf  mov     r12d, [rbp+57h+arg_10]
0x14017d9d3  jmp     short loc_14017D9D8
0x14017d9d5  xor     sil, sil
0x14017d9d8  mov     rbx, [rbp+57h+arg_18]
0x14017d9dc  cmp     [rbp+57h+Process], 0
0x14017d9e1  jz      short loc_14017DA02
0x14017d9e3  test    [rbp+57h+var_7C], 8
0x14017d9e7  jz      short loc_14017D9F9
0x14017d9e9  call    ?PtiCurrent@@YAPEAUtagTHREADINFO@@XZ; PtiCurrent(void)
0x14017d9ee  mov     rcx, [rbp+57h+var_60]
0x14017d9f2  mov     [rax+178h], rcx
0x14017d9f9  lea     rcx, [rbp+57h+var_90]; this
0x14017d9fd  call    ?_Cleanup@CLockProcessByPid@@AEAAXXZ; CLockProcessByPid::_Cleanup(void)
0x14017da02  test    sil, sil
0x14017da05  jnz     loc_14017DFA3
0x14017da0b  cmp     r12d, 5
0x14017da0f  jnb     loc_14017DE4A
0x14017da15  add     r12d, edi
0x14017da18  mov     [rbp+57h+arg_10], r12d
0x14017da1c  jmp     loc_14017D649
0x14017da21  mov     rcx, cs:WPP_GLOBAL_Control
0x14017da28  lea     r12, WPP_GLOBAL_Control
0x14017da2f  cmp     rcx, r12
0x14017da32  jz      short loc_14017DA46
0x14017da34  mov     eax, [rcx+2Ch]
0x14017da37  test    al, 2
0x14017da39  jz      short loc_14017DA46
  ... truncated ...
```
