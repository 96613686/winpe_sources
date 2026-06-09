# CSession::PerformDelayedSwitchToApplicationDesktop(void *,int)

- ea: `0x1400176f8`
- end: `0x1400180e4`
- name: `?PerformDelayedSwitchToApplicationDesktop@CSession@@QEAAXPEAXH@Z`
- size: `2540`
- prototype: `void(CSession *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140017240`

## callees

- `0x140004f20`
- `0x1400057f4`
- `0x1400060d0`
- `0x140006970`
- `0x140012164`
- `0x1400155f0`
- `0x1400176f8`
- `0x14002a7a8`
- `0x14002ba10`
- `0x14002d410`
- `0x1400333b0`
- `0x140036c20`
- `0x140037b00`
- `0x14003d7d8`
- `0x14003f84c`
- `0x140041c34`
- `0x1400422c0`
- `0x14004327c`
- `0x140044830`
- `0x14004a600`
- `0x14004bff4`
- `0x14004c08c`
- `0x14004c124`
- `0x140050984`
- `0x14005b630`
- `0x14005d714`
- `0x1400651ec`
- `0x14007ab3c`
- `0x14007c988`
- `0x1400828e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140017c90`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140017c90`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140017f55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009d96c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140017f55`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14009d96c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140017caa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009d9b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017f89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009d9b0`
- `ntdll!TpAllocWait` at `0x140017d08`
- `ntdll!TpAllocWait` at `0x140017d6e`
- `ntdll!TpAllocWait` at `0x140017d08`
- `ntdll!TpAllocWait` at `0x140017d6e`
- `ntdll!TpSetWait` at `0x140017ded`
- `ntdll!TpSetWait` at `0x140017e5f`
- `ntdll!TpSetWait` at `0x140017ded`
- `ntdll!TpSetWait` at `0x140017e5f`
- `ntdll!RtlNtStatusToDosError` at `0x140017d41`
- `ntdll!RtlNtStatusToDosError` at `0x140017d41`
- `USERENV!GetProfileType` at `0x140017a7a`
- `USERENV!GetProfileType` at `0x140017a7a`

## string_xrefs

- `0x140017ec5`: `WluiNotifyIsReadyForDesktopSwitch`
- `0x140017f14`: `WluiNotifyIsReadyForDesktopSwitch`
- `0x14009d8c5`: `WluiNotifyIsReadyForDesktopSwitch`
- `0x14009d917`: `WluiNotifyIsReadyForDesktopSwitch`
- `0x140017fe9`: `clientcore\ds\security\umstartup\winlogon\core\session.cxx`
- `0x14009da1b`: `clientcore\ds\security\umstartup\winlogon\core\session.cxx`

## pseudocode

```c
void __fastcall CSession::PerformDelayedSwitchToApplicationDesktop(CSession *this, CSession **a2, int a3)
{
  signed int v4; // ebx
  int v5; // esi
  unsigned int v6; // r13d
  __int64 v7; // rdx
  HKEY v8; // rcx
  __int64 v9; // rdx
  CMachine *v10; // rcx
  const unsigned __int16 *v11; // rdx
  const unsigned __int16 *v12; // r8
  unsigned int v13; // r9d
  unsigned int v14; // r9d
  CMachine *v15; // rcx
  CUser *v16; // rcx
  CMachine *v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rdx
  CUser *v20; // rcx
  DWORD LastError; // eax
  __int64 v22; // rdx
  __int64 v23; // r9
  int v24; // ebx
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // r13d
  HANDLE EventW; // rax
  DWORD v29; // eax
  NTSTATUS v30; // ebx
  CUser *v31; // rcx
  __int64 v32; // rdx
  __int64 *v33; // r8
  unsigned int v34; // ebx
  __int64 *v35; // r8
  void *IsReadyForDesktopSwitch; // r13
  DWORD v37; // eax
  int v38; // eax
  const struct _EVENT_DESCRIPTOR *v39; // rcx
  int v40; // edx
  int v41; // [rsp+20h] [rbp-108h]
  int v42; // [rsp+50h] [rbp-D8h]
  DWORD dwFlags; // [rsp+54h] [rbp-D4h] BYREF
  int v44; // [rsp+58h] [rbp-D0h]
  __int64 v45; // [rsp+60h] [rbp-C8h] BYREF
  unsigned int v46; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v47; // [rsp+6Ch] [rbp-BCh] BYREF
  unsigned int v48; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v49; // [rsp+74h] [rbp-B4h]
  int v50; // [rsp+78h] [rbp-B0h]
  int v51; // [rsp+7Ch] [rbp-ACh]
  int v52; // [rsp+80h] [rbp-A8h]
  _DWORD v53[8]; // [rsp+88h] [rbp-A0h] BYREF
  _DWORD v54[8]; // [rsp+A8h] [rbp-80h] BYREF
  int v55; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  CSession **v58; // [rsp+138h] [rbp+10h] BYREF
  int v59; // [rsp+140h] [rbp+18h]
  unsigned int v60; // [rsp+148h] [rbp+20h] BYREF

  v59 = a3;
  v58 = a2;
  v4 = 87;
  v44 = 87;
  v42 = 0;
  v45 = 0;
  v60 = 30;
  v51 = CSession::IsBoundToConsole(a2[2]) == 0;
  v52 = v51;
  v5 = *((_DWORD *)a2[4] + 132);
  v50 = v5;
  v6 = 600;
  LOBYTE(v7) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::GetImpl'::`2'::impl,
    v7);
  dwFlags = 0;
  if ( (int)SHRegGetDWORD(v8, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE", L"RestoreStatus", &dwFlags) >= 0
    && dwFlags )
  {
    v6 = 900;
  }
  if ( IsUserOOBE() || IsCredentialReset() || IsAutoLogonAfterCredentialReset() || v5 == 1 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids);
    }
    v60 = 600;
  }
  v46 = 1;
  CUser::RegQueryDWORD(a2[4], L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", L"FirstLogon", 1u, &v46);
  if ( v46 == 1 )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids);
    }
    *((_DWORD *)a2[4] + 130) = 1;
    v60 = 600;
    LOBYTE(v9) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::GetImpl'::`2'::impl,
      v9);
    v60 = v6;
    CUser::RegSetDWORD(a2[4], v11, v12, v13);
  }
  v14 = v60;
  v49 = v60;
  if ( *((_DWORD *)a2[4] + 130) )
  {
    CMachine::RegQueryDWORD(
      v10,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
      L"FirstLogonTimeout",
      v60,
      &v60);
    v14 = v60;
  }
  CMachine::RegQueryDWORD(
    v10,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
    L"DelayedDesktopSwitchTimeout",
    v14,
    &v60);
  CUser::RegQueryDWORD(
    a2[4],
    L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
    L"DelayedDesktopSwitchTimeout",
    v60,
    &v60);
  if ( !v60 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids);
    }
    goto LABEL_100;
  }
  if ( *((_DWORD *)a2[4] + 130) )
  {
    v47 = 0;
    CMachine::RegQueryDWORD(
      v15,
      L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
      L"EnableFirstLogonAnimation",
      0,
      &v47);
    v48 = 1;
    CMachine::RegQueryDWORD(
      v17,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
      L"EnableFirstLogonAnimation",
      1u,
      &v48);
    if ( !v47 || !v48 || v59 )
    {
LABEL_61:
      if ( !g_fLaunchedFirstLogonAnimation )
      {
        v26 = 1013;
        if ( v50 != 1 )
          v26 = 1011;
        WlDisplayStatusByResourceId(v26, 4, 16, a2[4]);
      }
      goto LABEL_65;
    }
    dwFlags = 0;
    v18 = CUser::ImpersonateUser(a2[4], 0);
    v4 = v18;
    v44 = v18;
    if ( v18 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_100;
      }
      v19 = 69;
      goto LABEL_35;
    }
    if ( GetProfileType(&dwFlags) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v22 = 71;
        v23 = dwFlags;
        goto LABEL_45;
      }
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v22 = 70;
      v23 = LastError;
      v20 = WPP_GLOBAL_Control;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v20 + 2), v22, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v23);
    }
    CUser::StopImpersonating(v20);
    v42 = 0;
    if ( (dwFlags & 1) != 0 || g_fLaunchedFirstLogonAnimation )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids);
      }
    }
    else
    {
      RecordBlackboxInfo(L"WluiInformLogonUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)a2);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
      {
        CallWithHangTimeout::CallWithHangTimeout(&v55, 0);
        v24 = WluiInformLogonUI(5, 4);
        v44 = v24;
        CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)&v55);
      }
      else
      {
        v24 = WluiInformLogonUI(5, 4);
        v44 = v24;
      }
      RecordBlackboxInfo(L"WluiInformLogonUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)a2);
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_lll(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, 5, 4, v24);
      }
      g_fLaunchedFirstLogonAnimation = 1;
      LOBYTE(v25) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::GetImpl'::`2'::impl,
        v25);
      v49 = v6;
      if ( v60 == v6 )
        v60 = v6;
    }
    goto LABEL_61;
  }
