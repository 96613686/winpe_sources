# WLGeneric_Unlocking_Execute(_StateMachineCallContext *)

- ea: `0x140044c90`
- end: `0x140045ebb`
- name: `?WLGeneric_Unlocking_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `4651`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `43`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140001e38`
- `0x1400057f4`
- `0x1400060d0`
- `0x140008d74`
- `0x14000b73c`
- `0x1400102d4`
- `0x140014250`
- `0x140016f60`
- `0x1400198e0`
- `0x14001a3a8`
- `0x14002aae0`
- `0x1400333b0`
- `0x140035698`
- `0x140037608`
- `0x1400378d0`
- `0x140039458`
- `0x1400396fc`
- `0x14003ba50`
- `0x14003bec8`
- `0x14003bfec`
- `0x14003cb6c`
- `0x14003f584`
- `0x140041c34`
- `0x14004282c`
- `0x14004327c`
- `0x140044800`
- `0x140044830`
- `0x140044c90`
- `0x140045ec4`
- `0x14004ea3c`
- `0x14004eb98`
- `0x14004f0b4`
- `0x140053398`
- `0x140053720`
- `0x140056348`
- `0x14005639c`
- `0x14005f020`
- `0x14006012c`
- `0x1400608f0`
- `0x14007cc30`
- `0x140081d40`
- `0x140082bd8`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004553b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004553b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140045dba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140045dba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140045dac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140045dac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140044d34`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140045cc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140045cfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140044d34`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140045cc5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140045cfa`
- `ntdll!RtlFreeSid` at `0x140045d6f`
- `ntdll!RtlFreeSid` at `0x140045d6f`
- `ntdll!WinSqmAddToStream` at `0x140045d54`
- `ntdll!WinSqmAddToStream` at `0x140045d54`
- `ntdll!TpSimpleTryPost` at `0x140045b7b`
- `ntdll!TpSimpleTryPost` at `0x140045b7b`
- `ntdll!RtlEqualSid` at `0x140044ff8`
- `ntdll!RtlEqualSid` at `0x140044ff8`
- `ntdll!RtlCopyLuid` at `0x140045b5f`
- `ntdll!RtlCopyLuid` at `0x140045b5f`
- `ntdll!RtlGetActiveConsoleId` at `0x1400456d1`
- `ntdll!RtlGetActiveConsoleId` at `0x1400456d1`
- `ntdll!NtQueryInformationToken` at `0x140044fdb`
- `ntdll!NtQueryInformationToken` at `0x140044fdb`
- `ntdll!NtClose` at `0x140045de5`
- `ntdll!NtClose` at `0x140045de5`
- `SspiCli!LsaFreeReturnBuffer` at `0x140045dc5`
- `SspiCli!LsaFreeReturnBuffer` at `0x140045dc5`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserSessionInfo` at `0x140045211`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserSessionInfo` at `0x140045211`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetAllUserSessions` at `0x140045113`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetAllUserSessions` at `0x140045113`
- `ext-ms-win-session-winsta-l1-1-3!WinStationConsumeCacheSession` at `0x1400459b0`
- `ext-ms-win-session-winsta-l1-1-3!WinStationConsumeCacheSession` at `0x1400459b0`

## string_xrefs

- `0x14004571f`: `clientcore\ds\security\umstartup\winlogon\core\lock.cxx`

## pseudocode

```c
__int64 __fastcall WLGeneric_Unlocking_Execute(struct _StateMachineCallContext *a1)
{
  CUser *v1; // r15
  int v2; // r12d
  struct _FILETIME *v3; // rsi
  struct _CRED_PROV_CREDENTIAL *v4; // r13
  int v5; // edi
  enum _SECURITY_LOGON_TYPE v6; // ebx
  CloudPCHelpers *v7; // rcx
  bool v8; // al
  __int64 v9; // rcx
  CMachine *v10; // rcx
  unsigned int LastLogonInfo; // ebx
  int v12; // r13d
  struct _FILETIME v13; // rcx
  unsigned int v14; // eax
  int AssignedAccessType; // ebx
  NTSTATUS v16; // eax
  BOOL v17; // edx
  CUser *v18; // rcx
  const char *v19; // r9
  CUser *v20; // rcx
  CUser *v21; // rax
  int v22; // r9d
  CUser *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  unsigned int v26; // edi
  DWORD dwLowDateTime; // ebx
  struct _FILETIME v28; // rdi
  struct _FILETIME v29; // rbx
  int v30; // eax
  unsigned int v31; // eax
  int v32; // edi
  unsigned int v33; // ebx
  CUser *v34; // rcx
  struct _LUID *v35; // rbx
  int v36; // eax
  unsigned int updated; // eax
  unsigned int LastLogonInfoPolicy; // edi
  struct _FILETIME v39; // rcx
  int v40; // eax
  void *v41; // rdi
  HANDLE ProcessHeap; // rax
  int v43; // r12d
  int v44; // r12d
  __int64 result; // rax
  BOOL ReturnLength; // [rsp+20h] [rbp-2F8h]
  int IsLogonFromUnlockEnabled; // [rsp+60h] [rbp-2B8h]
  bool v48[4]; // [rsp+68h] [rbp-2B0h] BYREF
  BOOL v49; // [rsp+6Ch] [rbp-2ACh]
  HANDLE TokenHandle; // [rsp+70h] [rbp-2A8h] BYREF
  int v51; // [rsp+78h] [rbp-2A0h]
  unsigned int IsAuditingLogFull; // [rsp+7Ch] [rbp-29Ch] BYREF
  struct _LUID SourceLuid; // [rsp+80h] [rbp-298h] BYREF
  int v54; // [rsp+88h] [rbp-290h]
  int v55; // [rsp+8Ch] [rbp-28Ch]
  LPVOID lpMem; // [rsp+90h] [rbp-288h] BYREF
  PSID Sid; // [rsp+98h] [rbp-280h]
  __int64 v58; // [rsp+A0h] [rbp-278h] BYREF
  int v59; // [rsp+A8h] [rbp-270h] BYREF
  unsigned int v60; // [rsp+ACh] [rbp-26Ch] BYREF
  unsigned int v61; // [rsp+B0h] [rbp-268h] BYREF
  unsigned int v62; // [rsp+B4h] [rbp-264h] BYREF
  ULONG v63; // [rsp+B8h] [rbp-260h] BYREF
  int v64; // [rsp+BCh] [rbp-25Ch] BYREF
  int v65; // [rsp+C0h] [rbp-258h]
  struct _FILETIME v66; // [rsp+C8h] [rbp-250h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+D0h] [rbp-248h] BYREF
  int v68; // [rsp+D8h] [rbp-240h]
  BOOL v69; // [rsp+DCh] [rbp-23Ch]
  __int64 v70; // [rsp+E0h] [rbp-238h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-230h] BYREF
  struct _FILETIME *v72; // [rsp+F0h] [rbp-228h] BYREF
  CUser *v73; // [rsp+F8h] [rbp-220h]
  int v74; // [rsp+100h] [rbp-218h]
  __int128 v75; // [rsp+110h] [rbp-208h]
  __int128 v76; // [rsp+120h] [rbp-1F8h]
  __int128 v77; // [rsp+130h] [rbp-1E8h]
  __int128 v78; // [rsp+140h] [rbp-1D8h]
  __int128 v79; // [rsp+150h] [rbp-1C8h]
  __int128 v80; // [rsp+160h] [rbp-1B8h]
  __int128 v81; // [rsp+170h] [rbp-1A8h]
  _OWORD v82[2]; // [rsp+180h] [rbp-198h] BYREF
  struct _QUOTA_LIMITS v83; // [rsp+1A0h] [rbp-178h]
  __int128 v84; // [rsp+1D0h] [rbp-148h]
  __int128 v85; // [rsp+1E0h] [rbp-138h]
  struct _FILETIME v86[2]; // [rsp+1F0h] [rbp-128h] BYREF
  struct _QUOTA_LIMITS v87; // [rsp+200h] [rbp-118h] BYREF
  __int128 v88; // [rsp+230h] [rbp-E8h] BYREF
  __int128 v89; // [rsp+240h] [rbp-D8h]
  __int128 v90; // [rsp+250h] [rbp-C8h]
  unsigned __int16 v91[8]; // [rsp+260h] [rbp-B8h] BYREF
  __int128 v92; // [rsp+270h] [rbp-A8h]
  void *TokenInformation; // [rsp+280h] [rbp-98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  v1 = 0;
  v2 = 0;
  v3 = (struct _FILETIME *)*((_QWORD *)a1 + 1);
  v4 = *(struct _CRED_PROV_CREDENTIAL **)(*(_QWORD *)v3 + 112LL);
  SourceLuid = 0;
  TokenHandle = 0;
  lpMem = 0;
  v61 = 0;
  IsAuditingLogFull = 0;
  memset(&v87, 0, sizeof(v87));
  v63 = 0;
  v49 = 0;
  v5 = 0;
  v6 = Unlock;
  v66 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&v66);
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v51 = 1;
  v59 = 0;
  if ( (*(_BYTE *)v4 & 4) != 0 )
  {
    IsLogonFromUnlockEnabled = 1;
  }
  else if ( *(_DWORD *)(*(_QWORD *)&v3[4] + 528LL) )
  {
    IsLogonFromUnlockEnabled = 1;
  }
  else
  {
    IsLogonFromUnlockEnabled = CSession::IsLogonFromUnlockEnabled((CSession *)1, v3);
  }
  v55 = 0;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
  }
  DWORD2(v88) = 1;
  LODWORD(v88) = 1;
  WLEventWrite(&WLDiagEvt_Unlock_Start);
  v8 = CloudPCHelpers::IsBootToCloudModeRegistryCheck(v7);
  v9 = 7140;
  if ( !v8 )
    v9 = 1005;
  WlDisplayStatusByResourceId(v9, 2, 16, 0);
  v3[7].dwHighDateTime = 0;
  if ( IsLogonFromUnlockEnabled )
  {
    Sid = (PSID)CreateLogonSid();
    if ( !Sid )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
      }
      LastLogonInfo = 14;
      goto LABEL_19;
    }
    v6 = Interactive;
    IsAuditingLogFull = CMachine::IsAuditingLogFull(v10);
  }
  else
  {
    v13 = v3[4];
    Sid = *(PSID *)(*(_QWORD *)&v13 + 120LL);
    SourceLuid = *(struct _LUID *)(*(_QWORD *)&v13 + 128LL);
  }
  v14 = AuthenticateUser(
          (struct _WLSM_GLOBAL_CONTEXT *)v3,
          v6,
          Sid,
          v4,
          &SourceLuid,
          &TokenHandle,
          &v87,
          &lpMem,
          &v61,
          (int *)&v3[6].dwHighDateTime,
          (int *)&v3[7],
          &v59);
  LastLogonInfo = v14;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v14);
      v12 = IsLogonFromUnlockEnabled;
      goto LABEL_177;
    }
