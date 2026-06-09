# xxxInitProcessInfo

- ea: `0x14014e31c`
- end: `0x14014ed33`
- name: `xxxInitProcessInfo`
- size: `2583`
- prototype: `int __fastcall(struct _W32PROCESS *, void *, unsigned int, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14014da60`
- `0x14014e0ec`

## callees

- `0x14000730c`
- `0x140035ecc`
- `0x140063ef0`
- `0x14006b610`
- `0x14009dac0`
- `0x1400a5ba0`
- `0x1400a612c`
- `0x1400c1c0c`
- `0x1400de43c`
- `0x1400e5ce0`
- `0x1400e5d38`
- `0x140111520`
- `0x140121070`
- `0x14014924c`
- `0x14014e31c`
- `0x14014f9c4`
- `0x14014fdcc`
- `0x1401877ac`
- `0x1401968fc`
- `0x140196a78`
- `0x1401a7e80`
- `0x1401c78bc`
- `0x1401c7d70`
- `0x1402388e0`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14014e998`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014e998`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e43b`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e624`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e840`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e944`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e43b`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e624`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e840`
- `ntoskrnl!SeQueryInformationToken` at `0x14014e944`
- `ntoskrnl!PsIsProtectedProcess` at `0x14014e5c9`
- `ntoskrnl!PsIsProtectedProcess` at `0x14014e73d`
- `ntoskrnl!PsIsProtectedProcess` at `0x14014e5c9`
- `ntoskrnl!PsIsProtectedProcess` at `0x14014e73d`
- `ntoskrnl!PsGetProcessProtection` at `0x14014e5e0`
- `ntoskrnl!PsGetProcessProtection` at `0x14014e753`
- `ntoskrnl!PsGetProcessProtection` at `0x14014e5e0`
- `ntoskrnl!PsGetProcessProtection` at `0x14014e753`
- `ntoskrnl!RtlGetAppContainerSidType` at `0x14014e96d`
- `ntoskrnl!RtlGetAppContainerSidType` at `0x14014e96d`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14014e9b9`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14014e9b9`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014eb03`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014eb03`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014e3be`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014e3be`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014eca3`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014eca3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014ea62`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014eb5c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014eb89`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014ea62`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014eb5c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014eb89`
- `WIN32K!W32GetUserSessionState` at `0x14014e4aa`
- `WIN32K!W32GetUserSessionState` at `0x14014e55e`
- `WIN32K!W32GetUserSessionState` at `0x14014e6b3`
- `WIN32K!W32GetUserSessionState` at `0x14014e7d5`
- `WIN32K!W32GetUserSessionState` at `0x14014e8b9`
- `WIN32K!W32GetUserSessionState` at `0x14014e9fc`
- `WIN32K!W32GetUserSessionState` at `0x14014ea34`
- `WIN32K!W32GetUserSessionState` at `0x14014ea4f`
- `WIN32K!W32GetUserSessionState` at `0x14014ea95`
- `WIN32K!W32GetUserSessionState` at `0x14014eb3c`
- `WIN32K!W32GetUserSessionState` at `0x14014ec06`
- `WIN32K!W32GetUserSessionState` at `0x14014ec65`
- `WIN32K!W32GetUserSessionState` at `0x14014ec8d`
- `WIN32K!W32GetUserSessionState` at `0x14014e4aa`
- `WIN32K!W32GetUserSessionState` at `0x14014e55e`
- `WIN32K!W32GetUserSessionState` at `0x14014e6b3`
- `WIN32K!W32GetUserSessionState` at `0x14014e7d5`
- `WIN32K!W32GetUserSessionState` at `0x14014e8b9`
- `WIN32K!W32GetUserSessionState` at `0x14014e9fc`
- `WIN32K!W32GetUserSessionState` at `0x14014ea34`
- `WIN32K!W32GetUserSessionState` at `0x14014ea4f`
- `WIN32K!W32GetUserSessionState` at `0x14014ea95`
- `WIN32K!W32GetUserSessionState` at `0x14014eb3c`
- `WIN32K!W32GetUserSessionState` at `0x14014ec06`
- `WIN32K!W32GetUserSessionState` at `0x14014ec65`
- `WIN32K!W32GetUserSessionState` at `0x14014ec8d`

## pseudocode

