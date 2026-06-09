# WLGeneric_Authenticating_Execute(_StateMachineCallContext *)

- ea: `0x14006cf20`
- end: `0x14006dcdf`
- name: `?WLGeneric_Authenticating_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `3519`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `54`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001e38`
- `0x1400057f4`
- `0x1400060d0`
- `0x140008d74`
- `0x14001202c`
- `0x140012c24`
- `0x140012f40`
- `0x140013050`
- `0x140014370`
- `0x1400155f0`
- `0x140016f30`
- `0x14001a200`
- `0x14001a3a8`
- `0x14002aae0`
- `0x1400333b0`
- `0x140034700`
- `0x140035698`
- `0x1400374d4`
- `0x140037608`
- `0x1400378d0`
- `0x140037b00`
- `0x140037b84`
- `0x140039458`
- `0x1400396fc`
- `0x14003a5d0`
- `0x14003aca4`
- `0x14003af90`
- `0x14003ba50`
- `0x14003bec8`
- `0x14003e630`
- `0x14003eef4`
- `0x14003f584`
- `0x140041c34`
- `0x14004282c`
- `0x140044800`
- `0x140045ec4`
- `0x14004ea3c`
- `0x14004eb98`
- `0x14004effc`
- `0x140051370`
- `0x140053398`
- `0x140053720`
- `0x140055158`
- `0x140056230`
- `0x140056348`
- `0x14005697c`
- `0x1400687c8`
- `0x140068bbc`
- `0x14006cf20`
- `0x140073914`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006da78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006da78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d662`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006d662`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14006d1c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14006d1c7`
- `ntdll!WinSqmAddToStream` at `0x14006dc9a`
- `ntdll!WinSqmAddToStream` at `0x14006dc9a`
- `ntdll!NtClose` at `0x14006dbf1`
- `ntdll!NtClose` at `0x14009f76f`
- `ntdll!NtClose` at `0x14006dbf1`
- `ntdll!NtClose` at `0x14009f76f`
- `SspiCli!LsaFreeReturnBuffer` at `0x14006dbb0`
- `SspiCli!LsaFreeReturnBuffer` at `0x14006dc1d`
- `SspiCli!LsaFreeReturnBuffer` at `0x14009f721`
- `SspiCli!LsaFreeReturnBuffer` at `0x14009f79a`
- `SspiCli!LsaFreeReturnBuffer` at `0x14006dbb0`
- `SspiCli!LsaFreeReturnBuffer` at `0x14006dc1d`
- `SspiCli!LsaFreeReturnBuffer` at `0x14009f721`
- `SspiCli!LsaFreeReturnBuffer` at `0x14009f79a`
- `SspiCli!LsaGetLogonSessionData` at `0x14006d70c`
- `SspiCli!LsaGetLogonSessionData` at `0x14006d70c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14006d5fc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14006d5fc`
- `ext-ms-win-session-winlogon-l1-1-0!EnableDisableElevationForSessionWorker` at `0x14006d770`
- `ext-ms-win-session-winlogon-l1-1-0!EnableDisableElevationForSessionWorker` at `0x14006d770`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14006d580`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x14006d580`
- `ext-ms-win-winlogon-mincreds-l1-1-0!MinCredGetLogonType` at `0x14006d161`
- `ext-ms-win-winlogon-mincreds-l1-1-0!MinCredGetLogonType` at `0x14006d161`

## pseudocode

```c
unsigned int __fastcall WLGeneric_Authenticating_Execute(struct _StateMachineCallContext *a1)
{
  int v2; // edx
  __int64 v3; // r9
  struct _FILETIME *v4; // rsi
  __int64 v5; // rbx
  struct _CRED_PROV_CREDENTIAL *v6; // r13
  int v7; // edi
  CUser *v8; // r15
  DWORD *p_dwHighDateTime; // r12
  CMachine *v10; // rcx
  CloudPCHelpers *v11; // rcx
  __int64 v12; // rcx
  bool v13; // al
  __int64 v14; // r9
  unsigned int LastLogonInfo; // ebx
  enum _SECURITY_LOGON_TYPE LogonType; // ebx
  CMachine *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // r9
  __int64 v20; // r9
  CUser *v21; // rax
  __int64 v22; // r9
  CUser *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  CUser *v26; // rcx
  __int64 v27; // rdx
  int v28; // r13d
  __int64 v29; // r9
  int IsCandidateUser; // eax
  int v31; // ecx
  int v32; // eax
  int v33; // ebx
  DWORD LastError; // eax
  NTSTATUS LogonSessionData; // eax
  __int64 v36; // rcx
  __int64 v37; // r9
  unsigned int v38; // eax
  CUser *v39; // rcx
  __int64 v40; // rdx
  CUser *v41; // rcx
  __int64 v42; // rdx
  unsigned int LastLogonInfoPolicy; // r13d
  int v44; // ebx
  unsigned int v45; // edi
  __int64 v46; // r9
  int v48; // [rsp+60h] [rbp-168h]
  bool v49[4]; // [rsp+68h] [rbp-160h] BYREF
  unsigned int v50; // [rsp+6Ch] [rbp-15Ch] BYREF
  int v51; // [rsp+70h] [rbp-158h]
  int IsAuditingLogFull; // [rsp+74h] [rbp-154h] BYREF
  int v53; // [rsp+78h] [rbp-150h]
  int v54; // [rsp+7Ch] [rbp-14Ch]
  unsigned int AssignedAccessType; // [rsp+80h] [rbp-148h] BYREF
  PVOID Buffer; // [rsp+88h] [rbp-140h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp-138h] BYREF
  void *LogonSid; // [rsp+98h] [rbp-130h]
  HANDLE Handle; // [rsp+A0h] [rbp-128h] BYREF
  int v60; // [rsp+A8h] [rbp-120h] BYREF
  unsigned int v61; // [rsp+ACh] [rbp-11Ch] BYREF
  int v62; // [rsp+B0h] [rbp-118h] BYREF
  int v63; // [rsp+B4h] [rbp-114h]
  struct _LUID LogonId; // [rsp+B8h] [rbp-110h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+C0h] [rbp-108h] BYREF
  CUser *v66; // [rsp+C8h] [rbp-100h]
  __int64 v67; // [rsp+D0h] [rbp-F8h] BYREF
  __int64 v68; // [rsp+D8h] [rbp-F0h] BYREF
  _QWORD v69[2]; // [rsp+E0h] [rbp-E8h] BYREF
  _BYTE v70[16]; // [rsp+F0h] [rbp-D8h] BYREF
  __int128 v71; // [rsp+100h] [rbp-C8h] BYREF
  struct _QUOTA_LIMITS v72; // [rsp+110h] [rbp-B8h] BYREF
  __int128 v73; // [rsp+140h] [rbp-88h] BYREF
  __int128 v74; // [rsp+150h] [rbp-78h]
  __int128 v75; // [rsp+160h] [rbp-68h]
  unsigned __int16 v76[8]; // [rsp+170h] [rbp-58h] BYREF
  __int128 v77; // [rsp+180h] [rbp-48h]

  WLEventWrite(&WLEvt_AuthenticateUser_Start);
  Timer::Timer((Timer *)v70, v2);
  v73 = 0;
  v74 = 0;
  v75 = 0;
  LODWORD(v73) = 1;
  LogonSid = 0;
  LogonId = 0;
  Handle = 0;
  v48 = 0;
  LODWORD(v71) = 0;
  v63 = 0;
  Buffer = 0;
  v61 = 0;
  v51 = 1;
  v54 = 1;
  memset(&v72, 0, sizeof(v72));
  ppLogonSessionData = 0;
  v4 = (struct _FILETIME *)*((_QWORD *)a1 + 1);
  v69[1] = v4;
  v5 = *(_QWORD *)(*(_QWORD *)v4 + 144LL);
  v6 = *(struct _CRED_PROV_CREDENTIAL **)(*(_QWORD *)v4 + 112LL);
  v7 = *(_DWORD *)v6 & 8;
  v8 = 0;
  v66 = 0;
  v60 = 0;
  v50 = 0;
  p_dwHighDateTime = &v4[6].dwHighDateTime;
  v4[6].dwHighDateTime = 0;
  v4[7] = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v3);
  }
  CMachine::RegQueryDWORD(
    v10,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
    L"ForceAutoLockOnLogon",
    v50,
    &v50);
  if ( v7 )
  {
    v12 = 1013;
  }
  else
  {
    if ( v50 )
      goto LABEL_11;
    v13 = CloudPCHelpers::IsBootToCloudModeRegistryCheck(v11);
    v12 = 7140;
    if ( !v13 )
      v12 = 1002;
  }
  WlDisplayStatusByResourceId(v12, 3u, 0x10u, 0);