LABEL_19:
    v12 = IsLogonFromUnlockEnabled;
    goto LABEL_177;
  }
  v51 = 2 - (v59 != 0);
  v68 = v51;
  AssignedAccessType = GetAssignedAccessType(TokenHandle);
  v54 = AssignedAccessType;
  v16 = NtQueryInformationToken(TokenHandle, TokenUser, &TokenInformation, 0x54u, &v63);
  if ( v16 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids,
        (unsigned int)v16);
      v18 = WPP_GLOBAL_Control;
    }
    v17 = v49;
  }
  else
  {
    v17 = RtlEqualSid(TokenInformation, *(PSID *)(*(_QWORD *)&v3[4] + 160LL)) != 0;
    v49 = v17;
    v69 = v17;
    v18 = WPP_GLOBAL_Control;
  }
  if ( v18 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v18 + 7) & 0x4000) != 0 && *((_BYTE *)v18 + 25) >= 4u )
  {
    v19 = "same";
    if ( !v17 )
      v19 = "different";
    WPP_SF_s(*((_QWORD *)v18 + 2), 88, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v19);
  }
  if ( v49 )
  {
    v32 = v55;
    goto LABEL_137;
  }
  if ( !IsLogonFromUnlockEnabled )
  {
    LastLogonInfo = 5;
    v3[7].dwHighDateTime = 1400;
    v12 = 0;
    goto LABEL_177;
  }
  if ( (unsigned __int8)IsWinStationConnectAndLockDesktopPresent()
    && (unsigned __int8)IsWinStationConnectAndLockDesktopPresent() )
  {
    v58 = 0;
    v60 = 0;
    if ( (unsigned __int8)WinStationGetAllUserSessions(0, TokenInformation, &v58, &v60) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
        v20 = WPP_GLOBAL_Control;
      }
      v5 = 1;
      if ( (*(_BYTE *)v4 & 4) != 0 )
      {
        if ( v20 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v20 + 7) & 0x1000) != 0 && *((_BYTE *)v20 + 25) >= 4u )
          WPP_SF_(*((_QWORD *)v20 + 2), 90, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
        CSession::SetAutoLock(*(_QWORD *)&v3[2], 1, 3);
        *(_DWORD *)(*(_QWORD *)&v3[2] + 400LL) = 1;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
        }
      }
      *(_DWORD *)(*(_QWORD *)&v3[2] + 288LL) = *(_DWORD *)(v58 + 4);
      WinStationFreeUserSessionInfo(v58, v60);
      v58 = 0;
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
    }
  }
  if ( !v5 )
  {
    if ( (*(_BYTE *)v4 & 4) != 0 )
    {
      *(_DWORD *)(*(_QWORD *)&v3[2] + 400LL) = 1;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
      }
    }
    if ( !(unsigned int)AttemptSequentialLogon((struct _WLSM_GLOBAL_CONTEXT *)v3, TokenInformation) )
    {
      v28 = *v3;
      v29 = v3[2];
      ReturnLength = RtlGetActiveConsoleId() != *(_DWORD *)(*(_QWORD *)&v29 + 88LL);
      v30 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))CGlobalStore::StopAndDeleteGlobalTraceLoggingActivity)(
              v28,
              *(unsigned int *)(*(_QWORD *)&v3[2] + 88LL),
              4,
              2);
      if ( v30 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x91D,
          (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\lock.cxx",
          (const char *)(unsigned int)v30,
          ReturnLength);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
      }
      *(_DWORD *)(*(_QWORD *)&v3[2] + 396LL) = 1;
      LastLogonInfo = 5;
      v12 = IsLogonFromUnlockEnabled;
      goto LABEL_177;
    }
    if ( !AttemptAADConnect(
            (struct _WLSM_GLOBAL_CONTEXT *)v3,
            TokenHandle,
            AssignedAccessType == 2,
            SourceLuid,
            TokenInformation) )
    {
      v75 = 0;
      v76 = 0;
      v77 = 0;
      v78 = 0;
      v79 = 0;
      v80 = 0;
      v81 = 0;
      *(struct _FILETIME *)&v75 = *(struct _FILETIME *)((char *)v3 + 52);
      *((struct _LUID *)&v75 + 1) = SourceLuid;
      *(_QWORD *)&v76 = TokenHandle;
      TokenHandle = 0;
      *((struct _FILETIME *)&v76 + 1) = v3[8];
      LODWORD(v80) = IsAuditingLogFull;
      *((_QWORD *)&v80 + 1) = Sid;
      Sid = 0;
      *(_QWORD *)&v81 = __PAIR64__(v61, v51);
      *((_QWORD *)&v81 + 1) = lpMem;
      lpMem = 0;
      v82[0] = v75;
      v82[1] = v76;
      v83 = v87;
      v84 = v80;
      v85 = v81;
      v31 = ((__int64 (__fastcall *)(_QWORD, _QWORD))CGlobalStore::SetPreSwitchUserLogonInfo)(*v3, v82);
      LastLogonInfo = v31;
      if ( !v31 )
      {
        v65 = 33;
        v2 = 2;
        v12 = IsLogonFromUnlockEnabled;
        goto LABEL_177;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v24 = 100;
      v25 = v31;
      goto LABEL_79;
    }
    v32 = 1;
    v55 = 1;
    v74 = 1;
    if ( (unsigned __int8)IsWinStationIsBoundToCacheTerminalPresent()
      && (unsigned int)CandidateAccountManagerPolicy::IsSequentialLogonEnforced()
      && *(_DWORD *)(*(_QWORD *)&v3[4] + 528LL) != 2 )
    {
      v33 = WinStationConsumeCacheSession();
      v62 = v33;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v33);
      }
      if ( v33 )
        WinlogonProvider::ConsumeCacheSessionFailed<unsigned long &>(&v62);
      AssignedAccessType = v54;
    }
    *(_DWORD *)(*(_QWORD *)&v3[4] + 528LL) = 3;
    *(_DWORD *)(*(_QWORD *)&v3[2] + 400LL) = 1;