LABEL_65:
  v18 = CUser::ImpersonateUser(a2[4], 0);
  v4 = v18;
  v44 = v18;
  if ( v18 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_100;
    }
    v19 = 74;
LABEL_35:
    WPP_SF_d(*((_QWORD *)v16 + 2), v19, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v18);
LABEL_100:
    v27 = v42;
    goto LABEL_101;
  }
  v27 = 1;
  v42 = 1;
  EventW = CreateEventW(0, 1, 0, L"ShellDesktopSwitchEvent");
  *((_QWORD *)this + 24) = EventW;
  if ( EventW )
  {
    v30 = TpAllocWait((char *)this + 176, PerformDelayedSwitchToApplicationDesktopCallback, a2, 0);
    if ( v30 >= 0 )
    {
      v30 = TpAllocWait((char *)this + 184, PerformDelayedSwitchToApplicationDesktopPerformanceCallback, a2, 0);
      if ( v30 >= 0 )
      {
        v45 = -10000000LL * v60;
        RecordBlackboxInfo(L"ShellStartup", 1, (struct _WLSM_GLOBAL_CONTEXT *)a2);
        v33 = &v45;
        if ( v60 == -1 )
          v33 = 0;
        TpSetWait(*((_QWORD *)this + 22), *((_QWORD *)this + 24), v33);
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v60);
        }
        v34 = v49;
        v45 = -10000000LL * v49;
        v35 = &v45;
        if ( v49 == -1 )
          v35 = 0;
        TpSetWait(*((_QWORD *)this + 23), *((_QWORD *)this + 24), v35);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v34);
        }
        v4 = 0;
        v44 = 0;
        goto LABEL_100;
      }
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v32 = 77;
    }
    else
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v32 = 76;
    }
    WPP_SF_d(*((_QWORD *)v31 + 2), v32, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, (unsigned int)v30);
