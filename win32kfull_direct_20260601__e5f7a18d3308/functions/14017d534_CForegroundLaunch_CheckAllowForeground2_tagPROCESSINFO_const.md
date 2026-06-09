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
  int v16; // ebx
  __int64 v17; // rdx
  const struct tagPROCESSINFO *ProcessWin32Process; // rax
  __int64 v19; // rdx
  const struct tagPROCESSINFO *v20; // r14
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  tagTHREADINFO *v25; // rcx
  bool v26; // si
  bool v27; // r15
  int v28; // ebx
  __int64 v29; // rax
  int v30; // r8d
  int v31; // edx
  bool v32; // bl
  bool v33; // r15
  __int64 v34; // rax
  int v35; // r8d
  int v36; // edx
  bool v37; // bl
  bool v38; // r15
  __int64 v39; // rax
  int v40; // r8d
  int v41; // edx
  PACCESS_TOKEN v42; // rax
  bool v43; // r15
  bool v44; // r12
  int v45; // ebx
  __int64 v46; // rax
  int v47; // r8d
  int v48; // edx
  bool v49; // bl
  bool v50; // si
  __int64 v51; // rax
  int v52; // r8d
  int v53; // edx
  bool v54; // bl
  bool v55; // r14
  __int64 v56; // rax
  int v57; // edx
  int v58; // r8d
  struct MOVESIZEDATA *v59; // rcx
  bool v60; // bl
  bool v61; // r14
  __int64 v62; // rax
  int v63; // r8d
  int v64; // edx
  CInputGlobals *v65; // rbx
  unsigned int *v66; // rax
  bool v67; // bl
  bool v68; // si
  __int64 v69; // rax
  int v70; // edx
  int v71; // r8d
  bool v72; // bl
  bool v73; // r14
  __int64 v74; // rax
  int v75; // r8d
  int v76; // edx
  struct MOVESIZEDATA *v77; // rcx
  bool v78; // bl
  bool v79; // si
  __int64 v80; // rax
  int v81; // r8d
  int v82; // edx
  __int64 v83; // rcx
  __int64 v84; // rax
  bool v85; // bl
  bool v86; // si
  __int64 v87; // rax
  int v88; // r8d
  int v89; // edx
  bool v90; // r14
  int v91; // ebx
  __int64 v92; // rax
  int v93; // r8d
  int v94; // edx
  __int64 v95; // r9
  const char *v96; // rax
  int v98; // [rsp+20h] [rbp-79h]
  __int16 v99; // [rsp+30h] [rbp-69h]
  __int16 v100; // [rsp+30h] [rbp-69h]
  _LUID AuthenticationId; // [rsp+50h] [rbp-49h] BYREF
  char v102[8]; // [rsp+60h] [rbp-39h] BYREF
  int v103; // [rsp+68h] [rbp-31h]
  char v104; // [rsp+74h] [rbp-25h]
  PEPROCESS Process; // [rsp+78h] [rbp-21h]
  int v106; // [rsp+88h] [rbp-11h]
  __int64 v107; // [rsp+90h] [rbp-9h]
  unsigned int v110; // [rsp+110h] [rbp+77h]
  __int64 v111; // [rsp+118h] [rbp+7Fh]

  if ( *((_BYTE *)this + 440) )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1256);
  v3 = 0;
  v4 = 1;
  v110 = 0;
  v5 = 0;
  v6 = 1;
  ProcessInheritedFromUniqueProcessId = PsGetProcessInheritedFromUniqueProcessId(*(_QWORD *)a2);
  v111 = ProcessInheritedFromUniqueProcessId;
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
    UserSessionState = W32GetUserSessionState(v7, WPP_GLOBAL_Control);
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
    ProcessInheritedFromUniqueProcessId = v111;
  }
  while ( 1 )
  {
    v98 = 0;
    CLockProcessByPid::CLockProcessByPid(v102, ProcessInheritedFromUniqueProcessId, 0);
    if ( v103 < 0 )
    {
      v54 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v55 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v54 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v56 = W32GetUserSessionState(WPP_GLOBAL_Control, v15);
        v99 = 60;
LABEL_132:
        LOBYTE(v58) = v55;
        LOBYTE(v57) = v54;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v57,
          v58,
          *(_QWORD *)(v56 + 69152),
          4,
          2,
          v99,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
LABEL_133:
      if ( CForegroundLaunch::_HasLegacyForegroundActivateRight(this, *(struct _EPROCESS **)a2) )
        v5 = 1;
      goto LABEL_135;
    }
    v16 = v106;
    if ( (unsigned int)W32GetCurrentWin32kSessionId() != v16 )
      break;
    ProcessWin32Process = (const struct tagPROCESSINFO *)PsGetProcessWin32Process(Process);
    v20 = ProcessWin32Process;
    if ( !ProcessWin32Process || !*(_QWORD *)ProcessWin32Process )
    {
      v54 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v55 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v54 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v56 = W32GetUserSessionState(WPP_GLOBAL_Control, v19);
        v99 = 61;
        goto LABEL_132;
      }
      goto LABEL_133;
    }
    if ( !v6
      && ((unsigned int)IsShellProcess(ProcessWin32Process)
       || (v23 = *(_QWORD *)(v22 + 656)) != 0 && (*(_DWORD *)(v23 + 32) & 4) != 0) )
    {
      v49 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v50 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v49 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v51 = W32GetUserSessionState(WPP_GLOBAL_Control, v21);
        LOBYTE(v52) = v50;
        LOBYTE(v53) = v49;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v53,
          v52,
          *(_QWORD *)(v51 + 69152),
          4,
          2,
          62,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      CLockProcessByPid::~CLockProcessByPid((CLockProcessByPid *)v102);
LABEL_140:
      v77 = WPP_GLOBAL_Control;
      v78 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v79 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v78 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v80 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
        LOBYTE(v81) = v79;
        LOBYTE(v82) = v78;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v82,
          v81,
          *(_QWORD *)(v80 + 69152),
          4,
          2,
          67,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      if ( *(_QWORD *)(W32GetUserSessionState(v77, v24) + 18984)
        && (v84 = *(_QWORD *)(W32GetUserSessionState(v83, v24) + 18984), *(_DWORD *)(v84 + 664) <= 0x400u)
        && (*(_DWORD *)(v84 + 680) & 0x40) != 0 )
      {
        v85 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v86 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v85 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v87 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
          LOBYTE(v88) = v86;
          LOBYTE(v89) = v85;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v89,
            v88,
            *(_QWORD *)(v87 + 69152),
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
    v5 = CanForceForeground(v20);
    if ( v5 )
      goto LABEL_62;
    v25 = (tagTHREADINFO *)*((_QWORD *)v20 + 41);
    if ( v25 && tagTHREADINFO::ComputeAndTestForegroundActivate(v25) )
    {
      v26 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v27 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v26 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v28 = *((_DWORD *)v20 + 14);
        v29 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
        LOBYTE(v30) = v27;
        LOBYTE(v31) = v26;
        WPP_RECORDER_AND_TRACE_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v31,
          v30,
          *(_QWORD *)(v29 + 69152),
          4,
          2,
          63,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
          v28);
      }
      v5 = 1;
LABEL_62:
      ProcessInheritedFromUniqueProcessId = v111;
      goto LABEL_63;
    }
    v32 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v33 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v32 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v34 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
      LOBYTE(v35) = v33;
      LOBYTE(v36) = v32;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v36,
        v35,
        *(_QWORD *)(v34 + 69152),
        4,
        2,
        64,
        (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
    }
    v111 = PsGetProcessInheritedFromUniqueProcessId(Process);
    ProcessInheritedFromUniqueProcessId = v111;
    if ( v6 )
    {
      v37 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v38 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v37 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v39 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
        LOBYTE(v40) = v38;
        LOBYTE(v41) = v37;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v41,
          v40,
          *(_QWORD *)(v39 + 69152),
          4,
          2,
          65,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      v6 = 0;
      v42 = PsReferencePrimaryToken(Process);
      if ( v42 )
      {
        AuthenticationId = 0;
        if ( SeQueryAuthenticationIdToken(v42, &AuthenticationId) >= 0 )
        {
          if ( AuthenticationId.LowPart == luidSystem[0] && AuthenticationId.HighPart == luidSystem[1] )
          {
            v5 = 1;
            v43 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
               && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
            v44 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
            if ( v43 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v45 = *((_DWORD *)v20 + 14);
              v46 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
              LOBYTE(v47) = v44;
              LOBYTE(v48) = v43;
              WPP_RECORDER_AND_TRACE_SF_D(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v48,
                v47,
                *(_QWORD *)(v46 + 69152),
                4,
                2,
                66,
                (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
                v45);
            }
            *((_DWORD *)v20 + 3) |= 0x80000u;
            v3 = v110;
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
      if ( (v104 & 8) != 0 )
        *((_QWORD *)PtiCurrent() + 47) = v107;
      CLockProcessByPid::_Cleanup((CLockProcessByPid *)v102);
    }
    if ( v5 )
      goto LABEL_161;
    if ( v3 >= 5 )
      goto LABEL_140;
    v110 = ++v3;
  }
  v59 = WPP_GLOBAL_Control;
  v60 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v61 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v60 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v62 = W32GetUserSessionState(WPP_GLOBAL_Control, v17);
    LOBYTE(v63) = v61;
    LOBYTE(v64) = v60;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v64,
      v63,
      *(_QWORD *)(v62 + 69152),
      4,
      2,
      56,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
  }
  v65 = *(CInputGlobals **)(W32GetUserSessionState(v59, v17) + 3008);
  v66 = (unsigned int *)UPDWORDPointer(0x2000);
  if ( CInputGlobals::IsTimeFromLastInputEvent(v65, *v66) )
  {
    v67 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v68 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v67 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v69 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
      v100 = 57;
      goto LABEL_114;
    }
    goto LABEL_115;
  }
  if ( !v6 )
    goto LABEL_135;
  if ( (*((_DWORD *)a2 + 3) & 1) != 0 )
  {
    v67 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v68 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v67 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v69 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
      v100 = 58;
LABEL_114:
      LOBYTE(v71) = v68;
      LOBYTE(v70) = v67;
      WPP_RECORDER_AND_TRACE_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v70,
        v71,
        *(_QWORD *)(v69 + 69152),
        4,
        2,
        v100,
        (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
    }
LABEL_115:
    v5 = 1;
    goto LABEL_135;
  }
  v72 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v73 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v72 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v74 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
    LOBYTE(v75) = v73;
    LOBYTE(v76) = v72;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v76,
      v75,
      *(_QWORD *)(v74 + 69152),
      4,
      2,
      59,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
  }
LABEL_135:
  if ( Process )
  {
    if ( (v104 & 8) != 0 )
      *((_QWORD *)PtiCurrent() + 47) = v107;
    CLockProcessByPid::_Cleanup((CLockProcessByPid *)v102);
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
  v90 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v4 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v91 = *((_DWORD *)a2 + 14);
    v92 = W32GetUserSessionState(WPP_GLOBAL_Control, v24);
    LOBYTE(v93) = v90;
    LOBYTE(v94) = v4;
    v95 = *(_QWORD *)(v92 + 69152);
    v96 = "Yes";
    if ( !v5 )
      v96 = "No";
    WPP_RECORDER_AND_TRACE_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v94,
      v93,
      v95,
      v98,
      2,
      68,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
      (__int64)v96,
      v91);
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