LABEL_11:
  if ( v5 )
  {
    *p_dwHighDateTime = *(_DWORD *)v5;
    v4[7].dwLowDateTime = *(_DWORD *)(v5 + 4);
    LogonId = *(struct _LUID *)(v5 + 8);
    Handle = *(HANDLE *)(v5 + 16);
    *(_QWORD *)(v5 + 16) = 0;
    v4[8] = *(struct _FILETIME *)(v5 + 24);
    v72 = *(struct _QUOTA_LIMITS *)(v5 + 32);
    IsAuditingLogFull = *(_DWORD *)(v5 + 80);
    LogonSid = *(void **)(v5 + 88);
    *(_QWORD *)(v5 + 88) = 0;
    v51 = 0;
    v54 = 0;
    v61 = *(_DWORD *)(v5 + 100);
    Buffer = *(PVOID *)(v5 + 104);
    *(_QWORD *)(v5 + 104) = 0;
  }
  else
  {
    LogonSid = (void *)CreateLogonSid();
    if ( !LogonSid )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v14);
      }
      LastLogonInfo = 14;
      *p_dwHighDateTime = -1073283058;
      goto LABEL_154;
    }
    LogonType = Interactive;
    if ( !(unsigned int)CSession::IsBoundToConsole(*(CSession **)&v4[2]) )
      LogonType = RemoteInteractive;
    v53 = LogonType;
    if ( !(unsigned __int8)IsWinStationConnectAndLockDesktopPresent() && (unsigned __int8)IsMinCredGetLogonTypePresent() )
    {
      LogonType = (unsigned int)MinCredGetLogonType();
      v53 = LogonType;
    }
    v17 = (CMachine *)v4[2];
    if ( *((_DWORD *)v17 + 37) == 3
      || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
      && *(_DWORD *)(*(_QWORD *)&v4[2] + 148LL) == 4 )
    {
      LogonType = Interactive;
      v53 = 2;
    }
    if ( *(_DWORD *)(*(_QWORD *)&v4[2] + 248LL) || v7 )
    {
      LogonType = Interactive;
      v53 = 2;
    }
    IsAuditingLogFull = CMachine::IsAuditingLogFull(v17);
    GetSystemTimeAsFileTime(v4 + 8);
    LastLogonInfo = AuthenticateUser(
                      (struct _WLSM_GLOBAL_CONTEXT *)v4,
                      LogonType,
                      LogonSid,
                      v6,
                      &LogonId,
                      &Handle,
                      &v72,
                      &Buffer,
                      &v61,
                      (int *)&v4[6].dwHighDateTime,
                      (int *)&v4[7],
                      &v60);
    v51 = 2 - (v60 != 0);
    v54 = v51;
    CleanupAutoLogonCredentials((struct _WLSM_GLOBAL_CONTEXT *)v4, LastLogonInfo, v50 != 0, v18);
    if ( LastLogonInfo )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
          LastLogonInfo);
      }
      goto LABEL_154;
    }
  }
  AssignedAccessType = GetAssignedAccessType(Handle);
  if ( (*(_BYTE *)v6 & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v19);
    }
    CSession::SetAutoLock(*(_QWORD *)&v4[2], 2, 2);
    *(_DWORD *)(*(_QWORD *)&v4[2] + 400LL) = 1;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v20);
    }
  }
  v21 = (CUser *)operator new(0x288u);
  if ( v21 )
    v8 = CUser::CUser(v21);
  else
    v8 = 0;
  v66 = v8;
  if ( !v8 )
  {
    LastLogonInfo = 14;
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_154;
    }
    v24 = 60;
    goto LABEL_53;
  }
  v25 = CUser::Initialize(v8, *(struct CGlobalStore **)v4, *(struct CSession **)&v4[2], v22);
  LastLogonInfo = v25;
  if ( v25 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_154;
    }
    v27 = 61;
    goto LABEL_59;
  }
  v25 = CUser::InitializeLogonData(
          (__int64)v8,
          LogonSid,
          *(_QWORD *)&LogonId,
          Handle,
          (__int64)Buffer,
          v51,
          &v4[8],
          &v72);
  LastLogonInfo = v25;
  if ( v25 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_154;
    }
    v27 = 62;
