# ShutdownWindowsWorkerThread(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x140065950`
- end: `0x1400666b4`
- name: `?ShutdownWindowsWorkerThread@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `3428`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x140004e80`
- `0x1400057f4`
- `0x1400060d0`
- `0x140010300`
- `0x140012164`
- `0x1400155f0`
- `0x140016f30`
- `0x14002aae0`
- `0x14002ab60`
- `0x14002ba10`
- `0x140032e54`
- `0x140034700`
- `0x140037b00`
- `0x140039488`
- `0x14003c7b8`
- `0x14003f1c8`
- `0x14003f84c`
- `0x140041b5c`
- `0x140041c34`
- `0x14004cba8`
- `0x14004e874`
- `0x140050984`
- `0x1400560f4`
- `0x140056348`
- `0x14005b630`
- `0x14005d714`
- `0x14006554c`
- `0x140065950`
- `0x140089844`
- `0x14008b244`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140065df7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140065df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400661ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400665a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009f286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065c03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400660b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400661ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400665a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009f286`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140065bf9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400660ad`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400661a4`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140065bf9`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400660ad`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1400661a4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140065f17`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140066111`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400663ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14009f095`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140065f17`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140066111`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400663ba`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x14009f095`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140065af9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140065af9`
- `ntdll!RtlLeaveCriticalSection` at `0x140065edb`
- `ntdll!RtlLeaveCriticalSection` at `0x140066647`
- `ntdll!RtlLeaveCriticalSection` at `0x14009f337`
- `ntdll!RtlLeaveCriticalSection` at `0x140065edb`
- `ntdll!RtlLeaveCriticalSection` at `0x140066647`
- `ntdll!RtlLeaveCriticalSection` at `0x14009f337`
- `ntdll!RtlEnterCriticalSection` at `0x140065a4f`
- `ntdll!RtlEnterCriticalSection` at `0x140066416`
- `ntdll!RtlEnterCriticalSection` at `0x140066612`
- `ntdll!RtlEnterCriticalSection` at `0x14009f0e5`
- `ntdll!RtlEnterCriticalSection` at `0x14009f2fe`
- `ntdll!RtlEnterCriticalSection` at `0x140065a4f`
- `ntdll!RtlEnterCriticalSection` at `0x140066416`
- `ntdll!RtlEnterCriticalSection` at `0x140066612`
- `ntdll!RtlEnterCriticalSection` at `0x14009f0e5`
- `ntdll!RtlEnterCriticalSection` at `0x14009f2fe`
- `ext-ms-win-ntuser-private-l1-1-1!CancelShutdown` at `0x140065d87`
- `ext-ms-win-ntuser-private-l1-1-1!CancelShutdown` at `0x140065d87`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformFlags` at `0x140066129`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformFlags` at `0x140066516`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformFlags` at `0x14009f1ea`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformFlags` at `0x140066129`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformFlags` at `0x140066516`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformFlags` at `0x14009f1ea`
- `ext-ms-win-session-winsta-l1-1-0!WinStationPreCreateGlassReplacementSession` at `0x140065b74`
- `ext-ms-win-session-winsta-l1-1-0!WinStationPreCreateGlassReplacementSession` at `0x140065b74`
- `ext-ms-win-session-winsta-l1-1-0!WinStationTerminateGlassReplacementSession` at `0x14006657b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationTerminateGlassReplacementSession` at `0x14009f25a`
- `ext-ms-win-session-winsta-l1-1-0!WinStationTerminateGlassReplacementSession` at `0x14006657b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationTerminateGlassReplacementSession` at `0x14009f25a`

## string_xrefs

- `0x140065b6d`: `%SYSTEMROOT%\System32\WinLogon.exe -SpecialSession`
- `0x140065f04`: `FadePeriodConfiguration`

## pseudocode

```c
void __fastcall ShutdownWindowsWorkerThread(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  unsigned int v2; // r13d
  DWORD v3; // r12d
  BOOL v4; // edi
  int v5; // ebx
  CUser *v6; // rcx
  unsigned __int8 v7; // dl
  int v8; // edi
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // ebx
  CUser *v16; // rcx
  CMachine *v17; // rcx
  __int64 v18; // rdx
  unsigned int v19; // edi
  unsigned int v20; // ebx
  CloudPCHelpers *v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // r9
  DWORD v24; // eax
  unsigned int ShutdownResolverInfo; // ebx
  int v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // r9
  DWORD v29; // eax
  char v30; // [rsp+30h] [rbp-F8h]
  int v31; // [rsp+34h] [rbp-F4h]
  int v32; // [rsp+40h] [rbp-E8h]
  int v33; // [rsp+44h] [rbp-E4h] BYREF
  int v34; // [rsp+48h] [rbp-E0h] BYREF
  unsigned int v35; // [rsp+4Ch] [rbp-DCh] BYREF
  int v36; // [rsp+50h] [rbp-D8h]
  unsigned int v37; // [rsp+54h] [rbp-D4h]
  int v38; // [rsp+58h] [rbp-D0h]
  int v39; // [rsp+5Ch] [rbp-CCh] BYREF
  __int64 v40; // [rsp+60h] [rbp-C8h] BYREF
  int v41; // [rsp+68h] [rbp-C0h]
  int v42; // [rsp+6Ch] [rbp-BCh]
  __int64 v43; // [rsp+70h] [rbp-B8h]
  _BYTE v44[32]; // [rsp+78h] [rbp-B0h] BYREF
  _BYTE v45[32]; // [rsp+98h] [rbp-90h] BYREF
  _BYTE v46[32]; // [rsp+B8h] [rbp-70h] BYREF
  _BYTE v47[80]; // [rsp+D8h] [rbp-50h] BYREF
  int v48; // [rsp+138h] [rbp+10h] BYREF
  int v49; // [rsp+140h] [rbp+18h]
  int v50; // [rsp+148h] [rbp+20h] BYREF

  v2 = (unsigned int)Context;
  v3 = 0;
  v4 = 0;
  v48 = 0;
  v36 = 0;
  v5 = 0;
  v49 = 0;
  v32 = 0;
  v50 = 0;
  v37 = (unsigned int)Context;
  v35 = -1;
  v30 = 0;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
  }
  _InterlockedIncrement(&dword_1400D2E4C);
  if ( dword_1400D2E48 )
  {
    RtlEnterCriticalSection(&g_LogoffThreadCritSec);
    WLEventWrite(&WLDiagEvt_LogoffRequestToUserFeedback_Start, v2);
    v32 = 1;
    v49 = 1;
    v8 = CallCheckForHiberbootRpc(0, v7);
    if ( !hToken )
    {
      v48 = 1;
      v36 = 1;
      if ( v8 )
        dword_1400D2E38 = v2;
      else
        dword_1400D2E38 |= v2;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v2);
      }
      SuspendPowerTransitions();
      goto LABEL_19;
    }
    g_ulLogoffStartTick = GetTickCount64();
    if ( (unsigned int)IsHiberboot(v2)
      && (unsigned int)CSession::IsBoundToConsole(qword_1400D2550)
      && (unsigned __int8)IsWinStationConnectAndLockDesktopPresent() )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
      }
      v30 = WinStationPreCreateGlassReplacementSession(L"%SYSTEMROOT%\\System32\\WinLogon.exe -SpecialSession", 0, &v35);
      if ( v30 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, LastError);
      }
    }
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      v3 = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v10 = 19;
      v11 = v3;
      goto LABEL_42;
    }
    v5 = 1;
    if ( *((_DWORD *)qword_1400D2550 + 103) && (v2 & 4) == 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v12 = 20;
      goto LABEL_49;
    }
    if ( dword_1400D2E3C )
    {
      if ( (v2 & 4) == 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v13 = 21;
        v14 = v2;
LABEL_56:
        WPP_SF_d(*((_QWORD *)v6 + 2), v13, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v14);
        v6 = WPP_GLOBAL_Control;
LABEL_57:
        dword_1400D2E38 |= v2;
        goto LABEL_20;
      }
      v14 = dword_1400D2E38;
      if ( (dword_1400D2E38 & 4) != 0 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_57;
        }
        v13 = 22;
        goto LABEL_56;
      }
      v2 |= dword_1400D2E38;
      v37 = v2;
      v15 = 0;
      v6 = WPP_GLOBAL_Control;
      while ( 1 )
      {
        v38 = v15;
        if ( v15 >= 5 )
        {
LABEL_89:
          v5 = 1;
          goto LABEL_90;
        }
        if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x2000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
          WPP_SF_d(*((_QWORD *)v6 + 2), 23, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v2);
        if ( !CancelShutdown() )
          goto LABEL_74;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
          goto LABEL_79;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          break;
LABEL_75:
        if ( v16 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v16 + 7) & 0x2000) != 0 && *((_BYTE *)v16 + 25) >= 4u )
          WPP_SF_(*((_QWORD *)v16 + 2), 25, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
LABEL_79:
        Sleep(0x3E8u);
        if ( !dword_1400D2E3C )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
            v6 = WPP_GLOBAL_Control;
          }
          goto LABEL_89;
        }
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
          v6 = WPP_GLOBAL_Control;
        }
        ++v15;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v2);
