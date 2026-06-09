# WLGeneric_NotifyLogon_Execute(_StateMachineCallContext *)

- ea: `0x140047370`
- end: `0x140048afc`
- name: `?WLGeneric_NotifyLogon_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `6028`
- prototype: `__int64 __fastcall(struct _StateMachineCallContext *, __int64, __int64, __int64)`
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
__int64 __fastcall WLGeneric_NotifyLogon_Execute(
        struct _StateMachineCallContext *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  CGlobalStore **v5; // rsi
  unsigned __int16 *String; // r12
  int v7; // r14d
  CGlobalStore *v8; // rax
  __int64 v9; // r9
  PSID v10; // rdi
  DWORD v11; // edi
  CUser *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  unsigned int IsFirstToSetEvent; // eax
  bool v16; // cl
  CUser *v17; // rcx
  __int64 v18; // r9
  unsigned int v19; // eax
  int v20; // eax
  __int64 v21; // r9
  int v22; // edi
  int v23; // ecx
  unsigned __int16 *v24; // rbx
  void *NotifyConfig; // rax
  CUser *v26; // rcx
  __int64 v27; // r9
  void *v28; // rax
  __int64 v29; // rbx
  unsigned __int16 *v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rax
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rbx
  unsigned __int16 *v36; // rbx
  int v37; // eax
  const unsigned __int16 *v38; // rbx
  unsigned __int16 *v39; // rcx
  int v40; // r12d
  void *v41; // rax
  __int64 FailedSubscriberName; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned __int16 *v46; // rax
  unsigned __int16 *v47; // rbx
  unsigned __int16 *v48; // r12
  int IsBoundToConsole; // eax
  const unsigned __int16 *v50; // rcx
  int v51; // ecx
  const BYTE *v52; // rax
  struct _WLSM_GLOBAL_CONTEXT *v53; // rcx
  unsigned __int16 *v54; // r14
  int v55; // eax
  CSession *v56; // rcx
  __int64 v57; // r9
  CGlobalStore *v58; // rbx
  ULONG v59; // eax
  unsigned int v60; // ebx
  __int64 v61; // r9
  __int64 v62; // r9
  LANGID ThreadUILanguage; // bx
  CUser *v64; // rcx
  CMachine *v65; // rcx
  unsigned int v66; // ebx
  int v67; // edi
  unsigned int v68; // ebx
  int v69; // edi
  int v70; // eax
  __int64 v71; // r9
  CMachine *v72; // rcx
  unsigned int v73; // eax
  unsigned int v74; // eax
  CUser *v75; // rbx
  unsigned int MachinePolicy; // eax
  unsigned int v77; // eax
  unsigned int v78; // ebx
  int v80; // [rsp+60h] [rbp-1E8h]
  unsigned int v81; // [rsp+64h] [rbp-1E4h] BYREF
  _BYTE v82[8]; // [rsp+68h] [rbp-1E0h] BYREF
  unsigned __int16 *v83; // [rsp+70h] [rbp-1D8h] BYREF
  int v84; // [rsp+78h] [rbp-1D0h] BYREF
  int v85; // [rsp+7Ch] [rbp-1CCh] BYREF
  int v86; // [rsp+80h] [rbp-1C8h] BYREF
  unsigned __int16 *v87; // [rsp+88h] [rbp-1C0h] BYREF
  int v88; // [rsp+90h] [rbp-1B8h] BYREF
  unsigned __int16 *v89; // [rsp+98h] [rbp-1B0h] BYREF
  unsigned int v90; // [rsp+A0h] [rbp-1A8h] BYREF
  DWORD v91; // [rsp+A4h] [rbp-1A4h] BYREF
  unsigned int v92; // [rsp+A8h] [rbp-1A0h] BYREF
  const BYTE *v93; // [rsp+B0h] [rbp-198h] BYREF
  unsigned __int16 *v94; // [rsp+B8h] [rbp-190h] BYREF
  unsigned __int16 *v95; // [rsp+C0h] [rbp-188h] BYREF
  PSID Sid; // [rsp+C8h] [rbp-180h] BYREF
  int v97; // [rsp+D0h] [rbp-178h] BYREF
  int v98; // [rsp+D4h] [rbp-174h]
  int v99; // [rsp+D8h] [rbp-170h]
  unsigned __int16 *v100; // [rsp+E0h] [rbp-168h] BYREF
  __int64 v101; // [rsp+E8h] [rbp-160h] BYREF
  __int64 v102; // [rsp+F0h] [rbp-158h] BYREF
  int v103; // [rsp+F8h] [rbp-150h] BYREF
  __int64 v104; // [rsp+100h] [rbp-148h] BYREF
  struct _GUID *v105; // [rsp+108h] [rbp-140h] BYREF
  struct _GUID *v106; // [rsp+110h] [rbp-138h] BYREF
  _BYTE v107[8]; // [rsp+118h] [rbp-130h] BYREF
  __int64 v108; // [rsp+120h] [rbp-128h] BYREF
  __int64 v109; // [rsp+128h] [rbp-120h] BYREF
  __int64 v110; // [rsp+130h] [rbp-118h]
  const BYTE *v111; // [rsp+138h] [rbp-110h] BYREF
  __int64 v112; // [rsp+140h] [rbp-108h] BYREF
  int v113; // [rsp+148h] [rbp-100h]
  __int64 v114; // [rsp+150h] [rbp-F8h] BYREF
  int v115; // [rsp+158h] [rbp-F0h]
  __int64 v116; // [rsp+160h] [rbp-E8h] BYREF
  struct _GUID *v117; // [rsp+168h] [rbp-E0h] BYREF
  __int128 v118; // [rsp+170h] [rbp-D8h] BYREF
  __int64 v119; // [rsp+180h] [rbp-C8h]
  __int128 v120; // [rsp+190h] [rbp-B8h] BYREF
  __int64 v121; // [rsp+1A0h] [rbp-A8h]
  __int128 v122; // [rsp+1B0h] [rbp-98h] BYREF
  __int64 v123; // [rsp+1C0h] [rbp-88h]
  struct _GUID v124; // [rsp+1D0h] [rbp-78h] BYREF
  struct _GUID v125; // [rsp+1E0h] [rbp-68h] BYREF

  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 169, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, a4);
  }
  v5 = (CGlobalStore **)*((_QWORD *)a1 + 1);
  StartUserLogonToUxShownTest(v107);
  v95 = 0;
  v94 = 0;
  String = 0;
  v83 = 0;
  v90 = 0;
  v7 = 0;
  v80 = 0;
  v99 = 0;
  v84 = 0;
  v86 = 0;
  v85 = 0;
  v88 = 0;
  v93 = 0;
  v91 = *((_DWORD *)v5[4] + 132);
  v97 = 0;
  v8 = v5[2];
  v9 = *((unsigned int *)v8 + 22);
  dword_1400D18A0 = *((_DWORD *)v8 + 22);
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 95, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v9);
  }
  qword_1400D30D8 = (__int64)&dword_1400D18A0;
  qword_1400D30D0 = WinSqmStartSession(&dword_1400D18A0, 984068, 0);
  v10 = (PSID)*((_QWORD *)v5[4] + 15);
  Sid = v10;
  if ( !(unsigned __int8)IsLoadLocalFontsPresent() )
  {
LABEL_17:
    if ( (unsigned __int8)IsSetUserObjectSecurityPresent() )
    {
      v11 = CSession::SetUserDesktopSecurity(v5[2], 2, v10);
      v81 = v11;
      if ( v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
          goto LABEL_271;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_270;
        v13 = 171;
        goto LABEL_15;
      }
    }
    v11 = CUser::AddUserToBNO(v5[4], *((_DWORD *)v5[2] + 22));
    v81 = v11;
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
        goto LABEL_271;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_270;
      v13 = 172;
      goto LABEL_15;
    }
    if ( (unsigned __int8)IsUnlockWindowStationPresent() && (unsigned __int8)IsUnlockWindowStationPresent() )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v14);
      }
      UnlockWindowStation(*((_QWORD *)v5[2] + 12));
      LockWindowStation(*((_QWORD *)v5[2] + 12));
    }
    IsFirstToSetEvent = _IsFirstToSetEvent(L"Global\\WinLogon_FirstLogon", &v88);
    v81 = IsFirstToSetEvent;
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
    v11 = CUser::ImpersonateUser(v5[4], 0);
    v81 = v11;
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v13 = 176;
      goto LABEL_15;
    }
    if ( g_TraceRegHandle )
    {
      if ( !v88 || (g_Diagnostics_Status & 2) != 0 )
      {
        v124.Data1 = -1623097062;
        *(_DWORD *)&v124.Data2 = 1118438441;
        *(_DWORD *)v124.Data4 = -724584575;
        *(_DWORD *)&v124.Data4[4] = 524380377;
        WLEventWriteStartStopScenario(v16, &WLDiagEvt_UserBootScenario_Info, &v124, *((_DWORD *)v5[2] + 22));
      }
      else
      {
        v125.Data1 = -2042418677;
        *(_DWORD *)&v125.Data2 = 1306475645;
        *(_DWORD *)v125.Data4 = 790076584;
        *(_DWORD *)&v125.Data4[4] = 1565036714;
        WLEventWriteStartStopScenario(v16, &WLDiagEvt_UserBootScenario_Start, &v125, *((_DWORD *)v5[2] + 22));
        g_Diagnostics_Status |= 2u;
      }
    }
    if ( (unsigned __int8)IsThemesOnLogoffPresent() )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v18);
      }
      WLEventWrite(&WLEvt_ThemesOnLogonPre_Start);
      ThemesOnLogon(0);
      WLEventWrite(&WLEvt_ThemesOnLogonPre_Stop);
    }
    CUser::StopImpersonating(v17);
    v19 = 1013;
    if ( v91 != 1 )
      v19 = 1009;
    v92 = v19;
    WlDisplayStatusByResourceId(v19, 4, 32, v5[4]);
    if ( (unsigned __int8)IsCrossContainerAuthHelperConfigureGuestMachinePresent() )
    {
      v20 = CrossContainerAuthHelperConfigureGuestMachine();
      if ( v20 < 0 )
        MicrosoftTelemetryAssertTriggeredArgs("CrossContainerAuthHelper.dll", (unsigned int)v20, 0);
    }
    v11 = CUser::ImpersonateUser(v5[4], 0);
    v81 = v11;
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v13 = 179;
      goto LABEL_15;
    }
    v80 = 1;
    v11 = CUser::CreatePreNotifyEnvironment(v5[4], &v95);
    v81 = v11;
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v13 = 177;
      goto LABEL_15;
    }
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v21);
    }
    wil::srwlock::lock_shared((char *)*v5 + 64, &v101);
    v108 = 0;
    if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v5, &v108) >= 0 )
    {
      v22 = v108;
      if ( v108 )
      {
        v124 = 0;
        WLGetTSActivityId(&v124);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
          {
            v109 = 0x1000000;
            v89 = (unsigned __int16 *)&v124;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
              v23,
              (unsigned int)byte_1400BBBF1,
              v22 + 8,
              (unsigned int)&v124,
              (__int64)&v89,
              (__int64)&v109);
          }
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v101);
    if ( *((_DWORD *)v5[2] + 94) )
      v97 = 1;
    v24 = v95;
    NotifyConfig = CGlobalStore::GetNotifyConfig(*v5, 0, 0);
    v11 = InternalNotifyExecute(NotifyConfig, 2, &v97, DisplayMessage_Callback, 0, v24);
    v81 = v11;
    if ( !v11 )
    {
      v84 = 1;
      v11 = g_dwCreateSessionRet;
      v81 = g_dwCreateSessionRet;
    }
    FailPreviousUserLogonUxShownTest();
    SetCorrelationIdForUserLogonToUxShownTest(v107, (unsigned int)v84);
    CUser::StopImpersonating(v26);
    v80 = 0;
    if ( v11 )
    {
      if ( v11 == 1753 )
      {
        v40 = *((_DWORD *)v5[4] + 38);
        v85 = v40;
        v115 = v40;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v27);
        }
        String = AllocAndLoadString((unsigned int)(v40 != 0) + 1900, v5[4]);
        v83 = String;
        v41 = CGlobalStore::GetNotifyConfig(*v5, 0, 0);
        FailedSubscriberName = GetFailedSubscriberName(v41);
        v43 = FailedSubscriberName;
        v93 = (const BYTE *)FailedSubscriberName;
        v110 = FailedSubscriberName;
        if ( String )
        {
          if ( !FailedSubscriberName )
            goto LABEL_116;
          v44 = -1;
          v45 = -1;
          do
            ++v45;
          while ( String[v45] );
          do
            ++v44;
          while ( *(_WORD *)(v43 + 2 * v44) );
          v89 = (unsigned __int16 *)(unsigned int)(v44 + 1 + v45);
          v46 = (unsigned __int16 *)WLAlloc(2LL * (_QWORD)v89);
          v47 = v46;
          v87 = v46;
          if ( v46 )
          {
            StringCchPrintfW(v46, (unsigned __int64)v89, String, v93);
            UHHeapFree(&v83);
            String = v47;
            v83 = v47;
          }
          else
          {
LABEL_116:
            v87 = String;
          }
          if ( v85 )
          {
            v99 = 1;
            v113 = 1;
            v38 = (const unsigned __int16 *)&pPassword;
          }
          else
          {
            v48 = AllocAndLoadString(0x3E8u, v5[4]);
            v94 = v48;
            IsBoundToConsole = CSession::IsBoundToConsole(v5[2]);
            v122 = 0;
            v123 = 0;
            ToSetTimeout(IsBoundToConsole != 0 ? 120000 : 30000, &v122);
            v38 = (const unsigned __int16 *)&pPassword;
            v50 = (const unsigned __int16 *)&pPassword;
            if ( v48 )
              v50 = v48;
            WlDisplayMessage(v50, v87, 0x10u, &v90);
            ToResetTimeout();
            UHHeapFree(&v83);
            String = v83;
          }
          if ( v94 )
            UHHeapFree(&v94);
        }
        else
        {
          v38 = (const unsigned __int16 *)&pPassword;
        }
        v51 = v86;
        if ( !v85 )
          v51 = 1;
        v86 = v51;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v11);
        }
        String = MyFormatMessage(v11);
        v83 = String;
        if ( String )
        {
          v28 = CGlobalStore::GetNotifyConfig(*v5, 0, 0);
          v29 = GetFailedSubscriberName(v28);
          v93 = (const BYTE *)v29;
          v110 = v29;
          if ( v29 && (v30 = AllocAndLoadString(0x76Fu, v5[4]), (v100 = v30) != 0) )
          {
            v31 = -1;
            v32 = -1;
            do
              ++v32;
            while ( String[v32] );
            v33 = -1;
            do
              ++v33;
            while ( *(_WORD *)(v29 + 2 * v33) );
            do
              ++v31;
            while ( v30[v31] );
            v89 = (unsigned __int16 *)(unsigned int)(v31 + v32 + 1 + v33);
            v34 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (_QWORD)v89);
            v35 = v34;
            v87 = v34;
            if ( v34 )
            {
              if ( (int)StringCchPrintfW(v34, (unsigned __int64)v89, v100, v93, String) < 0 )
                *v35 = 0;
              LocalFree(String);
              String = v35;
              v83 = v35;
            }
            else
            {
              v87 = String;
            }
            UHHeapFree(&v100);
          }
          else
          {
            v87 = String;
          }
          v36 = AllocAndLoadString(0x3E8u, v5[4]);
          v89 = v36;
          v94 = v36;
          v37 = CSession::IsBoundToConsole(v5[2]);
          v120 = 0;
          v121 = 0;
          ToSetTimeout(v37 != 0 ? 120000 : 30000, &v120);
          if ( v36 )
          {
            v100 = v36;
            v38 = (const unsigned __int16 *)&pPassword;
            v39 = v89;
          }
          else
          {
            v38 = (const unsigned __int16 *)&pPassword;
            v39 = (unsigned __int16 *)&pPassword;
            v100 = 0;
          }
          WlDisplayMessage(v39, v87, 0, &v90);
          ToResetTimeout();
          if ( v100 )
            UHHeapFree(&v94);
          LocalFree(String);
          String = 0;
          v83 = 0;
        }
        else
        {
          v38 = (const unsigned __int16 *)&pPassword;
        }
        v86 = 1;
      }
    }
    else
    {
      v38 = (const unsigned __int16 *)&pPassword;
    }
    wil::srwlock::lock_shared((char *)*v5 + 64, &v89);
    v104 = 0;
    if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v5, &v104) >= 0 )
    {
      if ( v104 )
      {
        v124 = 0;
        WLGetTSActivityId(&v124);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_1400CF778, 0x400000000000LL) )
          {
            v91 = v11;
            v88 = *((_DWORD *)v5[2] + 22);
            v52 = &pPassword;
            if ( v93 )
              v52 = v93;
            v111 = v52;
            v103 = v84;
            v112 = 0x1000000;
            v105 = &v124;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (_DWORD)v93,
              (unsigned int)byte_1400BBB55,
              v104 + 8,
              (unsigned int)&v124,
              (__int64)&v105,
              (__int64)&v112,
              (__int64)&v103,
              (__int64)&v85,
              (__int64)&v111,
              (__int64)&v88,
              (__int64)&v91);
          }
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v89);
    if ( v86 )
      goto LABEL_270;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SyncDpapiCredKeyToUserProfile>::GetImpl'::`2'::impl);
    if ( ShouldLoadAadCredKeyFromProfile(v53) )
    {
      v84 = 0;
      v11 = CUser::ConfirmCredKeyAvailablePostProfileLoad(v5[4], &v84);
      if ( (v11 & 0x80000000) != 0 )
      {
        if ( (v11 & 0x1FFF0000) == 0x70000 )
          v11 = (unsigned __int16)v11;
        goto LABEL_143;
      }
      if ( !v84 )
      {
        v11 = 6001;
LABEL_143:
        v81 = v11;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v11);
        }
        WinlogonProvider::ForceLogOffAadUserAsDpApiCredKeyDecryptionFailed<unsigned long &>(&v81);
        String = AllocAndLoadString(0x1B58u, v5[4]);
        v83 = String;
        if ( String )
        {
          v54 = AllocAndLoadString(0x3E8u, v5[4]);
          v94 = v54;
          v55 = CSession::IsBoundToConsole(v5[2]);
          v118 = 0;
          v119 = 0;
          ToSetTimeout(v55 != 0 ? 120000 : 30000, &v118);
          if ( v54 )
            v38 = v54;
          else
            v54 = 0;
          WlDisplayMessage(v38, String, 0x10u, &v90);
          ToResetTimeout();
          if ( v54 )
            UHHeapFree(&v94);
          UHHeapFree(&v83);
          String = v83;
        }
        goto LABEL_261;
      }
    }
    WlDisplayStatusByResourceId(v92, 4, 32, v5[4]);
    v81 = CUser::ImpersonateUser(v5[4], 0);
    if ( !v81 )
    {
      v80 = 1;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v57);
      }
      if ( (unsigned __int8)IsLoadLocalFontsPresent() )
      {
        v102 = 0;
        v102 = *((_QWORD *)v5[4] + 16);
        v58 = v5[2];
        v59 = RtlLengthSid(Sid);
        SetWindowStationUser(*((_QWORD *)v58 + 12), &v102, Sid, v59);
      }
      v98 = 1;
      if ( (unsigned int)CSession::IsBoundToConsole(v5[2]) )
      {
        v82[0] = 0;
        if ( !(unsigned __int8)IsWinStationConnectAndLockDesktopPresent()
          || !(unsigned __int8)WinStationIsSessionRemoteable(0, 0xFFFFFFFFLL, v82) )
        {
          v82[0] = 0;
        }
        v60 = 1;
        if ( v82[0] )
          v60 = 5;
      }
      else
      {
        v60 = 5;
      }
      v98 = v60;
      if ( (unsigned __int8)IsLoadLocalFontsPresent() )
      {
        WLEventWrite(&WLEvt_UpdatePerUserSystemParameters_Start, v60);
        if ( !(unsigned int)UpdatePerUserSystemParameters(v60)
          && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 184, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v61);
        }
        WLEventWrite(&WLEvt_UpdatePerUserSystemParameters_Stop, v60);
      }
      ThreadUILanguage = 0;
      if ( (unsigned __int8)IsThemesOnLogoffPresent() )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v62);
        }
        WLEventWrite(&WLEvt_ThemesOnLogonPost_Start);
        ThemesOnLogon(1);
        WLEventWrite(&WLEvt_ThemesOnLogonPost_Stop);
      }
      v11 = CUser::OpenHKeyCurrentUser(v5[4]);
      v81 = v11;
      if ( v11 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_270;
        }
        v13 = 186;
        goto LABEL_15;
      }
      if ( (unsigned __int8)IsWinLogonExtPresent() )
        ThreadUILanguage = GetThreadUILanguage();
      CUser::StopImpersonating(v64);
      v80 = 0;
      if ( (unsigned __int8)IsWinLogonExtPresent() )
      {
        RecordBlackboxInfo(L"WluiNotifyUserIsLoggedOn", 1, (struct _WLSM_GLOBAL_CONTEXT *)v5);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_HangDetectionOnLogonUICallouts2>::GetImpl'::`2'::impl) )
        {
          CallWithHangTimeout::CallWithHangTimeout(&v118, 0);
          WluiNotifyUserIsLoggedOn(ThreadUILanguage);
          CallWithHangTimeout::~CallWithHangTimeout((CallWithHangTimeout *)&v118);
        }
        else
        {
          WluiNotifyUserIsLoggedOn(ThreadUILanguage);
        }
        RecordBlackboxInfo(L"WluiNotifyUserIsLoggedOn", 0, (struct _WLSM_GLOBAL_CONTEXT *)v5);
      }
    }
    if ( (unsigned int)CSession::IsShellRequiredInSession(v56) )
    {
      if ( (unsigned __int8)IsUMgrLaunchShellInfrastructureHostPresent() )
      {
        v66 = UMgrInformUserLogon(*((_QWORD *)v5[4] + 17));
        if ( (v66 & 0x1FFF0000) == 0x70000 )
          v66 = (unsigned __int16)v66;
        v81 = v66;
        wil::srwlock::lock_shared((char *)*v5 + 64, &v105);
        Sid = 0;
        if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v5, &Sid) >= 0 )
        {
          v67 = (int)Sid;
          if ( Sid )
          {
            v124 = 0;
            WLGetTSActivityId(&v124);
            if ( (unsigned int)dword_1400CF778 > 5 )
            {
              v92 = v66;
              v86 = *((_DWORD *)v5[2] + 22);
              v114 = 0x1000000;
              v106 = &v124;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v86,
                (unsigned int)byte_1400BBAF1,
                v67 + 8,
                (unsigned int)&v124,
                (__int64)&v106,
                (__int64)&v114,
                (__int64)&v86,
                (__int64)&v92);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v105);
        if ( v66 )
        {
          v65 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v66);
          }
          v81 = 0;
        }
      }
      if ( (unsigned int)CMachine::IsSiHostIntegrationEnabled(v65) )
      {
        v11 = CSession::SubscribeForWnfNotifications(v5[2]);
        v81 = v11;
        if ( v11 )
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_270;
          }
          v13 = 188;
          goto LABEL_15;
        }
        RecordBlackboxInfo(L"UMgrLaunchShellInfrastructureHost", 1, (struct _WLSM_GLOBAL_CONTEXT *)v5);
        v68 = UMgrLaunchShellInfrastructureHost(*((_QWORD *)v5[4] + 15));
        RecordBlackboxInfo(L"UMgrLaunchShellInfrastructureHost", 0, (struct _WLSM_GLOBAL_CONTEXT *)v5);
        if ( (v68 & 0x1FFF0000) == 0x70000 )
          v68 = (unsigned __int16)v68;
        v81 = v68;
        wil::srwlock::lock_shared((char *)*v5 + 64, &v106);
        v101 = 0;
        if ( (int)CGlobalStore::GetGlobalTraceLoggingActivity(*v5, &v101) >= 0 )
        {
          v69 = v101;
          if ( v101 )
          {
            v124 = 0;
            WLGetTSActivityId(&v124);
            if ( (unsigned int)dword_1400CF778 > 5 )
            {
              LODWORD(v87) = v68;
              LODWORD(v93) = *((_DWORD *)v5[2] + 22);
              v116 = 0x1000000;
              v117 = &v124;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (_DWORD)v93,
                (unsigned int)&byte_1400BBA8F,
                v69 + 8,
                (unsigned int)&v124,
                (__int64)&v117,
                (__int64)&v116,
                (__int64)&v93,
                (__int64)&v87);
            }
          }
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v106);
        if ( v68 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v68);
          }
          v81 = 0;
        }
      }
    }
    v70 = WlSecureDesktopiStartup(*((_QWORD *)v5[4] + 20));
    if ( v70 < 0 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          191,
          WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
          (unsigned int)v70);
      }
    }
    else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v71);
    }
    v11 = CUser::ApplyLogonHoursRestrictions(v5[4]);
    v81 = v11;
    if ( v11 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_270;
      }
      v13 = 192;
      goto LABEL_15;
    }
    if ( v99 )
    {
      v73 = WlRemindersDisplay(7, String, 0);
      v81 = v73;
      if ( v73
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v73);
      }
      UHHeapFree(&v83);
      v11 = 0;
      v81 = 0;
      String = v83;
    }
    if ( *((_DWORD *)v5[4] + 38) && (unsigned int)CMachine::IsAuditingLogFull(v72) )
    {
      v74 = WlRemindersDisplay(2, 0, 0);
      v81 = v74;
      if ( v74
        && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 194, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v74);
      }
      v11 = 0;
      v81 = 0;
    }
    v75 = v5[4];
    MachinePolicy = CMachine::GetMachinePolicy(v5[1], L"ReportControllerMissing", 0xFFFFFFFF);
    if ( !(unsigned int)CUser::ShouldReportCachedLogon(v75, MachinePolicy) )
      goto LABEL_270;
    v77 = WlRemindersDisplay(6, 0, 0);
    v81 = v77;
    if ( v77 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v77);
      }
    }
    v11 = 0;
    v81 = 0;
LABEL_261:
    v7 = 0;
    goto LABEL_271;
  }
  v11 = AddUserToWinsta(*((HWINSTA *)v5[2] + 12), *((void **)v5[2] + 13), v10, *((PSID *)v5[4] + 20));
  v81 = v11;
  if ( !v11 )
  {
    WLEventWriteWinSqmUserSessionChange(&WLEvt_WinSqmUserLogin, *((_DWORD *)v5[2] + 22), *((void **)v5[4] + 20));
    v10 = Sid;
    goto LABEL_17;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control )
    goto LABEL_271;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
    goto LABEL_261;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 170;
LABEL_15:
    WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v11);
  }
LABEL_270:
  v7 = v80;
LABEL_271:
  if ( v7 )
    CUser::StopImpersonating(v12);
  if ( v95 )
    UHHeapFree(&v95);
  if ( String )
    UHHeapFree(&v83);
  v78 = WlStateMachineSetSignal(v11 != 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v107);
  return v78;
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
