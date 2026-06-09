# WcmSvcMain(ulong,ushort const * *)

- ea: `0x1800b0d60`
- end: `0x1800b1af6`
- name: `?WcmSvcMain@@YAXKPEAPEBG@Z`
- size: `3478`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800137a0`
- `0x180019434`
- `0x180020cc0`
- `0x18002af10`
- `0x180046e20`
- `0x18004d784`
- `0x18004dc3c`
- `0x18004eaf8`
- `0x18004f054`
- `0x180060784`
- `0x1800690b8`
- `0x180069ce8`
- `0x1800765a0`
- `0x18007a7ec`
- `0x18007ab04`
- `0x18007bf34`
- `0x18007ecbc`
- `0x180084f50`
- `0x18008bca4`
- `0x18008e0bc`
- `0x1800911ec`
- `0x1800adf74`
- `0x1800ae544`
- `0x1800b0c4c`
- `0x1800b0d60`
- `0x1800bf2f4`
- `0x1800c4680`
- `0x1800c6988`
- `0x1800e3938`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b182a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b182a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b183c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b183c`
- `ntdll!RtlPublishWnfStateData` at `0x1800b1a6f`
- `ntdll!RtlPublishWnfStateData` at `0x1800b1a6f`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x1800b0f9a`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x1800b0f9a`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800b0ee2`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x1800b0ee2`
- `MobileNetworking!HtCreateHandleTable` at `0x1800b0e5f`
- `MobileNetworking!HtCreateHandleTable` at `0x1800b0e5f`

## string_xrefs

- `0x1800b1058`: `WcmSvcMain - ConfigManager Init`
- `0x1800b1277`: `WcmSvcMain - TokenManagerInit`
- `0x1800b17e6`: `WcmSvcMain - Register service callback to SCM. Update status to running`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall WcmSvcMain(__int64 a1, const unsigned __int16 **a2)
{
  int v2; // r8d
  DWORD v3; // ebx
  int v4; // ecx
  DWORD HandleTable; // eax
  DWORD LastError; // eax
  unsigned int inited; // eax
  __int64 v8; // rcx
  __int64 v9; // rdx
  WcmTimerTracking *v10; // rcx
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  DWORD v15; // eax
  DWORD updated; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // r8d
  int v21; // eax
  int v22; // [rsp+40h] [rbp-19h] BYREF
  __int128 v23; // [rsp+48h] [rbp-11h] BYREF
  __int128 v24; // [rsp+58h] [rbp-1h] BYREF
  __int128 v25; // [rsp+68h] [rbp+Fh] BYREF

  v24 = 0;
  WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v24, "WcmSvcMain");
  v3 = 13;
  v4 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
  }
  if ( (Microsoft_Windows_WcmsvcEnableBits & 2) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v4, (unsigned int)BeginSvcStartup, v2, 1, (__int64)&v25);
  PublishInitialAirplaneModeState();
  if ( !qword_18013F938 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 14, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
    }
    goto LABEL_178;
  }
  *(_OWORD *)&g_WcmServiceStatus.dwServiceType = 0;
  *(_OWORD *)&g_WcmServiceStatus.dwWin32ExitCode = 0;
  HandleTable = HtCreateHandleTable(0, 100, &g_hHandleTable);
  v3 = HandleTable;
  if ( HandleTable )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, HandleTable);
    }
    goto LABEL_178;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
  }
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"wcmsvc", WcmScmNotificationHandler, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, LastError);
    }
    goto LABEL_155;
  }
  g_WcmServiceStatus.dwServiceType = 32;
  *(_QWORD *)&g_WcmServiceStatus.dwCurrentState = 2;
  g_WcmServiceStatus.dwCheckPoint = 0;
  g_WcmServiceStatus.dwWaitHint = 10000;
  *(_QWORD *)&g_WcmServiceStatus.dwWin32ExitCode = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
  }
  WcmSvcUpdateStatus();
  v22 = 0;
  GetOsSafeBootMode(&v22);
  if ( v22 )
  {
    v11 = 1;
    dword_18013F958 = 1;
  }
  else
  {
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - NotificationEngineInit");
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
    }
    inited = NotificationEngine::NotificationEngineInit();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 20;