LABEL_74:
      v16 = WPP_GLOBAL_Control;
      goto LABEL_75;
    }
    v6 = WPP_GLOBAL_Control;
LABEL_90:
    if ( dword_1400D2E3C )
    {
      if ( v6 == (CUser *)&WPP_GLOBAL_Control || (*((_DWORD *)v6 + 7) & 0x2000) == 0 || *((_BYTE *)v6 + 25) < 2u )
        goto LABEL_20;
      v12 = 28;
LABEL_49:
      WPP_SF_(*((_QWORD *)v6 + 2), v12, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
      goto LABEL_19;
    }
    dword_1400D2E3C = 1;
    dword_1400D2E38 = v2;
    RtlLeaveCriticalSection(&g_LogoffThreadCritSec);
    v49 = 0;
    CMachine::RegQueryDWORD(
      v17,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
      L"FadePeriodConfiguration",
      0x14Eu,
      &g_FadeDelay);
    RevertToSelf();
    v31 = 0;
    RecordBlackboxInfo(L"WluiAcquireUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
    {
      CallWithHangTimeout::CallWithHangTimeout(v45, 0);
      dword_1400D3468 = 4;
      WluiAcquireUI();
      dword_1400D3468 = 0;
      CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v45);
    }
    else
    {
      dword_1400D3468 = 4;
      WluiAcquireUI();
      dword_1400D3468 = 0;
    }
    RecordBlackboxInfo(L"WluiAcquireUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
    SuspendPowerTransitions();
    if ( (dword_1400D2E38 & 2) != 0 )
    {
      v19 = 8;
      v20 = (v2 & 0x1000000) != 0 ? 1008 : 1205;
    }
    else if ( (v2 & 9) != 0 || v8 )
    {
      v20 = 1204;
      v19 = 7;
    }
    else
    {
      LOBYTE(v18) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_W365Boot_DedicatedCloudOnly>::GetImpl'::`2'::impl,
        v18);
      v20 = CloudPCHelpers::IsBootToCloudModeRegistryCheck(v21) ? 7100 : 1003;
      v19 = 5;
    }
    if ( !g_fShutdownResolverDisabled )
    {
      RecordBlackboxInfo(L"WluiInformLogonUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
      {
        CallWithHangTimeout::CallWithHangTimeout(v46, 0);
        WluiInformLogonUI(0, v19);
        CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v46);
      }
      else
      {
        WluiInformLogonUI(0, v19);
      }
      RecordBlackboxInfo(L"WluiInformLogonUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
    }
    WlDisplayStatusByResourceId(v20, v19, 16, qword_1400D2560);
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      v3 = GetLastError();
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v3);
        v6 = WPP_GLOBAL_Control;
      }
      v4 = v48;
      goto LABEL_150;
    }
    RevertToSelf();
    v5 = 0;
    if ( (unsigned __int8)IsUMgrLaunchShellInfrastructureHostPresent() )
    {
      v22 = UMgrInformFlags(0);
      v23 = v22;
      if ( (v22 & 0x1FFF0000) == 0x70000 )
        v23 = (unsigned __int16)v22;
      if ( (_DWORD)v23
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v23);
      }
    }
    if ( !g_fShutdownResolverDisabled )
      CSession::AsyncSwitchDesktop(qword_1400D2550, 0, g_FadeDelay);
    if ( !ImpersonateLoggedOnUser(hToken) )
    {
      v24 = GetLastError();
      v3 = v24;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v10 = 31;
      v11 = v24;
LABEL_42:
      WPP_SF_d(*((_QWORD *)v6 + 2), v10, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v11);
LABEL_19:
      v6 = WPP_GLOBAL_Control;
LABEL_20:
      v4 = v48;
      goto LABEL_151;
    }
    v31 = 1;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v2);
    }
    WLEventWrite(&WLDiagEvt_LogoffRequestToUserFeedback_Stop, v2);
    v32 = 0;
    v3 = ShutdownWindowsWrapper((struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext, v2 & 0xFFFCFFFF | 0x10000);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
      }
      v34 = 0;
      v33 = 0;
      v48 = 0;
      RecordBlackboxInfo(L"WluiGetShutdownResolverInfo", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
      {
        CallWithHangTimeout::CallWithHangTimeout(v47, 0);
        ShutdownResolverInfo = WluiGetShutdownResolverInfo(&v34, &v50, &v33);
        v48 = ShutdownResolverInfo;
        CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v47);
      }
      else
      {
        ShutdownResolverInfo = WluiGetShutdownResolverInfo(&v34, &v50, &v33);
        v48 = ShutdownResolverInfo;
      }
      RecordBlackboxInfo(L"WluiGetShutdownResolverInfo", 0, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
      v39 = 1;
      WinlogonProvider::WluiGetShutdownResolverInfo<int,int &,int &,unsigned long &,unsigned long &>(
        (unsigned int)&v39,
        (unsigned int)&v34,
        (unsigned int)&v50,
        (unsigned int)&v33,
        (__int64)&v48);
      if ( ShutdownResolverInfo )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_149;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_0869ef17fb29338ff610f5528229efc9_Traceguids,
          ShutdownResolverInfo);
      }
    }
    v6 = WPP_GLOBAL_Control;
