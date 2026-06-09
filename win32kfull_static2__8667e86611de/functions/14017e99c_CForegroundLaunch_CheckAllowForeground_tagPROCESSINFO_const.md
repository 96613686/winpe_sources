# CForegroundLaunch::_CheckAllowForeground(tagPROCESSINFO const *)

- ea: `0x14017e99c`
- end: `0x14017f515`
- name: `?_CheckAllowForeground@CForegroundLaunch@@AEBA_NPEBUtagPROCESSINFO@@@Z`
- size: `2937`
- prototype: `bool __fastcall(CForegroundLaunch *__hidden this, const struct tagPROCESSINFO *)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14017d0a8`
- `0x1401875c4`
- `0x140214584`

## callees

- `0x1400a4a38`
- `0x1400dd43c`
- `0x140179c44`
- `0x140179cc4`
- `0x14017bc34`
- `0x14017c278`
- `0x14017cc14`
- `0x14017d534`
- `0x14017e99c`
- `0x1401d1fc4`
- `0x1401ea6d8`
- `0x1402938dc`

## import_xrefs

- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14017ed7d`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14017ed7d`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017ea22`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017ecad`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017ea22`
- `ntoskrnl!PsGetProcessInheritedFromUniqueProcessId` at `0x14017ecad`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14017ed5e`
- `ntoskrnl!PsReferencePrimaryToken` at `0x14017ed5e`
- `ntoskrnl!ObfDereferenceObject` at `0x14017ee57`
- `ntoskrnl!ObfDereferenceObject` at `0x14017ee6f`
- `ntoskrnl!ObfDereferenceObject` at `0x14017ef27`
- `ntoskrnl!ObfDereferenceObject` at `0x14017efc6`
- `ntoskrnl!ObfDereferenceObject` at `0x14017f225`
- `ntoskrnl!ObfDereferenceObject` at `0x14017ee57`
- `ntoskrnl!ObfDereferenceObject` at `0x14017ee6f`
- `ntoskrnl!ObfDereferenceObject` at `0x14017ef27`
- `ntoskrnl!ObfDereferenceObject` at `0x14017efc6`
- `ntoskrnl!ObfDereferenceObject` at `0x14017f225`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14017eafa`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14017eafa`
- `win32kbase!?IsTimeFromLastInputEvent@CInputGlobals@@QEBA_NK@Z` at `0x14017f08e`
- `win32kbase!?IsTimeFromLastInputEvent@CInputGlobals@@QEBA_NK@Z` at `0x14017f08e`
- `win32kbase!luidSystem` at `0x14017ed91`
- `win32kbase!UPDWORDPointer` at `0x14017f07d`
- `win32kbase!UPDWORDPointer` at `0x14017f07d`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x14017eb6b`
- `win32kbase!?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ` at `0x14017eb6b`
- `WIN32K!W32GetUserSessionState` at `0x14017ea7f`
- `WIN32K!W32GetUserSessionState` at `0x14017ebc7`
- `WIN32K!W32GetUserSessionState` at `0x14017ec61`
- `WIN32K!W32GetUserSessionState` at `0x14017ed0b`
- `WIN32K!W32GetUserSessionState` at `0x14017edf9`
- `WIN32K!W32GetUserSessionState` at `0x14017eedb`
- `WIN32K!W32GetUserSessionState` at `0x14017ef7a`
- `WIN32K!W32GetUserSessionState` at `0x14017f020`
- `WIN32K!W32GetUserSessionState` at `0x14017f065`
- `WIN32K!W32GetUserSessionState` at `0x14017f0de`
- `WIN32K!W32GetUserSessionState` at `0x14017f154`
- `WIN32K!W32GetUserSessionState` at `0x14017f1dc`
- `WIN32K!W32GetUserSessionState` at `0x14017f287`
- `WIN32K!W32GetUserSessionState` at `0x14017f330`
- `WIN32K!W32GetUserSessionState` at `0x14017f375`
- `WIN32K!W32GetUserSessionState` at `0x14017f38f`
- `WIN32K!W32GetUserSessionState` at `0x14017f3f9`
- `WIN32K!W32GetUserSessionState` at `0x14017f48d`
- `WIN32K!W32GetUserSessionState` at `0x14017ea7f`
- `WIN32K!W32GetUserSessionState` at `0x14017ebc7`
- `WIN32K!W32GetUserSessionState` at `0x14017ec61`
- `WIN32K!W32GetUserSessionState` at `0x14017ed0b`
- `WIN32K!W32GetUserSessionState` at `0x14017edf9`
- `WIN32K!W32GetUserSessionState` at `0x14017eedb`
- `WIN32K!W32GetUserSessionState` at `0x14017ef7a`
- `WIN32K!W32GetUserSessionState` at `0x14017f020`
- `WIN32K!W32GetUserSessionState` at `0x14017f065`
- `WIN32K!W32GetUserSessionState` at `0x14017f0de`
- `WIN32K!W32GetUserSessionState` at `0x14017f154`
- `WIN32K!W32GetUserSessionState` at `0x14017f1dc`
- `WIN32K!W32GetUserSessionState` at `0x14017f287`
- `WIN32K!W32GetUserSessionState` at `0x14017f330`
- `WIN32K!W32GetUserSessionState` at `0x14017f375`
- `WIN32K!W32GetUserSessionState` at `0x14017f38f`
- `WIN32K!W32GetUserSessionState` at `0x14017f3f9`
- `WIN32K!W32GetUserSessionState` at `0x14017f48d`

## pseudocode

```c
bool __fastcall CForegroundLaunch::_CheckAllowForeground(CForegroundLaunch *this, const struct tagPROCESSINFO *a2)
{
  char v4; // di
  __int64 v5; // r14
  int v6; // r12d
  unsigned int v7; // r13d
  int v8; // esi
  __int64 v9; // rcx
  __int64 ProcessInheritedFromUniqueProcessId; // rbx
  char v11; // r14
  bool v12; // r15
  int v13; // ebx
  __int64 UserSessionState; // rax
  int v15; // r8d
  int v16; // edx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int CurrentWin32kSessionId; // eax
  const struct tagPROCESSINFO *ProcessWin32Process; // rax
  const struct tagPROCESSINFO *v21; // r14
  __int64 v22; // rcx
  __int64 v23; // rax
  bool v24; // al
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
  void *v43; // r13
  bool v44; // r15
  bool v45; // r12
  int v46; // ebx
  __int64 v47; // rax
  int v48; // r8d
  int v49; // edx
  bool v50; // bl
  bool v51; // si
  __int64 v52; // rax
  int v53; // r8d
  int v54; // edx
  bool v55; // bl
  bool v56; // si
  __int64 v57; // rax
  int v58; // r8d
  int v59; // edx
  struct MOVESIZEDATA *v60; // rcx
  bool v61; // bl
  bool v62; // r14
  __int64 v63; // rax
  int v64; // r8d
  int v65; // edx
  CInputGlobals *v66; // rbx
  unsigned int *v67; // rax
  bool v68; // bl
  bool v69; // si
  __int64 v70; // rax
  int v71; // edx
  int v72; // r8d
  bool v73; // bl
  bool v74; // r14
  __int64 v75; // rax
  int v76; // r8d
  int v77; // edx
  bool v78; // bl
  bool v79; // si
  __int64 v80; // rax
  int v81; // r8d
  int v82; // edx
  struct MOVESIZEDATA *v83; // rcx
  bool v84; // bl
  bool v85; // si
  __int64 v86; // rax
  int v87; // r8d
  int v88; // edx
  __int64 v89; // rcx
  __int64 v90; // rax
  bool v91; // bl
  bool v92; // si
  __int64 v93; // rax
  int v94; // r8d
  int v95; // edx
  bool v96; // r14
  int v97; // ebx
  __int64 v98; // rax
  int v99; // r8d
  int v100; // edx
  __int64 v101; // r9
  const char *v102; // rax
  int v104; // [rsp+20h] [rbp-49h]
  __int16 v105; // [rsp+30h] [rbp-39h]
  int v106; // [rsp+50h] [rbp-19h] BYREF
  PEPROCESS Process; // [rsp+58h] [rbp-11h] BYREF
  __int64 v108; // [rsp+60h] [rbp-9h]
  struct _LUID AuthenticationId; // [rsp+68h] [rbp-1h] BYREF
  struct _EPROCESS *v110; // [rsp+70h] [rbp+7h]
  unsigned int v113; // [rsp+E0h] [rbp+77h]

  if ( (unsigned int)Feature_ResponsiblePid__private_IsEnabledDeviceUsageNoInline() )
    return CForegroundLaunch::_CheckAllowForeground2(this, a2);
  v4 = 1;
  v5 = *(_QWORD *)a2;
  v6 = 1;
  v110 = *(struct _EPROCESS **)a2;
  v7 = 0;
  AuthenticationId = 0;
  v8 = 0;
  Process = 0;
  v113 = 0;
  v106 = -1;
  if ( *((_BYTE *)this + 440) )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1433);
  ProcessInheritedFromUniqueProcessId = PsGetProcessInheritedFromUniqueProcessId(v5);
  v108 = ProcessInheritedFromUniqueProcessId;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (v9 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v9 & 2) == 0)
    || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v11 = 0;
  }
  v12 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v11 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v13 = *((_DWORD *)a2 + 14);
    UserSessionState = W32GetUserSessionState(v9);
    LOBYTE(v15) = v12;
    LOBYTE(v16) = v11;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v16,
      v15,
      *(_QWORD *)(UserSessionState + 69152),
      4,
      2,
      69,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
      v13);
    ProcessInheritedFromUniqueProcessId = v108;
  }
  while ( 1 )
  {
    if ( (int)LockProcessByClientIdEx(ProcessInheritedFromUniqueProcessId, &Process, &v106) < 0 )
    {
      v78 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v79 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v78 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v80 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v81) = v79;
        LOBYTE(v82) = v78;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v82,
          v81,
          *(_QWORD *)(v80 + 69152),
          4,
          2,
          74,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
LABEL_132:
      if ( !CForegroundLaunch::_HasLegacyForegroundActivateRight(this, v110) )
        goto LABEL_134;
LABEL_133:
      v8 = 1;
      goto LABEL_154;
    }
    CurrentWin32kSessionId = W32GetCurrentWin32kSessionId(v18, v17);
    if ( v106 != CurrentWin32kSessionId )
      break;
    ProcessWin32Process = (const struct tagPROCESSINFO *)PsGetProcessWin32Process(Process);
    v21 = ProcessWin32Process;
    if ( !ProcessWin32Process || !*(_QWORD *)ProcessWin32Process )
    {
      v55 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v56 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v55 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v57 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v58) = v56;
        LOBYTE(v59) = v55;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v59,
          v58,
          *(_QWORD *)(v57 + 69152),
          4,
          2,
          75,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      ObfDereferenceObject(Process);
      goto LABEL_132;
    }
    if ( !v6
      && ((unsigned int)IsShellProcess(ProcessWin32Process)
       || (v23 = *(_QWORD *)(v22 + 656)) != 0 && (*(_DWORD *)(v23 + 32) & 4) != 0) )
    {
      v50 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v51 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v50 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v52 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v53) = v51;
        LOBYTE(v54) = v50;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v54,
          v53,
          *(_QWORD *)(v52 + 69152),
          4,
          2,
          76,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      ObfDereferenceObject(Process);
      goto LABEL_134;
    }
    v24 = CanForceForeground(v21);
    v8 = v24;
    if ( !v24 )
    {
      v25 = (tagTHREADINFO *)*((_QWORD *)v21 + 41);
      if ( v25 && tagTHREADINFO::ComputeAndTestForegroundActivate(v25) )
      {
        v26 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v27 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v26 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v28 = *((_DWORD *)v21 + 14);
          v29 = W32GetUserSessionState(WPP_GLOBAL_Control);
          LOBYTE(v30) = v27;
          LOBYTE(v31) = v26;
          WPP_RECORDER_AND_TRACE_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v31,
            v30,
            *(_QWORD *)(v29 + 69152),
            4,
            2,
            77,
            (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
            v28);
          ProcessInheritedFromUniqueProcessId = v108;
        }
        v8 = 1;
      }
      else
      {
        v32 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v33 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v32 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v34 = W32GetUserSessionState(WPP_GLOBAL_Control);
          LOBYTE(v35) = v33;
          LOBYTE(v36) = v32;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v36,
            v35,
            *(_QWORD *)(v34 + 69152),
            4,
            2,
            78,
            (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
        }
        v108 = PsGetProcessInheritedFromUniqueProcessId(Process);
        ProcessInheritedFromUniqueProcessId = v108;
        if ( v6 )
        {
          v37 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v38 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v37 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v39 = W32GetUserSessionState(WPP_GLOBAL_Control);
            LOBYTE(v40) = v38;
            LOBYTE(v41) = v37;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v41,
              v40,
              *(_QWORD *)(v39 + 69152),
              4,
              2,
              79,
              (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
          }
          v6 = 0;
          v42 = PsReferencePrimaryToken(Process);
          v43 = v42;
          if ( v42 )
          {
            if ( SeQueryAuthenticationIdToken(v42, &AuthenticationId) >= 0 )
            {
              if ( AuthenticationId.LowPart == luidSystem[0] && AuthenticationId.HighPart == luidSystem[1] )
              {
                v8 = 1;
                v44 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
                v45 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
                if ( v44 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  v46 = *((_DWORD *)v21 + 14);
                  v47 = W32GetUserSessionState(WPP_GLOBAL_Control);
                  LOBYTE(v48) = v45;
                  LOBYTE(v49) = v44;
                  WPP_RECORDER_AND_TRACE_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v49,
                    v48,
                    *(_QWORD *)(v47 + 69152),
                    4,
                    2,
                    80,
                    (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
                    v46);
                }
                *((_DWORD *)v21 + 3) |= 0x80000u;
                v6 = 0;
              }
              else
              {
                v8 = 0;
              }
            }
            ObfDereferenceObject(v43);
          }
          ProcessInheritedFromUniqueProcessId = v108;
          v7 = v113;
        }
      }
    }
    ObfDereferenceObject(Process);
    if ( v8 )
      goto LABEL_154;
    if ( v7 >= 5 )
      goto LABEL_134;
    v113 = ++v7;
  }
  v60 = WPP_GLOBAL_Control;
  v61 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v62 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v61 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v63 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v64) = v62;
    LOBYTE(v65) = v61;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v65,
      v64,
      *(_QWORD *)(v63 + 69152),
      4,
      2,
      70,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
  }
  v66 = *(CInputGlobals **)(W32GetUserSessionState(v60) + 3008);
  v67 = (unsigned int *)UPDWORDPointer(0x2000);
  if ( CInputGlobals::IsTimeFromLastInputEvent(v66, *v67) )
  {
    v68 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v69 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v68 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v70 = W32GetUserSessionState(WPP_GLOBAL_Control);
      v105 = 71;
      goto LABEL_112;
    }
    goto LABEL_113;
  }
  if ( v6 )
  {
    if ( (*((_DWORD *)a2 + 3) & 1) != 0 )
    {
      v68 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v69 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v68 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v70 = W32GetUserSessionState(WPP_GLOBAL_Control);
        v105 = 72;
LABEL_112:
        LOBYTE(v72) = v69;
        LOBYTE(v71) = v68;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v71,
          v72,
          *(_QWORD *)(v70 + 69152),
          4,
          2,
          v105,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
LABEL_113:
      v8 = 1;
    }
    else
    {
      v73 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v74 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v73 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v75 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v76) = v74;
        LOBYTE(v77) = v73;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v77,
          v76,
          *(_QWORD *)(v75 + 69152),
          4,
          2,
          73,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
    }
  }
  ObfDereferenceObject(Process);
  if ( v8 )
    goto LABEL_154;