LABEL_40:
      WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, inited);
LABEL_41:
      v10 = (WcmTimerTracking *)&v25;
LABEL_177:
      WcmTimerTracking::~WcmTimerTracking(v10);
      goto LABEL_178;
    }
    dword_18013F940 |= 0x20u;
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v11 = dword_18013F958;
  }
  if ( !v11 )
  {
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - ConfigManager Init");
    inited = ConfigManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 21;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x8000u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - ClientManagerInit");
    v12 = ClientManager::Init();
    v3 = v12;
    if ( v12 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, v12);
      }
      goto LABEL_41;
    }
    dword_18013F940 |= 8u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - AggregatorInit");
    v13 = ConnectionAggregator::AggregatorInit();
    v3 = v13;
    if ( v13 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, v13);
      }
      goto LABEL_41;
    }
    dword_18013F940 |= 0x40u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - OnDemandInit");
    v14 = OnDemand::OnDemandInit();
    v3 = v14;
    if ( v14 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, v14);
      }
      goto LABEL_41;
    }
    dword_18013F940 |= 0x10u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - RoutePolicyOnDemandInit");
    inited = RoutePolicyOnDemand::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 25;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x40000u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - TokenManagerInit");
    inited = TokenManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 26;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x4000u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - PdcHandler::Init");
    inited = PdcManager::PdcHandler::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 27;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x800u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - FirewallManagerInit");
    inited = FirewallManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 28;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x1000u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - NlmManagerInit");
    inited = NlmManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 29;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x20000u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - RouteManagerInit");
    inited = RouteManager::Init();
    v3 = inited;
    if ( inited != 50 && inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 30;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x80u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - LocationManagerInit");
    inited = LocationManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 31;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x400u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - ProxyManagerInit");
    inited = ProxyManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 32;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x10000u;
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - WcmTcpipInit");
    inited = WcmTcpip::Init();
    v3 = inited;
    if ( inited != 50 && inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 33;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x100u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - WnfStateManagerInit");
    inited = WnfStateManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 34;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x200u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - SelectionManagerInit");
    inited = SelectionManager::Init();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 35;
      goto LABEL_40;
    }
    dword_18013F940 |= 0x2000u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - CdeInit");
    inited = CdeInit();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 36;
      goto LABEL_40;
    }
    dword_18013F940 |= 4u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
    v25 = 0;
    WcmTimerTracking::WcmTimerTracking((WcmTimerTracking *)&v25, "WcmSvcMain - WcmSvcInitRPCServer");
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
    }
    inited = WcmSvcInitRPCServer();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 39;
      goto LABEL_40;
    }
    inited = WcmSvcStartRPCServer();
    v3 = inited;
    if ( inited )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_41;
      }
      v9 = 40;
      goto LABEL_40;
    }
    dword_18013F940 |= 2u;
    ++g_WcmServiceStatus.dwCheckPoint;
    WcmSvcUpdateStatus();
    WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v25);
  }
  v23 = 0;
  WcmTimerTracking::WcmTimerTracking(
    (WcmTimerTracking *)&v23,
    "WcmSvcMain - Register service callback to SCM. Update status to running");
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 41, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
  }
  hObject = CreateEventW(0, 1, 0, 0);
  if ( hObject )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
    }
    g_WcmServiceStatus.dwCurrentState = 4;
    g_WcmServiceStatus.dwControlsAccepted = 4805;
    *(_QWORD *)&g_WcmServiceStatus.dwCheckPoint = 0;
    updated = WcmSvcUpdateStatus();
    v3 = updated;
    if ( updated )
    {
      v17 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_176;
      }
      v18 = 44;
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 45, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
      }
      updated = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_18013F938 + 192))(
                  &WaitHandle,
                  L"wcmsvc",
                  hObject,
                  WcmStopServiceCallback,
                  0,
                  8);
      v3 = updated;
      if ( !updated )
      {
        if ( (Microsoft_Windows_WcmsvcEnableBits & 2) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(v19, (unsigned int)CompleteSvcStartup, v20, 1, (__int64)&v25);
        WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v23);
        goto LABEL_187;
      }
      v17 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || !*(_BYTE *)(WPP_GLOBAL_Control + 25LL)
        || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
        goto LABEL_176;
      }
      v18 = 46;
    }
    WPP_SF_d(*(_QWORD *)(v17 + 16), v18, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, updated);
