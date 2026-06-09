# xxxInitProcessInfo

- ea: `0x14014e31c`
- end: `0x14014ed33`
- name: `xxxInitProcessInfo`
- size: `2583`
- prototype: `__int64 __usercall@<rax>(struct _W32PROCESS *@<rcx>, __int64)`
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
  AtomicExecutionCheck *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 CurrentThreadWin32Thread; // r14
  PACCESS_TOKEN v16; // rsi
  NTSTATUS InformationToken; // r15d
  __int64 v18; // r8
  bool v19; // di
  int v20; // ebx
  __int64 v21; // rax
  int v22; // r8d
  int v23; // edx
  int v24; // eax
  bool v25; // di
  int v26; // ebx
  __int64 v27; // rax
  int v28; // r8d
  int v29; // edx
  __int64 v30; // rcx
  __int64 v31; // rdx
  unsigned __int8 v32; // al
  __int64 v33; // rdx
  __int64 v34; // r8
  CTouchProcessor *v35; // rcx
  char v36; // al
  __int64 v37; // rax
  int v38; // r8d
  int v39; // edx
  int v40; // eax
  __int64 v41; // rcx
  unsigned __int8 ProcessProtection; // al
  CTouchProcessor *v43; // rcx
  char v44; // al
  int v45; // ebx
  int v46; // edi
  __int64 v47; // rsi
  __int64 UserSessionState; // rax
  int v49; // r8d
  int v50; // edx
  CTouchProcessor *v51; // rcx
  int v52; // ebx
  __int64 v53; // rdi
  __int64 v54; // rax
  int v55; // r8d
  int v56; // edx
  PACCESS_TOKEN v57; // rbx
  NTSTATUS v58; // eax
  int v59; // ebx
  unsigned int SpriteFillColorOverrideForCurrentProcess; // eax
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // r8
  int v65; // eax
  __int64 v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // rcx
  void (__fastcall *v72)(struct _W32PROCESS *); // rax
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  int Win32KFilterSet; // eax
  __int64 v80; // r8
  __int64 v81; // rcx
  unsigned __int64 v82; // rcx
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // rdx
  __int64 v86; // rcx
  __int64 v87; // r8
  int (*v88)(void); // rax
  void (__fastcall *v89)(struct _W32PROCESS *); // rax
  __int64 v90; // rdx
  __int64 v91; // r8
  char v92; // si
  int v93; // ebx
  __int64 v94; // rax
  int v95; // edx
  int v96; // r8d
  __int64 v97; // rdx
  __int64 v98; // rcx
  __int64 v99; // r8
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 v102; // r8
  __int64 v103; // r9
  int v104; // [rsp+20h] [rbp-81h]
  bool v105; // [rsp+70h] [rbp-31h] BYREF
  char v106; // [rsp+71h] [rbp-30h]
  PVOID v107; // [rsp+74h] [rbp-2Dh] BYREF
  int v108; // [rsp+7Ch] [rbp-25h] BYREF
  PACCESS_TOKEN Token; // [rsp+80h] [rbp-21h]
  PVOID P; // [rsp+88h] [rbp-19h] BYREF
  unsigned int v111; // [rsp+90h] [rbp-11h]
  __int64 v112; // [rsp+98h] [rbp-9h]
  __int64 v113; // [rsp+A0h] [rbp-1h]
  PVOID TokenInformation; // [rsp+A8h] [rbp+7h] BYREF
  int v115; // [rsp+B0h] [rbp+Fh]

  v113 = a5;
  v111 = a3;
  TokenInformation = 0;
  v115 = 0;
  v7 = 1;
  v8 = *((_BYTE *)a1 + 1200);
  Token = a2;
  HIDWORD(v107) = 0;
  P = 0;
  v108 = 0;
  if ( v8 == 1 )
    return 1073741851;
  if ( (Microsoft_Windows_Win32kEnableBits & 0x8000) != 0 )
    McTemplateK0_EtwWriteTransfer(a1, "T", &W32kControlGuid);
  result = xxxCheckProcessAndSessionState(a1);
  if ( result < 0 )
    return result;
  AtomicExecutionCheck::EnforceConsistency(v10);
  CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread(v12, v11, v13, v14);
  v112 = CurrentThreadWin32Thread;
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
  v16 = Token;
  InformationToken = SeQueryInformationToken(Token, TokenIntegrityLevel, &TokenInformation);
  if ( !(unsigned int)Feature_UIPIAlwaysOn2__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( UIPrivilegeIsolation::fEnforceUIPI )
    {
      if ( InformationToken < 0
        || (v40 = (int)TokenInformation, HIDWORD(TokenInformation)) && (_DWORD)TokenInformation != 4096 )
      {
LABEL_27:
        result = -1073741823;
LABEL_103:
        --*(_DWORD *)(CurrentThreadWin32Thread + 28);
        return result;
      }
      *((_DWORD *)a1 + 217) = HIDWORD(TokenInformation);
      v41 = *(_QWORD *)a1;
      *((_DWORD *)a1 + 216) = v40;
      if ( (unsigned int)PsIsProtectedProcess(v41, 0) )
      {
        ProcessProtection = PsGetProcessProtection(*(_QWORD *)a1, 0);
        *((_DWORD *)a1 + 218) = ((ProcessProtection >> 4)
                               | ((((ProcessProtection & 7) << 8) | (ProcessProtection >> 3) & 1) << 8)) << 8;
      }
    }
    v43 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) == 0
      || (v44 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v44 = 0;
    }
    v106 = v44;
    v105 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v44 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v45 = *((_DWORD *)a1 + 217);
      v46 = *((_DWORD *)a1 + 216);
      v47 = *(_QWORD *)a1;
      LOBYTE(v43) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      UserSessionState = W32GetUserSessionState(v43, 0, v18);
      LOBYTE(v49) = v105;
      LOBYTE(v50) = v106;
      WPP_RECORDER_AND_TRACE_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v50,
        v49,
        *(_QWORD *)(UserSessionState + 69136),
        4,
        14,
        30,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
        v47,
        v46,
        v45);
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
    v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = *((_DWORD *)a1 + 14);
      v21 = W32GetUserSessionState(WPP_GLOBAL_Control, 0, v18);
      LOBYTE(v22) = v19;
      LOBYTE(v23) = v7;
      WPP_RECORDER_AND_TRACE_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v23,
        v22,
        *(_QWORD *)(v21 + 69136),
        3,
        8,
        27,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
        InformationToken,
        v20);
    }
    goto LABEL_102;
  }
  v24 = (int)TokenInformation;
  if ( HIDWORD(TokenInformation) && (_DWORD)TokenInformation != 4096 )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v7 = 0;
    }
    v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = *((_DWORD *)a1 + 14);
      v27 = W32GetUserSessionState(WPP_GLOBAL_Control, 0, v18);
      LOBYTE(v28) = v25;
      LOBYTE(v29) = v7;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v29,
        v28,
        *(_QWORD *)(v27 + 69136),
        3,
        8,
        28,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
        v26);
    }
    goto LABEL_27;
  }
  *((_DWORD *)a1 + 217) = HIDWORD(TokenInformation);
  v30 = *(_QWORD *)a1;
  *((_DWORD *)a1 + 216) = v24;
  if ( (unsigned int)PsIsProtectedProcess(v30, 0) )
  {
    v32 = PsGetProcessProtection(*(_QWORD *)a1, v31);
    *((_DWORD *)a1 + 218) = ((v32 >> 4) | ((((v32 & 7) << 8) | (v32 >> 3) & 1) << 8)) << 8;
  }
  LODWORD(v107) = 0;
  if ( SeQueryInformationToken(v16, TokenDeviceClaimAttributes|TokenAuditPolicy, &v107) >= 0 && (_DWORD)v107 )
    *((_QWORD *)a1 + 101) |= 0x4000000000uLL;
  v35 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
    || (v36 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v36 = 0;
  }
  v106 = v36;
  v105 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v36 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v35) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    v37 = W32GetUserSessionState(v35, v33, v34);
    LOBYTE(v38) = v105;
    LOBYTE(v39) = v106;
    WPP_RECORDER_AND_TRACE_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v39, v38, *(_QWORD *)(v37 + 69136));
    CurrentThreadWin32Thread = v112;
  }