LABEL_137:
    if ( *(_QWORD *)(*(_QWORD *)v3 + 120LL) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    ((void (__fastcall *)(_QWORD, _QWORD))CGlobalStore::FreeCredentialContext)(*v3, 0);
    if ( (*(_BYTE *)v4 & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
      }
      CSession::SetAutoLock(*(_QWORD *)&v3[2], 1, 3);
      *(_DWORD *)(*(_QWORD *)&v3[2] + 400LL) = 1;
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
LABEL_149:
        if ( AssignedAccessType == 1 )
        {
          if ( v34 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v34 + 7) & 0x1000) != 0 && *((_BYTE *)v34 + 25) >= 4u )
            WPP_SF_(*((_QWORD *)v34 + 2), 104, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
          CSession::SetAutoLock(*(_QWORD *)&v3[2], 2, 5);
        }
        v12 = IsLogonFromUnlockEnabled;
        if ( IsLogonFromUnlockEnabled && !v32 )
        {
          v35 = (struct _LUID *)WLAlloc(0x10u);
          RtlCopyLuid(v35, &SourceLuid);
          v35[1] = (struct _LUID)TokenHandle;
          v36 = TpSimpleTryPost(TransferCredentialsWorkerThread, v35, 0);
          if ( v36 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                105,
                WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids,
                (unsigned int)v36);
            }
          }
          else
          {
            TokenHandle = 0;
          }
        }
        updated = CUser::UpdateLogonDataOnUnlock(
                    *(CUser **)&v3[4],
                    (struct _MSV1_0_INTERACTIVE_PROFILE *)lpMem,
                    v3 + 8,
                    &v87);
        LastLogonInfo = updated;
        if ( updated )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, updated);
          }
          goto LABEL_177;
        }
        LastLogonInfoPolicy = CMachine::GetLastLogonInfoPolicy(*(CMachine **)&v3[1], 0);
        if ( LastLogonInfoPolicy )
        {
          LastLogonInfo = CUser::RetrieveLastLogonInfo(*(CUser **)&v3[4]);
          if ( LastLogonInfo && LastLogonInfoPolicy == 1 )
          {
            v3[7].dwHighDateTime = 2031;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
            }
            goto LABEL_177;
          }
          LastLogonInfo = 0;
        }
        v2 = 1;
        goto LABEL_177;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
    }
    v34 = WPP_GLOBAL_Control;
    goto LABEL_149;
  }
  v3[7].dwHighDateTime = 0;
  v21 = (CUser *)operator new(0x288u);
  if ( v21 )
    v1 = CUser::CUser(v21);
  else
    v1 = 0;
  v73 = v1;
  if ( v1 )
  {
    LastLogonInfo = CUser::Initialize(v1, *(struct CGlobalStore **)v3, *(struct CSession **)&v3[2], v22);
    if ( LastLogonInfo )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v24 = 94;
    }
    else
    {
      LastLogonInfo = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD))CUser::InitializeLogonData)(
                        v1,
                        Sid,
                        SourceLuid,
                        TokenHandle,
                        lpMem,
                        v51,
                        &v3[8],
                        &v87);
      if ( !LastLogonInfo )
      {
        TokenHandle = 0;
        lpMem = 0;
        v26 = CMachine::GetLastLogonInfoPolicy(*(CMachine **)&v3[1], 0);
        if ( v26 && (LastLogonInfo = CUser::RetrieveLastLogonInfo(v1)) != 0 && v26 == 1 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              96,
              WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids,
              LastLogonInfo);
          }
          v3[7].dwHighDateTime = 2031;
          v12 = IsLogonFromUnlockEnabled;
        }
        else
        {
          wil::srwlock::lock_shared(*(_QWORD *)v3 + 64LL, &v58);
          v86[0] = 0;
          if ( (int)((__int64 (__fastcall *)(_QWORD, _QWORD))CGlobalStore::GetGlobalTraceLoggingActivity)(*v3, v86) >= 0 )
          {
            dwLowDateTime = v86[0].dwLowDateTime;
            if ( v86[0] )
            {
              *(_OWORD *)v91 = 0;
              v92 = 0;
              IsAuditingLogFull = 16;
              CMachine::GetName(*(CMachine **)&v3[1], v91, &IsAuditingLogFull);
              *(_OWORD *)&v86[0].dwLowDateTime = 0;
              WLGetTSActivityId(v86);
              if ( (unsigned int)dword_1400CF778 > 5 )
              {
                if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x200000000000LL) )
                {
                  v70 = *((_QWORD *)v1 + 13);
                  v48[0] = (unsigned int)_o__wcsicmp(v70, v91) != 0;
                  v64 = *(_DWORD *)(*(_QWORD *)&v3[2] + 88LL);
                  v71 = 0x1000000;
                  v72 = v86;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
                    v64,
                    (unsigned int)&dword_1400BB2CC,
                    dwLowDateTime + 8,
                    (unsigned int)v86,
                    (__int64)&v72,
                    (__int64)&v71,
                    (__int64)&v64,
                    (__int64)v48,
                    (__int64)&v70);
                }
              }
            }
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v58);
          if ( v54 == 1 )
          {
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
            }
            CSession::SetAutoLock(*(_QWORD *)&v3[2], 2, 5);
          }
          v3[5] = (struct _FILETIME)v1;
          v1 = 0;
          v73 = 0;
          v65 = 32;
          LastLogonInfo = 0;
          v2 = 3;
          v12 = IsLogonFromUnlockEnabled;
        }
        goto LABEL_177;
      }
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v24 = 95;
    }
    v25 = LastLogonInfo;