LABEL_176:
    v10 = (WcmTimerTracking *)&v23;
    goto LABEL_177;
  }
  v15 = GetLastError();
  v3 = v15;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 42, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids, v15);
  }
  WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v23);
LABEL_155:
  if ( v3 )
  {
LABEL_178:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL)
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 47, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
    }
    if ( hServiceStatus )
    {
      *(_QWORD *)&g_WcmServiceStatus.dwCurrentState = 3;
      g_WcmServiceStatus.dwCheckPoint = 0;
      g_WcmServiceStatus.dwWaitHint = 10000;
      *(_QWORD *)&g_WcmServiceStatus.dwWin32ExitCode = 0;
      WcmSvcShutdown(v3);
      *(_QWORD *)&g_WcmServiceStatus.dwCurrentState = 1;
      *(_QWORD *)&g_WcmServiceStatus.dwCheckPoint = 0;
      g_WcmServiceStatus.dwWin32ExitCode = v3;
      g_WcmServiceStatus.dwServiceSpecificExitCode = 0;
      WcmSvcUpdateStatus();
    }
    goto LABEL_196;
  }
LABEL_187:
  v21 = RtlPublishWnfStateData(WNF_WCM_SERVICE_STATUS, 0, 0, 0, 0);
  if ( v21 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 3u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        49,
        WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids,
        (unsigned int)v21);
    }
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
         && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 48, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids);
  }
LABEL_196:
  WcmTimerTracking::~WcmTimerTracking((WcmTimerTracking *)&v24);
}