LABEL_149:
    v4 = v3 == 0;
    v36 = v4;
    dword_1400D2E3C = 0;
LABEL_150:
    v5 = v31;
    goto LABEL_151;
  }
  v3 = 1115;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
LABEL_151:
  if ( v5 )
  {
    RevertToSelf();
    v6 = WPP_GLOBAL_Control;
  }
  if ( !v3 )
  {
    v26 = v49;
    goto LABEL_191;
  }
  if ( !g_fShutdownResolverDisabled && v3 != 1115 )
  {
    if ( v50 )
    {
      CSession::WaitForAsyncSwitchDesktop(qword_1400D2550);
      v26 = v49;
      if ( !v49 )
      {
        RtlEnterCriticalSection(&g_LogoffThreadCritSec);
        v26 = 1;
      }
      if ( g_SafeToSwitch )
      {
        WlAccessibilitySwitchDesktop(&xGlobalContext, 2, 0);
        RecordBlackboxInfo(L"WluiReleaseUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
        {
          CallWithHangTimeout::CallWithHangTimeout(v44, 0);
          WluiReleaseUI();
          CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v44);
        }
        else
        {
          WluiReleaseUI();
        }
        RecordBlackboxInfo(L"WluiReleaseUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
      }
      goto LABEL_170;
    }
    if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x2000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
      WPP_SF_(*((_QWORD *)v6 + 2), 35, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
    v40 = 0;
    v43 = 0;
    v41 = 2;
    v42 = 5;
    v3 = WlStateMachineSetSignal(0xCu, (struct _StateMachineSignalData *)&v40);
  }
  v26 = v49;
LABEL_170:
  if ( (unsigned __int8)IsUMgrLaunchShellInfrastructureHostPresent() )
  {
    v27 = UMgrInformFlags(1);
    v28 = v27;
    if ( (v27 & 0x1FFF0000) == 0x70000 )
      v28 = (unsigned __int16)v27;
    if ( (_DWORD)v28
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v28);
    }
  }
  if ( v30 && (unsigned __int8)IsWinStationConnectAndLockDesktopPresent() )
  {
    if ( (unsigned __int8)WinStationTerminateGlassReplacementSession(v35) )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v29);
    }
  }
  ResumePowerTransitions();