LABEL_79:
    WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids, v25);
    v12 = IsLogonFromUnlockEnabled;
    goto LABEL_177;
  }
  LastLogonInfo = 14;
  if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_19;
  }
  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids);
  v12 = IsLogonFromUnlockEnabled;
LABEL_177:
  v39 = SystemTimeAsFileTime;
  if ( !*(_QWORD *)&SystemTimeAsFileTime )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v39 = SystemTimeAsFileTime;
  }
  DWORD2(v89) = LastLogonInfo;
  LODWORD(v89) = 1;
  if ( !*(_QWORD *)&v39 )
  {
    v86[0] = 0;
    GetSystemTimeAsFileTime(v86);
    v39 = v86[0];
  }
  v40 = 0x7FFFFFFF;
  if ( (*(_QWORD *)&v39 - *(_QWORD *)&v66) / 0x2710uLL <= 0x7FFFFFFF )
    v40 = (*(_QWORD *)&v39 - *(_QWORD *)&v66) / 0x2710uLL;
  DWORD2(v90) = v40;
  LODWORD(v90) = 1;
  WinSqmAddToStream(0, 6415, 3, &v88);
  if ( v12 && Sid )
    RtlFreeSid(Sid);
  if ( v1 )
    (**(void (__fastcall ***)(CUser *, __int64))v1)(v1, 1);
  v41 = lpMem;
  if ( lpMem )
  {
    if ( v51 )
    {
      if ( v51 != 1 )
      {
        if ( v51 == 2 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v41);
        }
        goto LABEL_195;
      }
      if ( LsaFreeReturnBuffer(lpMem) >= 0 )
        goto LABEL_195;
    }
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
LABEL_195:
  if ( TokenHandle )
    NtClose(TokenHandle);
  if ( LastLogonInfo )
  {
    CGlobalStore::FreeCredentials(*(CGlobalStore **)v3);
    v3[6].dwLowDateTime = LastLogonInfo;
  }
  else
  {
    v43 = v2 - 1;
    if ( v43 )
    {
      v44 = v43 - 1;
      if ( v44 )
      {
        if ( v44 == 1 )
          v3[6].dwLowDateTime = 0;
      }
      else
      {
        v3[6].dwLowDateTime = 5;
      }
    }
    else
    {
      v3[6].dwLowDateTime = 0;
      CGlobalStore::FreeCredentials(*(CGlobalStore **)v3);
    }
  }
  result = 13;
  if ( qword_1400D30C8 )
    return SignalManagerSetSignal(*(PRTL_CRITICAL_SECTION *)qword_1400D30C8);
  return result;
}