```

## disassembly

```asm
0x1800b0d60  push    rbp
0x1800b0d62  push    rbx
0x1800b0d63  push    rsi
0x1800b0d64  push    rdi
0x1800b0d65  push    r14
0x1800b0d67  push    r15
0x1800b0d69  lea     rbp, [rsp-2Fh]
0x1800b0d6e  sub     rsp, 88h
0x1800b0d75  mov     rax, cs:__security_cookie
0x1800b0d7c  xor     rax, rsp
0x1800b0d7f  mov     [rbp+57h+var_38], rax
0x1800b0d83  xorps   xmm0, xmm0
0x1800b0d86  movups  [rbp+57h+var_58], xmm0
0x1800b0d8a  lea     rdx, aWcmsvcmain_0; "WcmSvcMain"
0x1800b0d91  lea     rcx, [rbp+57h+var_58]; this
0x1800b0d95  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x1800b0d9a  nop
0x1800b0d9b  lea     r14, WPP_GLOBAL_Control
0x1800b0da2  mov     edi, 1
0x1800b0da7  lea     ebx, [rdi+0Ch]
0x1800b0daa  lea     r15, WPP_8b88784e3ccd341027a7600f51db5fb9_Traceguids
0x1800b0db1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0db8  cmp     rcx, r14
0x1800b0dbb  jz      short loc_1800B0DD7
0x1800b0dbd  cmp     byte ptr [rcx+19h], 5
0x1800b0dc1  jb      short loc_1800B0DD7
0x1800b0dc3  test    [rcx+1Ch], dil
0x1800b0dc7  jz      short loc_1800B0DD7
0x1800b0dc9  mov     edx, ebx
0x1800b0dcb  mov     r8, r15
0x1800b0dce  mov     rcx, [rcx+10h]
0x1800b0dd2  call    WPP_SF_
0x1800b0dd7  test    cs:Microsoft_Windows_WcmsvcEnableBits, 2
0x1800b0dde  jz      short loc_1800B0DF8
0x1800b0de0  lea     rax, [rbp+57h+var_48]
0x1800b0de4  mov     [rsp+0B0h+var_90], rax
0x1800b0de9  mov     r9d, edi
0x1800b0dec  lea     rdx, BeginSvcStartup
0x1800b0df3  call    McGenEventWrite_EtwEventWriteTransfer
0x1800b0df8  call    PublishInitialAirplaneModeState
0x1800b0dfd  xor     esi, esi
0x1800b0dff  cmp     cs:qword_18013F938, rsi
0x1800b0e06  jnz     short loc_1800B0E40
0x1800b0e08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0e0f  cmp     rcx, r14
0x1800b0e12  jz      loc_1800B19A9
0x1800b0e18  cmp     [rcx+19h], dil
0x1800b0e1c  jb      loc_1800B19A9
0x1800b0e22  test    [rcx+1Ch], dil
0x1800b0e26  jz      loc_1800B19A9
0x1800b0e2c  lea     edx, [rsi+0Eh]
0x1800b0e2f  mov     r8, r15
0x1800b0e32  mov     rcx, [rcx+10h]
0x1800b0e36  call    WPP_SF_
0x1800b0e3b  jmp     loc_1800B19A9
0x1800b0e40  xorps   xmm0, xmm0
0x1800b0e43  movups  xmmword ptr cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, xmm0; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b0e4a  movups  xmmword ptr cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, xmm0; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b0e51  lea     r8, g_hHandleTable
0x1800b0e58  mov     edx, 64h ; 'd'
0x1800b0e5d  xor     ecx, ecx
0x1800b0e5f  call    cs:__imp_HtCreateHandleTable
0x1800b0e65  mov     ebx, eax
0x1800b0e67  test    eax, eax
0x1800b0e69  jz      short loc_1800B0EA8
0x1800b0e6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0e72  cmp     rcx, r14
0x1800b0e75  jz      loc_1800B19A9
0x1800b0e7b  cmp     [rcx+19h], dil
0x1800b0e7f  jb      loc_1800B19A9
0x1800b0e85  test    [rcx+1Ch], dil
0x1800b0e89  jz      loc_1800B19A9
0x1800b0e8f  mov     edx, 0Fh
0x1800b0e94  mov     r9d, eax
0x1800b0e97  mov     r8, r15
0x1800b0e9a  mov     rcx, [rcx+10h]
0x1800b0e9e  call    WPP_SF_d
0x1800b0ea3  jmp     loc_1800B19A9
0x1800b0ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0eaf  cmp     rcx, r14
0x1800b0eb2  jz      short loc_1800B0ED1
0x1800b0eb4  cmp     byte ptr [rcx+19h], 5
0x1800b0eb8  jb      short loc_1800B0ED1
0x1800b0eba  test    [rcx+1Ch], dil
0x1800b0ebe  jz      short loc_1800B0ED1
0x1800b0ec0  mov     edx, 10h
0x1800b0ec5  mov     r8, r15
0x1800b0ec8  mov     rcx, [rcx+10h]
0x1800b0ecc  call    WPP_SF_
0x1800b0ed1  xor     r8d, r8d; lpContext
0x1800b0ed4  lea     rdx, WcmScmNotificationHandler; lpHandlerProc
0x1800b0edb  lea     rcx, aWcmsvc; "wcmsvc"
0x1800b0ee2  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x1800b0ee8  mov     cs:hServiceStatus, rax
0x1800b0eef  test    rax, rax
0x1800b0ef2  jnz     short loc_1800B0F39
0x1800b0ef4  call    cs:__imp_GetLastError
0x1800b0efa  mov     ebx, eax
0x1800b0efc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0f03  cmp     rcx, r14
0x1800b0f06  jz      loc_1800B187A
0x1800b0f0c  cmp     [rcx+19h], dil
0x1800b0f10  jb      loc_1800B187A
0x1800b0f16  test    [rcx+1Ch], dil
0x1800b0f1a  jz      loc_1800B187A
0x1800b0f20  mov     edx, 11h
0x1800b0f25  mov     r9d, eax
0x1800b0f28  mov     r8, r15
0x1800b0f2b  mov     rcx, [rcx+10h]
0x1800b0f2f  call    WPP_SF_d
0x1800b0f34  jmp     loc_1800B187A
0x1800b0f39  mov     cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b0f43  mov     qword ptr cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b0f4e  mov     cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, esi; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b0f54  mov     cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 2710h; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b0f5e  mov     qword ptr cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, rsi; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b0f65  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0f6c  cmp     rcx, r14
0x1800b0f6f  jz      short loc_1800B0F8E
0x1800b0f71  cmp     byte ptr [rcx+19h], 5
0x1800b0f75  jb      short loc_1800B0F8E
0x1800b0f77  test    [rcx+1Ch], dil
0x1800b0f7b  jz      short loc_1800B0F8E
0x1800b0f7d  mov     edx, 12h
0x1800b0f82  mov     r8, r15
0x1800b0f85  mov     rcx, [rcx+10h]
0x1800b0f89  call    WPP_SF_
0x1800b0f8e  call    WcmSvcUpdateStatus
0x1800b0f93  mov     [rbp+57h+var_70], esi
0x1800b0f96  lea     rcx, [rbp+57h+var_70]
0x1800b0f9a  call    cs:__imp_GetOsSafeBootMode
0x1800b0fa0  cmp     [rbp+57h+var_70], esi
0x1800b0fa3  jnz     loc_1800B1041
0x1800b0fa9  xorps   xmm0, xmm0
0x1800b0fac  movups  [rbp+57h+var_48], xmm0
0x1800b0fb0  lea     rdx, aWcmsvcmainNoti; "WcmSvcMain - NotificationEngineInit"
0x1800b0fb7  lea     rcx, [rbp+57h+var_48]; this
0x1800b0fbb  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x1800b0fc0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0fc7  cmp     rcx, r14
0x1800b0fca  jz      short loc_1800B0FE9
0x1800b0fcc  cmp     byte ptr [rcx+19h], 5
0x1800b0fd0  jb      short loc_1800B0FE9
0x1800b0fd2  test    [rcx+1Ch], dil
0x1800b0fd6  jz      short loc_1800B0FE9
0x1800b0fd8  mov     edx, 13h
0x1800b0fdd  mov     r8, r15
0x1800b0fe0  mov     rcx, [rcx+10h]
0x1800b0fe4  call    WPP_SF_
0x1800b0fe9  call    ?NotificationEngineInit@NotificationEngine@@SAKXZ; NotificationEngine::NotificationEngineInit(void)
0x1800b0fee  mov     ebx, eax
0x1800b0ff0  test    eax, eax
0x1800b0ff2  jz      short loc_1800B1029
0x1800b0ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b0ffb  cmp     rcx, r14
0x1800b0ffe  jz      short loc_1800B1020
0x1800b1000  cmp     [rcx+19h], dil
0x1800b1004  jb      short loc_1800B1020
0x1800b1006  test    [rcx+1Ch], dil
0x1800b100a  jz      short loc_1800B1020
0x1800b100c  mov     edx, 14h
0x1800b1011  mov     r9d, eax
0x1800b1014  mov     r8, r15
0x1800b1017  mov     rcx, [rcx+10h]
0x1800b101b  call    WPP_SF_d
0x1800b1020  lea     rcx, [rbp+57h+var_48]
0x1800b1024  jmp     loc_1800B19A4
0x1800b1029  or      cs:dword_18013F940, 20h
0x1800b1030  lea     rcx, [rbp+57h+var_48]; this
0x1800b1034  call    ??1WcmTimerTracking@@QEAA@XZ; WcmTimerTracking::~WcmTimerTracking(void)
0x1800b1039  mov     eax, cs:dword_18013F958
0x1800b103f  jmp     short loc_1800B1049
0x1800b1041  mov     eax, edi
0x1800b1043  mov     cs:dword_18013F958, eax
0x1800b1049  test    eax, eax
0x1800b104b  jnz     loc_1800B17DF
0x1800b1051  xorps   xmm0, xmm0
0x1800b1054  movups  [rbp+57h+var_48], xmm0
0x1800b1058  lea     rdx, aWcmsvcmainConf; "WcmSvcMain - ConfigManager Init"
0x1800b105f  lea     rcx, [rbp+57h+var_48]; this
0x1800b1063  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x1800b1068  call    ?Init@ConfigManager@@SAKXZ; ConfigManager::Init(void)
0x1800b106d  mov     ebx, eax
0x1800b106f  test    eax, eax
0x1800b1071  jz      short loc_1800B1095
0x1800b1073  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b107a  cmp     rcx, r14
0x1800b107d  jz      short loc_1800B1020
0x1800b107f  cmp     [rcx+19h], dil
0x1800b1083  jb      short loc_1800B1020
0x1800b1085  test    [rcx+1Ch], dil
0x1800b1089  jz      short loc_1800B1020
0x1800b108b  mov     edx, 15h
0x1800b1090  jmp     loc_1800B1011
0x1800b1095  bts     cs:dword_18013F940, 0Fh
0x1800b109d  add     cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b10a3  call    WcmSvcUpdateStatus
0x1800b10a8  lea     rcx, [rbp+57h+var_48]; this
0x1800b10ac  call    ??1WcmTimerTracking@@QEAA@XZ; WcmTimerTracking::~WcmTimerTracking(void)
0x1800b10b1  xorps   xmm0, xmm0
0x1800b10b4  movups  [rbp+57h+var_48], xmm0
0x1800b10b8  lea     rdx, aWcmsvcmainClie; "WcmSvcMain - ClientManagerInit"
0x1800b10bf  lea     rcx, [rbp+57h+var_48]; this
0x1800b10c3  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x1800b10c8  nop
0x1800b10c9  call    ?Init@ClientManager@@SAKXZ; ClientManager::Init(void)
0x1800b10ce  mov     ebx, eax
0x1800b10d0  test    eax, eax
0x1800b10d2  jz      short loc_1800B1106
0x1800b10d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b10db  cmp     rcx, r14
0x1800b10de  jz      short loc_1800B1101
0x1800b10e0  cmp     [rcx+19h], dil
0x1800b10e4  jb      short loc_1800B1101
0x1800b10e6  test    [rcx+1Ch], dil
0x1800b10ea  jz      short loc_1800B1101
0x1800b10ec  mov     edx, 16h
0x1800b10f1  mov     r9d, eax
0x1800b10f4  mov     r8, r15
0x1800b10f7  mov     rcx, [rcx+10h]
0x1800b10fb  call    WPP_SF_d
0x1800b1100  nop
0x1800b1101  jmp     loc_1800B1020
0x1800b1106  or      cs:dword_18013F940, 8
0x1800b110d  add     cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b1113  call    WcmSvcUpdateStatus
0x1800b1118  nop
0x1800b1119  lea     rcx, [rbp+57h+var_48]; this
0x1800b111d  call    ??1WcmTimerTracking@@QEAA@XZ; WcmTimerTracking::~WcmTimerTracking(void)
0x1800b1122  xorps   xmm0, xmm0
0x1800b1125  movups  [rbp+57h+var_48], xmm0
0x1800b1129  lea     rdx, aWcmsvcmainAggr; "WcmSvcMain - AggregatorInit"
0x1800b1130  lea     rcx, [rbp+57h+var_48]; this
0x1800b1134  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x1800b1139  nop
0x1800b113a  call    ?AggregatorInit@ConnectionAggregator@@SAKXZ; ConnectionAggregator::AggregatorInit(void)
0x1800b113f  mov     ebx, eax
0x1800b1141  test    eax, eax
0x1800b1143  jz      short loc_1800B1177
0x1800b1145  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b114c  cmp     rcx, r14
0x1800b114f  jz      short loc_1800B1172
0x1800b1151  cmp     [rcx+19h], dil
0x1800b1155  jb      short loc_1800B1172
0x1800b1157  test    [rcx+1Ch], dil
0x1800b115b  jz      short loc_1800B1172
0x1800b115d  mov     edx, 17h
0x1800b1162  mov     r9d, eax
0x1800b1165  mov     r8, r15
0x1800b1168  mov     rcx, [rcx+10h]
0x1800b116c  call    WPP_SF_d
0x1800b1171  nop
0x1800b1172  jmp     loc_1800B1020
0x1800b1177  or      cs:dword_18013F940, 40h
0x1800b117e  add     cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b1184  call    WcmSvcUpdateStatus
0x1800b1189  nop
0x1800b118a  lea     rcx, [rbp+57h+var_48]; this
0x1800b118e  call    ??1WcmTimerTracking@@QEAA@XZ; WcmTimerTracking::~WcmTimerTracking(void)
0x1800b1193  xorps   xmm0, xmm0
0x1800b1196  movups  [rbp+57h+var_48], xmm0
0x1800b119a  lea     rdx, aWcmsvcmainOnde; "WcmSvcMain - OnDemandInit"
0x1800b11a1  lea     rcx, [rbp+57h+var_48]; this
0x1800b11a5  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x1800b11aa  nop
0x1800b11ab  call    ?OnDemandInit@OnDemand@@SAKXZ; OnDemand::OnDemandInit(void)
0x1800b11b0  mov     ebx, eax
0x1800b11b2  test    eax, eax
0x1800b11b4  jz      short loc_1800B11E8
0x1800b11b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b11bd  cmp     rcx, r14
0x1800b11c0  jz      short loc_1800B11E3
0x1800b11c2  cmp     [rcx+19h], dil
0x1800b11c6  jb      short loc_1800B11E3
0x1800b11c8  test    [rcx+1Ch], dil
0x1800b11cc  jz      short loc_1800B11E3
0x1800b11ce  mov     edx, 18h
0x1800b11d3  mov     r9d, eax
0x1800b11d6  mov     r8, r15
0x1800b11d9  mov     rcx, [rcx+10h]
0x1800b11dd  call    WPP_SF_d
0x1800b11e2  nop
0x1800b11e3  jmp     loc_1800B1020
0x1800b11e8  or      cs:dword_18013F940, 10h
0x1800b11ef  add     cs:?g_WcmServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS g_WcmServiceStatus ...
0x1800b11f5  call    WcmSvcUpdateStatus
0x1800b11fa  nop
0x1800b11fb  lea     rcx, [rbp+57h+var_48]; this
0x1800b11ff  call    ??1WcmTimerTracking@@QEAA@XZ; WcmTimerTracking::~WcmTimerTracking(void)
0x1800b1204  xorps   xmm0, xmm0
0x1800b1207  movups  [rbp+57h+var_48], xmm0
0x1800b120b  lea     rdx, aWcmsvcmainRout_0; "WcmSvcMain - RoutePolicyOnDemandInit"
0x1800b1212  lea     rcx, [rbp+57h+var_48]; this
0x1800b1216  call    ??0WcmTimerTracking@@QEAA@PEBD@Z; WcmTimerTracking::WcmTimerTracking(char const *)
0x1800b121b  call    ?Init@RoutePolicyOnDemand@@SAJXZ; RoutePolicyOnDemand::Init(void)
0x1800b1220  mov     ebx, eax
0x1800b1222  test    eax, eax
0x1800b1224  jz      short loc_1800B1254
0x1800b1226  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b122d  cmp     rcx, r14
  ... truncated ...
```