LABEL_59:
    WPP_SF_d(*((_QWORD *)v26 + 2), v27, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v25);
    goto LABEL_154;
  }
  v28 = 1;
  v48 = 1;
  if ( (unsigned __int8)IsCamCleanupDisardedCandidateAccountsPresent() )
  {
    v62 = 0;
    IsCandidateUser = CamIsCandidateUser(*((_QWORD *)v8 + 20), &v62);
    if ( (IsCandidateUser & 0x1FFF0000) == 0x70000 )
      IsCandidateUser = (unsigned __int16)IsCandidateUser;
    if ( !IsCandidateUser )
    {
      if ( v62 )
      {
        *((_DWORD *)v8 + 132) = 1;
        if ( !(unsigned int)CandidateAccountManagerPolicy::IsAutoAadConnectEnabled() )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
          if ( StringSid )
            wil::details::close_invoke_helper<1,void * (*)(void *),&void * LocalFree(void *),unsigned short *>::close_reset(StringSid);
          StringSid = 0;
          if ( ConvertSidToStringSidW(*((PSID *)v8 + 20), &StringSid) )
          {
            v32 = SetCamCxhOnlyUser(v31, StringSid);
            v33 = v32;
            if ( v32 < 0 )
              MicrosoftTelemetryAssertTriggeredArgs("useroobehelper", (unsigned int)v32, 0);
            if ( v33 < 0
              && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                63,
                WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                (unsigned int)v33);
            }
          }
          else
          {
            LastError = GetLastError();
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                64,
                WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                LastError);
            }
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        }
      }
    }
  }
  if ( AssignedAccessType == 1 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v29);
    }
    CSession::SetAutoLock(*(_QWORD *)&v4[2], 2, 4);
  }
  LogonSessionData = LsaGetLogonSessionData(&LogonId, &ppLogonSessionData);
  if ( LogonSessionData < 0 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        71,
        WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
        (unsigned int)LogonSessionData);
    }
  }
  else if ( (ppLogonSessionData->UserFlags & 0x40000) != 0 && (unsigned __int8)IsWinLogonExtPresent(v36) )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v37);
    }
    v38 = EnableDisableElevationForSessionWorker(*(unsigned int *)(*(_QWORD *)&v4[2] + 88LL), 0);
    if ( v38 )
    {
      if ( v38 == 5 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, 5);
        }
        LastLogonInfo = 5;
        goto LABEL_155;
      }
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v38);
      }
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)&v4[2] + 316LL) = 1;
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v40 = 67;
LABEL_118:
        WPP_SF_(*((_QWORD *)v39 + 2), v40, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v37);
      }
    }
  }
  else
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v40 = 70;
      goto LABEL_118;
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)v4 + 200LL)
    && CMachine::GetMachinePolicy(*(CMachine **)&v4[1], L"SafeModeBlockNonAdmins", 0)
    && !*((_DWORD *)v8 + 38) )
  {
    LastLogonInfo = 5;
    v4[7].dwHighDateTime = 2037;
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_155;
    }
    v42 = 72;
    goto LABEL_130;
  }
  if ( IsAuditingLogFull && !*((_DWORD *)v8 + 38) )
  {
    LastLogonInfo = 5;
    v4[7].dwHighDateTime = 2030;
    v41 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_155;
    }
    v42 = 73;
