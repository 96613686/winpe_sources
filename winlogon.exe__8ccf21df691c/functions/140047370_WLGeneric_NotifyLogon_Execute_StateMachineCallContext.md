# WLGeneric_NotifyLogon_Execute(_StateMachineCallContext *)

- ea: `0x140047370`
- end: `0x140048afc`
- name: `?WLGeneric_NotifyLogon_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `6028`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `69`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x140001dbc`
- `0x140002300`
- `0x14000246c`
- `0x1400057f4`
- `0x1400060d0`
- `0x1400064b0`
- `0x140006970`
- `0x14000cb50`
- `0x14000d4e0`
- `0x14000f8b4`
- `0x14000fb98`
- `0x140013050`
- `0x140013be8`
- `0x140014370`
- `0x140016850`
- `0x140016a30`
- `0x140016f30`
- `0x1400198e0`
- `0x14001a200`
- `0x1400253c8`
- `0x14002a944`
- `0x14002ba10`
- `0x14002c218`
- `0x14002f800`
- `0x1400333b0`
- `0x140034700`
- `0x1400378d0`
- `0x140037b00`
- `0x140039458`
- `0x14003ba30`
- `0x14003ba50`
- `0x14003be1c`
- `0x14003c318`
- `0x14003d7d8`
- `0x14003f584`
- `0x14003fbcc`
- `0x14003fc3c`
- `0x1400403d8`
- `0x140041c34`
- `0x140042ad8`
- `0x140042d80`
- `0x140043178`
- `0x1400436f8`
- `0x140043970`
- `0x140044800`
- `0x140047370`
- `0x14004a034`
- `0x14004a234`
- `0x14004d74c`
- `0x14004dcb4`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x140048433`
- `api-ms-win-core-localization-l1-2-0!GetThreadUILanguage` at `0x140048433`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140047bc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140047cc2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140047bc7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140047cc2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140047b80`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140047b80`
- `ntdll!WinSqmStartSession` at `0x1400474bd`
- `ntdll!WinSqmStartSession` at `0x1400474bd`
- `ntdll!RtlLengthSid` at `0x1400482ab`
- `ntdll!RtlLengthSid` at `0x1400482ab`
- `ext-ms-win-gui-uxinit-l1-1-0!ThemesOnLogon` at `0x140047813`
- `ext-ms-win-gui-uxinit-l1-1-0!ThemesOnLogon` at `0x1400483ce`
- `ext-ms-win-gui-uxinit-l1-1-0!ThemesOnLogon` at `0x140047813`
- `ext-ms-win-gui-uxinit-l1-1-0!ThemesOnLogon` at `0x1400483ce`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x14004833d`
- `ext-ms-win-ntuser-private-l1-1-0!UpdatePerUserSystemParameters` at `0x14004833d`
- `ext-ms-win-ntuser-private-l1-1-0!SetWindowStationUser` at `0x1400482c8`
- `ext-ms-win-ntuser-private-l1-1-0!SetWindowStationUser` at `0x1400482c8`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x14004769c`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x14004769c`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x14004768e`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x14004768e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformUserLogon` at `0x1400484d8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrInformUserLogon` at `0x1400484d8`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrLaunchShellInfrastructureHost` at `0x14004869b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrLaunchShellInfrastructureHost` at `0x14004869b`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x140048300`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x140048300`
- `ext-ms-win-security-crosscontainerauthhelper-l1-1-0!CrossContainerAuthHelperConfigureGuestMachine` at `0x140047860`
- `ext-ms-win-security-crosscontainerauthhelper-l1-1-0!CrossContainerAuthHelperConfigureGuestMachine` at `0x140047860`

## string_xrefs

- `0x14004786f`: `CrossContainerAuthHelper.dll`

## pseudocode

```c
__int64 __fastcall WLGeneric_NotifyLogon_Execute(struct _StateMachineCallContext *a1)
{
  CGlobalStore **v2; // rsi
  unsigned __int16 *String; // r12
  int v4; // r14d
  CGlobalStore *v5; // rax
  __int64 v6; // r9
  PSID v7; // rdi
  DWORD v8; // edi
  CUser *v9; // rcx
  __int64 v10; // rdx
  unsigned int IsFirstToSetEvent; // eax
  bool v12; // cl
  CUser *v13; // rcx
  unsigned int v14; // eax
  int v15; // eax
  int v16; // edi
  int v17; // ecx
  unsigned __int16 *v18; // rbx
  void *NotifyConfig; // rax
  CUser *v20; // rcx
  void *v21; // rax
  __int64 v22; // rbx
  unsigned __int16 *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  unsigned __int16 *v27; // rax
  unsigned __int16 *v28; // rbx
  unsigned __int16 *v29; // rbx
  int v30; // eax
  const unsigned __int16 *v31; // rbx
  unsigned __int16 *v32; // rcx
  int v33; // r12d
  void *v34; // rax
  __int64 FailedSubscriberName; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 v38; // rax
  unsigned __int16 *v39; // rax
  unsigned __int16 *v40; // rbx
  unsigned __int16 *v41; // r12
  int IsBoundToConsole; // eax
  const unsigned __int16 *v43; // rcx
  int v44; // ecx
  const BYTE *v45; // rax
  struct _WLSM_GLOBAL_CONTEXT *v46; // rcx
  unsigned __int16 *v47; // r14
  int v48; // eax
  CSession *v49; // rcx
  CGlobalStore *v50; // rbx
  ULONG v51; // eax
  unsigned int v52; // ebx
  LANGID ThreadUILanguage; // bx
  CUser *v54; // rcx
  CMachine *v55; // rcx
  unsigned int v56; // ebx
  int v57; // edi
  unsigned int v58; // ebx
  int v59; // edi
  int v60; // eax
  CMachine *v61; // rcx
  unsigned int v62; // eax
  unsigned int v63; // eax
  CUser *v64; // rbx
  unsigned int MachinePolicy; // eax
  unsigned int v66; // eax
  unsigned int v67; // ebx
  int v69; // [rsp+60h] [rbp-1E8h]
  unsigned int v70; // [rsp+64h] [rbp-1E4h] BYREF
  _BYTE v71[8]; // [rsp+68h] [rbp-1E0h] BYREF
  unsigned __int16 *v72; // [rsp+70h] [rbp-1D8h] BYREF
  int v73; // [rsp+78h] [rbp-1D0h] BYREF
  int v74; // [rsp+7Ch] [rbp-1CCh] BYREF
  int v75; // [rsp+80h] [rbp-1C8h] BYREF
  unsigned __int16 *v76; // [rsp+88h] [rbp-1C0h] BYREF
  int v77; // [rsp+90h] [rbp-1B8h] BYREF
  unsigned __int16 *v78; // [rsp+98h] [rbp-1B0h] BYREF
  unsigned int v79; // [rsp+A0h] [rbp-1A8h] BYREF
  DWORD v80; // [rsp+A4h] [rbp-1A4h] BYREF
  unsigned int v81; // [rsp+A8h] [rbp-1A0h] BYREF
  const BYTE *v82; // [rsp+B0h] [rbp-198h] BYREF
  unsigned __int16 *v83; // [rsp+B8h] [rbp-190h] BYREF
  unsigned __int16 *v84; // [rsp+C0h] [rbp-188h] BYREF
  PSID Sid; // [rsp+C8h] [rbp-180h] BYREF
  int v86; // [rsp+D0h] [rbp-178h] BYREF
  int v87; // [rsp+D4h] [rbp-174h]
  int v88; // [rsp+D8h] [rbp-170h]
  unsigned __int16 *v89; // [rsp+E0h] [rbp-168h] BYREF
  __int64 v90; // [rsp+E8h] [rbp-160h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-158h] BYREF
  int v92; // [rsp+F8h] [rbp-150h] BYREF
  __int64 v93; // [rsp+100h] [rbp-148h] BYREF
  struct _GUID *v94; // [rsp+108h] [rbp-140h] BYREF
  struct _GUID *v95; // [rsp+110h] [rbp-138h] BYREF
  _BYTE v96[8]; // [rsp+118h] [rbp-130h] BYREF
  __int64 v97; // [rsp+120h] [rbp-128h] BYREF
  __int64 v98; // [rsp+128h] [rbp-120h] BYREF
  __int64 v99; // [rsp+130h] [rbp-118h]
  const BYTE *v100; // [rsp+138h] [rbp-110h] BYREF
  __int64 v101; // [rsp+140h] [rbp-108h] BYREF
  int v102; // [rsp+148h] [rbp-100h]
  __int64 v103; // [rsp+150h] [rbp-F8h] BYREF
  int v104; // [rsp+158h] [rbp-F0h]
  __int64 v105; // [rsp+160h] [rbp-E8h] BYREF
  struct _GUID *v106; // [rsp+168h] [rbp-E0h] BYREF
  __int128 v107; // [rsp+170h] [rbp-D8h] BYREF
  __int64 v108; // [rsp+180h] [rbp-C8h]
  __int128 v109; // [rsp+190h] [rbp-B8h] BYREF
  __int64 v110; // [rsp+1A0h] [rbp-A8h]
  __int128 v111; // [rsp+1B0h] [rbp-98h] BYREF
  __int64 v112; // [rsp+1C0h] [rbp-88h]
  struct _GUID v113; // [rsp+1D0h] [rbp-78h] BYREF
  struct _GUID v114; // [rsp+1E0h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
  }
  v2 = (CGlobalStore **)*((_QWORD *)a1 + 1);
  StartUserLogonToUxShownTest(v96);
  v84 = 0;
  v83 = 0;
  String = 0;
  v72 = 0;
  v79 = 0;
  v4 = 0;
  v69 = 0;
  v88 = 0;
  v73 = 0;
  v75 = 0;
  v74 = 0;
  v77 = 0;
  v82 = 0;
  v80 = *((_DWORD *)v2[4] + 132);
  v86 = 0;
  v5 = v2[2];
  v6 = *((unsigned int *)v5 + 22);
  dword_1400D18A0 = *((_DWORD *)v5 + 22);
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v6);
  }
  qword_1400D30D8 = (__int64)&dword_1400D18A0;
  qword_1400D30D0 = WinSqmStartSession(&dword_1400D18A0, 984068, 0);
  v7 = (PSID)*((_QWORD *)v2[4] + 15);
  Sid = v7;
  if ( !(unsigned __int8)IsLoadLocalFontsPresent() )
  {
LABEL_17:
    if ( (unsigned __int8)IsSetUserObjectSecurityPresent() )
    {
      v8 = CSession::SetUserDesktopSecurity(v2[2], 2, v7);
      v70 = v8;
      if ( v8 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
          goto LABEL_271;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_270;
        v10 = 171;
        goto LABEL_15;
      }
    }
    v8 = CUser::AddUserToBNO(v2[4], *((_DWORD *)v2[2] + 22));
    v70 = v8;
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
        goto LABEL_271;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_270;
      v10 = 172;
      goto LABEL_15;
    }
    if ( (unsigned __int8)IsUnlockWindowStationPresent() && (unsigned __int8)IsUnlockWindowStationPresent() )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
      }
      UnlockWindowStation(*((_QWORD *)v2[2] + 12));
      LockWindowStation(*((_QWORD *)v2[2] + 12));
    }
    IsFirstToSetEvent = _IsFirstToSetEvent(L"Global\\WinLogon_FirstLogon", &v77);
    v70 = IsFirstToSetEvent;
    if ( IsFirstToSetEvent
      && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        174,
        WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
        IsFirstToSetEvent);
    }
    v8 = CUser::ImpersonateUser(v2[4], 0);
    v70 = v8;
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v10 = 176;
      goto LABEL_15;
    }
    if ( g_TraceRegHandle )
    {
      if ( !v77 || (g_Diagnostics_Status & 2) != 0 )
      {
        v113.Data1 = -1623097062;
        *(_DWORD *)&v113.Data2 = 1118438441;
        *(_DWORD *)v113.Data4 = -724584575;
        *(_DWORD *)&v113.Data4[4] = 524380377;
        WLEventWriteStartStopScenario(v12, &WLDiagEvt_UserBootScenario_Info, &v113, *((_DWORD *)v2[2] + 22));
      }
      else
      {
        v114.Data1 = -2042418677;
        *(_DWORD *)&v114.Data2 = 1306475645;
        *(_DWORD *)v114.Data4 = 790076584;
        *(_DWORD *)&v114.Data4[4] = 1565036714;
        WLEventWriteStartStopScenario(v12, &WLDiagEvt_UserBootScenario_Start, &v114, *((_DWORD *)v2[2] + 22));
        g_Diagnostics_Status |= 2u;
      }
    }
    if ( (unsigned __int8)IsThemesOnLogoffPresent() )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
      }
      WLEventWrite(&WLEvt_ThemesOnLogonPre_Start);
      ThemesOnLogon(0);
      WLEventWrite(&WLEvt_ThemesOnLogonPre_Stop);
    }
    CUser::StopImpersonating(v13);
    v14 = 1013;
    if ( v80 != 1 )
      v14 = 1009;
    v81 = v14;
    WlDisplayStatusByResourceId(v14, 4, 32, v2[4]);
    if ( (unsigned __int8)IsCrossContainerAuthHelperConfigureGuestMachinePresent() )
    {
      v15 = CrossContainerAuthHelperConfigureGuestMachine();
      if ( v15 < 0 )
        MicrosoftTelemetryAssertTriggeredArgs("CrossContainerAuthHelper.dll", (unsigned int)v15, 0);
    }
    v8 = CUser::ImpersonateUser(v2[4], 0);
    v70 = v8;
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v10 = 179;
      goto LABEL_15;
    }
    v69 = 1;
    v8 = CUser::CreatePreNotifyEnvironment(v2[4], &v84);
    v70 = v8;
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v10 = 177;
      goto LABEL_15;
    }
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    }
    wil::srwlock::lock_shared((char *)*v2 + 64, &v90);
    v97 = 0;
    if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v2, &v97) >= 0 )
    {
      v16 = v97;
      if ( v97 )
      {
        v113 = 0;
        WLGetTSActivityId(&v113);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
          {
            v98 = 0x1000000;
            v78 = (unsigned __int16 *)&v113;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
              v17,
              (unsigned int)byte_1400BBBF1,
              v16 + 8,
              (unsigned int)&v113,
              (__int64)&v78,
              (__int64)&v98);
          }
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v90);
    if ( *((_DWORD *)v2[2] + 94) )
      v86 = 1;
    v18 = v84;
    NotifyConfig = CGlobalStore::GetNotifyConfig(*v2, 0, 0);
    v8 = InternalNotifyExecute(NotifyConfig, 2, &v86, DisplayMessage_Callback, 0, v18);
    v70 = v8;
    if ( !v8 )
    {
      v73 = 1;
      v8 = g_dwCreateSessionRet;
      v70 = g_dwCreateSessionRet;
    }
    FailPreviousUserLogonUxShownTest();
    SetCorrelationIdForUserLogonToUxShownTest(v96, (unsigned int)v73);
    CUser::StopImpersonating(v20);
    v69 = 0;
    if ( v8 )
    {
      if ( v8 == 1753 )
      {
        v33 = *((_DWORD *)v2[4] + 38);
        v74 = v33;
        v104 = v33;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
        }
        String = AllocAndLoadString((unsigned int)(v33 != 0) + 1900, v2[4]);
        v72 = String;
        v34 = CGlobalStore::GetNotifyConfig(*v2, 0, 0);
        FailedSubscriberName = GetFailedSubscriberName(v34);
        v36 = FailedSubscriberName;
        v82 = (const BYTE *)FailedSubscriberName;
        v99 = FailedSubscriberName;
        if ( String )
        {
          if ( !FailedSubscriberName )
            goto LABEL_116;
          v37 = -1;
          v38 = -1;
          do
            ++v38;
          while ( String[v38] );
          do
            ++v37;
          while ( *(_WORD *)(v36 + 2 * v37) );
          v78 = (unsigned __int16 *)(unsigned int)(v37 + 1 + v38);
          v39 = (unsigned __int16 *)WLAlloc(2LL * (_QWORD)v78);
          v40 = v39;
          v76 = v39;
          if ( v39 )
          {
            StringCchPrintfW(v39, (unsigned __int64)v78, String, v82);
            UHHeapFree(&v72);
            String = v40;
            v72 = v40;
          }
          else
          {
LABEL_116:
            v76 = String;
          }
          if ( v74 )
          {
            v88 = 1;
            v102 = 1;
            v31 = (const unsigned __int16 *)&pPassword;
          }
          else
          {
            v41 = AllocAndLoadString(0x3E8u, v2[4]);
            v83 = v41;
            IsBoundToConsole = CSession::IsBoundToConsole(v2[2]);
            v111 = 0;
            v112 = 0;
            ToSetTimeout(IsBoundToConsole != 0 ? 120000 : 30000, &v111);
            v31 = (const unsigned __int16 *)&pPassword;
            v43 = (const unsigned __int16 *)&pPassword;
            if ( v41 )
              v43 = v41;
            WlDisplayMessage(v43, v76, 0x10u, &v79);
            ToResetTimeout();
            UHHeapFree(&v72);
            String = v72;
          }
          if ( v83 )
            UHHeapFree(&v83);
        }
        else
        {
          v31 = (const unsigned __int16 *)&pPassword;
        }
        v44 = v75;
        if ( !v74 )
          v44 = 1;
        v75 = v44;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v8);
        }
        String = MyFormatMessage(v8);
        v72 = String;
        if ( String )
        {
          v21 = CGlobalStore::GetNotifyConfig(*v2, 0, 0);
          v22 = GetFailedSubscriberName(v21);
          v82 = (const BYTE *)v22;
          v99 = v22;
          if ( v22 && (v23 = AllocAndLoadString(0x76Fu, v2[4]), (v89 = v23) != 0) )
          {
            v24 = -1;
            v25 = -1;
            do
              ++v25;
            while ( String[v25] );
            v26 = -1;
            do
              ++v26;
            while ( *(_WORD *)(v22 + 2 * v26) );
            do
              ++v24;
            while ( v23[v24] );
            v78 = (unsigned __int16 *)(unsigned int)(v24 + v25 + 1 + v26);
            v27 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (_QWORD)v78);
            v28 = v27;
            v76 = v27;
            if ( v27 )
            {
              if ( (int)StringCchPrintfW(v27, (unsigned __int64)v78, v89, v82, String) < 0 )
                *v28 = 0;
              LocalFree(String);
              String = v28;
              v72 = v28;
            }
            else
            {
              v76 = String;
            }
            UHHeapFree(&v89);
          }
          else
          {
            v76 = String;
          }
          v29 = AllocAndLoadString(0x3E8u, v2[4]);
          v78 = v29;
          v83 = v29;
          v30 = CSession::IsBoundToConsole(v2[2]);
          v109 = 0;
          v110 = 0;
          ToSetTimeout(v30 != 0 ? 120000 : 30000, &v109);
          if ( v29 )
          {
            v89 = v29;
            v31 = (const unsigned __int16 *)&pPassword;
            v32 = v78;
          }
          else
          {
            v31 = (const unsigned __int16 *)&pPassword;
            v32 = (unsigned __int16 *)&pPassword;
            v89 = 0;
          }
          WlDisplayMessage(v32, v76, 0, &v79);
          ToResetTimeout();
          if ( v89 )
            UHHeapFree(&v83);
          LocalFree(String);
          String = 0;
          v72 = 0;
        }
        else
        {
          v31 = (const unsigned __int16 *)&pPassword;
        }
        v75 = 1;
      }
    }
    else
    {
      v31 = (const unsigned __int16 *)&pPassword;
    }
    wil::srwlock::lock_shared((char *)*v2 + 64, &v78);
    v93 = 0;
    if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v2, &v93) >= 0 )
    {
      if ( v93 )
      {
        v113 = 0;
        WLGetTSActivityId(&v113);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
          {
            v80 = v8;
            v77 = *((_DWORD *)v2[2] + 22);
            v45 = &pPassword;
            if ( v82 )
              v45 = v82;
            v100 = v45;
            v92 = v73;
            v101 = 0x1000000;
            v94 = &v113;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (_DWORD)v82,
              (unsigned int)byte_1400BBB55,
              v93 + 8,
              (unsigned int)&v113,
              (__int64)&v94,
              (__int64)&v101,
              (__int64)&v92,
              (__int64)&v74,
              (__int64)&v100,
              (__int64)&v77,
              (__int64)&v80);
          }
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v78);
    if ( v75 )
      goto LABEL_270;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl'::`2'::impl);
    if ( ShouldLoadAadCredKeyFromProfile(v46) )
    {
      v73 = 0;
      v8 = CUser::ConfirmCredKeyAvailablePostProfileLoad(v2[4], &v73);
      if ( (v8 & 0x80000000) != 0 )
      {
        if ( (v8 & 0x1FFF0000) == 0x70000 )
          v8 = (unsigned __int16)v8;
        goto LABEL_143;
      }
      if ( !v73 )
      {
        v8 = v73 == 0 ? 0x1771 : 0;
LABEL_143:
        v70 = v8;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v8);
        }
        WinlogonProvider::ForceLogOffAadUserAsDpApiCredKeyDecryptionFailed<unsigned long &>(&v70);
        String = AllocAndLoadString(0x1B58u, v2[4]);
        v72 = String;
        if ( String )
        {
          v47 = AllocAndLoadString(0x3E8u, v2[4]);
          v83 = v47;
          v48 = CSession::IsBoundToConsole(v2[2]);
          v107 = 0;
          v108 = 0;
          ToSetTimeout(v48 != 0 ? 120000 : 30000, &v107);
          if ( v47 )
            v31 = v47;
          else
            v47 = 0;
          WlDisplayMessage(v31, String, 0x10u, &v79);
          ToResetTimeout();
          if ( v47 )
            UHHeapFree(&v83);
          UHHeapFree(&v72);
          String = v72;
        }
        goto LABEL_261;
      }
    }
    WlDisplayStatusByResourceId(v81, 4, 32, v2[4]);
    v70 = CUser::ImpersonateUser(v2[4], 0);
    if ( !v70 )
    {
      v69 = 1;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
      }
      if ( (unsigned __int8)IsLoadLocalFontsPresent() )
      {
        v91 = 0;
        v91 = *((_QWORD *)v2[4] + 16);
        v50 = v2[2];
        v51 = RtlLengthSid(Sid);
        SetWindowStationUser(*((_QWORD *)v50 + 12), &v91, Sid, v51);
      }
      v87 = 1;
      if ( (unsigned int)CSession::IsBoundToConsole(v2[2]) )
      {
        v71[0] = 0;
        if ( !(unsigned __int8)IsWinStationConnectAndLockDesktopPresent()
          || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v71) )
        {
          v71[0] = 0;
        }
        v52 = 1;
        if ( v71[0] )
          v52 = 5;
      }
      else
      {
        v52 = 5;
      }
      v87 = v52;
      if ( (unsigned __int8)IsLoadLocalFontsPresent() )
      {
        WLEventWrite(&WLEvt_UpdatePerUserSystemParameters_Start, v52);
        if ( !(unsigned int)UpdatePerUserSystemParameters(v52)
          && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
        }
        WLEventWrite(&WLEvt_UpdatePerUserSystemParameters_Stop, v52);
      }
      ThreadUILanguage = 0;
      if ( (unsigned __int8)IsThemesOnLogoffPresent() )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
        }
        WLEventWrite(&WLEvt_ThemesOnLogonPost_Start);
        ThemesOnLogon(1);
        WLEventWrite(&WLEvt_ThemesOnLogonPost_Stop);
      }
      v8 = CUser::OpenHKeyCurrentUser(v2[4]);
      v70 = v8;
      if ( v8 )
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_270;
        }
        v10 = 186;
        goto LABEL_15;
      }
      if ( (unsigned __int8)IsWinLogonExtPresent() )
        ThreadUILanguage = GetThreadUILanguage();
      CUser::StopImpersonating(v54);
      v69 = 0;
      if ( (unsigned __int8)IsWinLogonExtPresent() )
      {
        RecordBlackboxInfo(L"WluiNotifyUserIsLoggedOn", 1, (struct _WLSM_GLOBAL_CONTEXT *)v2);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
        {
          CallWithHangTimeout::CallWithHangTimeout(&v107, 0);
          WluiNotifyUserIsLoggedOn(ThreadUILanguage);
          CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)&v107);
        }
        else
        {
          WluiNotifyUserIsLoggedOn(ThreadUILanguage);
        }
        RecordBlackboxInfo(L"WluiNotifyUserIsLoggedOn", 0, (struct _WLSM_GLOBAL_CONTEXT *)v2);
      }
    }
    if ( (unsigned int)CSession::IsShellRequiredInSession(v49) )
    {
      if ( (unsigned __int8)IsUMgrLaunchShellInfrastructureHostPresent() )
      {
        v56 = UMgrInformUserLogon(*((_QWORD *)v2[4] + 17));
        if ( (v56 & 0x1FFF0000) == 0x70000 )
          v56 = (unsigned __int16)v56;
        v70 = v56;
        wil::srwlock::lock_shared((char *)*v2 + 64, &v94);
        Sid = 0;
        if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v2, &Sid) >= 0 )
        {
          v57 = (int)Sid;
          if ( Sid )
          {
            v113 = 0;
            WLGetTSActivityId(&v113);
            if ( (unsigned int)dword_1400CF778 > 5 )
            {
              v81 = v56;
              v75 = *((_DWORD *)v2[2] + 22);
              v103 = 0x1000000;
              v95 = &v113;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v75,
                (unsigned int)byte_1400BBAF1,
                v57 + 8,
                (unsigned int)&v113,
                (__int64)&v95,
                (__int64)&v103,
                (__int64)&v75,
                (__int64)&v81);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v94);
        if ( v56 )
        {
          v55 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v56);
          }
          v70 = 0;
        }
      }
      if ( (unsigned int)CMachine::IsSiHostIntegrationEnabled(v55) )
      {
        v8 = CSession::SubscribeForWnfNotifications(v2[2]);
        v70 = v8;
        if ( v8 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_270;
          }
          v10 = 188;
          goto LABEL_15;
        }
        RecordBlackboxInfo(L"UMgrLaunchShellInfrastructureHost", 1, (struct _WLSM_GLOBAL_CONTEXT *)v2);
        v58 = UMgrLaunchShellInfrastructureHost(*((_QWORD *)v2[4] + 15));
        RecordBlackboxInfo(L"UMgrLaunchShellInfrastructureHost", 0, (struct _WLSM_GLOBAL_CONTEXT *)v2);
        if ( (v58 & 0x1FFF0000) == 0x70000 )
          v58 = (unsigned __int16)v58;
        v70 = v58;
        wil::srwlock::lock_shared((char *)*v2 + 64, &v95);
        v90 = 0;
        if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v2, &v90) >= 0 )
        {
          v59 = v90;
          if ( v90 )
          {
            v113 = 0;
            WLGetTSActivityId(&v113);
            if ( (unsigned int)dword_1400CF778 > 5 )
            {
              LODWORD(v76) = v58;
              LODWORD(v82) = *((_DWORD *)v2[2] + 22);
              v105 = 0x1000000;
              v106 = &v113;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (_DWORD)v82,
                (unsigned int)&byte_1400BBA8F,
                v59 + 8,
                (unsigned int)&v113,
                (__int64)&v106,
                (__int64)&v105,
                (__int64)&v82,
                (__int64)&v76);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v95);
        if ( v58 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v58);
          }
          v70 = 0;
        }
      }
    }
    v60 = WlSecureDesktopiStartup(*((_QWORD *)v2[4] + 20));
    if ( v60 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          191,
          WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
          (unsigned int)v60);
      }
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    }
    v8 = CUser::ApplyLogonHoursRestrictions(v2[4]);
    v70 = v8;
    if ( v8 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v10 = 192;
      goto LABEL_15;
    }
    if ( v88 )
    {
      v62 = WlRemindersDisplay(7, String, 0);
      v70 = v62;
      if ( v62
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v62);
      }
      UHHeapFree(&v72);
      v8 = 0;
      v70 = 0;
      String = v72;
    }
    if ( *((_DWORD *)v2[4] + 38) && (unsigned int)CMachine::IsAuditingLogFull(v61) )
    {
      v63 = WlRemindersDisplay(2, 0, 0);
      v70 = v63;
      if ( v63
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v63);
      }
      v8 = 0;
      v70 = 0;
    }
    v64 = v2[4];
    MachinePolicy = CMachine::GetMachinePolicy(v2[1], L"ReportControllerMissing", 0xFFFFFFFF);
    if ( !(unsigned int)CUser::ShouldReportCachedLogon(v64, MachinePolicy) )
      goto LABEL_270;
    v66 = WlRemindersDisplay(6, 0, 0);
    v70 = v66;
    if ( v66 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v66);
      }
    }
    v8 = 0;
    v70 = 0;