```c
int __fastcall xxxInitProcessInfo(struct _W32PROCESS *a1, void *a2, unsigned int a3, unsigned int a4, __int64 a5)
{
  char v7; // r13
  char v8; // al
  int result; // eax
  __int64 v10; // rdx
  AtomicExecutionCheck *v11; // rcx
  __int64 v12; // rcx
  __int64 CurrentThreadWin32Thread; // r14
  PACCESS_TOKEN v14; // rsi
  NTSTATUS InformationToken; // r15d
  char v16; // di
  int v17; // ebx
  __int64 v18; // rax
  int v19; // eax
  char v20; // di
  int v21; // ebx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned __int8 v25; // al
  __int64 v26; // rdx
  CTouchProcessor *v27; // rcx
  char v28; // al
  __int64 v29; // rax
  int v30; // r8d
  int v31; // edx
  int v32; // eax
  __int64 v33; // rcx
  unsigned __int8 ProcessProtection; // al
  CTouchProcessor *v35; // rcx
  char v36; // al
  int v37; // ebx
  int v38; // edi
  __int64 v39; // rsi
  __int64 UserSessionState; // rax
  CTouchProcessor *v41; // rcx
  __int64 v42; // rdi
  __int64 v43; // rax
  PACCESS_TOKEN v44; // rbx
  NTSTATUS v45; // eax
  int v46; // ebx
  int SpriteFillColorOverrideForCurrentProcess; // eax
  __int64 v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  void (__fastcall *v57)(struct _W32PROCESS *); // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rcx
  int Win32KFilterSet; // eax
  __int64 v64; // rcx
  unsigned __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rcx
  int (*v69)(void); // rax
  void (__fastcall *v70)(struct _W32PROCESS *); // rax
  __int64 v71; // rdx
  char v72; // si
  int v73; // ebx
  __int64 v74; // rax
  __int64 v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // [rsp+20h] [rbp-81h]
  __int64 v78; // [rsp+40h] [rbp-61h]
  __int64 v79; // [rsp+48h] [rbp-59h]
  char v80; // [rsp+70h] [rbp-31h] BYREF
  char v81; // [rsp+71h] [rbp-30h]
  PVOID v82; // [rsp+74h] [rbp-2Dh] BYREF
  int v83; // [rsp+7Ch] [rbp-25h] BYREF
  PACCESS_TOKEN Token; // [rsp+80h] [rbp-21h]
  PVOID P; // [rsp+88h] [rbp-19h] BYREF
  unsigned int v86; // [rsp+90h] [rbp-11h]
  __int64 v87; // [rsp+98h] [rbp-9h]
  __int64 v88; // [rsp+A0h] [rbp-1h]
  PVOID TokenInformation; // [rsp+A8h] [rbp+7h] BYREF
  int v90; // [rsp+B0h] [rbp+Fh]

  v88 = a5;
  v86 = a3;
  TokenInformation = 0;
  v90 = 0;
  v7 = 1;
  v8 = *((_BYTE *)a1 + 1200);
  Token = a2;
  HIDWORD(v82) = 0;
  P = 0;
  v83 = 0;
  if ( v8 == 1 )
    return 1073741851;
  if ( (Microsoft_Windows_Win32kEnableBits & 0x8000) != 0 )
    McTemplateK0_EtwWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)"T", &W32kControlGuid);
  result = xxxCheckProcessAndSessionState((PEPROCESS *)a1);
  if ( result < 0 )
    return result;
  AtomicExecutionCheck::EnforceConsistency(v11, v10);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v12);
  v87 = CurrentThreadWin32Thread;
  ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
  *((_BYTE *)a1 + 1200) = 1;
  *((_QWORD *)a1 + 38) = 0;
  *((_QWORD *)a1 + 39) = 0;
  *((_DWORD *)a1 + 80) = 0;
  if ( (unsigned int)Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline() )
  {
    result = InitProcessUipiInfo(a1, Token, a4);
    if ( result < 0 )
      goto LABEL_103;
    goto LABEL_54;
  }
  HIDWORD(TokenInformation) = a4;
  v14 = Token;
  InformationToken = SeQueryInformationToken(Token, TokenIntegrityLevel, &TokenInformation);
  if ( !(unsigned int)Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( UIPrivilegeIsolation::fEnforceUIPI )
    {
      if ( InformationToken < 0
        || (v32 = (int)TokenInformation, HIDWORD(TokenInformation)) && (_DWORD)TokenInformation != 4096 )
      {
LABEL_27:
        result = -1073741823;
LABEL_103:
        --*(_DWORD *)(CurrentThreadWin32Thread + 28);
        return result;
      }
      *((_DWORD *)a1 + 217) = HIDWORD(TokenInformation);
      v33 = *(_QWORD *)a1;
      *((_DWORD *)a1 + 216) = v32;
      if ( (unsigned int)PsIsProtectedProcess(v33, 0) )
      {
        ProcessProtection = PsGetProcessProtection(*(_QWORD *)a1, 0);
        *((_DWORD *)a1 + 218) = ((ProcessProtection >> 4)
                               | ((((ProcessProtection & 7) << 8) | (ProcessProtection >> 3) & 1) << 8)) << 8;
      }
    }
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0
      || (v36 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v36 = 0;
    }
    v81 = v36;
    v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v36 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v37 = *((_DWORD *)a1 + 217);
      v38 = *((_DWORD *)a1 + 216);
      v39 = *(_QWORD *)a1;
      LOBYTE(v35) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      UserSessionState = W32GetUserSessionState(v35, 0);
      WPP_RECORDER_AND_TRACE_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v81,
        v80,
        *(_QWORD *)(UserSessionState + 69136),
        4u,
        0xEu,
        0x1Eu,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
        v39,
        v38,
        v37);
    }
    if ( InformationToken < 0 )
      goto LABEL_55;
    goto LABEL_54;
  }
  if ( InformationToken < 0 )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v7 = 0;
    }
    v16 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = *((_DWORD *)a1 + 14);
      v18 = W32GetUserSessionState(WPP_GLOBAL_Control, 0);
      WPP_RECORDER_AND_TRACE_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v7,
        v16,
        *(_QWORD *)(v18 + 69136),
        3u,
        8u,
        0x1Bu,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
        InformationToken,
        v17);
    }
    goto LABEL_102;
  }
  v19 = (int)TokenInformation;
  if ( HIDWORD(TokenInformation) && (_DWORD)TokenInformation != 4096 )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v7 = 0;
    }
    v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = *((_DWORD *)a1 + 14);
      v22 = W32GetUserSessionState(WPP_GLOBAL_Control, 0);
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v7,
        v20,
        *(_QWORD *)(v22 + 69136),
        3u,
        8u,
        0x1Cu,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
        v21);
    }
    goto LABEL_27;
  }
  *((_DWORD *)a1 + 217) = HIDWORD(TokenInformation);
  v23 = *(_QWORD *)a1;
  *((_DWORD *)a1 + 216) = v19;
  if ( (unsigned int)PsIsProtectedProcess(v23, 0) )
  {
    v25 = PsGetProcessProtection(*(_QWORD *)a1, v24);
    *((_DWORD *)a1 + 218) = ((v25 >> 4) | ((((v25 & 7) << 8) | (v25 >> 3) & 1) << 8)) << 8;
  }
  LODWORD(v82) = 0;
  if ( SeQueryInformationToken(v14, TokenDeviceClaimAttributes|TokenAuditPolicy, &v82) >= 0 && (_DWORD)v82 )
    *((_QWORD *)a1 + 101) |= 0x4000000000uLL;
  v27 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
    || (v28 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v28 = 0;
  }
  v81 = v28;
  v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v29 = W32GetUserSessionState(v27, v26);
    LOBYTE(v30) = v80;
    LOBYTE(v31) = v81;
    WPP_RECORDER_AND_TRACE_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v31, v30, *(_QWORD *)(v29 + 69136));
    CurrentThreadWin32Thread = v87;
  }
LABEL_54:
  InformationToken = SeQueryInformationToken(Token, TokenUIAccess, (PVOID *)((char *)&v82 + 4));
LABEL_55:
  if ( HIDWORD(v82) )
  {
    *((_DWORD *)a1 + 3) |= 0x80080000;
    *((_QWORD *)a1 + 101) |= 2uLL;
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || (LOBYTE(v41) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      LOBYTE(v41) = 0;
    }
    v81 = (char)v41;
    v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v41 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v42 = *(_QWORD *)a1;
      v43 = W32GetUserSessionState(v41, 0);
      HIDWORD(v78) = HIDWORD(v42);
      WPP_RECORDER_AND_TRACE_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v81,
        v80,
        *(_QWORD *)(v43 + 69136),
        v77,
        8u,
        0x1Fu,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids);
    }
  }
  v44 = Token;
  SetProcessType(a1, Token, v86, v88);
  SetProcessInitialCapabilities(a1);
  if ( InformationToken < 0 )
  {
    v46 = 0;
  }
  else
  {
    v45 = SeQueryInformationToken(v44, TokenAppContainerSid, &P);
    v46 = 0;
    InformationToken = v45;
    if ( v45 >= 0 )
    {
      if ( *(_QWORD *)P && (int)RtlGetAppContainerSidType(*(_QWORD *)P, &v83) >= 0 )
        *((_DWORD *)a1 + 219) = v83;
      else
        *((_DWORD *)a1 + 219) = 0;
      ExFreePoolWithTag(P, 0);
      P = 0;
      goto LABEL_70;
    }
  }
  if ( !(unsigned int)Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline() )
  {
LABEL_70:
    SpriteFillColorOverrideForCurrentProcess = GetSpriteFillColorOverrideForCurrentProcess();
    v48 = *(_QWORD *)a1;
    *((_DWORD *)a1 + 269) = SpriteFillColorOverrideForCurrentProcess;
    if ( PsGetProcessWow64Process(v48) )
      *((_DWORD *)a1 + 3) |= 0x80u;
    *((_QWORD *)a1 + 111) = -1;
    *((_QWORD *)a1 + 112) = -1;
    v51 = *((_DWORD *)a1 + 3);
    if ( (v51 & 0x20) == 0 )
    {
      *((_DWORD *)a1 + 3) = v51 | 0x22;
      v52 = W32GetUserSessionState(v50, v49);
      *(_DWORD *)(v52 + 66784) |= 0x8000000u;
      if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
      {
        CWinEventNoopDeferral::CWinEventNoopDeferral((CWinEventNoopDeferral *)&v80, v49);
        zzzCalcStartCursorHide(0, 0);
        CWinEventNoopDeferral::~CWinEventNoopDeferral((CWinEventNoopDeferral *)&v80, v53);
      }
    }
    v54 = *(_QWORD *)(W32GetUserSessionState(v50, v49) + 36200);
    *((_QWORD *)a1 + 46) = v54;
    *(_QWORD *)(W32GetUserSessionState(v54, v55) + 36200) = a1;
    v57 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v56) + 48) + 4776LL);
    if ( v57 )
      v57(a1);
    GetProcessLuid(0, (PLUID)((char *)a1 + 764));
    v60 = W32GetUserSessionState(v59, v58);
    LOBYTE(v61) = 1;
    *((_DWORD *)a1 + 98) = *(_DWORD *)(v60 + 41156);
    *((_DWORD *)a1 + 186) = 0;
    CitProcessCallout((__int64)a1, v61);
    *((_QWORD *)a1 + 101) &= 0xFFFFFFFFFFBE7FFFuLL;
    v62 = *((_QWORD *)a1 + 101);
    *((_DWORD *)a1 + 67) = 24592;
    *((_WORD *)a1 + 136) = 96;
    if ( (v62 & 0x30) == 0x20 )
      *((_QWORD *)a1 + 101) = v62 | 0x100000;
    Win32KFilterSet = PsGetWin32KFilterSet();
    v64 = 0;
    if ( Win32KFilterSet == 5 )
      v64 = 0x1000000;
    v65 = *((_QWORD *)a1 + 101) & 0xFFFFFFFFF6FFFFFFuLL | v64 & 0xFFFFFFFFF7FFFFFFuLL;
    *((_QWORD *)a1 + 101) = v65;
    v66 = *(_QWORD *)(W32GetUserSessionState(v65, 0x1000000) + 19704);
    if ( *(_WORD *)(v66 + 6998) )
    {
      v68 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v66) + 48);
      v69 = *(int (**)(void))(v68 + 832);
      if ( v69 && v69() >= 0 )
      {
        v70 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v68) + 48) + 840LL);
        if ( v70 )
          v70(a1);
      }
      else
      {
        *((_WORD *)a1 + 136) = *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v68, v67) + 19704) + 6998LL);
      }
    }
    Feature_WebThreatDefenseToggle__private_IsEnabledPreCheck();
    if ( *(_DWORD *)(W32GetUserSessionState(v76, v75) + 42376) )
    {
      if ( !W32GetInputMonitorSessionState() )
        MicrosoftTelemetryAssertTriggeredNoArgsKM();
      v46 = 1;
    }
    *((_DWORD *)a1 + 69) = (4 * v46) | *((_DWORD *)a1 + 69) & 0xFFFFFFFB;
    *((_QWORD *)a1 + 136) = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                           * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
LABEL_102:
    result = InformationToken;
    goto LABEL_103;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
    || (v72 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
  {
    v72 = 0;
  }
  v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v72 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v73 = *((_DWORD *)a1 + 14);
    v74 = W32GetUserSessionState(WPP_GLOBAL_Control, v71);
    LODWORD(v79) = v73;
    LODWORD(v78) = InformationToken;
    WPP_RECORDER_AND_TRACE_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v72,
      v80,
      *(_QWORD *)(v74 + 69136),
      3u,
      8u,
      0x20u,
      (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
      v78,
      v79);
  }
  --*(_DWORD *)(CurrentThreadWin32Thread + 28);
  return InformationToken;
}

```