LABEL_130:
    WPP_SF_(*((_QWORD *)v41 + 2), v42, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v37);
LABEL_155:
    v45 = v71;
    goto LABEL_156;
  }
  LastLogonInfoPolicy = CMachine::GetLastLogonInfoPolicy(*(CMachine **)&v4[1], 0);
  if ( LastLogonInfoPolicy )
  {
    LastLogonInfo = CUser::RetrieveLastLogonInfo(v8);
    if ( LastLogonInfo )
    {
      if ( LastLogonInfoPolicy == 1 )
      {
        v4[7].dwHighDateTime = 2031;
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_154;
        }
        v24 = 74;
LABEL_53:
        WPP_SF_(*((_QWORD *)v23 + 2), v24, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v22);
LABEL_154:
        v28 = v48;
        goto LABEL_155;
      }
    }
  }
  wil::srwlock::lock_shared(*(_QWORD *)v4 + 64LL, &StringSid);
  *(_QWORD *)&v71 = 0;
  if ( (int)((__int64 (__fastcall *)(_QWORD, _QWORD))CGlobalStore::GetGlobalTraceLoggingActivity)(*v4, &v71) >= 0 )
  {
    v44 = v71;
    if ( (_QWORD)v71 )
    {
      *(_OWORD *)v76 = 0;
      v77 = 0;
      AssignedAccessType = 16;
      CMachine::GetName(*(CMachine **)&v4[1], v76, &AssignedAccessType);
      v71 = 0;
      WLGetTSActivityId(&v71);
      if ( (unsigned int)dword_1400CF778 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x200000000000LL) )
        {
          v67 = *((_QWORD *)v8 + 13);
          v49[0] = (unsigned int)_o__wcsicmp(v67, v76) != 0;
          IsAuditingLogFull = *(_DWORD *)(*(_QWORD *)&v4[2] + 88LL);
          v68 = 0x1000000;
          v69[0] = &v71;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
            IsAuditingLogFull,
            (unsigned int)&unk_1400BC1D0,
            v44 + 8,
            (unsigned int)&v71,
            (__int64)v69,
            (__int64)&v68,
            (__int64)&IsAuditingLogFull,
            (__int64)v49,
            (__int64)&v67);
        }
      }
    }
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&StringSid);
  v45 = 32;
  v63 = 32;
  UHReportBootGood();
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v46);
  }
  AsyncLogoffSupportSetUser(*((void **)v8 + 17));
  v4[4] = (struct _FILETIME)v8;
  v8 = 0;
  v66 = 0;
  LastLogonInfo = 0;
  v28 = 1;