```

## disassembly

```asm
0x140044c90  mov     r11, rsp
0x140044c93  mov     [r11+10h], rbx
0x140044c97  mov     [r11+18h], rsi
0x140044c9b  push    rdi
0x140044c9c  push    r12
0x140044c9e  push    r13
0x140044ca0  push    r14
0x140044ca2  push    r15
0x140044ca4  sub     rsp, 2F0h
0x140044cab  mov     rax, cs:__security_cookie
0x140044cb2  xor     rax, rsp
0x140044cb5  mov     [rsp+318h+var_38], rax
0x140044cbd  xor     r15d, r15d
0x140044cc0  mov     r14d, r15d
0x140044cc3  mov     r12d, r15d
0x140044cc6  mov     rsi, [rcx+8]
0x140044cca  mov     rax, [rsi]
0x140044ccd  mov     r13, [rax+70h]
0x140044cd1  mov     [r11-298h], r15
0x140044cd8  mov     [rsp+318h+TokenHandle], r15
0x140044cdd  mov     [r11-288h], r15
0x140044ce4  mov     [r11-268h], r15d
0x140044ceb  mov     [rsp+318h+var_29C], r15d
0x140044cf0  xorps   xmm0, xmm0
0x140044cf3  movups  xmmword ptr [rsp+318h+var_118.PagedPoolLimit], xmm0
0x140044cfb  movups  xmmword ptr [rsp+318h+var_118.MinimumWorkingSetSize], xmm0
0x140044d03  movups  xmmword ptr [rsp+318h+var_118.PagefileLimit], xmm0
0x140044d0b  mov     [r11-260h], r15d
0x140044d12  mov     [rsp+318h+var_2AC], r15d
0x140044d17  mov     edi, r15d
0x140044d1a  mov     ebx, 7
0x140044d1f  mov     [r11-250h], r15
0x140044d26  mov     [r11-248h], r15
0x140044d2d  lea     rcx, [r11-250h]; lpSystemTimeAsFileTime
0x140044d34  call    cs:__imp_GetSystemTimeAsFileTime
0x140044d3a  xorps   xmm0, xmm0
0x140044d3d  movups  [rsp+318h+var_E8], xmm0
0x140044d45  movups  [rsp+318h+var_D8], xmm0
0x140044d4d  movups  [rsp+318h+var_C8], xmm0
0x140044d55  mov     ecx, 1; this
0x140044d5a  mov     [rsp+318h+var_2A0], ecx
0x140044d5e  mov     [rsp+318h+var_270], r15d
0x140044d66  test    byte ptr [r13+0], 4
0x140044d6b  jz      short loc_140044D73
0x140044d6d  mov     [rsp+318h+var_2B8], ecx
0x140044d71  jmp     short loc_140044D92
0x140044d73  mov     rax, [rsi+20h]
0x140044d77  cmp     [rax+210h], r15d
0x140044d7e  jz      short loc_140044D86
0x140044d80  mov     [rsp+318h+var_2B8], ecx
0x140044d84  jmp     short loc_140044D92
0x140044d86  mov     rdx, rsi; void *
0x140044d89  call    ?IsLogonFromUnlockEnabled@CSession@@QEAAHPEAX@Z; CSession::IsLogonFromUnlockEnabled(void *)
0x140044d8e  mov     [rsp+318h+var_2B8], eax
0x140044d92  mov     [rsp+318h+var_28C], r15d
0x140044d9a  lea     rax, WPP_GLOBAL_Control
0x140044da1  mov     rcx, cs:WPP_GLOBAL_Control
0x140044da8  cmp     rcx, rax
0x140044dab  jz      short loc_140044DD1
0x140044dad  test    dword ptr [rcx+1Ch], 100h
0x140044db4  jz      short loc_140044DD1
0x140044db6  cmp     byte ptr [rcx+19h], 4
0x140044dba  jb      short loc_140044DD1
0x140044dbc  mov     edx, 54h ; 'T'
0x140044dc1  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140044dc8  mov     rcx, [rcx+10h]
0x140044dcc  call    WPP_SF_
0x140044dd1  mov     dword ptr [rsp+318h+var_E8+8], 1
0x140044ddc  mov     dword ptr [rsp+318h+var_E8], 1
0x140044de7  lea     rcx, WLDiagEvt_Unlock_Start; struct _EVENT_DESCRIPTOR *
0x140044dee  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140044df3  call    ?IsBootToCloudModeRegistryCheck@CloudPCHelpers@@YA_NXZ; CloudPCHelpers::IsBootToCloudModeRegistryCheck(void)
0x140044df8  mov     ecx, 1BE4h
0x140044dfd  mov     edx, 3EDh
0x140044e02  test    al, al
0x140044e04  cmovz   ecx, edx
0x140044e07  xor     r9d, r9d
0x140044e0a  mov     edx, 2
0x140044e0f  mov     r8d, 10h
0x140044e15  call    ?WlDisplayStatusByResourceId@@YAKIW4_WLUI_STATE@@KPEAVCUser@@@Z; WlDisplayStatusByResourceId(uint,_WLUI_STATE,ulong,CUser *)
0x140044e1a  mov     dword ptr [rsi+3Ch], 0
0x140044e21  cmp     [rsp+318h+var_2B8], 0
0x140044e26  jz      short loc_140044E94
0x140044e28  call    CreateLogonSid
0x140044e2d  mov     [rsp+318h+Sid], rax
0x140044e35  test    rax, rax
0x140044e38  jnz     short loc_140044E84
0x140044e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e41  lea     rdx, WPP_GLOBAL_Control
0x140044e48  cmp     rcx, rdx
0x140044e4b  jz      short loc_140044E71
0x140044e4d  test    dword ptr [rcx+1Ch], 1000h
0x140044e54  jz      short loc_140044E71
0x140044e56  cmp     byte ptr [rcx+19h], 2
0x140044e5a  jb      short loc_140044E71
0x140044e5c  mov     edx, 55h ; 'U'
0x140044e61  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140044e68  mov     rcx, [rcx+10h]
0x140044e6c  call    WPP_SF_
0x140044e71  mov     ebx, 0Eh
0x140044e76  mov     [rsp+318h+var_2B4], ebx
0x140044e7a  mov     r13d, [rsp+318h+var_2B8]
0x140044e7f  jmp     loc_140045CB0
0x140044e84  mov     ebx, 2
0x140044e89  call    ?IsAuditingLogFull@CMachine@@QEAAHXZ; CMachine::IsAuditingLogFull(void)
0x140044e8e  mov     [rsp+318h+var_29C], eax
0x140044e92  jmp     short loc_140044EBE
0x140044e94  mov     rcx, [rsi+20h]
0x140044e98  mov     rax, [rcx+78h]
0x140044e9c  mov     [rsp+318h+Sid], rax
0x140044ea4  mov     eax, [rcx+80h]
0x140044eaa  mov     [rsp+318h+SourceLuid.LowPart], eax
0x140044eb1  mov     eax, [rcx+84h]
0x140044eb7  mov     [rsp+318h+SourceLuid.HighPart], eax
0x140044ebe  lea     rax, [rsi+38h]
0x140044ec2  lea     rcx, [rsi+34h]
0x140044ec6  lea     rdx, [rsp+318h+var_270]
0x140044ece  mov     [rsp+318h+var_2C0], rdx; int *
0x140044ed3  mov     [rsp+318h+var_2C8], rax; int *
0x140044ed8  mov     [rsp+318h+var_2D0], rcx; int *
0x140044edd  lea     rax, [rsp+318h+var_268]
0x140044ee5  mov     [rsp+318h+var_2D8], rax; unsigned int *
0x140044eea  lea     rax, [rsp+318h+lpMem]
0x140044ef2  mov     [rsp+318h+var_2E0], rax; void **
0x140044ef7  lea     rax, [rsp+318h+var_118]
0x140044eff  mov     [rsp+318h+var_2E8], rax; struct _QUOTA_LIMITS *
0x140044f04  lea     rax, [rsp+318h+TokenHandle]
0x140044f09  mov     [rsp+318h+var_2F0], rax; void **
0x140044f0e  lea     rax, [rsp+318h+SourceLuid]
0x140044f16  mov     [rsp+318h+ReturnLength], rax; struct _LUID *
0x140044f1b  mov     r9, r13; struct _CRED_PROV_CREDENTIAL *
0x140044f1e  mov     r8, [rsp+318h+Sid]; void *
0x140044f26  mov     edx, ebx; enum _SECURITY_LOGON_TYPE
0x140044f28  mov     rcx, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x140044f2b  call    ?AuthenticateUser@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@W4_SECURITY_LOGON_TYPE@@PEAXPEAU_CRED_PROV_CREDENTIAL@@PEAU_LUID@@PEAPEAXPEAU_QUOTA_LIMITS@@5PEAKPEAJ8PEAH@Z; AuthenticateUser(_WLSM_GLOBAL_CONTEXT *,_SECURITY_LOGON_TYPE,void *,_CRED_PROV_CREDENTIAL *,_LUID *,void * *,_QUOTA_LIMITS *,void * *,ulong *,long *,long *,int *)
0x140044f30  mov     ebx, eax
0x140044f32  mov     [rsp+318h+var_2B4], eax
0x140044f36  test    eax, eax
0x140044f38  jz      short loc_140044F8A
0x140044f3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140044f41  lea     rdx, WPP_GLOBAL_Control
0x140044f48  cmp     rcx, rdx
0x140044f4b  jz      loc_140044E7A
0x140044f51  test    dword ptr [rcx+1Ch], 4000h
0x140044f58  jz      loc_140044E7A
0x140044f5e  cmp     byte ptr [rcx+19h], 2
0x140044f62  jb      loc_140044E7A
0x140044f68  mov     edx, 56h ; 'V'
0x140044f6d  mov     r9d, eax
0x140044f70  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140044f77  mov     rcx, [rcx+10h]
0x140044f7b  call    WPP_SF_d
0x140044f80  mov     r13d, [rsp+318h+var_2B8]
0x140044f85  jmp     loc_140045CB0
0x140044f8a  mov     eax, [rsp+318h+var_270]
0x140044f91  neg     eax
0x140044f93  sbb     eax, eax
0x140044f95  add     eax, 2
0x140044f98  mov     [rsp+318h+var_2A0], eax
0x140044f9c  mov     [rsp+318h+var_240], eax
0x140044fa3  mov     rcx, [rsp+318h+TokenHandle]
0x140044fa8  call    ?GetAssignedAccessType@@YA?AW4AssignedAccessType@@PEAX@Z; GetAssignedAccessType(void *)
0x140044fad  mov     ebx, eax
0x140044faf  mov     [rsp+318h+var_290], eax
0x140044fb6  lea     rax, [rsp+318h+var_260]
0x140044fbe  mov     [rsp+318h+ReturnLength], rax; ReturnLength
0x140044fc3  mov     r9d, 54h ; 'T'; TokenInformationLength
0x140044fc9  lea     r8, [rsp+318h+TokenInformation]; TokenInformation
0x140044fd1  mov     edx, 1; TokenInformationClass
0x140044fd6  mov     rcx, [rsp+318h+TokenHandle]; TokenHandle
0x140044fdb  call    cs:__imp_NtQueryInformationToken
0x140044fe1  test    eax, eax
0x140044fe3  js      short loc_140045019
0x140044fe5  mov     rdx, [rsi+20h]
0x140044fe9  mov     rdx, [rdx+0A0h]; Sid2
0x140044ff0  mov     rcx, [rsp+318h+TokenInformation]; Sid1
0x140044ff8  call    cs:__imp_RtlEqualSid
0x140044ffe  xor     edx, edx
0x140045000  test    al, al
0x140045002  setnz   dl
0x140045005  mov     [rsp+318h+var_2AC], edx
0x140045009  mov     [rsp+318h+var_23C], edx
0x140045010  mov     rcx, cs:WPP_GLOBAL_Control
0x140045017  jmp     short loc_14004505E
0x140045019  mov     rcx, cs:WPP_GLOBAL_Control
0x140045020  lea     rdx, WPP_GLOBAL_Control
0x140045027  cmp     rcx, rdx
0x14004502a  jz      short loc_14004505A
0x14004502c  test    dword ptr [rcx+1Ch], 4000h
0x140045033  jz      short loc_14004505A
0x140045035  cmp     byte ptr [rcx+19h], 4
0x140045039  jb      short loc_14004505A
0x14004503b  mov     edx, 57h ; 'W'
0x140045040  mov     r9d, eax
0x140045043  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x14004504a  mov     rcx, [rcx+10h]
0x14004504e  call    WPP_SF_d
0x140045053  mov     rcx, cs:WPP_GLOBAL_Control
0x14004505a  mov     edx, [rsp+318h+var_2AC]
0x14004505e  lea     rax, WPP_GLOBAL_Control
0x140045065  cmp     rcx, rax
0x140045068  jz      short loc_1400450A2
0x14004506a  test    dword ptr [rcx+1Ch], 4000h
0x140045071  jz      short loc_1400450A2
0x140045073  cmp     byte ptr [rcx+19h], 4
0x140045077  jb      short loc_1400450A2
0x140045079  lea     r9, aSame; "same"
0x140045080  lea     rax, aDifferent; "different"
0x140045087  test    edx, edx
0x140045089  cmovz   r9, rax
0x14004508d  mov     edx, 58h ; 'X'
0x140045092  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140045099  mov     rcx, [rcx+10h]
0x14004509d  call    WPP_SF_s
0x1400450a2  cmp     [rsp+318h+var_2AC], 0
0x1400450a7  jnz     loc_140045A2B
0x1400450ad  cmp     [rsp+318h+var_2B8], 0
0x1400450b2  jnz     short loc_1400450CE
0x1400450b4  mov     ebx, 5
0x1400450b9  mov     [rsp+318h+var_2B4], ebx
0x1400450bd  mov     dword ptr [rsi+3Ch], 578h
0x1400450c4  mov     r13d, [rsp+318h+var_2B8]
0x1400450c9  jmp     loc_140045CB0
0x1400450ce  call    IsWinStationConnectAndLockDesktopPresent
0x1400450d3  test    al, al
0x1400450d5  jz      loc_14004525C
0x1400450db  call    IsWinStationConnectAndLockDesktopPresent
0x1400450e0  test    al, al
0x1400450e2  jz      loc_14004525C
0x1400450e8  xor     eax, eax
0x1400450ea  mov     [rsp+318h+var_278], rax
0x1400450f2  mov     [rsp+318h+var_26C], eax
0x1400450f9  lea     r9, [rsp+318h+var_26C]
0x140045101  lea     r8, [rsp+318h+var_278]
0x140045109  mov     rdx, [rsp+318h+TokenInformation]
0x140045111  xor     ecx, ecx
0x140045113  call    cs:__imp_WinStationGetAllUserSessions
0x140045119  test    al, al
0x14004511b  jz      loc_140045225
0x140045121  mov     rcx, cs:WPP_GLOBAL_Control
0x140045128  lea     rax, WPP_GLOBAL_Control
0x14004512f  cmp     rcx, rax
0x140045132  jz      short loc_140045166
0x140045134  test    dword ptr [rcx+1Ch], 1000h
0x14004513b  jz      short loc_140045166
0x14004513d  cmp     byte ptr [rcx+19h], 4
0x140045141  jb      short loc_140045166
0x140045143  mov     edx, 59h ; 'Y'
0x140045148  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x14004514f  mov     rcx, [rcx+10h]
0x140045153  call    WPP_SF_
0x140045158  mov     rcx, cs:WPP_GLOBAL_Control
0x14004515f  lea     rax, WPP_GLOBAL_Control
0x140045166  mov     edi, 1
0x14004516b  test    byte ptr [r13+0], 4
0x140045170  jz      short loc_1400451ED
0x140045172  cmp     rcx, rax
0x140045175  jz      short loc_14004519B
0x140045177  test    dword ptr [rcx+1Ch], 1000h
0x14004517e  jz      short loc_14004519B
0x140045180  cmp     byte ptr [rcx+19h], 4
0x140045184  jb      short loc_14004519B
0x140045186  mov     edx, 5Ah ; 'Z'
0x14004518b  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x140045192  mov     rcx, [rcx+10h]
0x140045196  call    WPP_SF_
0x14004519b  mov     edx, edi
0x14004519d  mov     r8d, 3
0x1400451a3  mov     rcx, [rsi+10h]
0x1400451a7  call    ?SetAutoLock@CSession@@QEAAXW4AutoLockType@1@W4AutoLockStartReason@1@@Z; CSession::SetAutoLock(CSession::AutoLockType,CSession::AutoLockStartReason)
0x1400451ac  mov     rax, [rsi+10h]
0x1400451b0  mov     [rax+190h], edi
0x1400451b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400451bd  lea     rax, WPP_GLOBAL_Control
0x1400451c4  cmp     rcx, rax
0x1400451c7  jz      short loc_1400451ED
0x1400451c9  test    dword ptr [rcx+1Ch], 1000h
0x1400451d0  jz      short loc_1400451ED
0x1400451d2  cmp     byte ptr [rcx+19h], 5
0x1400451d6  jb      short loc_1400451ED
0x1400451d8  mov     edx, 5Bh ; '['
0x1400451dd  lea     r8, WPP_1f80ccb0ea51320fbaee2b4e4d0a6e34_Traceguids
0x1400451e4  mov     rcx, [rcx+10h]
0x1400451e8  call    WPP_SF_
0x1400451ed  mov     rdx, [rsi+10h]
0x1400451f1  mov     rax, [rsp+318h+var_278]
0x1400451f9  mov     ecx, [rax+4]
0x1400451fc  mov     [rdx+120h], ecx
0x140045202  mov     edx, [rsp+318h+var_26C]
0x140045209  mov     rcx, [rsp+318h+var_278]
0x140045211  call    cs:__imp_WinStationFreeUserSessionInfo
0x140045217  mov     [rsp+318h+var_278], 0
0x140045223  jmp     short loc_14004525C
0x140045225  mov     rcx, cs:WPP_GLOBAL_Control
0x14004522c  lea     rax, WPP_GLOBAL_Control
0x140045233  cmp     rcx, rax
0x140045236  jz      short loc_14004525C
0x140045238  test    dword ptr [rcx+1Ch], 1000h
0x14004523f  jz      short loc_14004525C
0x140045241  cmp     byte ptr [rcx+19h], 4
  ... truncated ...
```