LABEL_191:
  if ( v4 )
  {
    if ( !v26 )
    {
      RtlEnterCriticalSection(&g_LogoffThreadCritSec);
      v26 = 1;
    }
    CGlobalStore::SetLogoffFlags(xGlobalContext, dword_1400D2E38);
    v3 = WlStateMachineSetSignal(2u, 0);
  }
  if ( v26 )
    RtlLeaveCriticalSection(&g_LogoffThreadCritSec);
  _InterlockedDecrement(&dword_1400D2E4C);
  if ( v32 )
    WLEventWrite(&WLDiagEvt_LogoffRequestToUserFeedback_Stop, v2);
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids, v3);
  }
}

```

## disassembly

```asm
0x140065950  mov     r11, rsp
0x140065953  mov     [r11+8], rbx
0x140065957  push    rsi
0x140065958  push    rdi
0x140065959  push    r12
0x14006595b  push    r13
0x14006595d  push    r14
0x14006595f  sub     rsp, 100h
0x140065966  mov     r13, rdx
0x140065969  xor     r12d, r12d
0x14006596c  mov     [rsp+128h+var_F0], r12d
0x140065971  xor     edi, edi
0x140065973  mov     [r11+10h], edi
0x140065977  mov     [rsp+128h+var_D8], edi
0x14006597b  xor     ebx, ebx
0x14006597d  mov     [rsp+128h+var_F4], ebx
0x140065981  xor     eax, eax
0x140065983  mov     [r11+18h], eax
0x140065987  mov     [rsp+128h+var_EC], eax
0x14006598b  mov     [rsp+128h+var_E8], eax
0x14006598f  mov     [r11+20h], eax
0x140065993  mov     [rsp+128h+var_D4], r13d
0x140065998  mov     [rsp+128h+var_DC], 0FFFFFFFFh
0x1400659a0  mov     [rsp+128h+var_F8], al
0x1400659a4  lea     rax, WPP_GLOBAL_Control
0x1400659ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400659b2  mov     esi, 2000h
0x1400659b7  cmp     rcx, rax
0x1400659ba  jz      short loc_1400659E6
0x1400659bc  test    [rcx+1Ch], esi
0x1400659bf  jz      short loc_1400659E6
0x1400659c1  lea     r14, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids
0x1400659c8  cmp     byte ptr [rcx+19h], 4
0x1400659cc  jb      short loc_1400659ED
0x1400659ce  lea     edx, [rdi+0Dh]
0x1400659d1  mov     r8, r14
0x1400659d4  mov     rcx, [rcx+10h]
0x1400659d8  call    WPP_SF_
0x1400659dd  lea     rax, WPP_GLOBAL_Control
0x1400659e4  jmp     short loc_1400659ED
0x1400659e6  lea     r14, WPP_0869ef17fb29338ff610f5528229efc9_Traceguids
0x1400659ed  lock inc cs:dword_1400D2E4C
0x1400659f4  cmp     cs:dword_1400D2E48, 0
0x1400659fb  jnz     short loc_140065A48
0x1400659fd  mov     r12d, 45Bh
0x140065a03  mov     [rsp+128h+var_F0], r12d
0x140065a08  mov     rcx, cs:WPP_GLOBAL_Control
0x140065a0f  cmp     rcx, rax
0x140065a12  jz      loc_1400663B6
0x140065a18  test    [rcx+1Ch], esi
0x140065a1b  jz      loc_1400663B6
0x140065a21  cmp     byte ptr [rcx+19h], 4
0x140065a25  jb      loc_1400663B6
0x140065a2b  mov     edx, 0Eh
0x140065a30  mov     r8, r14
0x140065a33  mov     rcx, [rcx+10h]
0x140065a37  call    WPP_SF_
0x140065a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140065a43  jmp     loc_1400663B6
0x140065a48  lea     rcx, ?g_LogoffThreadCritSec@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x140065a4f  call    cs:__imp_RtlEnterCriticalSection
0x140065a55  mov     edx, r13d; unsigned int
0x140065a58  lea     rcx, WLDiagEvt_LogoffRequestToUserFeedback_Start; struct _EVENT_DESCRIPTOR *
0x140065a5f  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@K@Z; WLEventWrite(_EVENT_DESCRIPTOR const &,ulong)
0x140065a64  mov     eax, 1
0x140065a69  mov     [rsp+128h+var_E8], eax
0x140065a6d  mov     [rsp+128h+arg_10], eax
0x140065a74  mov     [rsp+128h+var_EC], eax
0x140065a78  xor     ecx, ecx; unsigned __int8
0x140065a7a  call    ?CallCheckForHiberbootRpc@@YAHEE@Z; CallCheckForHiberbootRpc(uchar,uchar)
0x140065a7f  mov     edi, eax
0x140065a81  cmp     cs:hToken, 0
0x140065a89  jnz     short loc_140065AF9
0x140065a8b  mov     eax, 1
0x140065a90  mov     [rsp+128h+arg_8], eax
0x140065a97  mov     [rsp+128h+var_D8], eax
0x140065a9b  test    edi, edi
0x140065a9d  jz      short loc_140065AA8
0x140065a9f  mov     cs:dword_1400D2E38, r13d
0x140065aa6  jmp     short loc_140065AAF
0x140065aa8  or      cs:dword_1400D2E38, r13d
0x140065aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x140065ab6  lea     rax, WPP_GLOBAL_Control
0x140065abd  cmp     rcx, rax
0x140065ac0  jz      short loc_140065AE1
0x140065ac2  test    [rcx+1Ch], esi
0x140065ac5  jz      short loc_140065AE1
0x140065ac7  cmp     byte ptr [rcx+19h], 4
0x140065acb  jb      short loc_140065AE1
0x140065acd  mov     edx, 0Fh
0x140065ad2  mov     r9d, r13d
0x140065ad5  mov     r8, r14
0x140065ad8  mov     rcx, [rcx+10h]
0x140065adc  call    WPP_SF_d
0x140065ae1  call    ?SuspendPowerTransitions@@YAXXZ; SuspendPowerTransitions(void)
0x140065ae6  mov     rcx, cs:WPP_GLOBAL_Control
0x140065aed  mov     edi, [rsp+128h+arg_8]
0x140065af4  jmp     loc_1400663B6
0x140065af9  call    cs:__imp_GetTickCount64
0x140065aff  mov     cs:?g_ulLogoffStartTick@@3_KA, rax; unsigned __int64 g_ulLogoffStartTick
0x140065b06  mov     ecx, r13d; unsigned int
0x140065b09  call    ?IsHiberboot@@YAHK@Z; IsHiberboot(ulong)
0x140065b0e  test    eax, eax
0x140065b10  jz      loc_140065BF2
0x140065b16  mov     rcx, cs:qword_1400D2550; this
0x140065b1d  call    ?IsBoundToConsole@CSession@@QEAAHXZ; CSession::IsBoundToConsole(void)
0x140065b22  test    eax, eax
0x140065b24  jz      loc_140065BF2
0x140065b2a  call    IsWinStationConnectAndLockDesktopPresent
0x140065b2f  test    al, al
0x140065b31  jz      loc_140065BF2
0x140065b37  mov     rcx, cs:WPP_GLOBAL_Control
0x140065b3e  lea     rax, WPP_GLOBAL_Control
0x140065b45  cmp     rcx, rax
0x140065b48  jz      short loc_140065B66
0x140065b4a  test    [rcx+1Ch], esi
0x140065b4d  jz      short loc_140065B66
0x140065b4f  cmp     byte ptr [rcx+19h], 4
0x140065b53  jb      short loc_140065B66
0x140065b55  mov     edx, 10h
0x140065b5a  mov     r8, r14
0x140065b5d  mov     rcx, [rcx+10h]
0x140065b61  call    WPP_SF_
0x140065b66  lea     r8, [rsp+128h+var_DC]
0x140065b6b  xor     edx, edx
0x140065b6d  lea     rcx, aSystemrootSyst_2; "%SYSTEMROOT%\\System32\\WinLogon.exe -S"...
0x140065b74  call    cs:__imp_WinStationPreCreateGlassReplacementSession
0x140065b7a  mov     [rsp+128h+var_F8], al
0x140065b7e  test    al, al
0x140065b80  jnz     short loc_140065BC3
0x140065b82  mov     rax, cs:WPP_GLOBAL_Control
0x140065b89  lea     rcx, WPP_GLOBAL_Control
0x140065b90  cmp     rax, rcx
0x140065b93  jz      short loc_140065BF2
0x140065b95  test    [rax+1Ch], esi
0x140065b98  jz      short loc_140065BF2
0x140065b9a  cmp     byte ptr [rax+19h], 2
0x140065b9e  jb      short loc_140065BF2
0x140065ba0  call    cs:__imp_GetLastError
0x140065ba6  mov     edx, 11h
0x140065bab  mov     r9d, eax
0x140065bae  mov     r8, r14
0x140065bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x140065bb8  mov     rcx, [rcx+10h]
0x140065bbc  call    WPP_SF_d
0x140065bc1  jmp     short loc_140065BF2
0x140065bc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140065bca  lea     rax, WPP_GLOBAL_Control
0x140065bd1  cmp     rcx, rax
0x140065bd4  jz      short loc_140065BF2
0x140065bd6  test    [rcx+1Ch], esi
0x140065bd9  jz      short loc_140065BF2
0x140065bdb  cmp     byte ptr [rcx+19h], 4
0x140065bdf  jb      short loc_140065BF2
0x140065be1  mov     edx, 12h
0x140065be6  mov     r8, r14
0x140065be9  mov     rcx, [rcx+10h]
0x140065bed  call    WPP_SF_
0x140065bf2  mov     rcx, cs:hToken; hToken
0x140065bf9  call    cs:__imp_ImpersonateLoggedOnUser
0x140065bff  test    eax, eax
0x140065c01  jnz     short loc_140065C53
0x140065c03  call    cs:__imp_GetLastError
0x140065c09  mov     r12d, eax
0x140065c0c  mov     [rsp+128h+var_F0], eax
0x140065c10  mov     rcx, cs:WPP_GLOBAL_Control
0x140065c17  lea     rax, WPP_GLOBAL_Control
0x140065c1e  cmp     rcx, rax
0x140065c21  jz      loc_140065AED
0x140065c27  test    [rcx+1Ch], esi
0x140065c2a  jz      loc_140065AED
0x140065c30  cmp     byte ptr [rcx+19h], 2
0x140065c34  jb      loc_140065AED
0x140065c3a  mov     edx, 13h
0x140065c3f  mov     r9d, r12d
0x140065c42  mov     r8, r14
0x140065c45  mov     rcx, [rcx+10h]
0x140065c49  call    WPP_SF_d
0x140065c4e  jmp     loc_140065AE6
0x140065c53  mov     ebx, 1
0x140065c58  mov     [rsp+128h+var_F4], ebx
0x140065c5c  mov     rax, cs:qword_1400D2550
0x140065c63  cmp     dword ptr [rax+19Ch], 0
0x140065c6a  jz      short loc_140065CB0
0x140065c6c  test    r13b, 4
0x140065c70  jnz     short loc_140065CB0
0x140065c72  mov     rcx, cs:WPP_GLOBAL_Control
0x140065c79  lea     rax, WPP_GLOBAL_Control
0x140065c80  cmp     rcx, rax
0x140065c83  jz      loc_140065AED
0x140065c89  test    [rcx+1Ch], esi
0x140065c8c  jz      loc_140065AED
0x140065c92  cmp     byte ptr [rcx+19h], 2
0x140065c96  jb      loc_140065AED
0x140065c9c  lea     edx, [rbx+13h]
0x140065c9f  mov     r8, r14
0x140065ca2  mov     rcx, [rcx+10h]
0x140065ca6  call    WPP_SF_
0x140065cab  jmp     loc_140065AE6
0x140065cb0  cmp     cs:dword_1400D2E3C, 0
0x140065cb7  jz      loc_140065EB3
0x140065cbd  test    r13b, 4
0x140065cc1  jnz     short loc_140065D08
0x140065cc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140065cca  lea     rax, WPP_GLOBAL_Control
0x140065cd1  cmp     rcx, rax
0x140065cd4  jz      short loc_140065CFC
0x140065cd6  test    [rcx+1Ch], esi
0x140065cd9  jz      short loc_140065CFC
0x140065cdb  cmp     byte ptr [rcx+19h], 2
0x140065cdf  jb      short loc_140065CFC
0x140065ce1  mov     edx, 15h
0x140065ce6  mov     r9d, r13d
0x140065ce9  mov     r8, r14
0x140065cec  mov     rcx, [rcx+10h]
0x140065cf0  call    WPP_SF_d
0x140065cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x140065cfc  or      cs:dword_1400D2E38, r13d
0x140065d03  jmp     loc_140065AED
0x140065d08  mov     r9d, cs:dword_1400D2E38
0x140065d0f  test    r9b, 4
0x140065d13  jz      short loc_140065D3A
0x140065d15  mov     rcx, cs:WPP_GLOBAL_Control
0x140065d1c  lea     rax, WPP_GLOBAL_Control
0x140065d23  cmp     rcx, rax
0x140065d26  jz      short loc_140065CFC
0x140065d28  test    [rcx+1Ch], esi
0x140065d2b  jz      short loc_140065CFC
0x140065d2d  cmp     byte ptr [rcx+19h], 2
0x140065d31  jb      short loc_140065CFC
0x140065d33  mov     edx, 16h
0x140065d38  jmp     short loc_140065CE9
0x140065d3a  or      r13d, cs:dword_1400D2E38
0x140065d41  mov     [rsp+128h+var_D4], r13d
0x140065d46  xor     ebx, ebx
0x140065d48  mov     rcx, cs:WPP_GLOBAL_Control
0x140065d4f  mov     [rsp+128h+var_D0], ebx
0x140065d53  cmp     ebx, 5
0x140065d56  jge     loc_140065E79
0x140065d5c  lea     rax, WPP_GLOBAL_Control
0x140065d63  cmp     rcx, rax
0x140065d66  jz      short loc_140065D87
0x140065d68  test    [rcx+1Ch], esi
0x140065d6b  jz      short loc_140065D87
0x140065d6d  cmp     byte ptr [rcx+19h], 4
0x140065d71  jb      short loc_140065D87
0x140065d73  mov     edx, 17h
0x140065d78  mov     r9d, r13d
0x140065d7b  mov     r8, r14
0x140065d7e  mov     rcx, [rcx+10h]
0x140065d82  call    WPP_SF_d
0x140065d87  call    cs:__imp_CancelShutdown
0x140065d8d  test    eax, eax
0x140065d8f  jz      short loc_140065DC3
0x140065d91  mov     rcx, cs:WPP_GLOBAL_Control
0x140065d98  lea     rax, WPP_GLOBAL_Control
0x140065d9f  cmp     rcx, rax
0x140065da2  jz      short loc_140065DF2
0x140065da4  test    [rcx+1Ch], esi
0x140065da7  jz      short loc_140065DD1
0x140065da9  cmp     byte ptr [rcx+19h], 4
0x140065dad  jb      short loc_140065DD1
0x140065daf  mov     edx, 18h
0x140065db4  mov     r9d, r13d
0x140065db7  mov     r8, r14
0x140065dba  mov     rcx, [rcx+10h]
0x140065dbe  call    WPP_SF_d
0x140065dc3  lea     rax, WPP_GLOBAL_Control
0x140065dca  mov     rcx, cs:WPP_GLOBAL_Control
0x140065dd1  cmp     rcx, rax
0x140065dd4  jz      short loc_140065DF2
0x140065dd6  test    [rcx+1Ch], esi
0x140065dd9  jz      short loc_140065DF2
0x140065ddb  cmp     byte ptr [rcx+19h], 4
0x140065ddf  jb      short loc_140065DF2
0x140065de1  mov     edx, 19h
0x140065de6  mov     r8, r14
0x140065de9  mov     rcx, [rcx+10h]
0x140065ded  call    WPP_SF_
0x140065df2  mov     ecx, 3E8h; dwMilliseconds
0x140065df7  call    cs:__imp_Sleep
0x140065dfd  cmp     cs:dword_1400D2E3C, 0
0x140065e04  jz      short loc_140065E43
0x140065e06  mov     rcx, cs:WPP_GLOBAL_Control
0x140065e0d  lea     rax, WPP_GLOBAL_Control
0x140065e14  cmp     rcx, rax
0x140065e17  jz      short loc_140065E3C
0x140065e19  test    [rcx+1Ch], esi
0x140065e1c  jz      short loc_140065E3C
0x140065e1e  cmp     byte ptr [rcx+19h], 4
0x140065e22  jb      short loc_140065E3C
0x140065e24  mov     edx, 1Ah
0x140065e29  mov     r8, r14
0x140065e2c  mov     rcx, [rcx+10h]
0x140065e30  call    WPP_SF_
0x140065e35  mov     rcx, cs:WPP_GLOBAL_Control
0x140065e3c  inc     ebx
0x140065e3e  jmp     loc_140065D4F
0x140065e43  mov     rcx, cs:WPP_GLOBAL_Control
0x140065e4a  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