LABEL_54:
  InformationToken = SeQueryInformationToken(Token, TokenUIAccess, (PVOID *)((char *)&v107 + 4));
LABEL_55:
  if ( HIDWORD(v107) )
  {
    *((_DWORD *)a1 + 3) |= 0x80080000;
    *((_QWORD *)a1 + 101) |= 2uLL;
    v51 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || (LOBYTE(v51) = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      LOBYTE(v51) = 0;
    }
    v106 = (char)v51;
    v105 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v51 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v52 = *((_DWORD *)a1 + 14);
      v53 = *(_QWORD *)a1;
      v54 = W32GetUserSessionState(v51, 0, v18);
      LOBYTE(v55) = v105;
      LOBYTE(v56) = v106;
      WPP_RECORDER_AND_TRACE_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v56,
        v55,
        *(_QWORD *)(v54 + 69136),
        v104,
        8,
        31,
        (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
        v53,
        v52);
    }
  }
  v57 = Token;
  SetProcessType(a1, Token, v111, v113);
  SetProcessInitialCapabilities(a1);
  if ( InformationToken < 0 )
  {
    v59 = 0;
  }
  else
  {
    v58 = SeQueryInformationToken(v57, TokenAppContainerSid, &P);
    v59 = 0;
    InformationToken = v58;
    if ( v58 >= 0 )
    {
      if ( *(_QWORD *)P && (int)RtlGetAppContainerSidType(*(_QWORD *)P, &v108) >= 0 )
        *((_DWORD *)a1 + 219) = v108;
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
    v61 = *(_QWORD *)a1;
    *((_DWORD *)a1 + 269) = SpriteFillColorOverrideForCurrentProcess;
    if ( PsGetProcessWow64Process(v61) )
      *((_DWORD *)a1 + 3) |= 0x80u;
    *((_QWORD *)a1 + 111) = -1;
    *((_QWORD *)a1 + 112) = -1;
    v65 = *((_DWORD *)a1 + 3);
    if ( (v65 & 0x20) == 0 )
    {
      *((_DWORD *)a1 + 3) = v65 | 0x22;
      v66 = W32GetUserSessionState(v63, v62, v64);
      *(_DWORD *)(v66 + 66784) |= 0x8000000u;
      if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
      {
        CWinEventNoopDeferral::CWinEventNoopDeferral((CWinEventNoopDeferral *)&v105);
        zzzCalcStartCursorHide(0, 0);
        CWinEventNoopDeferral::~CWinEventNoopDeferral((CWinEventNoopDeferral *)&v105);
      }
    }
    v67 = *(_QWORD *)(W32GetUserSessionState(v63, v62, v64) + 36200);
    *((_QWORD *)a1 + 46) = v67;
    *(_QWORD *)(W32GetUserSessionState(v67, v68, v69) + 36200) = a1;
    v72 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v71, v70) + 48) + 4776LL);
    if ( v72 )
      v72(a1);
    GetProcessLuid(0, (PLUID)((char *)a1 + 764));
    v76 = W32GetUserSessionState(v74, v73, v75);
    LOBYTE(v77) = 1;
    *((_DWORD *)a1 + 98) = *(_DWORD *)(v76 + 41156);
    *((_DWORD *)a1 + 186) = 0;
    CitProcessCallout(a1, v77);
    *((_QWORD *)a1 + 101) &= 0xFFFFFFFFFFBE7FFFuLL;
    v78 = *((_QWORD *)a1 + 101);
    *((_DWORD *)a1 + 67) = 24592;
    *((_WORD *)a1 + 136) = 96;
    if ( (v78 & 0x30) == 0x20 )
      *((_QWORD *)a1 + 101) = v78 | 0x100000;
    Win32KFilterSet = PsGetWin32KFilterSet();
    v81 = 0;
    if ( Win32KFilterSet == 5 )
      v81 = 0x1000000;
    v82 = *((_QWORD *)a1 + 101) & 0xFFFFFFFFF6FFFFFFuLL | v81 & 0xFFFFFFFFF7FFFFFFuLL;
    *((_QWORD *)a1 + 101) = v82;
    v84 = *(_QWORD *)(W32GetUserSessionState(v82, 0x1000000, v80) + 19704);
    if ( *(_WORD *)(v84 + 6998) )
    {
      v86 = *(_QWORD *)(W32GetWin32kBaseApiSetTable(v84, v83) + 48);
      v88 = *(int (**)(void))(v86 + 832);
      if ( v88 && v88() >= 0 )
      {
        v89 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable(v86, v85) + 48)
                                                          + 840LL);
        if ( v89 )
          v89(a1);
      }
      else
      {
        *((_WORD *)a1 + 136) = *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v86, v85, v87) + 19704) + 6998LL);
      }
    }
    Feature_WebThreatDefenseToggle__private_IsEnabledPreCheck();
    if ( *(_DWORD *)(W32GetUserSessionState(v98, v97, v99) + 42376) )
    {
      if ( !W32GetInputMonitorSessionState() )
        MicrosoftTelemetryAssertTriggeredNoArgsKM(v101, v100, v102, v103);
      v59 = 1;
    }
    *((_DWORD *)a1 + 69) = (4 * v59) | *((_DWORD *)a1 + 69) & 0xFFFFFFFB;
    *((_QWORD *)a1 + 136) = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                           * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