## disassembly

```asm
0x14014e31c  mov     [rsp-8+arg_10], rbx
0x14014e321  push    rbp
0x14014e322  push    rsi
0x14014e323  push    rdi
0x14014e324  push    r12
0x14014e326  push    r13
0x14014e328  push    r14
0x14014e32a  push    r15
0x14014e32c  lea     rbp, [rsp-1Fh]
0x14014e331  sub     rsp, 0C0h
0x14014e338  mov     rax, cs:__security_cookie
0x14014e33f  xor     rax, rsp
0x14014e342  mov     [rbp+4Fh+var_38], rax
0x14014e346  mov     rax, [rbp+4Fh+arg_20]
0x14014e34a  xor     r15d, r15d
0x14014e34d  mov     [rbp+4Fh+var_50], rax
0x14014e351  mov     esi, r9d
0x14014e354  xor     eax, eax
0x14014e356  mov     [rbp+4Fh+var_60], r8d
0x14014e35a  mov     [rbp+4Fh+TokenInformation], rax
0x14014e35e  mov     r12, rcx
0x14014e361  mov     [rbp+4Fh+var_40], eax
0x14014e364  lea     r13d, [r15+1]
0x14014e368  mov     al, [rcx+4B0h]
0x14014e36e  mov     [rbp+4Fh+Token], rdx
0x14014e372  mov     dword ptr [rbp+4Fh+var_7C+4], r15d
0x14014e376  mov     [rbp+4Fh+P], r15
0x14014e37a  mov     [rbp+4Fh+var_74], r15d
0x14014e37e  cmp     al, r13b
0x14014e381  jnz     short loc_14014E38D
0x14014e383  mov     eax, 4000001Bh
0x14014e388  jmp     loc_14014ED0B
0x14014e38d  cmp     byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, r15b
0x14014e394  jge     short loc_14014E3A9
0x14014e396  lea     r8, W32kControlGuid
0x14014e39d  lea     rdx, InitiateGuiProcessExecution; "T"
0x14014e3a4  call    McTemplateK0_EtwWriteTransfer
0x14014e3a9  mov     rcx, r12; struct _W32PROCESS *
0x14014e3ac  call    ?xxxCheckProcessAndSessionState@@YAJPEAU_W32PROCESS@@@Z; xxxCheckProcessAndSessionState(_W32PROCESS *)
0x14014e3b1  test    eax, eax
0x14014e3b3  js      loc_14014ED0B
0x14014e3b9  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x14014e3be  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14014e3c5  nop     dword ptr [rax+rax+00h]
0x14014e3ca  mov     r14, rax
0x14014e3cd  mov     [rbp+4Fh+var_58], rax
0x14014e3d1  add     [rax+1Ch], r13d
0x14014e3d5  mov     [r12+4B0h], r13b
0x14014e3dd  mov     [r12+130h], r15
0x14014e3e5  mov     [r12+138h], r15
0x14014e3ed  mov     [r12+140h], r15d
0x14014e3f5  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x14014e3fa  lea     rbx, WPP_GLOBAL_Control
0x14014e401  lea     rdi, WPP_RECORDER_INITIALIZED
0x14014e408  test    eax, eax
0x14014e40a  jz      short loc_14014E428
0x14014e40c  mov     rdx, [rbp+4Fh+Token]; void *
0x14014e410  mov     r8d, esi; unsigned int
0x14014e413  mov     rcx, r12; struct tagPROCESSINFO *
0x14014e416  call    ?InitProcessUipiInfo@@YAJPEAUtagPROCESSINFO@@PEAXK@Z; InitProcessUipiInfo(tagPROCESSINFO *,void *,ulong)
0x14014e41b  test    eax, eax
0x14014e41d  jns     loc_14014E833
0x14014e423  jmp     loc_14014ED07
0x14014e428  mov     dword ptr [rbp+4Fh+TokenInformation+4], esi
0x14014e42b  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x14014e42f  mov     rsi, [rbp+4Fh+Token]
0x14014e433  mov     edx, 19h; TokenInformationClass
0x14014e438  mov     rcx, rsi; Token
0x14014e43b  call    cs:__imp_SeQueryInformationToken
0x14014e442  nop     dword ptr [rax+rax+00h]
0x14014e447  mov     r15d, eax
0x14014e44a  call    Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline
0x14014e44f  xor     edx, edx
0x14014e451  test    eax, eax
0x14014e453  jz      loc_14014E703
0x14014e459  test    r15d, r15d
0x14014e45c  jns     loc_14014E501
0x14014e462  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e469  lea     rsi, WPP_GLOBAL_Control
0x14014e470  cmp     rcx, rsi
0x14014e473  jz      short loc_14014E482
0x14014e475  mov     eax, [rcx+2Ch]
0x14014e478  test    al, al
0x14014e47a  jns     short loc_14014E482
0x14014e47c  cmp     byte ptr [rcx+29h], 3
0x14014e480  jnb     short loc_14014E485
0x14014e482  mov     r13b, dl
0x14014e485  lea     rax, WPP_RECORDER_INITIALIZED
0x14014e48c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014e493  setnz   dil
0x14014e497  test    r13b, r13b
0x14014e49a  jnz     short loc_14014E4A5
0x14014e49c  test    dil, dil
0x14014e49f  jz      loc_14014ED04
0x14014e4a5  mov     ebx, [r12+38h]
0x14014e4aa  call    cs:__imp_W32GetUserSessionState
0x14014e4b1  nop     dword ptr [rax+rax+00h]
0x14014e4b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e4bd  mov     r8b, dil
0x14014e4c0  mov     dword ptr [rsp+0F0h+var_A8], ebx
0x14014e4c4  mov     dl, r13b
0x14014e4c7  mov     dword ptr [rsp+0F0h+var_B0], r15d
0x14014e4cc  mov     r9, [rax+10E10h]
0x14014e4d3  lea     rax, WPP_88dc8779c13439e164336e7011252f30_Traceguids
0x14014e4da  mov     rcx, [rcx+18h]
0x14014e4de  mov     [rsp+0F0h+var_B8], rax
0x14014e4e3  mov     [rsp+0F0h+var_C0], 1Bh
0x14014e4ea  mov     [rsp+0F0h+var_C8], 8
0x14014e4f2  mov     byte ptr [rsp+0F0h+var_D0], 3
0x14014e4f7  call    WPP_RECORDER_AND_TRACE_SF_dD
0x14014e4fc  jmp     loc_14014ED04
0x14014e501  mov     ecx, dword ptr [rbp+4Fh+TokenInformation+4]
0x14014e504  mov     eax, dword ptr [rbp+4Fh+TokenInformation]
0x14014e507  test    ecx, ecx
0x14014e509  jz      loc_14014E5B5
0x14014e50f  cmp     eax, 1000h
0x14014e514  jz      loc_14014E5B5
0x14014e51a  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e521  lea     rsi, WPP_GLOBAL_Control
0x14014e528  cmp     rcx, rsi
0x14014e52b  jz      short loc_14014E53A
0x14014e52d  mov     eax, [rcx+2Ch]
0x14014e530  test    al, al
0x14014e532  jns     short loc_14014E53A
0x14014e534  cmp     byte ptr [rcx+29h], 3
0x14014e538  jnb     short loc_14014E53D
0x14014e53a  mov     r13b, dl
0x14014e53d  lea     rax, WPP_RECORDER_INITIALIZED
0x14014e544  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014e54b  setnz   dil
0x14014e54f  test    r13b, r13b
0x14014e552  jnz     short loc_14014E559
0x14014e554  test    dil, dil
0x14014e557  jz      short loc_14014E5AB
0x14014e559  mov     ebx, [r12+38h]
0x14014e55e  call    cs:__imp_W32GetUserSessionState
0x14014e565  nop     dword ptr [rax+rax+00h]
0x14014e56a  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e571  mov     r8b, dil
0x14014e574  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x14014e578  mov     dl, r13b
0x14014e57b  mov     r9, [rax+10E10h]
0x14014e582  lea     rax, WPP_88dc8779c13439e164336e7011252f30_Traceguids
0x14014e589  mov     rcx, [rcx+18h]
0x14014e58d  mov     [rsp+0F0h+var_B8], rax
0x14014e592  mov     [rsp+0F0h+var_C0], 1Ch
0x14014e599  mov     [rsp+0F0h+var_C8], 8
0x14014e5a1  mov     byte ptr [rsp+0F0h+var_D0], 3
0x14014e5a6  call    WPP_RECORDER_AND_TRACE_SF_D
0x14014e5ab  mov     eax, 0C0000001h
0x14014e5b0  jmp     loc_14014ED07
0x14014e5b5  mov     [r12+364h], ecx
0x14014e5bd  mov     rcx, [r12]
0x14014e5c1  mov     [r12+360h], eax
0x14014e5c9  call    cs:__imp_PsIsProtectedProcess
0x14014e5d0  nop     dword ptr [rax+rax+00h]
0x14014e5d5  xor     r15d, r15d
0x14014e5d8  test    eax, eax
0x14014e5da  jz      short loc_14014E614
0x14014e5dc  mov     rcx, [r12]
0x14014e5e0  call    cs:__imp_PsGetProcessProtection
0x14014e5e7  nop     dword ptr [rax+rax+00h]
0x14014e5ec  movzx   ecx, al
0x14014e5ef  mov     edx, ecx
0x14014e5f1  mov     eax, ecx
0x14014e5f3  shr     edx, 3
0x14014e5f6  and     eax, 7
0x14014e5f9  and     edx, r13d
0x14014e5fc  shl     eax, 8
0x14014e5ff  or      edx, eax
0x14014e601  shr     ecx, 4
0x14014e604  shl     edx, 8
0x14014e607  or      edx, ecx
0x14014e609  shl     edx, 8
0x14014e60c  mov     [r12+368h], edx
0x14014e614  lea     r8, [rbp+4Fh+var_7C]; TokenInformation
0x14014e618  mov     dword ptr [rbp+4Fh+var_7C], r15d
0x14014e61c  mov     edx, 32h ; '2'; TokenInformationClass
0x14014e621  mov     rcx, rsi; Token
0x14014e624  call    cs:__imp_SeQueryInformationToken
0x14014e62b  nop     dword ptr [rax+rax+00h]
0x14014e630  test    eax, eax
0x14014e632  js      short loc_14014E64C
0x14014e634  cmp     dword ptr [rbp+4Fh+var_7C], r15d
0x14014e638  jz      short loc_14014E64C
0x14014e63a  mov     rax, 4000000000h
0x14014e644  or      [r12+328h], rax
0x14014e64c  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e653  cmp     rcx, rbx
0x14014e656  jz      short loc_14014E668
0x14014e658  mov     eax, [rcx+2Ch]
0x14014e65b  test    al, al
0x14014e65d  jns     short loc_14014E668
0x14014e65f  cmp     byte ptr [rcx+29h], 4
0x14014e663  mov     al, r13b
0x14014e666  jnb     short loc_14014E66B
0x14014e668  mov     al, r15b
0x14014e66b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14014e672  mov     [rbp+4Fh+var_7F], al
0x14014e675  setnz   cl
0x14014e678  mov     [rbp+4Fh+var_80], cl
0x14014e67b  test    al, al
0x14014e67d  jnz     short loc_14014E687
0x14014e67f  test    cl, cl
0x14014e681  jz      loc_14014E833
0x14014e687  mov     r15, [r12+328h]
0x14014e68f  mov     ebx, [r12+368h]
0x14014e697  mov     edi, [r12+364h]
0x14014e69f  mov     esi, [r12+360h]
0x14014e6a7  mov     r14d, [r12+38h]
0x14014e6ac  shr     r15, 26h
0x14014e6b0  and     r15d, r13d
0x14014e6b3  call    cs:__imp_W32GetUserSessionState
0x14014e6ba  nop     dword ptr [rax+rax+00h]
0x14014e6bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e6c6  mov     r8b, [rbp+4Fh+var_80]
0x14014e6ca  mov     dl, [rbp+4Fh+var_7F]
0x14014e6cd  mov     r9, [rax+10E10h]
0x14014e6d4  mov     rcx, [rcx+18h]
0x14014e6d8  mov     [rsp+0F0h+var_90], r15d
0x14014e6dd  mov     [rsp+0F0h+var_98], ebx
0x14014e6e1  mov     [rsp+0F0h+var_A0], edi
0x14014e6e5  mov     dword ptr [rsp+0F0h+var_A8], esi
0x14014e6e9  mov     dword ptr [rsp+0F0h+var_B0], r14d
0x14014e6ee  mov     [rsp+0F0h+var_C0], 1Dh
0x14014e6f5  call    WPP_RECORDER_AND_TRACE_SF_DDDDD
0x14014e6fa  mov     r14, [rbp+4Fh+var_58]
0x14014e6fe  jmp     loc_14014E833
0x14014e703  cmp     cs:?fEnforceUIPI@UIPrivilegeIsolation@@3_NA, dl; bool UIPrivilegeIsolation::fEnforceUIPI
0x14014e709  jz      short loc_14014E789
0x14014e70b  test    r15d, r15d
0x14014e70e  js      loc_14014E5AB
0x14014e714  mov     ecx, dword ptr [rbp+4Fh+TokenInformation+4]
0x14014e717  mov     eax, dword ptr [rbp+4Fh+TokenInformation]
0x14014e71a  test    ecx, ecx
0x14014e71c  jz      short loc_14014E729
0x14014e71e  cmp     eax, 1000h
0x14014e723  jnz     loc_14014E5AB
0x14014e729  mov     [r12+364h], ecx
0x14014e731  mov     rcx, [r12]
0x14014e735  mov     [r12+360h], eax
0x14014e73d  call    cs:__imp_PsIsProtectedProcess
0x14014e744  nop     dword ptr [rax+rax+00h]
0x14014e749  xor     edx, edx
0x14014e74b  test    eax, eax
0x14014e74d  jz      short loc_14014E789
0x14014e74f  mov     rcx, [r12]
0x14014e753  call    cs:__imp_PsGetProcessProtection
0x14014e75a  nop     dword ptr [rax+rax+00h]
0x14014e75f  movzx   ecx, al
0x14014e762  mov     edx, ecx
0x14014e764  mov     eax, ecx
0x14014e766  shr     edx, 3
0x14014e769  and     eax, 7
0x14014e76c  and     edx, r13d
0x14014e76f  shl     eax, 8
0x14014e772  or      edx, eax
0x14014e774  shr     ecx, 4
0x14014e777  shl     edx, 8
0x14014e77a  or      edx, ecx
0x14014e77c  shl     edx, 8
0x14014e77f  mov     [r12+368h], edx
0x14014e787  xor     edx, edx
0x14014e789  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e790  cmp     rcx, rbx
0x14014e793  jz      short loc_14014E7A7
0x14014e795  test    dword ptr [rcx+2Ch], 2000h
0x14014e79c  jz      short loc_14014E7A7
0x14014e79e  cmp     byte ptr [rcx+29h], 4
0x14014e7a2  mov     al, r13b
0x14014e7a5  jnb     short loc_14014E7A9
0x14014e7a7  mov     al, dl
0x14014e7a9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14014e7b0  mov     [rbp+4Fh+var_7F], al
0x14014e7b3  setnz   cl
0x14014e7b6  mov     [rbp+4Fh+var_80], cl
0x14014e7b9  test    al, al
0x14014e7bb  jnz     short loc_14014E7C1
0x14014e7bd  test    cl, cl
0x14014e7bf  jz      short loc_14014E82E
0x14014e7c1  mov     ebx, [r12+364h]
0x14014e7c9  mov     edi, [r12+360h]
0x14014e7d1  mov     rsi, [r12]
0x14014e7d5  call    cs:__imp_W32GetUserSessionState
0x14014e7dc  nop     dword ptr [rax+rax+00h]
0x14014e7e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14014e7e8  mov     r8b, [rbp+4Fh+var_80]
0x14014e7ec  mov     dl, [rbp+4Fh+var_7F]
0x14014e7ef  mov     r9, [rax+10E10h]
0x14014e7f6  lea     rax, WPP_88dc8779c13439e164336e7011252f30_Traceguids
0x14014e7fd  mov     rcx, [rcx+18h]
0x14014e801  mov     [rsp+0F0h+var_A0], ebx
0x14014e805  mov     dword ptr [rsp+0F0h+var_A8], edi
0x14014e809  mov     [rsp+0F0h+var_B0], rsi
0x14014e80e  mov     [rsp+0F0h+var_B8], rax
0x14014e813  mov     [rsp+0F0h+var_C0], 1Eh
0x14014e81a  mov     [rsp+0F0h+var_C8], 0Eh
0x14014e822  mov     byte ptr [rsp+0F0h+var_D0], 4
0x14014e827  call    WPP_RECORDER_AND_TRACE_SF_qDD
0x14014e82c  xor     edx, edx
  ... truncated ...
```
