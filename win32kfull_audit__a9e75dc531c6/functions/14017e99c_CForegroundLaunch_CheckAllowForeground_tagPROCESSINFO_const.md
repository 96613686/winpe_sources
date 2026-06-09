# CForegroundLaunch::_CheckAllowForeground(tagPROCESSINFO const *)

- ea: `0x14017e99c`
- end: `0x14017f515`
- name: `?_CheckAllowForeground@CForegroundLaunch@@AEBA_NPEBUtagPROCESSINFO@@@Z`
- size: `2937`
- prototype: `char __fastcall(CForegroundLaunch *this, const struct tagPROCESSINFO *)`
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
char __fastcall CForegroundLaunch::_CheckAllowForeground(CForegroundLaunch *this, const struct tagPROCESSINFO *a2)
{
  char v4; // di
  __int64 v5; // r14
  int v6; // r12d
  unsigned int v7; // r13d
  int v8; // esi
  __int64 v9; // rcx
  __int64 ProcessInheritedFromUniqueProcessId; // rbx
  __int64 v11; // r8
  __int64 v12; // r9
  char v13; // r14
  bool v14; // r15
  int v15; // ebx
  __int64 UserSessionState; // rax
  int v17; // r8d
  int v18; // edx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  const struct tagPROCESSINFO *ProcessWin32Process; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  const struct tagPROCESSINFO *v29; // r14
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned __int8 v32; // al
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  tagTHREADINFO *v36; // rcx
  bool v37; // si
  bool v38; // r15
  int v39; // ebx
  __int64 v40; // rax
  int v41; // r8d
  int v42; // edx
  bool v43; // bl
  bool v44; // r15
  __int64 v45; // rax
  int v46; // r8d
  int v47; // edx
  __int64 v48; // rdx
  __int64 v49; // r8
  __int64 v50; // r9
  bool v51; // bl
  bool v52; // r15
  __int64 v53; // rax
  int v54; // r8d
  int v55; // edx
  PACCESS_TOKEN v56; // rax
  void *v57; // r13
  __int64 v58; // r8
  __int64 v59; // r9
  bool v60; // r15
  bool v61; // r12
  int v62; // ebx
  __int64 v63; // rax
  int v64; // r8d
  int v65; // edx
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  bool v69; // bl
  bool v70; // si
  __int64 v71; // rax
  int v72; // r8d
  int v73; // edx
  bool v74; // bl
  bool v75; // si
  __int64 v76; // rax
  int v77; // r8d
  int v78; // edx
  struct MOVESIZEDATA *v79; // rcx
  bool v80; // bl
  bool v81; // r14
  __int64 v82; // rax
  int v83; // r8d
  int v84; // edx
  CInputGlobals *v85; // rbx
  unsigned int *v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // r9
  bool v90; // bl
  bool v91; // si
  __int64 v92; // rax
  int v93; // edx
  int v94; // r8d
  bool v95; // bl
  bool v96; // r14
  __int64 v97; // rax
  int v98; // r8d
  int v99; // edx
  bool v100; // bl
  bool v101; // si
  __int64 v102; // rax
  int v103; // r8d
  int v104; // edx
  struct MOVESIZEDATA *v105; // rcx
  bool v106; // bl
  bool v107; // si
  __int64 v108; // rax
  int v109; // r8d
  int v110; // edx
  __int64 v111; // rcx
  __int64 v112; // rax
  bool v113; // bl
  bool v114; // si
  __int64 v115; // rax
  int v116; // r8d
  int v117; // edx
  bool v118; // r14
  int v119; // ebx
  __int64 v120; // rax
  int v121; // r8d
  int v122; // edx
  __int64 v123; // r9
  const char *v124; // rax
  int v126; // [rsp+20h] [rbp-49h]
  __int16 v127; // [rsp+30h] [rbp-39h]
  int v128; // [rsp+50h] [rbp-19h] BYREF
  PEPROCESS Process; // [rsp+58h] [rbp-11h] BYREF
  __int64 v130; // [rsp+60h] [rbp-9h]
  struct _LUID AuthenticationId; // [rsp+68h] [rbp-1h] BYREF
  struct _EPROCESS *v132; // [rsp+70h] [rbp+7h]
  unsigned int v135; // [rsp+E0h] [rbp+77h]

  if ( (unsigned int)Feature_ResponsiblePid__private_IsEnabledDeviceUsageNoInline() )
    return CForegroundLaunch::_CheckAllowForeground2(this, a2);
  v4 = 1;
  v5 = *(_QWORD *)a2;
  v6 = 1;
  v132 = *(struct _EPROCESS **)a2;
  v7 = 0;
  AuthenticationId = 0;
  v8 = 0;
  Process = 0;
  v135 = 0;
  v128 = -1;
  if ( *((_BYTE *)this + 440) )
    MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 1433);
  ProcessInheritedFromUniqueProcessId = PsGetProcessInheritedFromUniqueProcessId(v5);
  v130 = ProcessInheritedFromUniqueProcessId;
  if ( WPP_GLOBAL_Control == (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
    || (v9 = *((unsigned int *)WPP_GLOBAL_Control + 11), (v9 & 2) == 0)
    || (v13 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v13 = 0;
  }
  v14 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v13 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v15 = *((_DWORD *)a2 + 14);
    UserSessionState = W32GetUserSessionState(v9, WPP_GLOBAL_Control, v11, v12);
    LOBYTE(v17) = v14;
    LOBYTE(v18) = v13;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v18,
      v17,
      *(_QWORD *)(UserSessionState + 69152),
      4,
      2,
      69,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
      v15);
    ProcessInheritedFromUniqueProcessId = v130;
  }
  while ( 1 )
  {
    if ( (int)LockProcessByClientIdEx(ProcessInheritedFromUniqueProcessId, &Process, &v128) < 0 )
    {
      v100 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v101 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v100 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v102 = W32GetUserSessionState(WPP_GLOBAL_Control, v19, v20, v21);
        LOBYTE(v103) = v101;
        LOBYTE(v104) = v100;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v104,
          v103,
          *(_QWORD *)(v102 + 69152),
          4,
          2,
          74,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
LABEL_132:
      if ( !CForegroundLaunch::_HasLegacyForegroundActivateRight(this, v132) )
        goto LABEL_134;
LABEL_133:
      v8 = 1;
      goto LABEL_154;
    }
    if ( v128 != (unsigned int)W32GetCurrentWin32kSessionId() )
      break;
    ProcessWin32Process = (const struct tagPROCESSINFO *)PsGetProcessWin32Process(Process);
    v29 = ProcessWin32Process;
    if ( !ProcessWin32Process || !*(_QWORD *)ProcessWin32Process )
    {
      v74 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v75 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v74 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v76 = W32GetUserSessionState(WPP_GLOBAL_Control, v26, v27, v28);
        LOBYTE(v77) = v75;
        LOBYTE(v78) = v74;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v78,
          v77,
          *(_QWORD *)(v76 + 69152),
          4,
          2,
          75,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      ObfDereferenceObject(Process);
      goto LABEL_132;
    }
    if ( !v6
      && (IsShellProcess((__int64)ProcessWin32Process)
       || (v31 = *(_QWORD *)(v30 + 656)) != 0 && (*(_DWORD *)(v31 + 32) & 4) != 0) )
    {
      v69 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v70 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v69 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v71 = W32GetUserSessionState(WPP_GLOBAL_Control, v26, v27, v28);
        LOBYTE(v72) = v70;
        LOBYTE(v73) = v69;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v73,
          v72,
          *(_QWORD *)(v71 + 69152),
          4,
          2,
          76,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
      ObfDereferenceObject(Process);
      goto LABEL_134;
    }
    v32 = CanForceForeground(v29, v26, v27, v28);
    v8 = v32;
    if ( !v32 )
    {
      v36 = (tagTHREADINFO *)*((_QWORD *)v29 + 41);
      if ( v36 && tagTHREADINFO::ComputeAndTestForegroundActivate(v36) )
      {
        v37 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v38 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v37 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v39 = *((_DWORD *)v29 + 14);
          v40 = W32GetUserSessionState(WPP_GLOBAL_Control, v33, v34, v35);
          LOBYTE(v41) = v38;
          LOBYTE(v42) = v37;
          WPP_RECORDER_AND_TRACE_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v42,
            v41,
            *(_QWORD *)(v40 + 69152),
            4,
            2,
            77,
            (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
            v39);
          ProcessInheritedFromUniqueProcessId = v130;
        }
        v8 = 1;
      }
      else
      {
        v43 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
        v44 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
        if ( v43 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v45 = W32GetUserSessionState(WPP_GLOBAL_Control, v33, v34, v35);
          LOBYTE(v46) = v44;
          LOBYTE(v47) = v43;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v47,
            v46,
            *(_QWORD *)(v45 + 69152),
            4,
            2,
            78,
            (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
        }
        v130 = PsGetProcessInheritedFromUniqueProcessId(Process);
        ProcessInheritedFromUniqueProcessId = v130;
        if ( v6 )
        {
          v51 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
          v52 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
          if ( v51 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v53 = W32GetUserSessionState(WPP_GLOBAL_Control, v48, v49, v50);
            LOBYTE(v54) = v52;
            LOBYTE(v55) = v51;
            WPP_RECORDER_AND_TRACE_SF_(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v55,
              v54,
              *(_QWORD *)(v53 + 69152),
              4,
              2,
              79,
              (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
          }
          v6 = 0;
          v56 = PsReferencePrimaryToken(Process);
          v57 = v56;
          if ( v56 )
          {
            if ( SeQueryAuthenticationIdToken(v56, &AuthenticationId) >= 0 )
            {
              if ( AuthenticationId.LowPart == luidSystem[0] && AuthenticationId.HighPart == luidSystem[1] )
              {
                v8 = 1;
                v60 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
                v61 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
                if ( v60 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
                {
                  v62 = *((_DWORD *)v29 + 14);
                  v63 = W32GetUserSessionState(WPP_GLOBAL_Control, luidSystem[0], v58, v59);
                  LOBYTE(v64) = v61;
                  LOBYTE(v65) = v60;
                  WPP_RECORDER_AND_TRACE_SF_D(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    v65,
                    v64,
                    *(_QWORD *)(v63 + 69152),
                    4,
                    2,
                    80,
                    (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
                    v62);
                }
                *((_DWORD *)v29 + 3) |= 0x80000u;
                v6 = 0;
              }
              else
              {
                v8 = 0;
              }
            }
            ObfDereferenceObject(v57);
          }
          ProcessInheritedFromUniqueProcessId = v130;
          v7 = v135;
        }
      }
    }
    ObfDereferenceObject(Process);
    if ( v8 )
      goto LABEL_154;
    if ( v7 >= 5 )
      goto LABEL_134;
    v135 = ++v7;
  }
  v79 = WPP_GLOBAL_Control;
  v80 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v81 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v80 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v82 = W32GetUserSessionState(WPP_GLOBAL_Control, v22, v23, v24);
    LOBYTE(v83) = v81;
    LOBYTE(v84) = v80;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v84,
      v83,
      *(_QWORD *)(v82 + 69152),
      4,
      2,
      70,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
  }
  v85 = *(CInputGlobals **)(W32GetUserSessionState(v79, v22, v23, v24) + 3008);
  v86 = (unsigned int *)UPDWORDPointer(0x2000);
  if ( CInputGlobals::IsTimeFromLastInputEvent(v85, *v86) )
  {
    v90 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
       && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
       && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
    v91 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
    if ( v90 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v92 = W32GetUserSessionState(WPP_GLOBAL_Control, v87, v88, v89);
      v127 = 71;
      goto LABEL_112;
    }
    goto LABEL_113;
  }
  if ( v6 )
  {
    if ( (*((_DWORD *)a2 + 3) & 1) != 0 )
    {
      v90 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v91 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v90 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v92 = W32GetUserSessionState(WPP_GLOBAL_Control, v87, v88, v89);
        v127 = 72;
LABEL_112:
        LOBYTE(v94) = v91;
        LOBYTE(v93) = v90;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v93,
          v94,
          *(_QWORD *)(v92 + 69152),
          4,
          2,
          v127,
          (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
      }
LABEL_113:
      v8 = 1;
    }
    else
    {
      v95 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v96 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v95 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v97 = W32GetUserSessionState(WPP_GLOBAL_Control, v87, v88, v89);
        LOBYTE(v98) = v96;
        LOBYTE(v99) = v95;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v99,
          v98,
          *(_QWORD *)(v97 + 69152),
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
  v105 = WPP_GLOBAL_Control;
  v106 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v107 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v106 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v108 = W32GetUserSessionState(WPP_GLOBAL_Control, v66, v67, v68);
    LOBYTE(v109) = v107;
    LOBYTE(v110) = v106;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v110,
      v109,
      *(_QWORD *)(v108 + 69152),
      4,
      2,
      81,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids);
  }
  if ( *(_QWORD *)(W32GetUserSessionState(v105, v66, v67, v68) + 18984) )
  {
    v112 = *(_QWORD *)(W32GetUserSessionState(v111, v66, v67, v68) + 18984);
    if ( *(_DWORD *)(v112 + 664) <= 0x400u && (*(_DWORD *)(v112 + 680) & 0x40) != 0 )
    {
      v113 = WPP_GLOBAL_Control != (struct MOVESIZEDATA *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v114 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
      if ( v113 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v115 = W32GetUserSessionState(WPP_GLOBAL_Control, v66, v67, v68);
        LOBYTE(v116) = v114;
        LOBYTE(v117) = v113;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v117,
          v116,
          *(_QWORD *)(v115 + 69152),
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
  v118 = *(_QWORD *)&WPP_RECORDER_INITIALIZED != (_QWORD)&WPP_RECORDER_INITIALIZED;
  if ( v4 || *(unsigned int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v119 = *((_DWORD *)a2 + 14);
    v120 = W32GetUserSessionState(WPP_GLOBAL_Control, v66, v67, v68);
    LOBYTE(v121) = v118;
    LOBYTE(v122) = v4;
    v123 = *(_QWORD *)(v120 + 69152);
    v124 = "Yes";
    if ( !v8 )
      v124 = "No";
    WPP_RECORDER_AND_TRACE_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v122,
      v121,
      v123,
      v126,
      2,
      82,
      (__int64)WPP_3d9ce096fb1a308fe2f4900d37f39e7d_Traceguids,
      (__int64)v124,
      v119);
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