LABEL_102:
    result = InformationToken;
    goto LABEL_103;
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
    || (v92 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
  {
    v92 = 0;
  }
  v105 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v92 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v93 = *((_DWORD *)a1 + 14);
    v94 = W32GetUserSessionState(WPP_GLOBAL_Control, v90, v91);
    LOBYTE(v95) = v92;
    LOBYTE(v96) = v105;
    WPP_RECORDER_AND_TRACE_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v95,
      v96,
      *(_QWORD *)(v94 + 69136),
      3,
      8,
      32,
      (__int64)WPP_88dc8779c13439e164336e7011252f30_Traceguids,
      InformationToken,
      v93);
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
0x14014e4c0  mov     [rsp+0F0h+var_A8], ebx
0x14014e4c4  mov     dl, r13b
0x14014e4c7  mov     dword ptr [rsp+0F0h+var_B0], r15d
0x14014e4cc  mov     r9, [rax+10E10h]
0x14014e4d3  lea     rax, WPP_88dc8779c13439e164336e7011252f30_Traceguids
0x14014e4da  mov     rcx, [rcx+18h]
0x14014e4de  mov     [rsp+0F0h+var_B8], rax
0x14014e4e3  mov     [rsp+0F0h+var_C0], 1Bh
0x14014e4ea  mov     [rsp+0F0h+var_C8], 8
0x14014e4f2  mov     [rsp+0F0h+var_D0], 3
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
0x14014e5a1  mov     [rsp+0F0h+var_D0], 3
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
0x14014e6e5  mov     [rsp+0F0h+var_A8], esi
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
0x14014e805  mov     [rsp+0F0h+var_A8], edi
0x14014e809  mov     [rsp+0F0h+var_B0], rsi
0x14014e80e  mov     [rsp+0F0h+var_B8], rax
0x14014e813  mov     [rsp+0F0h+var_C0], 1Eh
0x14014e81a  mov     [rsp+0F0h+var_C8], 0Eh
0x14014e822  mov     [rsp+0F0h+var_D0], 4
0x14014e827  call    WPP_RECORDER_AND_TRACE_SF_qDD
0x14014e82c  xor     edx, edx
  ... truncated ...
```