LABEL_81:
    v4 = RtlNtStatusToDosError(v30);
    v44 = v4;
    goto LABEL_100;
  }
  v29 = GetLastError();
  v4 = v29;
  v44 = v29;
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v29);
  }
LABEL_101:
  if ( v27 )
    CUser::StopImpersonating(v16);
  if ( v4 )
  {
    if ( !v59 )
    {
      RecordBlackboxInfo(L"WluiNotifyIsReadyForDesktopSwitch", 1, (struct _WLSM_GLOBAL_CONTEXT *)a2);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
      {
        CallWithHangTimeout::CallWithHangTimeout(v53, 0);
        IsReadyForDesktopSwitch = (void *)WluiNotifyIsReadyForDesktopSwitch();
        CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v53);
      }
      else
      {
        IsReadyForDesktopSwitch = (void *)WluiNotifyIsReadyForDesktopSwitch();
      }
      RecordBlackboxInfo(L"WluiNotifyIsReadyForDesktopSwitch", 0, (struct _WLSM_GLOBAL_CONTEXT *)a2);
      if ( IsReadyForDesktopSwitch )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids);
        }
        v37 = WaitForSingleObject(IsReadyForDesktopSwitch, 0x1388u);
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids, v37);
        }
        CloseHandle(IsReadyForDesktopSwitch);
      }
      CSession::SwitchDesktop((__int64)a2[2], 2, 0, 0, 0);
      v41 = v51;
      v38 = CGlobalStore::StopAndDeleteGlobalTraceLoggingActivity(*a2, *((unsigned int *)a2[2] + 22), 0, 0);
      if ( v38 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x856,
          (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\session.cxx",
          (const char *)(unsigned int)v38,
          v41);
    }
    v39 = (const struct _EVENT_DESCRIPTOR *)WLDiagEvt_FirstLogonSuccessSwitchToUserDesktop_Stop;
    if ( !*((_DWORD *)a2[4] + 130) )
      v39 = &WLDiagEvt_NthLogonSuccessSwitchToUserDesktop_Stop;
    WLEventWrite(v39);
    PerformPostOOBEWorkIfNecessary((struct _WLSM_GLOBAL_CONTEXT *)a2);
    if ( !v59 )
    {
      RecordBlackboxInfo(L"WluiReleaseUI", 1, (struct _WLSM_GLOBAL_CONTEXT *)a2);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
      {
        CallWithHangTimeout::CallWithHangTimeout(v54, 0);
        WluiReleaseUI();
        CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)v54);
      }
      else
      {
        WluiReleaseUI();
      }
      RecordBlackboxInfo(L"WluiReleaseUI", 0, (struct _WLSM_GLOBAL_CONTEXT *)a2);
    }
    CSession::SetShellStartupCompleteOrTimedOut(a2[2], v40);
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0xC0070000;
    LODWORD(v58) = v4;
    dwFlags = 2;
    WinlogonProvider::ShellStartupWaitStopReason<enum ShellStartupWaitStopReason,long>(&dwFlags, &v58);
    RecordBlackboxInfo(L"ShellStartupSkipWaitDueToFailure", 0, (struct _WLSM_GLOBAL_CONTEXT *)a2);
  }
}