LABEL_156:
  CGlobalStore::FreeInternalSwitchUserLogonInfo(
    *(CGlobalStore **)v4,
    (struct CGlobalStore::_INTERNAL_SWITCH_USER_LOGON_INFO **)(*(_QWORD *)v4 + 144LL));
  if ( LogonSid )
    DeleteLogonSid(LogonSid);
  if ( ppLogonSessionData )
    LsaFreeReturnBuffer(ppLogonSessionData);
  if ( v45 != 32 )
    CGlobalStore::FreeCredentials(*(CGlobalStore **)v4);
  if ( LastLogonInfo )
  {
    if ( v8 )
      (**(void (__fastcall ***)(CUser *, __int64))v8)(v8, 1);
    if ( !v28 )
    {
      if ( Handle )
        NtClose(Handle);
      if ( Buffer )
      {
        if ( v51 )
        {
          if ( v51 == 1 )
          {
            if ( LsaFreeReturnBuffer(Buffer) < 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          else if ( v51 == 2 )
          {
            MemoryFree(Buffer);
          }
        }
        else
        {
          UHHeapFree(&Buffer);
        }
      }
    }
  }
  WLEventWrite(&WLEvt_AuthenticateUser_Stop, LastLogonInfo);
  Timer::Stop((Timer *)v70);
  DWORD2(v74) = LastLogonInfo;
  LODWORD(v74) = 1;
  DWORD2(v75) = Timer::ElapsedULONG((Timer *)v70);
  LODWORD(v75) = 1;
  WinSqmAddToStream(0, 6415, 3, &v73);
  v4[6].dwLowDateTime = LastLogonInfo;
  if ( LastLogonInfo )
    v45 = 1;
  return WlStateMachineSetSignal(v45, 0);
}

```

## disassembly

```asm
0x14006cf20  mov     [rsp+arg_8], rbx
0x14006cf25  mov     [rsp+arg_10], rsi
0x14006cf2a  push    rdi
0x14006cf2b  push    r12
0x14006cf2d  push    r13
0x14006cf2f  push    r14
0x14006cf31  push    r15
0x14006cf33  sub     rsp, 1A0h
0x14006cf3a  mov     rax, cs:__security_cookie
0x14006cf41  xor     rax, rsp
0x14006cf44  mov     [rsp+1C8h+var_38], rax
0x14006cf4c  mov     rbx, rcx
0x14006cf4f  lea     rcx, WLEvt_AuthenticateUser_Start; struct _EVENT_DESCRIPTOR *
0x14006cf56  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x14006cf5b  lea     rcx, [rsp+1C8h+var_D8]; this
0x14006cf63  call    ??0Timer@@QEAA@H@Z; Timer::Timer(int)
0x14006cf68  xorps   xmm0, xmm0
0x14006cf6b  movups  [rsp+1C8h+var_88], xmm0
0x14006cf73  movups  [rsp+1C8h+var_78], xmm0
0x14006cf7b  movups  [rsp+1C8h+var_68], xmm0
0x14006cf83  mov     edx, 1
0x14006cf88  mov     dword ptr [rsp+1C8h+var_88], edx
0x14006cf8f  xor     ecx, ecx
0x14006cf91  mov     [rsp+1C8h+var_164], ecx
0x14006cf95  mov     [rsp+1C8h+var_130], rcx
0x14006cf9d  mov     qword ptr [rsp+1C8h+LogonId.LowPart], rcx
0x14006cfa5  mov     [rsp+1C8h+Handle], rcx
0x14006cfad  mov     [rsp+1C8h+var_168], ecx
0x14006cfb1  mov     dword ptr [rsp+1C8h+var_C8], ecx
0x14006cfb8  mov     [rsp+1C8h+var_114], ecx
0x14006cfbf  mov     [rsp+1C8h+Buffer], rcx
0x14006cfc7  mov     [rsp+1C8h+var_11C], ecx
0x14006cfce  mov     [rsp+1C8h+var_158], edx
0x14006cfd2  mov     [rsp+1C8h+var_14C], edx
0x14006cfd6  movups  xmmword ptr [rsp+1C8h+var_B8.PagedPoolLimit], xmm0
0x14006cfde  movups  xmmword ptr [rsp+1C8h+var_B8.MinimumWorkingSetSize], xmm0
0x14006cfe6  movups  xmmword ptr [rsp+1C8h+var_B8.PagefileLimit], xmm0
0x14006cfee  mov     [rsp+1C8h+ppLogonSessionData], rcx
0x14006cff6  mov     rsi, [rbx+8]
0x14006cffa  mov     [rsp+1C8h+var_E0], rsi
0x14006d002  mov     rax, [rsi]
0x14006d005  mov     rbx, [rax+90h]
0x14006d00c  mov     r13, [rax+70h]
0x14006d010  mov     edi, [r13+0]
0x14006d014  and     edi, 8
0x14006d017  mov     r15d, ecx
0x14006d01a  mov     [rsp+1C8h+var_100], rcx
0x14006d022  mov     [rsp+1C8h+var_120], ecx
0x14006d029  mov     [rsp+1C8h+var_15C], ecx
0x14006d02d  lea     r12, [rsi+34h]
0x14006d031  mov     [r12], ecx
0x14006d035  mov     [rsi+38h], rcx
0x14006d039  lea     rax, WPP_GLOBAL_Control
0x14006d040  mov     rcx, cs:WPP_GLOBAL_Control; this
0x14006d047  cmp     rcx, rax
0x14006d04a  jz      short loc_14006D074
0x14006d04c  test    dword ptr [rcx+1Ch], 100h
0x14006d053  jz      short loc_14006D074
0x14006d055  lea     r14, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14006d05c  cmp     byte ptr [rcx+19h], 4
0x14006d060  jb      short loc_14006D07B
0x14006d062  lea     edx, [r15+37h]
0x14006d066  mov     r8, r14
0x14006d069  mov     rcx, [rcx+10h]
0x14006d06d  call    WPP_SF_
0x14006d072  jmp     short loc_14006D07B
0x14006d074  lea     r14, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14006d07b  lea     rax, [rsp+1C8h+var_15C]
0x14006d080  mov     [rsp+1C8h+var_1A8], rax; unsigned int *
0x14006d085  mov     r9d, [rsp+1C8h+var_15C]; unsigned int
0x14006d08a  lea     r8, aForceautolocko; "ForceAutoLockOnLogon"
0x14006d091  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14006d098  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x14006d09d  test    edi, edi
0x14006d09f  jz      short loc_14006D0A8
0x14006d0a1  mov     ecx, 3F5h
0x14006d0a6  jmp     short loc_14006D0C2
0x14006d0a8  cmp     [rsp+1C8h+var_15C], 0
0x14006d0ad  jnz     short loc_14006D0D2
0x14006d0af  call    ?IsBootToCloudModeRegistryCheck@CloudPCHelpers@@YA_NXZ; CloudPCHelpers::IsBootToCloudModeRegistryCheck(void)
0x14006d0b4  test    al, al
0x14006d0b6  mov     ecx, 1BE4h
0x14006d0bb  jnz     short loc_14006D0C2
0x14006d0bd  mov     ecx, 3EAh
0x14006d0c2  xor     r9d, r9d
0x14006d0c5  lea     r8d, [r9+10h]
0x14006d0c9  lea     edx, [r9+3]
0x14006d0cd  call    ?WlDisplayStatusByResourceId@@YAKIW4_WLUI_STATE@@KPEAVCUser@@@Z; WlDisplayStatusByResourceId(uint,_WLUI_STATE,ulong,CUser *)
0x14006d0d2  test    rbx, rbx
0x14006d0d5  jnz     loc_14006D2BD
0x14006d0db  call    CreateLogonSid
0x14006d0e0  mov     [rsp+1C8h+var_130], rax
0x14006d0e8  test    rax, rax
0x14006d0eb  jnz     short loc_14006D135
0x14006d0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d0f4  lea     rdx, WPP_GLOBAL_Control
0x14006d0fb  cmp     rcx, rdx
0x14006d0fe  jz      short loc_14006D11F
0x14006d100  mov     edi, 1000h
0x14006d105  test    [rcx+1Ch], edi
0x14006d108  jz      short loc_14006D11F
0x14006d10a  cmp     byte ptr [rcx+19h], 2
0x14006d10e  jb      short loc_14006D11F
0x14006d110  lea     edx, [rbx+38h]
0x14006d113  mov     r8, r14
0x14006d116  mov     rcx, [rcx+10h]
0x14006d11a  call    WPP_SF_
0x14006d11f  mov     ebx, 0Eh
0x14006d124  mov     [rsp+1C8h+var_164], ebx
0x14006d128  mov     dword ptr [r12], 0C007000Eh
0x14006d130  jmp     loc_14006DB73
0x14006d135  mov     rcx, [rsi+10h]; this
0x14006d139  call    ?IsBoundToConsole@CSession@@QEAAHXZ; CSession::IsBoundToConsole(void)
0x14006d13e  mov     ebx, 2
0x14006d143  lea     ecx, [rbx+8]
0x14006d146  test    eax, eax
0x14006d148  cmovz   ebx, ecx
0x14006d14b  mov     [rsp+1C8h+var_150], ebx
0x14006d14f  call    IsWinStationConnectAndLockDesktopPresent
0x14006d154  test    al, al
0x14006d156  jnz     short loc_14006D16D
0x14006d158  call    IsMinCredGetLogonTypePresent
0x14006d15d  test    al, al
0x14006d15f  jz      short loc_14006D16D
0x14006d161  call    cs:__imp_MinCredGetLogonType
0x14006d167  mov     ebx, eax
0x14006d169  mov     [rsp+1C8h+var_150], eax
0x14006d16d  mov     rcx, [rsi+10h]
0x14006d171  cmp     dword ptr [rcx+94h], 3
0x14006d178  jz      short loc_14006D197
0x14006d17a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x14006d181  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x14006d186  test    al, al
0x14006d188  jz      short loc_14006D1A0
0x14006d18a  mov     rax, [rsi+10h]
0x14006d18e  cmp     dword ptr [rax+94h], 4
0x14006d195  jnz     short loc_14006D1A0
0x14006d197  mov     ebx, 2
0x14006d19c  mov     [rsp+1C8h+var_150], ebx
0x14006d1a0  mov     rax, [rsi+10h]
0x14006d1a4  cmp     dword ptr [rax+0F8h], 0
0x14006d1ab  jnz     short loc_14006D1B1
0x14006d1ad  test    edi, edi
0x14006d1af  jz      short loc_14006D1BA
0x14006d1b1  mov     ebx, 2
0x14006d1b6  mov     [rsp+1C8h+var_150], ebx
0x14006d1ba  call    ?IsAuditingLogFull@CMachine@@QEAAHXZ; CMachine::IsAuditingLogFull(void)
0x14006d1bf  mov     [rsp+1C8h+var_154], eax
0x14006d1c3  lea     rcx, [rsi+40h]; lpSystemTimeAsFileTime
0x14006d1c7  call    cs:__imp_GetSystemTimeAsFileTime
0x14006d1cd  lea     rax, [rsp+1C8h+var_120]
0x14006d1d5  mov     [rsp+1C8h+var_170], rax; int *
0x14006d1da  lea     rcx, [rsi+38h]
0x14006d1de  mov     [rsp+1C8h+var_178], rcx; int *
0x14006d1e3  mov     [rsp+1C8h+var_180], r12; int *
0x14006d1e8  lea     rax, [rsp+1C8h+var_11C]
0x14006d1f0  mov     [rsp+1C8h+var_188], rax; unsigned int *
0x14006d1f5  lea     rax, [rsp+1C8h+Buffer]
0x14006d1fd  mov     [rsp+1C8h+var_190], rax; void **
0x14006d202  lea     rax, [rsp+1C8h+var_B8]
0x14006d20a  mov     [rsp+1C8h+var_198], rax; struct _QUOTA_LIMITS *
0x14006d20f  lea     rax, [rsp+1C8h+Handle]
0x14006d217  mov     [rsp+1C8h+var_1A0], rax; void **
0x14006d21c  lea     rax, [rsp+1C8h+LogonId]
0x14006d224  mov     [rsp+1C8h+var_1A8], rax; struct _LUID *
0x14006d229  mov     r9, r13; struct _CRED_PROV_CREDENTIAL *
0x14006d22c  mov     r8, [rsp+1C8h+var_130]; void *
0x14006d234  mov     edx, ebx; enum _SECURITY_LOGON_TYPE
0x14006d236  mov     rcx, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x14006d239  call    ?AuthenticateUser@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@W4_SECURITY_LOGON_TYPE@@PEAXPEAU_CRED_PROV_CREDENTIAL@@PEAU_LUID@@PEAPEAXPEAU_QUOTA_LIMITS@@5PEAKPEAJ8PEAH@Z; AuthenticateUser(_WLSM_GLOBAL_CONTEXT *,_SECURITY_LOGON_TYPE,void *,_CRED_PROV_CREDENTIAL *,_LUID *,void * *,_QUOTA_LIMITS *,void * *,ulong *,long *,long *,int *)
0x14006d23e  mov     ebx, eax
0x14006d240  mov     [rsp+1C8h+var_164], eax
0x14006d244  mov     ecx, [rsp+1C8h+var_120]
0x14006d24b  neg     ecx
0x14006d24d  sbb     edi, edi
0x14006d24f  add     edi, 2
0x14006d252  mov     [rsp+1C8h+var_158], edi
0x14006d256  mov     [rsp+1C8h+var_14C], edi
0x14006d25a  cmp     [rsp+1C8h+var_15C], 0
0x14006d25f  setnz   r8b; bool
0x14006d263  mov     edx, eax; unsigned int
0x14006d265  mov     rcx, rsi; struct _WLSM_GLOBAL_CONTEXT *
0x14006d268  call    ?CleanupAutoLogonCredentials@@YAXPEAU_WLSM_GLOBAL_CONTEXT@@K_N@Z; CleanupAutoLogonCredentials(_WLSM_GLOBAL_CONTEXT *,ulong,bool)
0x14006d26d  test    ebx, ebx
0x14006d26f  jz      loc_14006D358
0x14006d275  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d27c  lea     rdx, WPP_GLOBAL_Control
0x14006d283  cmp     rcx, rdx
0x14006d286  jz      loc_14006DB73
0x14006d28c  mov     edi, 1000h
0x14006d291  test    [rcx+1Ch], edi
0x14006d294  jz      loc_14006DB73
0x14006d29a  cmp     byte ptr [rcx+19h], 2
0x14006d29e  jb      loc_14006DB73
0x14006d2a4  mov     edx, 39h ; '9'
0x14006d2a9  mov     r9d, ebx
0x14006d2ac  mov     r8, r14
0x14006d2af  mov     rcx, [rcx+10h]
0x14006d2b3  call    WPP_SF_d
0x14006d2b8  jmp     loc_14006DB73
0x14006d2bd  mov     eax, [rbx]
0x14006d2bf  mov     [r12], eax
0x14006d2c3  mov     eax, [rbx+4]
0x14006d2c6  mov     [rsi+38h], eax
0x14006d2c9  mov     rax, [rbx+8]
0x14006d2cd  mov     qword ptr [rsp+1C8h+LogonId.LowPart], rax
0x14006d2d5  mov     rax, [rbx+10h]
0x14006d2d9  mov     [rsp+1C8h+Handle], rax
0x14006d2e1  mov     qword ptr [rbx+10h], 0
0x14006d2e9  mov     rax, [rbx+18h]
0x14006d2ed  mov     [rsi+40h], rax
0x14006d2f1  movups  xmm0, xmmword ptr [rbx+20h]
0x14006d2f5  movups  xmmword ptr [rsp+1C8h+var_B8.PagedPoolLimit], xmm0
0x14006d2fd  movups  xmm1, xmmword ptr [rbx+30h]
0x14006d301  movups  xmmword ptr [rsp+1C8h+var_B8.MinimumWorkingSetSize], xmm1
0x14006d309  movups  xmm0, xmmword ptr [rbx+40h]
0x14006d30d  movups  xmmword ptr [rsp+1C8h+var_B8.PagefileLimit], xmm0
0x14006d315  mov     eax, [rbx+50h]
0x14006d318  mov     [rsp+1C8h+var_154], eax
0x14006d31c  mov     rax, [rbx+58h]
0x14006d320  mov     [rsp+1C8h+var_130], rax
0x14006d328  mov     qword ptr [rbx+58h], 0
0x14006d330  xor     eax, eax
0x14006d332  mov     [rsp+1C8h+var_158], eax
0x14006d336  mov     [rsp+1C8h+var_14C], eax
0x14006d33a  mov     eax, [rbx+64h]
0x14006d33d  mov     [rsp+1C8h+var_11C], eax
0x14006d344  mov     rax, [rbx+68h]
0x14006d348  mov     [rsp+1C8h+Buffer], rax
0x14006d350  mov     qword ptr [rbx+68h], 0
0x14006d358  mov     rcx, [rsp+1C8h+Handle]
0x14006d360  call    ?GetAssignedAccessType@@YA?AW4AssignedAccessType@@PEAX@Z; GetAssignedAccessType(void *)
0x14006d365  mov     [rsp+1C8h+var_148], eax
0x14006d36c  test    byte ptr [r13+0], 4
0x14006d371  jz      loc_14006D3FA
0x14006d377  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d37e  lea     r13, WPP_GLOBAL_Control
0x14006d385  mov     edi, 1000h
0x14006d38a  cmp     rcx, r13
0x14006d38d  jz      short loc_14006D3AB
0x14006d38f  test    [rcx+1Ch], edi
0x14006d392  jz      short loc_14006D3AB
0x14006d394  cmp     byte ptr [rcx+19h], 4
0x14006d398  jb      short loc_14006D3AB
0x14006d39a  mov     edx, 3Ah ; ':'
0x14006d39f  mov     r8, r14
0x14006d3a2  mov     rcx, [rcx+10h]
0x14006d3a6  call    WPP_SF_
0x14006d3ab  mov     edx, 2
0x14006d3b0  mov     r8d, edx
0x14006d3b3  mov     rcx, [rsi+10h]
0x14006d3b7  call    ?SetAutoLock@CSession@@QEAAXW4AutoLockType@1@W4AutoLockStartReason@1@@Z; CSession::SetAutoLock(CSession::AutoLockType,CSession::AutoLockStartReason)
0x14006d3bc  mov     rax, [rsi+10h]
0x14006d3c0  mov     dword ptr [rax+190h], 1
0x14006d3ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d3d1  cmp     rcx, r13
0x14006d3d4  jz      short loc_14006D406
0x14006d3d6  test    [rcx+1Ch], edi
0x14006d3d9  jz      short loc_14006D406
0x14006d3db  mov     r12d, 5
0x14006d3e1  cmp     [rcx+19h], r12b
0x14006d3e5  jb      short loc_14006D40C
0x14006d3e7  lea     edx, [r12+36h]
0x14006d3ec  mov     r8, r14
0x14006d3ef  mov     rcx, [rcx+10h]
0x14006d3f3  call    WPP_SF_
0x14006d3f8  jmp     short loc_14006D40C
0x14006d3fa  mov     edi, 1000h
0x14006d3ff  lea     r13, WPP_GLOBAL_Control
0x14006d406  mov     r12d, 5
0x14006d40c  mov     ecx, 288h; Size
0x14006d411  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006d416  test    rax, rax
0x14006d419  jz      short loc_14006D428
0x14006d41b  mov     rcx, rax; this
0x14006d41e  call    ??0CUser@@QEAA@XZ; CUser::CUser(void)
0x14006d423  mov     r15, rax
0x14006d426  jmp     short loc_14006D42B
0x14006d428  xor     r15d, r15d
0x14006d42b  mov     [rsp+1C8h+var_100], r15
0x14006d433  test    r15, r15
0x14006d436  jnz     short loc_14006D477
0x14006d438  lea     ebx, [r15+0Eh]
0x14006d43c  mov     [rsp+1C8h+var_164], ebx
0x14006d440  mov     rcx, cs:WPP_GLOBAL_Control
0x14006d447  cmp     rcx, r13
0x14006d44a  jz      loc_14006DB73
0x14006d450  test    [rcx+1Ch], edi
0x14006d453  jz      loc_14006DB73
0x14006d459  cmp     byte ptr [rcx+19h], 2
0x14006d45d  jb      loc_14006DB73
0x14006d463  lea     edx, [rbx+2Eh]
0x14006d466  mov     r8, r14
0x14006d469  mov     rcx, [rcx+10h]
0x14006d46d  call    WPP_SF_
0x14006d472  jmp     loc_14006DB73
0x14006d477  mov     r8, [rsi+10h]; struct CSession *
0x14006d47b  mov     rdx, [rsi]; struct CGlobalStore *
0x14006d47e  mov     rcx, r15; this
0x14006d481  call    ?Initialize@CUser@@QEAAKPEAVCGlobalStore@@PEAVCSession@@H@Z; CUser::Initialize(CGlobalStore *,CSession *,int)
  ... truncated ...
```
