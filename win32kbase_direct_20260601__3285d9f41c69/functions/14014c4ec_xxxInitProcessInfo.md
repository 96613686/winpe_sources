# xxxInitProcessInfo

- ea: `0x14014c4ec`
- end: `0x14014cd62`
- name: `xxxInitProcessInfo`
- size: `2166`
- prototype: `__int64 __usercall@<rax>(struct _W32PROCESS *@<rcx>, PACCESS_TOKEN Token@<rdx>, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14014bc30`
- `0x14014c2bc`

## callees

- `0x14000763c`
- `0x14008f1d0`
- `0x140090df8`
- `0x1400984d0`
- `0x1400b1d40`
- `0x1400b22cc`
- `0x1400cc720`
- `0x1400cefec`
- `0x1400d3d40`
- `0x1400d3d98`
- `0x140110520`
- `0x14011d690`
- `0x140147830`
- `0x14014c4ec`
- `0x14014d9f4`
- `0x14014de38`
- `0x14018597c`
- `0x140193ddc`
- `0x140193f58`
- `0x1401c680c`
- `0x1401c6dd8`
- `0x140238160`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14014c9ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014c9ff`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c606`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c7b4`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c8ac`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c9a8`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c606`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c7b4`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c8ac`
- `ntoskrnl!SeQueryInformationToken` at `0x14014c9a8`
- `ntoskrnl!PsIsProtectedProcess` at `0x14014c75c`
- `ntoskrnl!PsIsProtectedProcess` at `0x14014c75c`
- `ntoskrnl!PsGetProcessProtection` at `0x14014c770`
- `ntoskrnl!PsGetProcessProtection` at `0x14014c770`
- `ntoskrnl!RtlGetAppContainerSidType` at `0x14014c9d4`
- `ntoskrnl!RtlGetAppContainerSidType` at `0x14014c9d4`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14014ca20`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14014ca20`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014cb6a`
- `ntoskrnl!PsGetWin32KFilterSet` at `0x14014cb6a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014c58d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14014c58d`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014cc4b`
- `WIN32K!W32GetInputMonitorSessionState` at `0x14014cc4b`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014cac9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014cbc0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014cbe5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014cac9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014cbc0`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x14014cbe5`
- `WIN32K!W32GetUserSessionState` at `0x14014c661`
- `WIN32K!W32GetUserSessionState` at `0x14014c6f1`
- `WIN32K!W32GetUserSessionState` at `0x14014c843`
- `WIN32K!W32GetUserSessionState` at `0x14014c91f`
- `WIN32K!W32GetUserSessionState` at `0x14014ca63`
- `WIN32K!W32GetUserSessionState` at `0x14014ca9b`
- `WIN32K!W32GetUserSessionState` at `0x14014cab6`
- `WIN32K!W32GetUserSessionState` at `0x14014cafc`
- `WIN32K!W32GetUserSessionState` at `0x14014cba3`
- `WIN32K!W32GetUserSessionState` at `0x14014cc0b`
- `WIN32K!W32GetUserSessionState` at `0x14014cc36`
- `WIN32K!W32GetUserSessionState` at `0x14014cce8`
- `WIN32K!W32GetUserSessionState` at `0x14014c661`
- `WIN32K!W32GetUserSessionState` at `0x14014c6f1`
- `WIN32K!W32GetUserSessionState` at `0x14014c843`
- `WIN32K!W32GetUserSessionState` at `0x14014c91f`
- `WIN32K!W32GetUserSessionState` at `0x14014ca63`
- `WIN32K!W32GetUserSessionState` at `0x14014ca9b`
- `WIN32K!W32GetUserSessionState` at `0x14014cab6`
- `WIN32K!W32GetUserSessionState` at `0x14014cafc`
- `WIN32K!W32GetUserSessionState` at `0x14014cba3`
- `WIN32K!W32GetUserSessionState` at `0x14014cc0b`
- `WIN32K!W32GetUserSessionState` at `0x14014cc36`
- `WIN32K!W32GetUserSessionState` at `0x14014cce8`

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
  __int64 v13; // r8
  NTSTATUS InformationToken; // r14d
  CTouchProcessor **v15; // rcx
  bool v16; // di
  int v17; // ebx
  __int64 UserSessionState; // rax
  int v19; // edx
  int v20; // r8d
  int v21; // eax
  bool v22; // di
  int v23; // ebx
  __int64 v24; // rax
  int v25; // r8d
  int v26; // edx
  __int64 v27; // rcx
  unsigned __int8 ProcessProtection; // al
  __int64 v29; // rdx
  __int64 v30; // r8
  CTouchProcessor *v31; // rcx
  char v32; // al
  __int64 v33; // rax
  int v34; // r8d
  int v35; // edx
  __int64 v36; // rdx
  __int64 v37; // r8
  CTouchProcessor *v38; // rcx
  bool v39; // al
  __int64 v40; // rax
  int v41; // r8d
  int v42; // edx
  __int64 v43; // r8
  unsigned int SpriteFillColorOverrideForCurrentProcess; // eax
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // r8
  int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // r8
  void (__fastcall *v54)(struct _W32PROCESS *); // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rcx
  int Win32KFilterSet; // eax
  __int64 v62; // r8
  __int64 v63; // rcx
  unsigned __int64 v64; // rcx
  __int64 v65; // rdx
  __int64 v66; // rcx
  __int64 v67; // r8
  int (*v68)(void); // rax
  void (__fastcall *v69)(struct _W32PROCESS *); // rax
  int v70; // ebx
  __int64 v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // r8
  __int64 v74; // rdx
  __int64 v75; // rcx
  int v76; // ebx
  __int16 v77; // [rsp+30h] [rbp-71h]
  char v78; // [rsp+40h] [rbp-61h]
  char v79; // [rsp+48h] [rbp-59h]
  bool v80; // [rsp+70h] [rbp-31h] BYREF
  char v81; // [rsp+71h] [rbp-30h]
  PVOID v82; // [rsp+74h] [rbp-2Dh] BYREF
  int v83; // [rsp+7Ch] [rbp-25h] BYREF
  PVOID P; // [rsp+80h] [rbp-21h] BYREF
  unsigned int v85; // [rsp+88h] [rbp-19h]
  PACCESS_TOKEN Tokena; // [rsp+90h] [rbp-11h]
  __int64 v87; // [rsp+98h] [rbp-9h]
  __int64 v88; // [rsp+A0h] [rbp-1h]
  PVOID TokenInformation; // [rsp+A8h] [rbp+7h] BYREF
  int v90; // [rsp+B0h] [rbp+Fh]

  v88 = a5;
  v85 = a3;
  TokenInformation = 0;
  v6 = Token;
  v90 = 0;
  v7 = 1;
  v8 = *((_BYTE *)a1 + 1200);
  Tokena = Token;
  HIDWORD(v82) = 0;
  P = 0;
  v83 = 0;
  if ( v8 == 1 )
    return 1073741851;
  if ( (Microsoft_Windows_Win32kEnableBits & 0x8000) != 0 )
    McTemplateK0_EtwWriteTransfer(a1, InitiateGuiProcessExecution, &W32kControlGuid);
  result = xxxCheckProcessAndSessionState(a1);
  if ( result >= 0 )
  {
    AtomicExecutionCheck::EnforceConsistency(v11);
    CurrentThreadWin32Thread = PsGetCurrentThreadWin32Thread();
    v87 = CurrentThreadWin32Thread;
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
        v15 = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (v15 = (CTouchProcessor **)*((unsigned int *)WPP_GLOBAL_Control + 11), (char)v15 >= 0)
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
        {
          v7 = 0;
        }
        v16 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( !v7 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_84;
        v17 = *((_DWORD *)a1 + 14);
        UserSessionState = W32GetUserSessionState(v15, WPP_GLOBAL_Control, v13);
        v79 = v17;
        v78 = InformationToken;
        LOBYTE(v20) = v16;
        v77 = 28;
        goto LABEL_83;
      }
      v21 = (int)TokenInformation;
      if ( HIDWORD(TokenInformation) && (_DWORD)TokenInformation != 4096 )
      {
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u )
        {
          v7 = 0;
        }
        v22 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v23 = *((_DWORD *)a1 + 14);
          v24 = W32GetUserSessionState(&WPP_GLOBAL_Control, WPP_GLOBAL_Control, v13);
          LOBYTE(v25) = v22;
          LOBYTE(v26) = v7;
          WPP_RECORDER_AND_TRACE_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v26,
            v25,
            *(_QWORD *)(v24 + 69136),
            3,
            8,
            29,
            (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
            v23);
        }
        result = -1073741823;
        goto LABEL_85;
      }
      *((_DWORD *)a1 + 217) = HIDWORD(TokenInformation);
      v27 = *(_QWORD *)a1;
      *((_DWORD *)a1 + 216) = v21;
      if ( (unsigned int)PsIsProtectedProcess(v27) )
      {
        ProcessProtection = PsGetProcessProtection(*(_QWORD *)a1);
        *((_DWORD *)a1 + 218) = ((ProcessProtection >> 4)
                               | ((((ProcessProtection & 7) << 8) | (ProcessProtection >> 3) & 1) << 8)) << 8;
      }
      LODWORD(v82) = 0;
      if ( SeQueryInformationToken(v6, TokenDeviceClaimAttributes|TokenAuditPolicy, &v82) >= 0 && (_DWORD)v82 )
        *((_QWORD *)a1 + 101) |= 0x4000000000uLL;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) == 0
        || (v32 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
      {
        v32 = 0;
      }
      v81 = v32;
      v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v32 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v31) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v33 = W32GetUserSessionState(v31, v29, v30);
        LOBYTE(v34) = v80;
        LOBYTE(v35) = v81;
        WPP_RECORDER_AND_TRACE_SF_DDDDD(*((_QWORD *)WPP_GLOBAL_Control + 3), v35, v34, *(_QWORD *)(v33 + 69136));
        CurrentThreadWin32Thread = v87;
        v6 = Tokena;
      }
    }
    InformationToken = SeQueryInformationToken(v6, TokenUIAccess, (PVOID *)((char *)&v82 + 4));
    if ( HIDWORD(v82) )
    {
      *((_DWORD *)a1 + 3) |= 0x80080000;
      *((_QWORD *)a1 + 101) |= 2uLL;
      v38 = WPP_GLOBAL_Control;
      v39 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x80u) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
      v81 = v39;
      v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v39 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v38) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        v40 = W32GetUserSessionState(v38, v36, v37);
        LOBYTE(v41) = v80;
        LOBYTE(v42) = v81;
        WPP_RECORDER_AND_TRACE_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 3), v42, v41, *(_QWORD *)(v40 + 69136));
      }
    }
    SetProcessType(a1, Tokena, v85, v88);
    SetProcessInitialCapabilities(a1);
    if ( InformationToken >= 0 )
    {
      InformationToken = SeQueryInformationToken(Tokena, TokenAppContainerSid, &P);
      if ( InformationToken >= 0 )
      {
        if ( *(_QWORD *)P && (int)RtlGetAppContainerSidType(*(_QWORD *)P, &v83) >= 0 )
          *((_DWORD *)a1 + 219) = v83;
        else
          *((_DWORD *)a1 + 219) = 0;
        ExFreePoolWithTag(P, 0);
        P = 0;
        SpriteFillColorOverrideForCurrentProcess = GetSpriteFillColorOverrideForCurrentProcess();
        v45 = *(_QWORD *)a1;
        *((_DWORD *)a1 + 269) = SpriteFillColorOverrideForCurrentProcess;
        if ( PsGetProcessWow64Process(v45) )
          *((_DWORD *)a1 + 3) |= 0x80u;
        *((_QWORD *)a1 + 111) = -1;
        *((_QWORD *)a1 + 112) = -1;
        v49 = *((_DWORD *)a1 + 3);
        if ( (v49 & 0x20) == 0 )
        {
          *((_DWORD *)a1 + 3) = v49 | 0x22;
          v50 = W32GetUserSessionState(v47, v46, v48);
          *(_DWORD *)(v50 + 66784) |= 0x8000000u;
          if ( (int)IszzzCalcStartCursorHideSupported() >= 0 )
          {
            CWinEventNoopDeferral::CWinEventNoopDeferral((CWinEventNoopDeferral *)&v80);
            zzzCalcStartCursorHide(0, 0);
            CWinEventNoopDeferral::~CWinEventNoopDeferral((CWinEventNoopDeferral *)&v80);
          }
        }
        v51 = *(_QWORD *)(W32GetUserSessionState(v47, v46, v48) + 36200);
        *((_QWORD *)a1 + 46) = v51;
        *(_QWORD *)(W32GetUserSessionState(v51, v52, v53) + 36200) = a1;
        v54 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 4776LL);
        if ( v54 )
          v54(a1);
        GetProcessLuid(0, (PLUID)((char *)a1 + 764));
        v58 = W32GetUserSessionState(v56, v55, v57);
        LOBYTE(v59) = 1;
        *((_DWORD *)a1 + 98) = *(_DWORD *)(v58 + 41156);
        *((_DWORD *)a1 + 186) = 0;
        CitProcessCallout(a1, v59);
        *((_QWORD *)a1 + 101) &= 0xFFFFFFFFFFBE7FFFuLL;
        v60 = *((_QWORD *)a1 + 101);
        *((_DWORD *)a1 + 67) = 24592;
        *((_WORD *)a1 + 136) = 96;
        if ( (v60 & 0x30) == 0x20 )
          *((_QWORD *)a1 + 101) = v60 | 0x100000;
        Win32KFilterSet = PsGetWin32KFilterSet();
        v63 = 0;
        if ( Win32KFilterSet == 5 )
          v63 = 0x1000000;
        v64 = *((_QWORD *)a1 + 101) & 0xFFFFFFFFF6FFFFFFuLL | v63 & 0xFFFFFFFFF7FFFFFFuLL;
        *((_QWORD *)a1 + 101) = v64;
        if ( *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v64, 0x1000000, v62) + 19704) + 6998LL) )
        {
          v66 = *(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48);
          v68 = *(int (**)(void))(v66 + 832);
          if ( v68 && v68() >= 0 )
          {
            v69 = *(void (__fastcall **)(struct _W32PROCESS *))(*(_QWORD *)(W32GetWin32kBaseApiSetTable() + 48) + 840LL);
            if ( v69 )
              v69(a1);
          }
          else
          {
            *((_WORD *)a1 + 136) = *(_WORD *)(*(_QWORD *)(W32GetUserSessionState(v66, v65, v67) + 19704) + 6998LL);
          }
        }
        Feature_WebThreatDefenseToggle__private_IsEnabledPreCheck();
        v70 = 0;
        if ( *(_DWORD *)(W32GetUserSessionState(v72, v71, v73) + 42376) )
        {
          if ( !W32GetInputMonitorSessionState() )
            MicrosoftTelemetryAssertTriggeredNoArgsKM(v75, v74);
          v70 = 1;
        }
        *((_DWORD *)a1 + 69) = (4 * v70) | *((_DWORD *)a1 + 69) & 0xFFFFFFFB;
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
    v80 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v7 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_84;
    v76 = *((_DWORD *)a1 + 14);
    UserSessionState = W32GetUserSessionState(WPP_GLOBAL_Control, 0, v43);
    LOBYTE(v20) = v80;
    v79 = v76;
    v78 = InformationToken;
    v77 = 32;
