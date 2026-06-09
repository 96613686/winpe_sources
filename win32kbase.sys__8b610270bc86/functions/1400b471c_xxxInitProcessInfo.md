# xxxInitProcessInfo

- ea: `0x1400b471c`
- end: `0x1400b4f92`
- name: `xxxInitProcessInfo`
- size: `2166`
- prototype: `__int64 __usercall@<rax>(struct _W32PROCESS *@<rcx>, PACCESS_TOKEN Token@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400b30d0`
- `0x1400b375c`

## callees

- `0x14005c210`
- `0x14005eb4c`
- `0x14008ba8c`
- `0x1400983d0`
- `0x140099ff8`
- `0x1400a16d0`
- `0x1400b471c`
- `0x1400cb450`
- `0x1400cb9dc`
- `0x14010f2b0`
- `0x14011d320`
- `0x1401456b4`
- `0x14014570c`
- `0x140148380`
- `0x14014cf44`
- `0x14014d388`
- `0x14018481c`
- `0x140193cac`
- `0x140193e28`
- `0x1401c6d6c`
- `0x1401c7338`
- `0x140238b10`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400b4c2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b4c2f`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4836`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b49e4`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4adc`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4bd8`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4836`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b49e4`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4adc`
- `ntoskrnl!SeQueryInformationToken` at `0x1400b4bd8`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400b498c`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400b498c`
- `ntoskrnl!PsGetProcessProtection` at `0x1400b49a0`
- `ntoskrnl!PsGetProcessProtection` at `0x1400b49a0`
- `ntoskrnl!RtlGetAppContainerSidType` at `0x1400b4c04`
- `ntoskrnl!RtlGetAppContainerSidType` at `0x1400b4c04`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400b4c50`
- `ntoskrnl!PsGetProcessWow64Process` at `0x1400b4c50`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400b4d9a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x1400b4d9a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b47bd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400b47bd`
- `WIN32K!W32GetInputMonitorSessionState` at `0x1400b4e7b`
- `WIN32K!W32GetInputMonitorSessionState` at `0x1400b4e7b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b4cf9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b4df0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b4e15`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b4cf9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b4df0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1400b4e15`
- `WIN32K!W32GetUserSessionState` at `0x1400b4891`
- `WIN32K!W32GetUserSessionState` at `0x1400b4921`
- `WIN32K!W32GetUserSessionState` at `0x1400b4a73`
- `WIN32K!W32GetUserSessionState` at `0x1400b4b4f`
- `WIN32K!W32GetUserSessionState` at `0x1400b4c93`
- `WIN32K!W32GetUserSessionState` at `0x1400b4ccb`
- `WIN32K!W32GetUserSessionState` at `0x1400b4ce6`
- `WIN32K!W32GetUserSessionState` at `0x1400b4d2c`
- `WIN32K!W32GetUserSessionState` at `0x1400b4dd3`
- `WIN32K!W32GetUserSessionState` at `0x1400b4e3b`
- `WIN32K!W32GetUserSessionState` at `0x1400b4e66`
- `WIN32K!W32GetUserSessionState` at `0x1400b4f18`
- `WIN32K!W32GetUserSessionState` at `0x1400b4891`
- `WIN32K!W32GetUserSessionState` at `0x1400b4921`
- `WIN32K!W32GetUserSessionState` at `0x1400b4a73`
- `WIN32K!W32GetUserSessionState` at `0x1400b4b4f`
- `WIN32K!W32GetUserSessionState` at `0x1400b4c93`
- `WIN32K!W32GetUserSessionState` at `0x1400b4ccb`
- `WIN32K!W32GetUserSessionState` at `0x1400b4ce6`
- `WIN32K!W32GetUserSessionState` at `0x1400b4d2c`
- `WIN32K!W32GetUserSessionState` at `0x1400b4dd3`
- `WIN32K!W32GetUserSessionState` at `0x1400b4e3b`
- `WIN32K!W32GetUserSessionState` at `0x1400b4e66`
- `WIN32K!W32GetUserSessionState` at `0x1400b4f18`

## pseudocode

```c
int __fastcall xxxInitProcessInfo(
        struct _W32PROCESS *a1,
        PACCESS_TOKEN Token,
        unsigned int a3,
        unsigned int a4,
        __int64 a5)
{
  PACCESS_TOKEN v6; // r15
  char v7; // r13
  char v8; // al
  int result; // eax
  AtomicExecutionCheck *v11; // rcx
  __int64 CurrentThreadWin32Thread; // rsi
  NTSTATUS InformationToken; // r14d
  CTouchProcessor **v14; // rcx
  bool v15; // di
  int v16; // ebx
  __int64 UserSessionState; // rax
  int v18; // edx
  int v19; // r8d
  int v20; // eax
  bool v21; // di
  int v22; // ebx
  __int64 v23; // rax
  int v24; // r8d
  int v25; // edx
  __int64 v26; // rcx
  unsigned __int8 ProcessProtection; // al
  CTouchProcessor *v28; // rcx
  char v29; // al
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  CTouchProcessor *v33; // rcx
  bool v34; // al
  __int64 v35; // rax
  int v36; // r8d
  int v37; // edx
  unsigned int SpriteFillColorOverrideForCurrentProcess; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rax
  __int64 v43; // rcx
  void (__fastcall *v44)(struct _W32PROCESS *); // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  int Win32KFilterSet; // eax
  __int64 v50; // rcx
  unsigned __int64 v51; // rcx
  __int64 v52; // rcx
  int (*v53)(void); // rax
  void (__fastcall *v54)(struct _W32PROCESS *); // rax
  int v55; // ebx
  __int64 v56; // rcx
  __int64 v57; // rdx
  __int64 v58; // rcx
  int v59; // ebx
  __int16 v60; // [rsp+30h] [rbp-71h]
  char v61; // [rsp+40h] [rbp-61h]
  char v62; // [rsp+48h] [rbp-59h]
  bool v63; // [rsp+70h] [rbp-31h] BYREF
  char v64; // [rsp+71h] [rbp-30h]
  PVOID v65; // [rsp+74h] [rbp-2Dh] BYREF
  int v66; // [rsp+7Ch] [rbp-25h] BYREF
  PVOID P; // [rsp+80h] [rbp-21h] BYREF
  unsigned int v68; // [rsp+88h] [rbp-19h]
  PACCESS_TOKEN Tokena; // [rsp+90h] [rbp-11h]
  __int64 v70; // [rsp+98h] [rbp-9h]
  __int64 v71; // [rsp+A0h] [rbp-1h]
  PVOID TokenInformation; // [rsp+A8h] [rbp+7h] BYREF
  int v73; // [rsp+B0h] [rbp+Fh]

  v71 = a5;
  v68 = a3;
  TokenInformation = 0;
  v6 = Token;
  v73 = 0;
  v7 = 1;
  v8 = *((_BYTE *)a1 + 1200);
  Tokena = Token;
  HIDWORD(v65) = 0;
  P = 0;
  v66 = 0;
  if ( v8 == 1 )
    return 1073741851;
  if ( (Microsoft_Windows_Win32kEnableBits & 0x8000) != 0 )
    McTemplateK0_EtwWriteTransfer(a1, InitiateGuiProcessExecution, &W32kControlGuid);
  result = xxxCheckProcessAndSessionState(a1);
  if ( result >= 0 )
  {
    AtomicExecutionCheck::EnforceConsistency(v11);
    CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread();
    v70 = CurrentThreadWin32Thread;
    ++*(_DWORD *)(CurrentThreadWin32Thread + 28);
    *((_BYTE *)a1 + 1200) = 1;
    *((_QWORD *)a1 + 38) = 0;
    *((_QWORD *)a1 + 39) = 0;
    *((_DWORD *)a1 + 80) = 0;
    if ( (unsigned int)Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline() )
    {
      result = InitProcessUipiInfo(a1, v6, a4);
      if ( result < 0 )
        goto LABEL_85;
    }
    else
    {
      HIDWORD(TokenInformation) = a4;
      InformationToken = SeQueryInformationToken(v6, TokenIntegrityLevel, &TokenInformation);
      if ( InformationToken < 0 )
      {
        v14 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (v14 = (CTouchProcessor **)*((unsigned int *)WPP_GLOBAL_Control + 11), (char)v14 >= 0)
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
        {
          v7 = 0;
        }
        v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v7 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_84;
        v16 = *((_DWORD *)a1 + 14);
        UserSessionState = W32GetUserSessionState(v14);
        v62 = v16;
        v61 = InformationToken;
        LOBYTE(v19) = v15;
        v60 = 28;
        goto LABEL_83;
      }
      v20 = (int)TokenInformation;
      if ( HIDWORD(TokenInformation) && (_DWORD)TokenInformation != 4096 )
      {
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
        {
          v7 = 0;
        }
        v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v22 = *((_DWORD *)a1 + 14);
          v23 = W32GetUserSessionState(&WPP_GLOBAL_Control);
          LOBYTE(v24) = v21;
          LOBYTE(v25) = v7;
          WPP_RECORDER_AND_TRACE_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v25,
            v24,
            *(_QWORD *)(v23 + 69136),
            3,
            8,
            29,
            (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
            v22);
        }
        result = -1073741823;
        goto LABEL_85;
      }
      *((_DWORD *)a1 + 217) = HIDWORD(TokenInformation);
      v26 = *(_QWORD *)a1;
      *((_DWORD *)a1 + 216) = v20;
      if ( (unsigned int)PsIsProtectedProcess(v26) )
      {
        ProcessProtection = PsGetProcessProtection(*(_QWORD *)a1);
        *((_DWORD *)a1 + 218) = ((ProcessProtection >> 4)
                               | ((((ProcessProtection & 7) << 8) | (ProcessProtection >> 3) & 1) << 8)) << 8;
      }
      LODWORD(v65) = 0;
      if ( SeQueryInformationToken(v6, TokenDeviceClaimAttributes|TokenAuditPolicy, &v65) >= 0 && (_DWORD)v65 )
        *((_QWORD *)a1 + 101) |= 0x4000000000uLL;
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
        || (v29 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
      {
        v29 = 0;
      }
      v64 = v29;
      v63 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v29 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v30 = W32GetUserSessionState(v28);
        LOBYTE(v31) = v63;
        LOBYTE(v32) = v64;
        WPP_RECORDER_AND_TRACE_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v32, v31, *(_QWORD *)(v30 + 69136));
        CurrentThreadWin32Thread = v70;
        v6 = Tokena;
      }
    }
    InformationToken = SeQueryInformationToken(v6, TokenUIAccess, (PVOID *)((char *)&v65 + 4));
    if ( HIDWORD(v65) )
    {
      *((_DWORD *)a1 + 3) |= 0x80080000;
      *((_QWORD *)a1 + 101) |= 2uLL;
      v33 = WPP_GLOBAL_Control;
      v34 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v64 = v34;
      v63 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v34 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v33) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v35 = W32GetUserSessionState(v33);
        LOBYTE(v36) = v63;
        LOBYTE(v37) = v64;
        WPP_RECORDER_AND_TRACE_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 3), v37, v36, *(_QWORD *)(v35 + 69136));
      }
    }
    SetProcessType(a1, Tokena, v68, v71);
    SetProcessInitialCapabilities(a1);
    if ( InformationToken >= 0 )
    {
      InformationToken = SeQueryInformationToken(Tokena, TokenAppContainerSid, &P);
      if ( InformationToken >= 0 )
      {
        if ( *(_QWORD *)P && (int)RtlGetAppContainerSidType(*(_QWORD *)P, &v66) >= 0 )
          *((_DWORD *)a1 + 219) = v66;
        else
          *((_DWORD *)a1 + 219) = 0;
        ExFreePoolWithTag(P, 0);
        P = 0;
        SpriteFillColorOverrideForCurrentProcess = GetSpriteFillColorOverrideForCurrentProcess();
        v39 = *(_QWORD *)a1;
        *((_DWORD *)a1 + 269) = SpriteFillColorOverrideForCurrentProcess;
        if ( PsGetProcessWow64Process(v39) )
          *((_DWORD *)a1 + 3) |= 0x80u;
        *((_QWORD *)a1 + 111) = -1;
        *((_QWORD *)a1 + 112) = -1;
        v41 = *((_DWORD *)a1 + 3);
        if ( (v41 & 0x20) == 0 )
        {
          *((_DWORD *)a1 + 3) = v41 | 0x22;
          v42 = W32GetUserSessionState(v40);
          *(_DWORD *)(v42 + 66784) |= 0x8000000u;
          if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
          {
            CWinEventNoopDeferral::CWinEventNoopDeferral((CWinEventNoopDeferral *)&v63);
            zzzCalcStartCursorHide(0, 0);
            CWinEventNoopDeferral::~CWinEventNoopDeferral((CWinEventNoopDeferral *)&v63);
          }
        }
        v43 = *(_QWORD *)(W32GetUserSessionState(v40) + 36200);
        *((_QWORD *)a1 + 46) = v43;
        *(_QWORD *)(W32GetUserSessionState(v43) + 36200) = a1;
        v44 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 4776LL);
        if ( v44 )
          v44(a1);
        GetProcessLuid(0, (PLUID)((char *)a1 + 764));
        v46 = W32GetUserSessionState(v45);
        LOBYTE(v47) = 1;
        *((_DWORD *)a1 + 98) = *(_DWORD *)(v46 + 41156);
        *((_DWORD *)a1 + 186) = 0;
        CitProcessCallout(a1, v47);
        *((_QWORD *)a1 + 101) &= 0xFFFFFFFFFFBE7FFFuLL;
        v48 = *((_QWORD *)a1 + 101);
        *((_DWORD *)a1 + 67) = 24592;
        *((_WORD *)a1 + 136) = 96;
        if ( (v48 & 0x30) == 0x20 )
          *((_QWORD *)a1 + 101) = v48 | 0x100000;
        Win32KFilterSet = PsGetWin32KFilterSet();
        v50 = 0;
        if ( Win32KFilterSet == 5 )
          v50 = 0x1000000;
        v51 = *((_QWORD *)a1 + 101) & 0xFFFFFFFFF6FFFFFFuLL | v50 & 0xFFFFFFFFF7FFFFFFuLL;
        *((_QWORD *)a1 + 101) = v51;
        if ( *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v51) + 19704) + 6998LL) )
        {
          v52 = *(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48);
          v53 = *(int (**)(void))(v52 + 832);
          if ( v53 && v53() >= 0 )
          {
            v54 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 840LL);
            if ( v54 )
              v54(a1);
          }
          else
          {
            *((_WORD *)a1 + 136) = *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v52) + 19704) + 6998LL);
          }
        }
        Feature_WebThreatDefenseToggle__private_IsEnabledPreCheck();
        v55 = 0;
        if ( *(_DWORD *)(W32GetUserSessionState(v56) + 42376) )
        {
          if ( !W32GetInputMonitorSessionState() )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v58, v57);
          v55 = 1;
        }
        *((_DWORD *)a1 + 69) = (4 * v55) | *((_DWORD *)a1 + 69) & 0xFFFFFFFB;
        *((_QWORD *)a1 + 136) = (((unsigned __int64)MEMORY[0xFFFFF78000000004] << 32)
                               * (unsigned __int128)(unsigned __int64)(MEMORY[0xFFFFF78000000320] << 8)) >> 64;
        goto LABEL_84;
      }
    }
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
    {
      v7 = 0;
    }
    v63 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v7 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_84;
    v59 = *((_DWORD *)a1 + 14);
    UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v19) = v63;
    v62 = v59;
    v61 = InformationToken;
    v60 = 32;