LABEL_261:
    v4 = 0;
    goto LABEL_271;
  }
  v8 = AddUserToWinsta(*((HWINSTA *)v2[2] + 12), *((void **)v2[2] + 13), v7, *((PSID *)v2[4] + 20));
  v70 = v8;
  if ( !v8 )
  {
    WLEventWriteWinSqmUserSessionChange(&WLEvt_WinSqmUserLogin, *((_DWORD *)v2[2] + 22), *((void **)v2[4] + 20));
    v7 = Sid;
    goto LABEL_17;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
    goto LABEL_271;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
    goto LABEL_261;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v10 = 170;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v9 + 2), v10, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v8);
  }
LABEL_270:
  v4 = v69;
LABEL_271:
  if ( v4 )
    CUser::StopImpersonating(v9);
  if ( v84 )
    UHHeapFree(&v84);
  if ( String )
    UHHeapFree(&v72);
  v67 = WlStateMachineSetSignal(v8 != 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v96);
  return v67;
}

```

## disassembly

```asm
0x140047370  mov     rax, rsp
0x140047373  mov     [rax+10h], rbx
0x140047377  mov     [rax+18h], rsi
0x14004737b  push    rdi
0x14004737c  push    r12
0x14004737e  push    r13
0x140047380  push    r14
0x140047382  push    r15
0x140047384  sub     rsp, 220h
0x14004738b  movaps  xmmword ptr [rax-38h], xmm6
0x14004738f  movaps  xmmword ptr [rax-48h], xmm7
0x140047393  mov     rax, cs:__security_cookie
0x14004739a  xor     rax, rsp
0x14004739d  mov     [rsp+248h+var_58], rax
0x1400473a5  mov     rsi, rcx
0x1400473a8  lea     rbx, WPP_GLOBAL_Control
0x1400473af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400473b6  cmp     rcx, rbx
0x1400473b9  jz      short loc_1400473E4
0x1400473bb  test    dword ptr [rcx+1Ch], 100h
0x1400473c2  jz      short loc_1400473E4
0x1400473c4  lea     r15, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400473cb  cmp     byte ptr [rcx+19h], 4
0x1400473cf  jb      short loc_1400473EB
0x1400473d1  mov     edx, 0A9h
0x1400473d6  mov     r8, r15
0x1400473d9  mov     rcx, [rcx+10h]
0x1400473dd  call    WPP_SF_
0x1400473e2  jmp     short loc_1400473EB
0x1400473e4  lea     r15, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400473eb  mov     rsi, [rsi+8]
0x1400473ef  lea     rcx, [rsp+248h+var_130]
0x1400473f7  call    ?StartUserLogonToUxShownTest@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; StartUserLogonToUxShownTest(void)
0x1400473fc  xor     r13d, r13d
0x1400473ff  mov     [rsp+248h+var_188], r13
0x140047407  mov     [rsp+248h+var_190], r13
0x14004740f  mov     r12d, r13d
0x140047412  mov     [rsp+248h+var_1D8], r13
0x140047417  mov     [rsp+248h+var_1A8], r13d
0x14004741f  mov     r14d, r13d
0x140047422  mov     [rsp+248h+var_1E8], r13d
0x140047427  mov     [rsp+248h+var_170], r13d
0x14004742f  mov     [rsp+248h+var_1D0], r13d
0x140047434  mov     [rsp+248h+var_1C8], r13d
0x14004743c  mov     [rsp+248h+var_1CC], r13d
0x140047441  mov     [rsp+248h+var_1B8], r13d
0x140047449  mov     [rsp+248h+var_198], r13
0x140047451  mov     rax, [rsi+20h]
0x140047455  mov     eax, [rax+210h]
0x14004745b  mov     [rsp+248h+var_1A4], eax
0x140047462  mov     [rsp+248h+var_178], r13d
0x14004746a  mov     rax, [rsi+10h]
0x14004746e  mov     r9d, [rax+58h]
0x140047472  mov     cs:dword_1400D18A0, r9d
0x140047479  mov     rcx, cs:WPP_GLOBAL_Control
0x140047480  cmp     rcx, rbx
0x140047483  lea     ebx, [r13+1]
0x140047487  jz      short loc_1400474A7
0x140047489  test    [rcx+1Ch], bl
0x14004748c  jz      short loc_1400474A7
0x14004748e  cmp     byte ptr [rcx+19h], 5
0x140047492  jb      short loc_1400474A7
0x140047494  lea     edx, [rbx+5Eh]
0x140047497  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14004749e  mov     rcx, [rcx+10h]
0x1400474a2  call    WPP_SF_d
0x1400474a7  lea     rcx, dword_1400D18A0
0x1400474ae  mov     cs:qword_1400D30D8, rcx
0x1400474b5  xor     r8d, r8d
0x1400474b8  mov     edx, 0F0404h
0x1400474bd  call    cs:__imp_WinSqmStartSession
0x1400474c3  mov     cs:qword_1400D30D0, rax
0x1400474ca  mov     rax, [rsi+20h]
0x1400474ce  mov     rdi, [rax+78h]
0x1400474d2  mov     [rsp+248h+Sid], rdi
0x1400474da  call    IsLoadLocalFontsPresent
0x1400474df  test    al, al
0x1400474e1  jz      loc_140047586
0x1400474e7  mov     rcx, [rsi+10h]
0x1400474eb  mov     r9, [rsi+20h]
0x1400474ef  mov     r9, [r9+0A0h]; PSID
0x1400474f6  mov     r8, rdi; SourceSid
0x1400474f9  mov     rdx, [rcx+68h]; void *
0x1400474fd  mov     rcx, [rcx+60h]; hObj
0x140047501  call    AddUserToWinsta
0x140047506  mov     edi, eax
0x140047508  mov     [rsp+248h+var_1E4], eax
0x14004750c  test    eax, eax
0x14004750e  jz      short loc_140047560
0x140047510  mov     rcx, cs:WPP_GLOBAL_Control; this
0x140047517  lea     rax, WPP_GLOBAL_Control
0x14004751e  cmp     rcx, rax
0x140047521  jz      loc_140048A75
0x140047527  mov     r14d, 1000h
0x14004752d  test    [rcx+1Ch], r14d
0x140047531  jz      loc_140048A14
0x140047537  mov     r13d, 2
0x14004753d  cmp     [rcx+19h], r13b
0x140047541  jb      loc_140048A6D
0x140047547  mov     edx, 0AAh
0x14004754c  mov     r9d, edi
0x14004754f  mov     r8, r15
0x140047552  mov     rcx, [rcx+10h]
0x140047556  call    WPP_SF_d
0x14004755b  jmp     loc_140048A6D
0x140047560  mov     r8, [rsi+20h]
0x140047564  mov     rdx, [rsi+10h]
0x140047568  mov     r8, [r8+0A0h]; void *
0x14004756f  mov     edx, [rdx+58h]; unsigned int
0x140047572  lea     rcx, WLEvt_WinSqmUserLogin; struct _EVENT_DESCRIPTOR *
0x140047579  call    ?WLEventWriteWinSqmUserSessionChange@@YAXAEBU_EVENT_DESCRIPTOR@@KPEAX@Z; WLEventWriteWinSqmUserSessionChange(_EVENT_DESCRIPTOR const &,ulong,void *)
0x14004757e  mov     rdi, [rsp+248h+Sid]
0x140047586  call    IsSetUserObjectSecurityPresent
0x14004758b  mov     r13d, 2
0x140047591  test    al, al
0x140047593  jz      short loc_1400475E9
0x140047595  mov     r8, rdi
0x140047598  mov     edx, r13d
0x14004759b  mov     rcx, [rsi+10h]
0x14004759f  call    ?SetUserDesktopSecurity@CSession@@QEAAKW4_DESKTOPID@@PEAX@Z; CSession::SetUserDesktopSecurity(_DESKTOPID,void *)
0x1400475a4  mov     edi, eax
0x1400475a6  mov     [rsp+248h+var_1E4], eax
0x1400475aa  test    eax, eax
0x1400475ac  jz      short loc_1400475E9
0x1400475ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400475b5  lea     rax, WPP_GLOBAL_Control
0x1400475bc  cmp     rcx, rax
0x1400475bf  jz      loc_140048A72
0x1400475c5  mov     r14d, 1000h
0x1400475cb  test    [rcx+1Ch], r14d
0x1400475cf  jz      loc_140048A6D
0x1400475d5  cmp     [rcx+19h], r13b
0x1400475d9  jb      loc_140048A6D
0x1400475df  mov     edx, 0ABh
0x1400475e4  jmp     loc_14004754C
0x1400475e9  mov     rdx, [rsi+10h]
0x1400475ed  mov     edx, [rdx+58h]; unsigned int
0x1400475f0  mov     rcx, [rsi+20h]; this
0x1400475f4  call    ?AddUserToBNO@CUser@@QEAAKK@Z; CUser::AddUserToBNO(ulong)
0x1400475f9  mov     edi, eax
0x1400475fb  mov     [rsp+248h+var_1E4], eax
0x1400475ff  test    eax, eax
0x140047601  jz      short loc_14004763E
0x140047603  mov     rcx, cs:WPP_GLOBAL_Control
0x14004760a  lea     rax, WPP_GLOBAL_Control
0x140047611  cmp     rcx, rax
0x140047614  jz      loc_140048A72
0x14004761a  mov     r14d, 1000h
0x140047620  test    [rcx+1Ch], r14d
0x140047624  jz      loc_140048A6D
0x14004762a  cmp     [rcx+19h], r13b
0x14004762e  jb      loc_140048A6D
0x140047634  mov     edx, 0ACh
0x140047639  jmp     loc_14004754C
0x14004763e  call    IsUnlockWindowStationPresent
0x140047643  test    al, al
0x140047645  jz      short loc_1400476A4
0x140047647  call    IsUnlockWindowStationPresent
0x14004764c  test    al, al
0x14004764e  jz      short loc_1400476A4
0x140047650  mov     rcx, cs:WPP_GLOBAL_Control
0x140047657  lea     rax, WPP_GLOBAL_Control
0x14004765e  mov     r14d, 1000h
0x140047664  cmp     rcx, rax
0x140047667  jz      short loc_140047686
0x140047669  test    [rcx+1Ch], r14d
0x14004766d  jz      short loc_140047686
0x14004766f  cmp     byte ptr [rcx+19h], 5
0x140047673  jb      short loc_140047686
0x140047675  mov     edx, 0ADh
0x14004767a  mov     r8, r15
0x14004767d  mov     rcx, [rcx+10h]
0x140047681  call    WPP_SF_
0x140047686  mov     rcx, [rsi+10h]
0x14004768a  mov     rcx, [rcx+60h]
0x14004768e  call    cs:__imp_UnlockWindowStation
0x140047694  mov     rcx, [rsi+10h]
0x140047698  mov     rcx, [rcx+60h]
0x14004769c  call    cs:__imp_LockWindowStation
0x1400476a2  jmp     short loc_1400476AA
0x1400476a4  mov     r14d, 1000h
0x1400476aa  lea     rdx, [rsp+248h+var_1B8]; int *
0x1400476b2  lea     rcx, aGlobalWinlogon_1; "Global\\WinLogon_FirstLogon"
0x1400476b9  call    ?_IsFirstToSetEvent@@YAKPEBGAEAH@Z; _IsFirstToSetEvent(ushort const *,int &)
0x1400476be  mov     [rsp+248h+var_1E4], eax
0x1400476c2  test    eax, eax
0x1400476c4  jz      short loc_1400476F9
0x1400476c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400476cd  lea     rdx, WPP_GLOBAL_Control
0x1400476d4  cmp     rcx, rdx
0x1400476d7  jz      short loc_1400476F9
0x1400476d9  test    [rcx+1Ch], r14d
0x1400476dd  jz      short loc_1400476F9
0x1400476df  cmp     byte ptr [rcx+19h], 3
0x1400476e3  jb      short loc_1400476F9
0x1400476e5  mov     edx, 0AEh
0x1400476ea  mov     r9d, eax
0x1400476ed  mov     r8, r15
0x1400476f0  mov     rcx, [rcx+10h]
0x1400476f4  call    WPP_SF_d
0x1400476f9  xor     edx, edx; int
0x1400476fb  mov     rcx, [rsi+20h]; this
0x1400476ff  call    ?ImpersonateUser@CUser@@QEAAKH@Z; CUser::ImpersonateUser(int)
0x140047704  mov     edi, eax
0x140047706  mov     [rsp+248h+var_1E4], eax
0x14004770a  test    eax, eax
0x14004770c  jnz     loc_140048A44
0x140047712  xor     edi, edi
0x140047714  cmp     cs:?g_TraceRegHandle@@3_KA, rdi; unsigned __int64 g_TraceRegHandle
0x14004771b  jz      loc_1400477CC
0x140047721  cmp     [rsp+248h+var_1B8], edi
0x140047728  jz      short loc_140047784
0x14004772a  test    cs:?g_Diagnostics_Status@@3UDiagnostics_Status@@A, r13b; Diagnostics_Status g_Diagnostics_Status
0x140047731  jnz     short loc_140047784
0x140047733  mov     [rsp+248h+var_68.Data1], 86432A0Bh
0x14004773e  mov     dword ptr [rsp+248h+var_68.Data2], 4DDF3C7Dh
0x140047749  mov     dword ptr [rsp+248h+var_68.Data4], 2F179CA8h
0x140047754  mov     dword ptr [rsp+248h+var_68.Data4+4], 5D4890AAh
0x14004775f  mov     r9, [rsi+10h]
0x140047763  mov     r9d, [r9+58h]; unsigned int
0x140047767  lea     r8, [rsp+248h+var_68]; struct _GUID *
0x14004776f  lea     rdx, WLDiagEvt_UserBootScenario_Start; struct _EVENT_DESCRIPTOR *
0x140047776  call    ?WLEventWriteStartStopScenario@@YAX_NAEBU_EVENT_DESCRIPTOR@@AEBU_GUID@@K@Z; WLEventWriteStartStopScenario(bool,_EVENT_DESCRIPTOR const &,_GUID const &,ulong)
0x14004777b  or      cs:?g_Diagnostics_Status@@3UDiagnostics_Status@@A, r13b; Diagnostics_Status g_Diagnostics_Status
0x140047782  jmp     short loc_1400477CC
0x140047784  mov     [rsp+248h+var_78.Data1], 9F41811Ah
0x14004778f  mov     dword ptr [rsp+248h+var_78.Data2], 42AA0429h
0x14004779a  mov     dword ptr [rsp+248h+var_78.Data4], 0D4CFB781h
0x1400477a5  mov     dword ptr [rsp+248h+var_78.Data4+4], 1F4168D9h
0x1400477b0  mov     r9, [rsi+10h]
0x1400477b4  mov     r9d, [r9+58h]; unsigned int
0x1400477b8  lea     r8, [rsp+248h+var_78]; struct _GUID *
0x1400477c0  lea     rdx, WLDiagEvt_UserBootScenario_Info; struct _EVENT_DESCRIPTOR *
0x1400477c7  call    ?WLEventWriteStartStopScenario@@YAX_NAEBU_EVENT_DESCRIPTOR@@AEBU_GUID@@K@Z; WLEventWriteStartStopScenario(bool,_EVENT_DESCRIPTOR const &,_GUID const &,ulong)
0x1400477cc  call    IsThemesOnLogoffPresent
0x1400477d1  test    al, al
0x1400477d3  jz      short loc_140047825
0x1400477d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400477dc  lea     rax, WPP_GLOBAL_Control
0x1400477e3  cmp     rcx, rax
0x1400477e6  jz      short loc_140047805
0x1400477e8  test    [rcx+1Ch], r14d
0x1400477ec  jz      short loc_140047805
0x1400477ee  cmp     byte ptr [rcx+19h], 4
0x1400477f2  jb      short loc_140047805
0x1400477f4  mov     edx, 0AFh
0x1400477f9  mov     r8, r15
0x1400477fc  mov     rcx, [rcx+10h]
0x140047800  call    WPP_SF_
0x140047805  lea     rcx, WLEvt_ThemesOnLogonPre_Start; struct _EVENT_DESCRIPTOR *
0x14004780c  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140047811  xor     ecx, ecx
0x140047813  call    cs:__imp_ThemesOnLogon
0x140047819  lea     rcx, WLEvt_ThemesOnLogonPre_Stop; struct _EVENT_DESCRIPTOR *
0x140047820  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140047825  call    ?StopImpersonating@CUser@@QEAAKXZ; CUser::StopImpersonating(void)
0x14004782a  mov     eax, 3F5h
0x14004782f  lea     ecx, [rax-4]
0x140047832  cmp     [rsp+248h+var_1A4], ebx
0x140047839  cmovnz  eax, ecx
0x14004783c  mov     [rsp+248h+var_1A0], eax
0x140047843  mov     r9, [rsi+20h]
0x140047847  mov     edx, 4
0x14004784c  lea     r8d, [rdx+1Ch]
0x140047850  mov     ecx, eax
0x140047852  call    ?WlDisplayStatusByResourceId@@YAKIW4_WLUI_STATE@@KPEAVCUser@@@Z; WlDisplayStatusByResourceId(uint,_WLUI_STATE,ulong,CUser *)
0x140047857  call    IsCrossContainerAuthHelperConfigureGuestMachinePresent
0x14004785c  test    al, al
0x14004785e  jz      short loc_14004787B
0x140047860  call    cs:__imp_CrossContainerAuthHelperConfigureGuestMachine
0x140047866  test    eax, eax
0x140047868  jns     short loc_14004787B
0x14004786a  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hr)", "CrossContainerAuthHelperConfigureGuestMachine")
0x14004786d  mov     edx, eax
0x14004786f  lea     rcx, aCrosscontainer_0; "CrossContainerAuthHelper.dll"
0x140047876  call    MicrosoftTelemetryAssertTriggeredArgs
0x14004787b  xor     edx, edx; int
0x14004787d  mov     rcx, [rsi+20h]; this
0x140047881  call    ?ImpersonateUser@CUser@@QEAAKH@Z; CUser::ImpersonateUser(int)
0x140047886  mov     edi, eax
0x140047888  mov     [rsp+248h+var_1E4], eax
0x14004788c  test    eax, eax
0x14004788e  jnz     loc_140048A1B
0x140047894  mov     [rsp+248h+var_1E8], ebx
0x140047898  lea     rdx, [rsp+248h+var_188]; unsigned __int16 **
0x1400478a0  mov     rcx, [rsi+20h]; this
0x1400478a4  call    ?CreatePreNotifyEnvironment@CUser@@QEAAKPEAPEAG@Z; CUser::CreatePreNotifyEnvironment(ushort * *)
0x1400478a9  mov     edi, eax
0x1400478ab  mov     [rsp+248h+var_1E4], eax
0x1400478af  test    eax, eax
0x1400478b1  jz      short loc_1400478E8
0x1400478b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400478ba  lea     rax, WPP_GLOBAL_Control
0x1400478c1  cmp     rcx, rax
0x1400478c4  jz      loc_140048A6D
0x1400478ca  test    [rcx+1Ch], r14d
0x1400478ce  jz      loc_140048A6D
0x1400478d4  cmp     [rcx+19h], r13b
0x1400478d8  jb      loc_140048A6D
0x1400478de  mov     edx, 0B1h
  ... truncated ...
```