```

## disassembly

```asm
0x1400176f8  mov     rax, rsp
0x1400176fb  mov     [rax+18h], r8d
0x1400176ff  mov     [rax+10h], rdx
0x140017703  mov     [rax+8], rcx
0x140017707  push    rbx
0x140017708  push    rsi
0x140017709  push    rdi
0x14001770a  push    r12
0x14001770c  push    r13
0x14001770e  push    r14
0x140017710  sub     rsp, 0F8h
0x140017717  mov     rdi, rdx
0x14001771a  mov     ebx, 57h ; 'W'
0x14001771f  mov     [rsp+128h+var_D0], ebx
0x140017723  xor     r14d, r14d
0x140017726  mov     [rsp+128h+var_D8], r14d
0x14001772b  mov     [rsp+128h+var_C8], r14
0x140017730  mov     dword ptr [rax+20h], 1Eh
0x140017737  mov     rcx, [rdx+10h]; this
0x14001773b  call    ?IsBoundToConsole@CSession@@QEAAHXZ; CSession::IsBoundToConsole(void)
0x140017740  mov     ecx, r14d
0x140017743  test    eax, eax
0x140017745  setz    cl
0x140017748  mov     [rsp+128h+var_AC], ecx
0x14001774c  mov     [rsp+128h+var_A8], ecx
0x140017753  mov     rax, [rdi+20h]
0x140017757  mov     esi, [rax+210h]
0x14001775d  mov     [rsp+128h+var_B0], esi
0x140017761  mov     r13d, 258h
0x140017767  mov     dl, 1
0x140017769  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait> `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::GetImpl(void)'::`2'::impl
0x140017770  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140017775  mov     [rsp+128h+dwFlags], r14d
0x14001777a  lea     r9, [rsp+128h+dwFlags]; unsigned int *
0x14001777f  lea     r8, aRestorestatus; "RestoreStatus"
0x140017786  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001778d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x140017792  test    eax, eax
0x140017794  js      short loc_1400177A4
0x140017796  mov     eax, 384h
0x14001779b  cmp     [rsp+128h+dwFlags], r14d
0x1400177a0  cmovnz  r13d, eax
0x1400177a4  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x1400177a9  test    al, al
0x1400177ab  jnz     short loc_1400177D9
0x1400177ad  call    ?IsCredentialReset@@YA_NXZ; IsCredentialReset(void)
0x1400177b2  test    al, al
0x1400177b4  jnz     short loc_1400177D9
0x1400177b6  call    ?IsAutoLogonAfterCredentialReset@@YA_NXZ; IsAutoLogonAfterCredentialReset(void)
0x1400177bb  test    al, al
0x1400177bd  jnz     short loc_1400177D9
0x1400177bf  cmp     esi, 1
0x1400177c2  jz      short loc_1400177D9
0x1400177c4  lea     r12, WPP_GLOBAL_Control
0x1400177cb  mov     esi, 1000h
0x1400177d0  lea     r14, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x1400177d7  jmp     short loc_140017828
0x1400177d9  lea     r12, WPP_GLOBAL_Control
0x1400177e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400177e7  mov     esi, 1000h
0x1400177ec  cmp     rcx, r12
0x1400177ef  jz      short loc_140017816
0x1400177f1  test    [rcx+1Ch], esi
0x1400177f4  jz      short loc_140017816
0x1400177f6  lea     r14, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x1400177fd  cmp     byte ptr [rcx+19h], 4
0x140017801  jb      short loc_14001781D
0x140017803  mov     edx, 42h ; 'B'
0x140017808  mov     r8, r14
0x14001780b  mov     rcx, [rcx+10h]
0x14001780f  call    WPP_SF_
0x140017814  jmp     short loc_14001781D
0x140017816  lea     r14, WPP_39cb63f4e0673f371acc3dc75ad2363e_Traceguids
0x14001781d  mov     [rsp+128h+arg_18], 258h
0x140017828  mov     ecx, 1
0x14001782d  mov     [rsp+128h+var_C0], ecx
0x140017831  lea     rax, [rsp+128h+var_C0]
0x140017836  mov     [rsp+128h+var_108], rax; unsigned int *
0x14001783b  mov     r9d, ecx; unsigned int
0x14001783e  lea     r8, aFirstlogon; "FirstLogon"
0x140017845  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001784c  mov     rcx, [rdi+20h]; this
0x140017850  call    ?RegQueryDWORD@CUser@@QEAAKPEBG0KPEAK@Z; CUser::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x140017855  cmp     [rsp+128h+var_C0], 1
0x14001785a  jnz     short loc_1400178BC
0x14001785c  mov     rcx, cs:WPP_GLOBAL_Control
0x140017863  cmp     rcx, r12
0x140017866  jz      short loc_140017884
0x140017868  test    [rcx+1Ch], esi
0x14001786b  jz      short loc_140017884
0x14001786d  cmp     byte ptr [rcx+19h], 4
0x140017871  jb      short loc_140017884
0x140017873  mov     edx, 43h ; 'C'
0x140017878  mov     r8, r14
0x14001787b  mov     rcx, [rcx+10h]
0x14001787f  call    WPP_SF_
0x140017884  mov     rax, [rdi+20h]
0x140017888  mov     dword ptr [rax+208h], 1
0x140017892  mov     [rsp+128h+arg_18], 258h
0x14001789d  mov     dl, 1
0x14001789f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait> `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::GetImpl(void)'::`2'::impl
0x1400178a6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400178ab  mov     [rsp+128h+arg_18], r13d
0x1400178b3  mov     rcx, [rdi+20h]; this
0x1400178b7  call    ?RegSetDWORD@CUser@@QEAAKPEBG0K@Z; CUser::RegSetDWORD(ushort const *,ushort const *,ulong)
0x1400178bc  mov     r9d, [rsp+128h+arg_18]; unsigned int
0x1400178c4  mov     [rsp+128h+var_B4], r9d
0x1400178c9  mov     rax, [rdi+20h]
0x1400178cd  cmp     dword ptr [rax+208h], 0
0x1400178d4  jz      short loc_1400178FE
0x1400178d6  lea     rax, [rsp+128h+arg_18]
0x1400178de  mov     [rsp+128h+var_108], rax; unsigned int *
0x1400178e3  lea     r8, aFirstlogontime; "FirstLogonTimeout"
0x1400178ea  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400178f1  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x1400178f6  mov     r9d, [rsp+128h+arg_18]; unsigned int
0x1400178fe  lea     rax, [rsp+128h+arg_18]
0x140017906  mov     [rsp+128h+var_108], rax; unsigned int *
0x14001790b  lea     r8, aDelayeddesktop; "DelayedDesktopSwitchTimeout"
0x140017912  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140017919  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x14001791e  lea     rax, [rsp+128h+arg_18]
0x140017926  mov     [rsp+128h+var_108], rax; unsigned int *
0x14001792b  mov     r9d, [rsp+128h+arg_18]; unsigned int
0x140017933  lea     r8, aDelayeddesktop; "DelayedDesktopSwitchTimeout"
0x14001793a  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140017941  mov     rcx, [rdi+20h]; this
0x140017945  call    ?RegQueryDWORD@CUser@@QEAAKPEBG0KPEAK@Z; CUser::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x14001794a  cmp     [rsp+128h+arg_18], 0
0x140017952  jnz     short loc_14001798D
0x140017954  mov     rcx, cs:WPP_GLOBAL_Control
0x14001795b  cmp     rcx, r12
0x14001795e  jz      loc_140017E96
0x140017964  test    [rcx+1Ch], esi
0x140017967  jz      loc_140017E96
0x14001796d  cmp     byte ptr [rcx+19h], 4
0x140017971  jb      loc_140017E96
0x140017977  mov     edx, 44h ; 'D'
0x14001797c  mov     r8, r14
0x14001797f  mov     rcx, [rcx+10h]
0x140017983  call    WPP_SF_
0x140017988  jmp     loc_140017E96
0x14001798d  mov     rax, [rdi+20h]
0x140017991  cmp     dword ptr [rax+208h], 0
0x140017998  jz      loc_140017C34
0x14001799e  mov     [rsp+128h+var_BC], 0
0x1400179a6  lea     rax, [rsp+128h+var_BC]
0x1400179ab  mov     [rsp+128h+var_108], rax; unsigned int *
0x1400179b0  xor     r9d, r9d; unsigned int
0x1400179b3  lea     r8, aEnablefirstlog; "EnableFirstLogonAnimation"
0x1400179ba  lea     rdx, aSoftwareMicros_48; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400179c1  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x1400179c6  mov     ebx, 1
0x1400179cb  mov     [rsp+128h+var_B8], ebx
0x1400179cf  lea     rax, [rsp+128h+var_B8]
0x1400179d4  mov     [rsp+128h+var_108], rax; unsigned int *
0x1400179d9  mov     r9d, ebx; unsigned int
0x1400179dc  lea     r8, aEnablefirstlog; "EnableFirstLogonAnimation"
0x1400179e3  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400179ea  call    ?RegQueryDWORD@CMachine@@QEAAKPEBG0KPEAK@Z; CMachine::RegQueryDWORD(ushort const *,ushort const *,ulong,ulong *)
0x1400179ef  cmp     [rsp+128h+var_BC], 0
0x1400179f4  jz      loc_140017C0A
0x1400179fa  cmp     [rsp+128h+var_B8], 0
0x1400179ff  jz      loc_140017C0A
0x140017a05  cmp     [rsp+128h+arg_10], 0
0x140017a0d  jnz     loc_140017C0A
0x140017a13  mov     [rsp+128h+dwFlags], 0
0x140017a1b  xor     edx, edx; int
0x140017a1d  mov     rcx, [rdi+20h]; this
0x140017a21  call    ?ImpersonateUser@CUser@@QEAAKH@Z; CUser::ImpersonateUser(int)
0x140017a26  mov     ebx, eax
0x140017a28  mov     [rsp+128h+var_D0], eax
0x140017a2c  test    eax, eax
0x140017a2e  jz      short loc_140017A6C
0x140017a30  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a37  cmp     rcx, r12
0x140017a3a  jz      loc_140017E96
0x140017a40  test    [rcx+1Ch], esi
0x140017a43  jz      loc_140017E96
0x140017a49  cmp     byte ptr [rcx+19h], 2
0x140017a4d  jb      loc_140017E96
0x140017a53  mov     edx, 45h ; 'E'
0x140017a58  mov     r9d, eax
0x140017a5b  mov     r8, r14
0x140017a5e  mov     rcx, [rcx+10h]
0x140017a62  call    WPP_SF_d
0x140017a67  jmp     loc_140017E96
0x140017a6c  mov     ebx, 1
0x140017a71  mov     [rsp+128h+var_D8], ebx
0x140017a75  lea     rcx, [rsp+128h+dwFlags]; dwFlags
0x140017a7a  call    cs:__imp_GetProfileType
0x140017a80  test    eax, eax
0x140017a82  jnz     short loc_140017AB0
0x140017a84  mov     rax, cs:WPP_GLOBAL_Control
0x140017a8b  cmp     rax, r12
0x140017a8e  jz      short loc_140017ADD
0x140017a90  test    [rax+1Ch], esi
0x140017a93  jz      short loc_140017ADD
0x140017a95  cmp     byte ptr [rax+19h], 2
0x140017a99  jb      short loc_140017ADD
0x140017a9b  call    cs:__imp_GetLastError
0x140017aa1  lea     edx, [rbx+45h]
0x140017aa4  mov     r9d, eax
0x140017aa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140017aae  jmp     short loc_140017AD1
0x140017ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x140017ab7  cmp     rcx, r12
0x140017aba  jz      short loc_140017ADD
0x140017abc  test    [rcx+1Ch], esi
0x140017abf  jz      short loc_140017ADD
0x140017ac1  cmp     byte ptr [rcx+19h], 4
0x140017ac5  jb      short loc_140017ADD
0x140017ac7  mov     edx, 47h ; 'G'
0x140017acc  mov     r9d, [rsp+128h+dwFlags]
0x140017ad1  mov     r8, r14
0x140017ad4  mov     rcx, [rcx+10h]
0x140017ad8  call    WPP_SF_d
0x140017add  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x140017ae2  xor     eax, eax
0x140017ae4  mov     [rsp+128h+var_D8], eax
0x140017ae8  test    byte ptr [rsp+128h+dwFlags], bl
0x140017aec  jnz     loc_140017BE2
0x140017af2  cmp     cs:?g_fLaunchedFirstLogonAnimation@@3HA, eax; int g_fLaunchedFirstLogonAnimation
0x140017af8  jnz     loc_140017BE2
0x140017afe  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140017b01  mov     edx, ebx; int
0x140017b03  lea     rcx, aWluiinformlogo; "WluiInformLogonUI"
0x140017b0a  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140017b0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2> `wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl(void)'::`2'::impl
0x140017b16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(void)
0x140017b1b  test    al, al
0x140017b1d  jz      short loc_140017B52
0x140017b1f  xor     edx, edx
0x140017b21  lea     rcx, [rsp+128h+var_60]
0x140017b29  call    ??0CallWithHangTimeout@@QEAA@W4TimeoutDuration@0@@Z; CallWithHangTimeout::CallWithHangTimeout(CallWithHangTimeout::TimeoutDuration)
0x140017b2e  xor     r8d, r8d
0x140017b31  lea     edx, [r8+4]
0x140017b35  lea     ecx, [rdx+1]
0x140017b38  call    WluiInformLogonUI
0x140017b3d  mov     ebx, eax
0x140017b3f  mov     [rsp+128h+var_D0], eax
0x140017b43  lea     rcx, [rsp+128h+var_60]; this
0x140017b4b  call    ??1CallWithHangTimeout@@QEAA@XZ; CallWithHangTimeout::~CallWithHangTimeout(void)
0x140017b50  jmp     short loc_140017B67
0x140017b52  xor     r8d, r8d
0x140017b55  lea     edx, [r8+4]
0x140017b59  lea     ecx, [rdx+1]
0x140017b5c  call    WluiInformLogonUI
0x140017b61  mov     ebx, eax
0x140017b63  mov     [rsp+128h+var_D0], eax
0x140017b67  mov     r8, rdi; struct _WLSM_GLOBAL_CONTEXT *
0x140017b6a  xor     edx, edx; int
0x140017b6c  lea     rcx, aWluiinformlogo; "WluiInformLogonUI"
0x140017b73  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
0x140017b78  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b7f  cmp     rcx, r12
0x140017b82  jz      short loc_140017BB0
0x140017b84  test    [rcx+1Ch], esi
0x140017b87  jz      short loc_140017BB0
0x140017b89  cmp     byte ptr [rcx+19h], 4
0x140017b8d  jb      short loc_140017BB0
0x140017b8f  mov     edx, 48h ; 'H'
0x140017b94  mov     [rsp+128h+var_100], ebx
0x140017b98  mov     dword ptr [rsp+128h+var_108], 4
0x140017ba0  lea     r9d, [rdx-43h]
0x140017ba4  mov     r8, r14
0x140017ba7  mov     rcx, [rcx+10h]
0x140017bab  call    WPP_SF_lll
0x140017bb0  mov     ebx, 1
0x140017bb5  mov     cs:?g_fLaunchedFirstLogonAnimation@@3HA, ebx; int g_fLaunchedFirstLogonAnimation
0x140017bbb  mov     dl, bl
0x140017bbd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait> `wil::Feature<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::GetImpl(void)'::`2'::impl
0x140017bc4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BackupRestoreCoordinatorWait>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140017bc9  mov     [rsp+128h+var_B4], r13d
0x140017bce  cmp     [rsp+128h+arg_18], r13d
0x140017bd6  jnz     short loc_140017C0A
0x140017bd8  mov     [rsp+128h+arg_18], r13d
0x140017be0  jmp     short loc_140017C0A
0x140017be2  mov     rcx, cs:WPP_GLOBAL_Control
0x140017be9  cmp     rcx, r12
0x140017bec  jz      short loc_140017C0A
0x140017bee  test    [rcx+1Ch], esi
0x140017bf1  jz      short loc_140017C0A
0x140017bf3  cmp     byte ptr [rcx+19h], 4
0x140017bf7  jb      short loc_140017C0A
0x140017bf9  mov     edx, 49h ; 'I'
0x140017bfe  mov     r8, r14
0x140017c01  mov     rcx, [rcx+10h]
0x140017c05  call    WPP_SF_
0x140017c0a  cmp     cs:?g_fLaunchedFirstLogonAnimation@@3HA, 0; int g_fLaunchedFirstLogonAnimation
0x140017c11  jnz     short loc_140017C34
0x140017c13  mov     ecx, 3F5h
0x140017c18  lea     eax, [rcx-2]
0x140017c1b  cmp     [rsp+128h+var_B0], ebx
0x140017c1f  cmovnz  ecx, eax
0x140017c22  mov     r9, [rdi+20h]
0x140017c26  mov     edx, 4
0x140017c2b  lea     r8d, [rdx+0Ch]
0x140017c2f  call    ?WlDisplayStatusByResourceId@@YAKIW4_WLUI_STATE@@KPEAVCUser@@@Z; WlDisplayStatusByResourceId(uint,_WLUI_STATE,ulong,CUser *)
0x140017c34  xor     edx, edx; int
  ... truncated ...
```