LABEL_83:
    LOBYTE(v18) = v7;
    WPP_RECORDER_AND_TRACE_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v18,
      v19,
      *(_QWORD *)(UserSessionState + 69136),
      3,
      8,
      v60,
      (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
      v61,
      v62);
LABEL_84:
    result = InformationToken;
LABEL_85:
    --*(_DWORD *)(CurrentThreadWin32Thread + 28);
  }
  return result;
}

```

## disassembly

```asm
0x1400b471c  mov     [rsp-8+arg_10], rbx
0x1400b4721  push    rbp
0x1400b4722  push    rsi
0x1400b4723  push    rdi
0x1400b4724  push    r12
0x1400b4726  push    r13
0x1400b4728  push    r14
0x1400b472a  push    r15
0x1400b472c  lea     rbp, [rsp-1Fh]
0x1400b4731  sub     rsp, 0C0h
0x1400b4738  mov     rax, cs:__security_cookie
0x1400b473f  xor     rax, rsp
0x1400b4742  mov     [rbp+4Fh+var_38], rax
0x1400b4746  mov     rax, [rbp+4Fh+arg_20]
0x1400b474a  xor     ebx, ebx
0x1400b474c  mov     [rbp+4Fh+var_50], rax
0x1400b4750  mov     r14d, r9d
0x1400b4753  xor     eax, eax
0x1400b4755  mov     [rbp+4Fh+var_68], r8d
0x1400b4759  mov     [rbp+4Fh+TokenInformation], rax
0x1400b475d  mov     r15, rdx
0x1400b4760  mov     [rbp+4Fh+var_40], eax
0x1400b4763  lea     r13d, [rbx+1]
0x1400b4767  mov     al, [rcx+4B0h]
0x1400b476d  mov     r12, rcx
0x1400b4770  mov     [rbp+4Fh+Token], rdx
0x1400b4774  mov     dword ptr [rbp+4Fh+var_7C+4], ebx
0x1400b4777  mov     [rbp+4Fh+P], rbx
0x1400b477b  mov     [rbp+4Fh+var_74], ebx
0x1400b477e  cmp     al, r13b
0x1400b4781  jnz     short loc_1400B478D
0x1400b4783  mov     eax, 4000001Bh
0x1400b4788  jmp     loc_1400B4F6A
0x1400b478d  cmp     byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, bl
0x1400b4793  jge     short loc_1400B47A8
0x1400b4795  lea     r8, W32kControlGuid
0x1400b479c  lea     rdx, InitiateGuiProcessExecution
0x1400b47a3  call    McTemplateK0_EtwWriteTransfer
0x1400b47a8  mov     rcx, r12; struct _W32PROCESS *
0x1400b47ab  call    ?xxxCheckProcessAndSessionState@@YAJPEAU_W32PROCESS@@@Z; xxxCheckProcessAndSessionState(_W32PROCESS *)
0x1400b47b0  test    eax, eax
0x1400b47b2  js      loc_1400B4F6A
0x1400b47b8  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x1400b47bd  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x1400b47c4  nop     dword ptr [rax+rax+00h]
0x1400b47c9  mov     rsi, rax
0x1400b47cc  mov     [rbp+4Fh+var_58], rax
0x1400b47d0  add     [rax+1Ch], r13d
0x1400b47d4  mov     [r12+4B0h], r13b
0x1400b47dc  mov     [r12+130h], rbx
0x1400b47e4  mov     [r12+138h], rbx
0x1400b47ec  mov     [r12+140h], ebx
0x1400b47f4  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x1400b47f9  lea     rbx, WPP_GLOBAL_Control
0x1400b4800  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400b4807  test    eax, eax
0x1400b4809  jz      short loc_1400B4826
0x1400b480b  mov     r8d, r14d; unsigned int
0x1400b480e  mov     rdx, r15; void *
0x1400b4811  mov     rcx, r12; struct tagPROCESSINFO *
0x1400b4814  call    ?InitProcessUipiInfo@@YAJPEAUtagPROCESSINFO@@PEAXK@Z; InitProcessUipiInfo(tagPROCESSINFO *,void *,ulong)
0x1400b4819  test    eax, eax
0x1400b481b  jns     loc_1400B4AD0
0x1400b4821  jmp     loc_1400B4F67
0x1400b4826  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x1400b482a  mov     dword ptr [rbp+4Fh+TokenInformation+4], r14d
0x1400b482e  mov     edx, 19h; TokenInformationClass
0x1400b4833  mov     rcx, r15; Token
0x1400b4836  call    cs:__imp_SeQueryInformationToken
0x1400b483d  nop     dword ptr [rax+rax+00h]
0x1400b4842  mov     r14d, eax
0x1400b4845  test    eax, eax
0x1400b4847  jns     short loc_1400B48C1
0x1400b4849  mov     rdx, cs:WPP_GLOBAL_Control
0x1400b4850  lea     rcx, WPP_GLOBAL_Control
0x1400b4857  cmp     rdx, rcx
0x1400b485a  jz      short loc_1400B4869
0x1400b485c  mov     ecx, [rdx+2Ch]
0x1400b485f  test    cl, cl
0x1400b4861  jns     short loc_1400B4869
0x1400b4863  cmp     byte ptr [rdx+29h], 3
0x1400b4867  jnb     short loc_1400B486C
0x1400b4869  xor     r13b, r13b
0x1400b486c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b4873  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b487a  setnz   dil
0x1400b487e  test    r13b, r13b
0x1400b4881  jnz     short loc_1400B488C
0x1400b4883  test    dil, dil
0x1400b4886  jz      loc_1400B4F64
0x1400b488c  mov     ebx, [r12+38h]
0x1400b4891  call    cs:__imp_W32GetUserSessionState
0x1400b4898  nop     dword ptr [rax+rax+00h]
0x1400b489d  mov     dword ptr [rsp+0F0h+var_A8], ebx
0x1400b48a1  lea     r15, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400b48a8  mov     dword ptr [rsp+0F0h+var_B0], r14d
0x1400b48ad  mov     r8b, dil
0x1400b48b0  mov     [rsp+0F0h+var_B8], r15
0x1400b48b5  mov     [rsp+0F0h+var_C0], 1Ch
0x1400b48bc  jmp     loc_1400B4F3D
0x1400b48c1  mov     ecx, dword ptr [rbp+4Fh+TokenInformation+4]
0x1400b48c4  xor     r14d, r14d
0x1400b48c7  mov     eax, dword ptr [rbp+4Fh+TokenInformation]
0x1400b48ca  test    ecx, ecx
0x1400b48cc  jz      loc_1400B4978
0x1400b48d2  cmp     eax, 1000h
0x1400b48d7  jz      loc_1400B4978
0x1400b48dd  mov     rdx, cs:WPP_GLOBAL_Control
0x1400b48e4  lea     rcx, WPP_GLOBAL_Control
0x1400b48eb  cmp     rdx, rcx
0x1400b48ee  jz      short loc_1400B48FD
0x1400b48f0  mov     eax, [rdx+2Ch]
0x1400b48f3  test    al, al
0x1400b48f5  jns     short loc_1400B48FD
0x1400b48f7  cmp     byte ptr [rdx+29h], 3
0x1400b48fb  jnb     short loc_1400B4900
0x1400b48fd  mov     r13b, r14b
0x1400b4900  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b4907  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b490e  setnz   dil
0x1400b4912  test    r13b, r13b
0x1400b4915  jnz     short loc_1400B491C
0x1400b4917  test    dil, dil
0x1400b491a  jz      short loc_1400B496E
0x1400b491c  mov     ebx, [r12+38h]
0x1400b4921  call    cs:__imp_W32GetUserSessionState
0x1400b4928  nop     dword ptr [rax+rax+00h]
0x1400b492d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4934  lea     r15, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400b493b  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x1400b493f  mov     r8b, dil
0x1400b4942  mov     [rsp+0F0h+var_B8], r15
0x1400b4947  mov     dl, r13b
0x1400b494a  mov     r9, [rax+10E10h]
0x1400b4951  mov     rcx, [rcx+18h]
0x1400b4955  mov     [rsp+0F0h+var_C0], 1Dh
0x1400b495c  mov     [rsp+0F0h+var_C8], 8
0x1400b4964  mov     [rsp+0F0h+var_D0], 3
0x1400b4969  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400b496e  mov     eax, 0C0000001h
0x1400b4973  jmp     loc_1400B4F67
0x1400b4978  mov     [r12+364h], ecx
0x1400b4980  mov     rcx, [r12]
0x1400b4984  mov     [r12+360h], eax
0x1400b498c  call    cs:__imp_PsIsProtectedProcess
0x1400b4993  nop     dword ptr [rax+rax+00h]
0x1400b4998  test    eax, eax
0x1400b499a  jz      short loc_1400B49D4
0x1400b499c  mov     rcx, [r12]
0x1400b49a0  call    cs:__imp_PsGetProcessProtection
0x1400b49a7  nop     dword ptr [rax+rax+00h]
0x1400b49ac  movzx   ecx, al
0x1400b49af  mov     edx, ecx
0x1400b49b1  mov     eax, ecx
0x1400b49b3  shr     edx, 3
0x1400b49b6  and     eax, 7
0x1400b49b9  and     edx, r13d
0x1400b49bc  shl     eax, 8
0x1400b49bf  or      edx, eax
0x1400b49c1  shr     ecx, 4
0x1400b49c4  shl     edx, 8
0x1400b49c7  or      edx, ecx
0x1400b49c9  shl     edx, 8
0x1400b49cc  mov     [r12+368h], edx
0x1400b49d4  lea     r8, [rbp+4Fh+var_7C]; TokenInformation
0x1400b49d8  mov     dword ptr [rbp+4Fh+var_7C], r14d
0x1400b49dc  mov     edx, 32h ; '2'; TokenInformationClass
0x1400b49e1  mov     rcx, r15; Token
0x1400b49e4  call    cs:__imp_SeQueryInformationToken
0x1400b49eb  nop     dword ptr [rax+rax+00h]
0x1400b49f0  test    eax, eax
0x1400b49f2  js      short loc_1400B4A0C
0x1400b49f4  cmp     dword ptr [rbp+4Fh+var_7C], r14d
0x1400b49f8  jz      short loc_1400B4A0C
0x1400b49fa  mov     rax, 4000000000h
0x1400b4a04  or      [r12+328h], rax
0x1400b4a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4a13  cmp     rcx, rbx
0x1400b4a16  jz      short loc_1400B4A28
0x1400b4a18  mov     eax, [rcx+2Ch]
0x1400b4a1b  test    al, al
0x1400b4a1d  jns     short loc_1400B4A28
0x1400b4a1f  cmp     byte ptr [rcx+29h], 4
0x1400b4a23  mov     al, r13b
0x1400b4a26  jnb     short loc_1400B4A2B
0x1400b4a28  mov     al, r14b
0x1400b4a2b  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400b4a32  mov     [rbp+4Fh+var_7F], al
0x1400b4a35  setnz   cl
0x1400b4a38  mov     [rbp+4Fh+var_80], cl
0x1400b4a3b  test    al, al
0x1400b4a3d  jnz     short loc_1400B4A47
0x1400b4a3f  test    cl, cl
0x1400b4a41  jz      loc_1400B4AD0
0x1400b4a47  mov     r15, [r12+328h]
0x1400b4a4f  mov     ebx, [r12+368h]
0x1400b4a57  mov     edi, [r12+364h]
0x1400b4a5f  mov     esi, [r12+360h]
0x1400b4a67  mov     r14d, [r12+38h]
0x1400b4a6c  shr     r15, 26h
0x1400b4a70  and     r15d, r13d
0x1400b4a73  call    cs:__imp_W32GetUserSessionState
0x1400b4a7a  nop     dword ptr [rax+rax+00h]
0x1400b4a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4a86  mov     r8b, [rbp+4Fh+var_80]
0x1400b4a8a  mov     dl, [rbp+4Fh+var_7F]
0x1400b4a8d  mov     r9, [rax+10E10h]
0x1400b4a94  mov     rcx, [rcx+18h]
0x1400b4a98  mov     [rsp+0F0h+var_90], r15d
0x1400b4a9d  mov     [rsp+0F0h+var_98], ebx
0x1400b4aa1  mov     [rsp+0F0h+var_A0], edi
0x1400b4aa5  mov     dword ptr [rsp+0F0h+var_A8], esi
0x1400b4aa9  mov     dword ptr [rsp+0F0h+var_B0], r14d
0x1400b4aae  mov     [rsp+0F0h+var_C0], 1Eh
0x1400b4ab5  call    WPP_RECORDER_AND_TRACE_SF_DDDDD
0x1400b4aba  mov     rsi, [rbp+4Fh+var_58]
0x1400b4abe  lea     rbx, WPP_GLOBAL_Control
0x1400b4ac5  mov     r15, [rbp+4Fh+Token]
0x1400b4ac9  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400b4ad0  lea     r8, [rbp+4Fh+var_7C+4]; TokenInformation
0x1400b4ad4  mov     edx, 1Ah; TokenInformationClass
0x1400b4ad9  mov     rcx, r15; Token
0x1400b4adc  call    cs:__imp_SeQueryInformationToken
0x1400b4ae3  nop     dword ptr [rax+rax+00h]
0x1400b4ae8  cmp     dword ptr [rbp+4Fh+var_7C+4], 0
0x1400b4aec  lea     r15, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x1400b4af3  mov     r14d, eax
0x1400b4af6  jz      loc_1400B4BA4
0x1400b4afc  or      dword ptr [r12+0Ch], 80080000h
0x1400b4b05  or      qword ptr [r12+328h], 2
0x1400b4b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4b15  cmp     rcx, rbx
0x1400b4b18  jz      short loc_1400B4B2C
0x1400b4b1a  mov     eax, [rcx+2Ch]
0x1400b4b1d  test    al, al
0x1400b4b1f  jns     short loc_1400B4B2C
0x1400b4b21  cmp     byte ptr [rcx+29h], 4
0x1400b4b25  jb      short loc_1400B4B2C
0x1400b4b27  mov     al, r13b
0x1400b4b2a  jmp     short loc_1400B4B2E
0x1400b4b2c  xor     al, al
0x1400b4b2e  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400b4b35  mov     [rbp+4Fh+var_7F], al
0x1400b4b38  setnz   cl
0x1400b4b3b  mov     [rbp+4Fh+var_80], cl
0x1400b4b3e  test    al, al
0x1400b4b40  jnz     short loc_1400B4B46
0x1400b4b42  test    cl, cl
0x1400b4b44  jz      short loc_1400B4BA4
0x1400b4b46  mov     ebx, [r12+38h]
0x1400b4b4b  mov     rdi, [r12]
0x1400b4b4f  call    cs:__imp_W32GetUserSessionState
0x1400b4b56  nop     dword ptr [rax+rax+00h]
0x1400b4b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b4b62  mov     r8b, [rbp+4Fh+var_80]
0x1400b4b66  mov     dl, [rbp+4Fh+var_7F]
0x1400b4b69  mov     r9, [rax+10E10h]
0x1400b4b70  mov     rcx, [rcx+18h]
0x1400b4b74  mov     dword ptr [rsp+0F0h+var_A8], ebx
0x1400b4b78  mov     [rsp+0F0h+var_B0], rdi
0x1400b4b7d  mov     [rsp+0F0h+var_B8], r15
0x1400b4b82  mov     [rsp+0F0h+var_C0], 1Fh
0x1400b4b89  mov     [rsp+0F0h+var_C8], 8
0x1400b4b91  call    WPP_RECORDER_AND_TRACE_SF_qD
0x1400b4b96  lea     rbx, WPP_GLOBAL_Control
0x1400b4b9d  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400b4ba4  mov     r9, [rbp+4Fh+var_50]
0x1400b4ba8  mov     rcx, r12
0x1400b4bab  mov     r8d, [rbp+4Fh+var_68]
0x1400b4baf  mov     rdx, [rbp+4Fh+Token]
0x1400b4bb3  call    ?SetProcessType@@YAXPEAUtagPROCESSINFO@@PEAXW4_PROCESS_IMMERSIVE_TYPE@@PEAU_PS_PKG_CLAIM@@@Z; SetProcessType(tagPROCESSINFO *,void *,_PROCESS_IMMERSIVE_TYPE,_PS_PKG_CLAIM *)
0x1400b4bb8  mov     rcx, r12; struct tagPROCESSINFO *
0x1400b4bbb  call    ?SetProcessInitialCapabilities@@YAXPEAUtagPROCESSINFO@@@Z; SetProcessInitialCapabilities(tagPROCESSINFO *)
0x1400b4bc0  xor     edx, edx
0x1400b4bc2  test    r14d, r14d
0x1400b4bc5  js      loc_1400B4EE1
0x1400b4bcb  mov     rcx, [rbp+4Fh+Token]; Token
0x1400b4bcf  lea     r8, [rbp+4Fh+P]; TokenInformation
0x1400b4bd3  mov     edx, 1Fh; TokenInformationClass
0x1400b4bd8  call    cs:__imp_SeQueryInformationToken
0x1400b4bdf  nop     dword ptr [rax+rax+00h]
0x1400b4be4  xor     edx, edx
0x1400b4be6  mov     r14d, eax
0x1400b4be9  test    eax, eax
0x1400b4beb  js      loc_1400B4EE1
0x1400b4bf1  mov     rax, [rbp+4Fh+P]
0x1400b4bf5  xor     r15d, r15d
0x1400b4bf8  mov     rcx, [rax]
0x1400b4bfb  test    rcx, rcx
0x1400b4bfe  jz      short loc_1400B4C21
0x1400b4c00  lea     rdx, [rbp+4Fh+var_74]
0x1400b4c04  call    cs:__imp_RtlGetAppContainerSidType
0x1400b4c0b  nop     dword ptr [rax+rax+00h]
0x1400b4c10  test    eax, eax
0x1400b4c12  js      short loc_1400B4C21
0x1400b4c14  mov     eax, [rbp+4Fh+var_74]
0x1400b4c17  mov     [r12+36Ch], eax
0x1400b4c1f  jmp     short loc_1400B4C29
0x1400b4c21  mov     [r12+36Ch], r15d
0x1400b4c29  mov     rcx, [rbp+4Fh+P]; P
  ... truncated ...
```