LABEL_83:
    LOBYTE(v19) = v7;
    WPP_RECORDER_AND_TRACE_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v19,
      v20,
      *(_QWORD *)(UserSessionState + 69136),
      3,
      8,
      v77,
      (__int64)WPP_a173d8203b92344252851dea77c1a613_Traceguids,
      v78,
      v79);
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
0x14014c4ec  mov     [rsp-8+arg_10], rbx
0x14014c4f1  push    rbp
0x14014c4f2  push    rsi
0x14014c4f3  push    rdi
0x14014c4f4  push    r12
0x14014c4f6  push    r13
0x14014c4f8  push    r14
0x14014c4fa  push    r15
0x14014c4fc  lea     rbp, [rsp-1Fh]
0x14014c501  sub     rsp, 0C0h
0x14014c508  mov     rax, cs:__security_cookie
0x14014c50f  xor     rax, rsp
0x14014c512  mov     [rbp+4Fh+var_38], rax
0x14014c516  mov     rax, [rbp+4Fh+arg_20]
0x14014c51a  xor     ebx, ebx
0x14014c51c  mov     [rbp+4Fh+var_50], rax
0x14014c520  mov     r14d, r9d
0x14014c523  xor     eax, eax
0x14014c525  mov     [rbp+4Fh+var_68], r8d
0x14014c529  mov     [rbp+4Fh+TokenInformation], rax
0x14014c52d  mov     r15, rdx
0x14014c530  mov     [rbp+4Fh+var_40], eax
0x14014c533  lea     r13d, [rbx+1]
0x14014c537  mov     al, [rcx+4B0h]
0x14014c53d  mov     r12, rcx
0x14014c540  mov     [rbp+4Fh+Token], rdx
0x14014c544  mov     dword ptr [rbp+4Fh+var_7C+4], ebx
0x14014c547  mov     [rbp+4Fh+P], rbx
0x14014c54b  mov     [rbp+4Fh+var_74], ebx
0x14014c54e  cmp     al, r13b
0x14014c551  jnz     short loc_14014C55D
0x14014c553  mov     eax, 4000001Bh
0x14014c558  jmp     loc_14014CD3A
0x14014c55d  cmp     byte ptr cs:Microsoft_Windows_Win32kEnableBits+1, bl
0x14014c563  jge     short loc_14014C578
0x14014c565  lea     r8, W32kControlGuid
0x14014c56c  lea     rdx, InitiateGuiProcessExecution
0x14014c573  call    McTemplateK0_EtwWriteTransfer
0x14014c578  mov     rcx, r12; struct _W32PROCESS *
0x14014c57b  call    ?xxxCheckProcessAndSessionState@@YAJPEAU_W32PROCESS@@@Z; xxxCheckProcessAndSessionState(_W32PROCESS *)
0x14014c580  test    eax, eax
0x14014c582  js      loc_14014CD3A
0x14014c588  call    ?EnforceConsistency@AtomicExecutionCheck@@AEAAXXZ; AtomicExecutionCheck::EnforceConsistency(void)
0x14014c58d  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x14014c594  nop     dword ptr [rax+rax+00h]
0x14014c599  mov     rsi, rax
0x14014c59c  mov     [rbp+4Fh+var_58], rax
0x14014c5a0  add     [rax+1Ch], r13d
0x14014c5a4  mov     [r12+4B0h], r13b
0x14014c5ac  mov     [r12+130h], rbx
0x14014c5b4  mov     [r12+138h], rbx
0x14014c5bc  mov     [r12+140h], ebx
0x14014c5c4  call    Feature_UIPIModernization__private_IsEnabledDeviceUsageNoInline
0x14014c5c9  lea     rbx, WPP_GLOBAL_Control
0x14014c5d0  lea     rdi, WPP_RECORDER_INITIALIZED
0x14014c5d7  test    eax, eax
0x14014c5d9  jz      short loc_14014C5F6
0x14014c5db  mov     r8d, r14d; unsigned int
0x14014c5de  mov     rdx, r15; void *
0x14014c5e1  mov     rcx, r12; struct tagPROCESSINFO *
0x14014c5e4  call    ?InitProcessUipiInfo@@YAJPEAUtagPROCESSINFO@@PEAXK@Z; InitProcessUipiInfo(tagPROCESSINFO *,void *,ulong)
0x14014c5e9  test    eax, eax
0x14014c5eb  jns     loc_14014C8A0
0x14014c5f1  jmp     loc_14014CD37
0x14014c5f6  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x14014c5fa  mov     dword ptr [rbp+4Fh+TokenInformation+4], r14d
0x14014c5fe  mov     edx, 19h; TokenInformationClass
0x14014c603  mov     rcx, r15; Token
0x14014c606  call    cs:__imp_SeQueryInformationToken
0x14014c60d  nop     dword ptr [rax+rax+00h]
0x14014c612  mov     r14d, eax
0x14014c615  test    eax, eax
0x14014c617  jns     short loc_14014C691
0x14014c619  mov     rdx, cs:WPP_GLOBAL_Control
0x14014c620  lea     rcx, WPP_GLOBAL_Control
0x14014c627  cmp     rdx, rcx
0x14014c62a  jz      short loc_14014C639
0x14014c62c  mov     ecx, [rdx+2Ch]
0x14014c62f  test    cl, cl
0x14014c631  jns     short loc_14014C639
0x14014c633  cmp     byte ptr [rdx+29h], 3
0x14014c637  jnb     short loc_14014C63C
0x14014c639  xor     r13b, r13b
0x14014c63c  lea     rax, WPP_RECORDER_INITIALIZED
0x14014c643  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014c64a  setnz   dil
0x14014c64e  test    r13b, r13b
0x14014c651  jnz     short loc_14014C65C
0x14014c653  test    dil, dil
0x14014c656  jz      loc_14014CD34
0x14014c65c  mov     ebx, [r12+38h]
0x14014c661  call    cs:__imp_W32GetUserSessionState
0x14014c668  nop     dword ptr [rax+rax+00h]
0x14014c66d  mov     dword ptr [rsp+0F0h+var_A8], ebx
0x14014c671  lea     r15, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x14014c678  mov     dword ptr [rsp+0F0h+var_B0], r14d
0x14014c67d  mov     r8b, dil
0x14014c680  mov     [rsp+0F0h+var_B8], r15
0x14014c685  mov     [rsp+0F0h+var_C0], 1Ch
0x14014c68c  jmp     loc_14014CD0D
0x14014c691  mov     ecx, dword ptr [rbp+4Fh+TokenInformation+4]
0x14014c694  xor     r14d, r14d
0x14014c697  mov     eax, dword ptr [rbp+4Fh+TokenInformation]
0x14014c69a  test    ecx, ecx
0x14014c69c  jz      loc_14014C748
0x14014c6a2  cmp     eax, 1000h
0x14014c6a7  jz      loc_14014C748
0x14014c6ad  mov     rdx, cs:WPP_GLOBAL_Control
0x14014c6b4  lea     rcx, WPP_GLOBAL_Control
0x14014c6bb  cmp     rdx, rcx
0x14014c6be  jz      short loc_14014C6CD
0x14014c6c0  mov     eax, [rdx+2Ch]
0x14014c6c3  test    al, al
0x14014c6c5  jns     short loc_14014C6CD
0x14014c6c7  cmp     byte ptr [rdx+29h], 3
0x14014c6cb  jnb     short loc_14014C6D0
0x14014c6cd  mov     r13b, r14b
0x14014c6d0  lea     rax, WPP_RECORDER_INITIALIZED
0x14014c6d7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14014c6de  setnz   dil
0x14014c6e2  test    r13b, r13b
0x14014c6e5  jnz     short loc_14014C6EC
0x14014c6e7  test    dil, dil
0x14014c6ea  jz      short loc_14014C73E
0x14014c6ec  mov     ebx, [r12+38h]
0x14014c6f1  call    cs:__imp_W32GetUserSessionState
0x14014c6f8  nop     dword ptr [rax+rax+00h]
0x14014c6fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14014c704  lea     r15, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x14014c70b  mov     dword ptr [rsp+0F0h+var_B0], ebx
0x14014c70f  mov     r8b, dil
0x14014c712  mov     [rsp+0F0h+var_B8], r15
0x14014c717  mov     dl, r13b
0x14014c71a  mov     r9, [rax+10E10h]
0x14014c721  mov     rcx, [rcx+18h]
0x14014c725  mov     [rsp+0F0h+var_C0], 1Dh
0x14014c72c  mov     [rsp+0F0h+var_C8], 8
0x14014c734  mov     [rsp+0F0h+var_D0], 3
0x14014c739  call    WPP_RECORDER_AND_TRACE_SF_D
0x14014c73e  mov     eax, 0C0000001h
0x14014c743  jmp     loc_14014CD37
0x14014c748  mov     [r12+364h], ecx
0x14014c750  mov     rcx, [r12]
0x14014c754  mov     [r12+360h], eax
0x14014c75c  call    cs:__imp_PsIsProtectedProcess
0x14014c763  nop     dword ptr [rax+rax+00h]
0x14014c768  test    eax, eax
0x14014c76a  jz      short loc_14014C7A4
0x14014c76c  mov     rcx, [r12]
0x14014c770  call    cs:__imp_PsGetProcessProtection
0x14014c777  nop     dword ptr [rax+rax+00h]
0x14014c77c  movzx   ecx, al
0x14014c77f  mov     edx, ecx
0x14014c781  mov     eax, ecx
0x14014c783  shr     edx, 3
0x14014c786  and     eax, 7
0x14014c789  and     edx, r13d
0x14014c78c  shl     eax, 8
0x14014c78f  or      edx, eax
0x14014c791  shr     ecx, 4
0x14014c794  shl     edx, 8
0x14014c797  or      edx, ecx
0x14014c799  shl     edx, 8
0x14014c79c  mov     [r12+368h], edx
0x14014c7a4  lea     r8, [rbp+4Fh+var_7C]; TokenInformation
0x14014c7a8  mov     dword ptr [rbp+4Fh+var_7C], r14d
0x14014c7ac  mov     edx, 32h ; '2'; TokenInformationClass
0x14014c7b1  mov     rcx, r15; Token
0x14014c7b4  call    cs:__imp_SeQueryInformationToken
0x14014c7bb  nop     dword ptr [rax+rax+00h]
0x14014c7c0  test    eax, eax
0x14014c7c2  js      short loc_14014C7DC
0x14014c7c4  cmp     dword ptr [rbp+4Fh+var_7C], r14d
0x14014c7c8  jz      short loc_14014C7DC
0x14014c7ca  mov     rax, 4000000000h
0x14014c7d4  or      [r12+328h], rax
0x14014c7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14014c7e3  cmp     rcx, rbx
0x14014c7e6  jz      short loc_14014C7F8
0x14014c7e8  mov     eax, [rcx+2Ch]
0x14014c7eb  test    al, al
0x14014c7ed  jns     short loc_14014C7F8
0x14014c7ef  cmp     byte ptr [rcx+29h], 4
0x14014c7f3  mov     al, r13b
0x14014c7f6  jnb     short loc_14014C7FB
0x14014c7f8  mov     al, r14b
0x14014c7fb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14014c802  mov     [rbp+4Fh+var_7F], al
0x14014c805  setnz   cl
0x14014c808  mov     [rbp+4Fh+var_80], cl
0x14014c80b  test    al, al
0x14014c80d  jnz     short loc_14014C817
0x14014c80f  test    cl, cl
0x14014c811  jz      loc_14014C8A0
0x14014c817  mov     r15, [r12+328h]
0x14014c81f  mov     ebx, [r12+368h]
0x14014c827  mov     edi, [r12+364h]
0x14014c82f  mov     esi, [r12+360h]
0x14014c837  mov     r14d, [r12+38h]
0x14014c83c  shr     r15, 26h
0x14014c840  and     r15d, r13d
0x14014c843  call    cs:__imp_W32GetUserSessionState
0x14014c84a  nop     dword ptr [rax+rax+00h]
0x14014c84f  mov     rcx, cs:WPP_GLOBAL_Control
0x14014c856  mov     r8b, [rbp+4Fh+var_80]
0x14014c85a  mov     dl, [rbp+4Fh+var_7F]
0x14014c85d  mov     r9, [rax+10E10h]
0x14014c864  mov     rcx, [rcx+18h]
0x14014c868  mov     [rsp+0F0h+var_90], r15d
0x14014c86d  mov     [rsp+0F0h+var_98], ebx
0x14014c871  mov     [rsp+0F0h+var_A0], edi
0x14014c875  mov     dword ptr [rsp+0F0h+var_A8], esi
0x14014c879  mov     dword ptr [rsp+0F0h+var_B0], r14d
0x14014c87e  mov     [rsp+0F0h+var_C0], 1Eh
0x14014c885  call    WPP_RECORDER_AND_TRACE_SF_DDDDD
0x14014c88a  mov     rsi, [rbp+4Fh+var_58]
0x14014c88e  lea     rbx, WPP_GLOBAL_Control
0x14014c895  mov     r15, [rbp+4Fh+Token]
0x14014c899  lea     rdi, WPP_RECORDER_INITIALIZED
0x14014c8a0  lea     r8, [rbp+4Fh+var_7C+4]; TokenInformation
0x14014c8a4  mov     edx, 1Ah; TokenInformationClass
0x14014c8a9  mov     rcx, r15; Token
0x14014c8ac  call    cs:__imp_SeQueryInformationToken
0x14014c8b3  nop     dword ptr [rax+rax+00h]
0x14014c8b8  cmp     dword ptr [rbp+4Fh+var_7C+4], 0
0x14014c8bc  lea     r15, WPP_a173d8203b92344252851dea77c1a613_Traceguids
0x14014c8c3  mov     r14d, eax
0x14014c8c6  jz      loc_14014C974
0x14014c8cc  or      dword ptr [r12+0Ch], 80080000h
0x14014c8d5  or      qword ptr [r12+328h], 2
0x14014c8de  mov     rcx, cs:WPP_GLOBAL_Control
0x14014c8e5  cmp     rcx, rbx
0x14014c8e8  jz      short loc_14014C8FC
0x14014c8ea  mov     eax, [rcx+2Ch]
0x14014c8ed  test    al, al
0x14014c8ef  jns     short loc_14014C8FC
0x14014c8f1  cmp     byte ptr [rcx+29h], 4
0x14014c8f5  jb      short loc_14014C8FC
0x14014c8f7  mov     al, r13b
0x14014c8fa  jmp     short loc_14014C8FE
0x14014c8fc  xor     al, al
0x14014c8fe  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14014c905  mov     [rbp+4Fh+var_7F], al
0x14014c908  setnz   cl
0x14014c90b  mov     [rbp+4Fh+var_80], cl
0x14014c90e  test    al, al
0x14014c910  jnz     short loc_14014C916
0x14014c912  test    cl, cl
0x14014c914  jz      short loc_14014C974
0x14014c916  mov     ebx, [r12+38h]
0x14014c91b  mov     rdi, [r12]
0x14014c91f  call    cs:__imp_W32GetUserSessionState
0x14014c926  nop     dword ptr [rax+rax+00h]
0x14014c92b  mov     rcx, cs:WPP_GLOBAL_Control
0x14014c932  mov     r8b, [rbp+4Fh+var_80]
0x14014c936  mov     dl, [rbp+4Fh+var_7F]
0x14014c939  mov     r9, [rax+10E10h]
0x14014c940  mov     rcx, [rcx+18h]
0x14014c944  mov     dword ptr [rsp+0F0h+var_A8], ebx
0x14014c948  mov     [rsp+0F0h+var_B0], rdi
0x14014c94d  mov     [rsp+0F0h+var_B8], r15
0x14014c952  mov     [rsp+0F0h+var_C0], 1Fh
0x14014c959  mov     [rsp+0F0h+var_C8], 8
0x14014c961  call    WPP_RECORDER_AND_TRACE_SF_qD
0x14014c966  lea     rbx, WPP_GLOBAL_Control
0x14014c96d  lea     rdi, WPP_RECORDER_INITIALIZED
0x14014c974  mov     r9, [rbp+4Fh+var_50]
0x14014c978  mov     rcx, r12
0x14014c97b  mov     r8d, [rbp+4Fh+var_68]
0x14014c97f  mov     rdx, [rbp+4Fh+Token]
0x14014c983  call    ?SetProcessType@@YAXPEAUtagPROCESSINFO@@PEAXW4_PROCESS_IMMERSIVE_TYPE@@PEAU_PS_PKG_CLAIM@@@Z; SetProcessType(tagPROCESSINFO *,void *,_PROCESS_IMMERSIVE_TYPE,_PS_PKG_CLAIM *)
0x14014c988  mov     rcx, r12; struct tagPROCESSINFO *
0x14014c98b  call    ?SetProcessInitialCapabilities@@YAXPEAUtagPROCESSINFO@@@Z; SetProcessInitialCapabilities(tagPROCESSINFO *)
0x14014c990  xor     edx, edx
0x14014c992  test    r14d, r14d
0x14014c995  js      loc_14014CCB1
0x14014c99b  mov     rcx, [rbp+4Fh+Token]; Token
0x14014c99f  lea     r8, [rbp+4Fh+P]; TokenInformation
0x14014c9a3  mov     edx, 1Fh; TokenInformationClass
0x14014c9a8  call    cs:__imp_SeQueryInformationToken
0x14014c9af  nop     dword ptr [rax+rax+00h]
0x14014c9b4  xor     edx, edx
0x14014c9b6  mov     r14d, eax
0x14014c9b9  test    eax, eax
0x14014c9bb  js      loc_14014CCB1
0x14014c9c1  mov     rax, [rbp+4Fh+P]
0x14014c9c5  xor     r15d, r15d
0x14014c9c8  mov     rcx, [rax]
0x14014c9cb  test    rcx, rcx
0x14014c9ce  jz      short loc_14014C9F1
0x14014c9d0  lea     rdx, [rbp+4Fh+var_74]
0x14014c9d4  call    cs:__imp_RtlGetAppContainerSidType
0x14014c9db  nop     dword ptr [rax+rax+00h]
0x14014c9e0  test    eax, eax
0x14014c9e2  js      short loc_14014C9F1
0x14014c9e4  mov     eax, [rbp+4Fh+var_74]
0x14014c9e7  mov     [r12+36Ch], eax
0x14014c9ef  jmp     short loc_14014C9F9
0x14014c9f1  mov     [r12+36Ch], r15d
0x14014c9f9  mov     rcx, [rbp+4Fh+P]; P
  ... truncated ...
```