LABEL_134:
  v83 = WPP_GLOBAL_Control;
  v84 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v85 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v84 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v86 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v87) = v85;
    LOBYTE(v88) = v84;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v88,
      v87,
      *(_QWORD *)(v86 + 69152),
      4,
      2,
      81,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v83) + 18984) )
  {
    v90 = *(_QWORD *)(W32GetUserSessionState(v89) + 18984);
    if ( *(_DWORD *)(v90 + 664) <= 0x400u && (*(_DWORD *)(v90 + 680) & 0x40) != 0 )
    {
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
          116,
          (__int64)WPP_ead4d7a99ff93d20acaa230191e6e258_Traceguids);
      }
      goto LABEL_133;
    }
  }
  v8 = 0;
LABEL_154:
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u )
  {
    v4 = 0;
  }
  v96 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v4 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v97 = *((_DWORD *)a2 + 14);
    v98 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v99) = v96;
    LOBYTE(v100) = v4;
    v101 = *(_QWORD *)(v98 + 69152);
    v102 = "Yes";
    if ( !v8 )
      v102 = "No";
    WPP_RECORDER_AND_TRACE_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v100,
      v99,
      v101,
      v104,
      2,
      82,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
      (__int64)v102,
      v97);
  }
  return v8 != 0;
}

```

## disassembly

```asm
0x14017e99c  mov     [rsp-8+arg_8], rdx
0x14017e9a1  mov     [rsp-8+arg_0], rcx
0x14017e9a6  push    rbp
0x14017e9a7  push    rbx
0x14017e9a8  push    rsi
0x14017e9a9  push    rdi
0x14017e9aa  push    r12
0x14017e9ac  push    r13
0x14017e9ae  push    r14
0x14017e9b0  push    r15
0x14017e9b2  lea     rbp, [rsp-1Fh]
0x14017e9b7  sub     rsp, 88h
0x14017e9be  mov     rsi, rdx
0x14017e9c1  mov     rbx, rcx
0x14017e9c4  call    Feature_ResponsiblePid__private_IsEnabledDeviceUsageNoInline
0x14017e9c9  xor     r15d, r15d
0x14017e9cc  test    eax, eax
0x14017e9ce  jnz     loc_14017F4F5
0x14017e9d4  lea     edi, [rax+1]
0x14017e9d7  mov     r14, [rsi]
0x14017e9da  mov     r12d, edi
0x14017e9dd  mov     [rbp+57h+var_50], r14
0x14017e9e1  mov     r13d, r15d
0x14017e9e4  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], r15
0x14017e9e8  mov     esi, r15d
0x14017e9eb  mov     [rbp+57h+Process], r15
0x14017e9ef  mov     [rbp+57h+arg_10], r15d
0x14017e9f3  mov     [rbp+57h+var_70], 0FFFFFFFFh
0x14017e9fa  cmp     [rbx+1B8h], r15b
0x14017ea01  jz      short loc_14017EA1F
0x14017ea03  mov     [rbp+57h+arg_18], 20000h
0x14017ea0a  lea     rcx, aIxptelassert; "IXPTelAssert"
0x14017ea11  mov     edx, [rbp+57h+arg_18]
0x14017ea14  mov     r8d, 599h
0x14017ea1a  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x14017ea1f  mov     rcx, r14
0x14017ea22  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x14017ea29  nop     dword ptr [rax+rax+00h]
0x14017ea2e  mov     rbx, rax
0x14017ea31  mov     [rbp+57h+var_60], rax
0x14017ea35  mov     rdx, cs:WPP_GLOBAL_Control
0x14017ea3c  lea     rax, WPP_GLOBAL_Control
0x14017ea43  cmp     rdx, rax
0x14017ea46  jz      short loc_14017EA59
0x14017ea48  mov     ecx, [rdx+2Ch]
0x14017ea4b  test    cl, 2
0x14017ea4e  jz      short loc_14017EA59
0x14017ea50  cmp     byte ptr [rdx+29h], 4
0x14017ea54  mov     r14b, dil
0x14017ea57  jnb     short loc_14017EA5C
0x14017ea59  mov     r14b, r15b
0x14017ea5c  lea     rax, WPP_RECORDER_INITIALIZED
0x14017ea63  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017ea6a  setnz   r15b
0x14017ea6e  test    r14b, r14b
0x14017ea71  jnz     short loc_14017EA78
0x14017ea73  test    r15b, r15b
0x14017ea76  jz      short loc_14017EAD0
0x14017ea78  mov     rbx, [rbp+57h+arg_8]
0x14017ea7c  mov     ebx, [rbx+38h]
0x14017ea7f  call    cs:__imp_W32GetUserSessionState
0x14017ea86  nop     dword ptr [rax+rax+00h]
0x14017ea8b  mov     dword ptr [rsp+0C0h+var_80], ebx
0x14017ea8f  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017ea96  mov     [rsp+0C0h+var_88], rcx
0x14017ea9b  mov     r8b, r15b
0x14017ea9e  mov     rcx, cs:WPP_GLOBAL_Control
0x14017eaa5  mov     dl, r14b
0x14017eaa8  mov     r9, [rax+10E20h]
0x14017eaaf  mov     [rsp+0C0h+var_90], 45h ; 'E'
0x14017eab6  mov     [rsp+0C0h+var_98], 2
0x14017eabe  mov     rcx, [rcx+18h]
0x14017eac2  mov     [rsp+0C0h+var_A0], 4
0x14017eac7  call    WPP_RECORDER_AND_TRACE_SF_D
0x14017eacc  mov     rbx, [rbp+57h+var_60]
0x14017ead0  lea     r8, [rbp+57h+var_70]
0x14017ead4  mov     rcx, rbx
0x14017ead7  lea     rdx, [rbp+57h+Process]
0x14017eadb  call    LockProcessByClientIdEx
0x14017eae0  test    eax, eax
0x14017eae2  js      loc_14017F245
0x14017eae8  call    W32GetCurrentWin32kSessionId
0x14017eaed  cmp     [rbp+57h+var_70], eax
0x14017eaf0  jnz     loc_14017EFD7
0x14017eaf6  mov     rcx, [rbp+57h+Process]
0x14017eafa  call    cs:__imp_PsGetProcessWin32Process
0x14017eb01  nop     dword ptr [rax+rax+00h]
0x14017eb06  mov     r14, rax
0x14017eb09  test    rax, rax
0x14017eb0c  jz      loc_14017EF38
0x14017eb12  cmp     qword ptr [rax], 0
0x14017eb16  jz      loc_14017EF38
0x14017eb1c  test    r12d, r12d
0x14017eb1f  jnz     short loc_14017EB48
0x14017eb21  mov     rcx, rax
0x14017eb24  call    IsShellProcess
0x14017eb29  test    eax, eax
0x14017eb2b  jnz     loc_14017EE99
0x14017eb31  mov     rax, [rcx+290h]
0x14017eb38  test    rax, rax
0x14017eb3b  jz      short loc_14017EB48
0x14017eb3d  mov     eax, [rax+20h]
0x14017eb40  test    al, 4
0x14017eb42  jnz     loc_14017EE99
0x14017eb48  mov     rcx, r14; struct tagPROCESSINFO *
0x14017eb4b  call    ?CanForceForeground@@YA_NPEBUtagPROCESSINFO@@@Z; CanForceForeground(tagPROCESSINFO const *)
0x14017eb50  movzx   esi, al
0x14017eb53  test    al, al
0x14017eb55  jnz     loc_14017EE6B
0x14017eb5b  mov     rcx, [r14+148h]
0x14017eb62  test    rcx, rcx
0x14017eb65  jz      loc_14017EC1F
0x14017eb6b  call    cs:__imp_?ComputeAndTestForegroundActivate@tagTHREADINFO@@QEAA_NXZ; tagTHREADINFO::ComputeAndTestForegroundActivate(void)
0x14017eb72  nop     dword ptr [rax+rax+00h]
0x14017eb77  test    al, al
0x14017eb79  jz      loc_14017EC1F
0x14017eb7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14017eb86  lea     rax, WPP_GLOBAL_Control
0x14017eb8d  cmp     rcx, rax
0x14017eb90  jz      short loc_14017EBA4
0x14017eb92  mov     eax, [rcx+2Ch]
0x14017eb95  test    al, 2
0x14017eb97  jz      short loc_14017EBA4
0x14017eb99  cmp     byte ptr [rcx+29h], 4
0x14017eb9d  jb      short loc_14017EBA4
0x14017eb9f  mov     sil, dil
0x14017eba2  jmp     short loc_14017EBA7
0x14017eba4  xor     sil, sil
0x14017eba7  lea     rax, WPP_RECORDER_INITIALIZED
0x14017ebae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017ebb5  setnz   r15b
0x14017ebb9  test    sil, sil
0x14017ebbc  jnz     short loc_14017EBC3
0x14017ebbe  test    r15b, r15b
0x14017ebc1  jz      short loc_14017EC18
0x14017ebc3  mov     ebx, [r14+38h]
0x14017ebc7  call    cs:__imp_W32GetUserSessionState
0x14017ebce  nop     dword ptr [rax+rax+00h]
0x14017ebd3  mov     dword ptr [rsp+0C0h+var_80], ebx
0x14017ebd7  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017ebde  mov     [rsp+0C0h+var_88], rcx
0x14017ebe3  mov     r8b, r15b
0x14017ebe6  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ebed  mov     dl, sil
0x14017ebf0  mov     r9, [rax+10E20h]
0x14017ebf7  mov     [rsp+0C0h+var_90], 4Dh ; 'M'
0x14017ebfe  mov     [rsp+0C0h+var_98], 2
0x14017ec06  mov     rcx, [rcx+18h]
0x14017ec0a  mov     [rsp+0C0h+var_A0], 4
0x14017ec0f  call    WPP_RECORDER_AND_TRACE_SF_D
0x14017ec14  mov     rbx, [rbp+57h+var_60]
0x14017ec18  mov     esi, edi
0x14017ec1a  jmp     loc_14017EE6B
0x14017ec1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ec26  lea     rax, WPP_GLOBAL_Control
0x14017ec2d  cmp     rcx, rax
0x14017ec30  jz      short loc_14017EC44
0x14017ec32  mov     eax, [rcx+2Ch]
0x14017ec35  test    al, 2
0x14017ec37  jz      short loc_14017EC44
0x14017ec39  cmp     byte ptr [rcx+29h], 4
0x14017ec3d  jb      short loc_14017EC44
0x14017ec3f  mov     bl, dil
0x14017ec42  jmp     short loc_14017EC46
0x14017ec44  xor     bl, bl
0x14017ec46  lea     rax, WPP_RECORDER_INITIALIZED
0x14017ec4d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017ec54  setnz   r15b
0x14017ec58  test    bl, bl
0x14017ec5a  jnz     short loc_14017EC61
0x14017ec5c  test    r15b, r15b
0x14017ec5f  jz      short loc_14017ECA9
0x14017ec61  call    cs:__imp_W32GetUserSessionState
0x14017ec68  nop     dword ptr [rax+rax+00h]
0x14017ec6d  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017ec74  mov     r8b, r15b
0x14017ec77  mov     [rsp+0C0h+var_88], rcx
0x14017ec7c  mov     dl, bl
0x14017ec7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ec85  mov     r9, [rax+10E20h]
0x14017ec8c  mov     [rsp+0C0h+var_90], 4Eh ; 'N'
0x14017ec93  mov     [rsp+0C0h+var_98], 2
0x14017ec9b  mov     rcx, [rcx+18h]
0x14017ec9f  mov     [rsp+0C0h+var_A0], 4
0x14017eca4  call    WPP_RECORDER_AND_TRACE_SF_
0x14017eca9  mov     rcx, [rbp+57h+Process]
0x14017ecad  call    cs:__imp_PsGetProcessInheritedFromUniqueProcessId
0x14017ecb4  nop     dword ptr [rax+rax+00h]
0x14017ecb9  mov     [rbp+57h+var_60], rax
0x14017ecbd  mov     rbx, rax
0x14017ecc0  test    r12d, r12d
0x14017ecc3  jz      loc_14017EE6B
0x14017ecc9  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ecd0  lea     rax, WPP_GLOBAL_Control
0x14017ecd7  cmp     rcx, rax
0x14017ecda  jz      short loc_14017ECEE
0x14017ecdc  mov     eax, [rcx+2Ch]
0x14017ecdf  test    al, 2
0x14017ece1  jz      short loc_14017ECEE
0x14017ece3  cmp     byte ptr [rcx+29h], 4
0x14017ece7  jb      short loc_14017ECEE
0x14017ece9  mov     bl, dil
0x14017ecec  jmp     short loc_14017ECF0
0x14017ecee  xor     bl, bl
0x14017ecf0  lea     rax, WPP_RECORDER_INITIALIZED
0x14017ecf7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017ecfe  setnz   r15b
0x14017ed02  test    bl, bl
0x14017ed04  jnz     short loc_14017ED0B
0x14017ed06  test    r15b, r15b
0x14017ed09  jz      short loc_14017ED53
0x14017ed0b  call    cs:__imp_W32GetUserSessionState
0x14017ed12  nop     dword ptr [rax+rax+00h]
0x14017ed17  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017ed1e  mov     r8b, r15b
0x14017ed21  mov     [rsp+0C0h+var_88], rcx
0x14017ed26  mov     dl, bl
0x14017ed28  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ed2f  mov     r9, [rax+10E20h]
0x14017ed36  mov     [rsp+0C0h+var_90], 4Fh ; 'O'
0x14017ed3d  mov     [rsp+0C0h+var_98], 2
0x14017ed45  mov     rcx, [rcx+18h]
0x14017ed49  mov     [rsp+0C0h+var_A0], 4
0x14017ed4e  call    WPP_RECORDER_AND_TRACE_SF_
0x14017ed53  mov     rcx, [rbp+57h+Process]; Process
0x14017ed57  xor     r12d, r12d
0x14017ed5a  mov     [rbp+57h+arg_18], r12d
0x14017ed5e  call    cs:__imp_PsReferencePrimaryToken
0x14017ed65  nop     dword ptr [rax+rax+00h]
0x14017ed6a  mov     r13, rax
0x14017ed6d  test    rax, rax
0x14017ed70  jz      loc_14017EE63
0x14017ed76  lea     rdx, [rbp+57h+AuthenticationId]; AuthenticationId
0x14017ed7a  mov     rcx, rax; Token
0x14017ed7d  call    cs:__imp_SeQueryAuthenticationIdToken
0x14017ed84  nop     dword ptr [rax+rax+00h]
0x14017ed89  test    eax, eax
0x14017ed8b  js      loc_14017EE54
0x14017ed91  mov     rcx, cs:__imp_luidSystem
0x14017ed98  mov     edx, [rcx]
0x14017ed9a  cmp     [rbp+57h+AuthenticationId.LowPart], edx
0x14017ed9d  jnz     loc_14017EE52
0x14017eda3  mov     eax, [rcx+4]
0x14017eda6  cmp     [rbp+57h+AuthenticationId.HighPart], eax
0x14017eda9  jnz     loc_14017EE52
0x14017edaf  mov     esi, edi
0x14017edb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14017edb8  lea     rax, WPP_GLOBAL_Control
0x14017edbf  cmp     rcx, rax
0x14017edc2  jz      short loc_14017EDD6
0x14017edc4  mov     eax, [rcx+2Ch]
0x14017edc7  test    al, 2
0x14017edc9  jz      short loc_14017EDD6
0x14017edcb  cmp     byte ptr [rcx+29h], 4
0x14017edcf  jb      short loc_14017EDD6
0x14017edd1  mov     r15b, dil
0x14017edd4  jmp     short loc_14017EDD9
0x14017edd6  xor     r15b, r15b
0x14017edd9  lea     rax, WPP_RECORDER_INITIALIZED
0x14017ede0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14017ede7  setnz   r12b
0x14017edeb  test    r15b, r15b
0x14017edee  jnz     short loc_14017EDF5
0x14017edf0  test    r12b, r12b
0x14017edf3  jz      short loc_14017EE46
0x14017edf5  mov     ebx, [r14+38h]
0x14017edf9  call    cs:__imp_W32GetUserSessionState
0x14017ee00  nop     dword ptr [rax+rax+00h]
0x14017ee05  mov     dword ptr [rsp+0C0h+var_80], ebx
0x14017ee09  lea     rcx, WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids
0x14017ee10  mov     [rsp+0C0h+var_88], rcx
0x14017ee15  mov     r8b, r12b
0x14017ee18  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ee1f  mov     dl, r15b
0x14017ee22  mov     r9, [rax+10E20h]
0x14017ee29  mov     [rsp+0C0h+var_90], 50h ; 'P'
0x14017ee30  mov     [rsp+0C0h+var_98], 2
0x14017ee38  mov     rcx, [rcx+18h]
0x14017ee3c  mov     [rsp+0C0h+var_A0], 4
0x14017ee41  call    WPP_RECORDER_AND_TRACE_SF_D
0x14017ee46  bts     dword ptr [r14+0Ch], 13h
0x14017ee4c  mov     r12d, [rbp+57h+arg_18]
0x14017ee50  jmp     short loc_14017EE54
0x14017ee52  xor     esi, esi
0x14017ee54  mov     rcx, r13; Object
0x14017ee57  call    cs:__imp_ObfDereferenceObject
0x14017ee5e  nop     dword ptr [rax+rax+00h]
0x14017ee63  mov     rbx, [rbp+57h+var_60]
0x14017ee67  mov     r13d, [rbp+57h+arg_10]
0x14017ee6b  mov     rcx, [rbp+57h+Process]; Object
0x14017ee6f  call    cs:__imp_ObfDereferenceObject
0x14017ee76  nop     dword ptr [rax+rax+00h]
0x14017ee7b  test    esi, esi
0x14017ee7d  jnz     loc_14017F447
0x14017ee83  cmp     r13d, 5
0x14017ee87  jnb     loc_14017F2E7
0x14017ee8d  add     r13d, edi
0x14017ee90  mov     [rbp+57h+arg_10], r13d
0x14017ee94  jmp     loc_14017EAD0
0x14017ee99  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
