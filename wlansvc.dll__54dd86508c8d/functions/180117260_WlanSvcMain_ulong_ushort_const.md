# WlanSvcMain(ulong,ushort const * *)

- ea: `0x180117260`
- end: `0x1801181f5`
- name: `?WlanSvcMain@@YAXKPEAPEBG@Z`
- size: `3989`
- prototype: `void __fastcall(__int64, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `56`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003894`
- `0x1800038dc`
- `0x18000aa0c`
- `0x180011530`
- `0x18003702c`
- `0x18008228c`
- `0x18008b7e0`
- `0x180095038`
- `0x1800ab1b8`
- `0x1800ac8ac`
- `0x1800c6044`
- `0x1800e17d8`
- `0x1800f2aa8`
- `0x1800fcc4c`
- `0x1800febec`
- `0x1801080b8`
- `0x180117090`
- `0x180117188`
- `0x180117260`
- `0x18011835c`
- `0x180118e48`
- `0x18011956c`
- `0x18011973c`
- `0x18011d364`
- `0x18011da24`
- `0x180122cb4`
- `0x180122e90`
- `0x18012306c`
- `0x1801231fc`
- `0x1801253d8`
- `0x180125410`
- `0x180146168`
- `0x18014621c`
- `0x1801587d8`
- `0x18015cca4`
- `0x18015f998`
- `0x180160ed8`
- `0x180160f08`
- `0x18016246c`
- `0x180162e00`
- `0x180163a78`
- `0x18019ba50`
- `0x1801bd970`
- `0x1801bda3c`
- `0x1801bf678`
- `0x1801c58f8`
- `0x1801cf124`
- `0x1801d08ac`
- `0x1801d5920`
- `0x1801ed5e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180117732`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180117a30`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180117732`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180117a30`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011775e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180117d28`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18011775e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180117d28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117d3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180117d3a`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180118171`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1801181cf`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x180118171`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1801181cf`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18011740f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18011740f`
- `MobileNetworking!HtCreateHandleTable` at `0x1801172c5`
- `MobileNetworking!HtCreateHandleTable` at `0x1801172c5`
- `ext-ms-win-wlan-grouppolicy-l1-1-0!WLGPAInit` at `0x180117c60`
- `ext-ms-win-wlan-grouppolicy-l1-1-0!WLGPAInit` at `0x180117c60`

## pseudocode

```c
void __fastcall WlanSvcMain(__int64 a1, const unsigned __int16 **a2)
{
  _DWORD *v2; // r8
  __int64 v3; // r8
  unsigned int HandleTable; // ebx
  _DWORD *v5; // r8
  int v6; // r8d
  int v7; // r9d
  _QWORD *v8; // rdi
  DWORD LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  DWORD updated; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  wlansvc::profile *v15; // rcx
  __int64 v16; // rdx
  PVOID v17; // rcx
  void *v18; // rdx
  unsigned int v19; // eax
  PVOID *v20; // rcx
  unsigned int v21; // eax
  wlansvc::power *v22; // rcx
  PVOID *v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int inited; // eax
  TRACEHANDLE v27; // rcx
  _QWORD *v28; // rbx
  TRACEHANDLE v29; // rcx
  void *v30; // [rsp+90h] [rbp+18h] BYREF

  g_nThreads = 1;
  WlanSvcInitTracing();
  v2 = *(_DWORD **)(wil::details::static_lazy<WlanTriageProvider>::get() + 8);
  if ( *v2 > 4u && (unsigned __int8)tlgKeywordOn(v2, 1, v2) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v3,
      byte_180275493);
  WlanStartSqmIfNeeded();
  HandleTable = HtCreateHandleTable(0, 100, &g_hHandleTable);
  if ( HandleTable )
    goto LABEL_10;
  if ( !g_svcHostGlobalData )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 12, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
    HandleTable = 13;
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  g_hWlanServiceStatusHandle = RegisterServiceCtrlHandlerExW(L"wlansvc", NhScmNotificationHandler, 0);
  if ( !g_hWlanServiceStatusHandle )
  {
    LastError = GetLastError();
    HandleTable = LastError;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v11 = 14;
LABEL_217:
      WPP_SF_d(v10[12], v11, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids, LastError);
      goto LABEL_218;
    }
    goto LABEL_218;
  }
  g_WlanServiceStatus.dwServiceType = 32;
  *(_QWORD *)&g_WlanServiceStatus.dwCurrentState = 2;
  g_WlanServiceStatus.dwCheckPoint = 0;
  g_WlanServiceStatus.dwWaitHint = 4000;
  *(_QWORD *)&g_WlanServiceStatus.dwWin32ExitCode = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 15, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = WlanSvcUpdateStatus();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 16;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  AnqpCacheInitialize();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = WlanSvcPAL_Initialize();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 19;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = StInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 21;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 22, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = WlanSvcContextInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 23;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = AcmInitSessionContext();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 25;
    goto LABEL_35;
  }
  HandleTable = TmInit();
  if ( HandleTable )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
    goto LABEL_10;
  }
  v15 = (wlansvc::profile *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = wlansvc::profile::Init(v15);
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 28;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 29, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  InitializeCriticalSection(&stru_1802A2660);
  qword_1802A269C = 0;
  qword_1802A2690 = (__int64)&qword_1802A2688;
  qword_1802A2688 = (__int64)&qword_1802A2688;
  qword_1802A26A8 = CreateEventW(0, 1, 1, 0);
  if ( qword_1802A26A8 )
  {
    dword_1802A2698 = 1;
  }
  else
  {
    updated = GetLastError();
    HandleTable = updated;
    if ( updated )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        goto LABEL_10;
      v14 = 30;
      goto LABEL_35;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 31, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = VIntfMgrInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 32;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 33, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = APDhcpInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 34;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 35, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = HNMgrInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 36;
    goto LABEL_35;
  }
  v30 = &VIntfMgrReceiveVLibStateChange;
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = VLibInit(v17, v16, &v30);
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 38;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  MDMPolicyInitCritSec();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = WimInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 41;
    goto LABEL_35;
  }
  HNMgrSynchronizeWim();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = VsIeProviderManagerInitialize();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 43;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 44, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  InitializeCriticalSection(&stru_1802A3810);
  dword_1802A3838 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 46, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = WfdInterfaceManagerStartup();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 48;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 49, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = InitACSecurity();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 50;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 51, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  updated = NhInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 52;
    goto LABEL_35;
  }
  HandleTable = WlanSvcInitRPCServer();
  if ( HandleTable )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  v30 = &WlanRpcSendWiFiDisplayControllerNotification;
  updated = WiFiDisplayControllerStartup((const struct _WIFIDISPLAY_CONTROLLER_FUNCTION_TABLE *)&v30);
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 54;
    goto LABEL_35;
  }
  if ( !dword_1802A0F54 )
  {
    updated = InitializeWirelessDiagnostics();
    HandleTable = updated;
    if ( updated )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        goto LABEL_10;
      v14 = 55;
      goto LABEL_35;
    }
  }
  updated = NlaWPlgInitialize();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 56;
    goto LABEL_35;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 57, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  if ( (!(unsigned __int8)IsWLGPAInitPresent() || (HandleTable = WLGPAInit(&g_AcmGpFuncTable)) != 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 58, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids, HandleTable);
  }
  updated = InitUIForwardingList();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 59;
    goto LABEL_35;
  }
  updated = WLNotifyInit();
  HandleTable = updated;
  if ( updated )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      goto LABEL_10;
    v14 = 60;
    goto LABEL_35;
  }
  ProtectedScenarioMgr_ServiceStartupOrShutdown();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 61, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
  }
  g_hStopServiceEvent = CreateEventW(0, 1, 0, 0);
  if ( g_hStopServiceEvent )
  {
    AcmNotifySessionChange();
    g_bTimerManagerStarted = 1;
    NhStart();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 63, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
    }
    updated = NhRegisterScmNotification(1u, v18);
    HandleTable = updated;
    if ( updated )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        goto LABEL_10;
      v14 = 64;
      goto LABEL_35;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 65, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
    }
    updated = NhRegisterWmiNotification(1u);
    HandleTable = updated;
    if ( updated )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
        goto LABEL_10;
      v14 = 66;
      goto LABEL_35;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 67, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
    }
    NhRegisterPowerManagementNotification(1u, g_hWlanServiceStatusHandle);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 68, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
    }
    v19 = RegisterLowPowerEpochNotification();
    if ( v19 )
    {
      v20 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_254;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 105) < 2u || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
      {
LABEL_250:
        if ( v20 != &WPP_GLOBAL_Control && *((_BYTE *)v20 + 105) >= 4u && (*((_BYTE *)v20 + 108) & 1) != 0 )
          WPP_SF_(v20[12], 70, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
LABEL_254:
        v21 = RegisterConnectivityInStandbyNotification();
        if ( v21 )
        {
          v22 = (wlansvc::power *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 71, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids, v21);
          }
        }
        wlansvc::power::InitializeDisplayStateTracker(v22);
        MDMPolicyInit();
        HandleTable = WlanSvcStartRPCServer();
        if ( HandleTable )
          goto LABEL_10;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 72, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
        }
        updated = (*((__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_svcHostGlobalData
                   + 24))(
                    &g_hWaitObject,
                    L"wlansvc",
                    g_hStopServiceEvent,
                    WlanStopService,
                    0,
                    8);
        HandleTable = updated;
        if ( updated )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
            goto LABEL_10;
          v14 = 73;
          goto LABEL_35;
        }
        v23 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 74, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
          v23 = (PVOID *)WPP_GLOBAL_Control;
        }
        g_WlanServiceStatus.dwCurrentState = 4;
        g_WlanServiceStatus.dwControlsAccepted = 197;
        if ( dword_1802A016C )
        {
          g_WlanServiceStatus.dwControlsAccepted = 4293;
          if ( v23 == &WPP_GLOBAL_Control || *((_BYTE *)v23 + 105) < 4u || (*((_BYTE *)v23 + 108) & 1) == 0 )
            goto LABEL_282;
          v24 = 75;
        }
        else
        {
          if ( v23 == &WPP_GLOBAL_Control || *((_BYTE *)v23 + 105) < 4u || (*((_BYTE *)v23 + 108) & 1) == 0 )
            goto LABEL_282;
          v24 = 76;
        }
        WPP_SF_(v23[12], v24, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
LABEL_282:
        *(_QWORD *)&g_WlanServiceStatus.dwCheckPoint = 0;
        updated = WlanSvcUpdateStatus();
        HandleTable = updated;
        if ( !updated )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 78, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
          }
          v25 = WiFiNetManInitialize();
          if ( v25 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 79, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids, v25);
          goto LABEL_294;
        }
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) == 0 )
          goto LABEL_10;
        v14 = 77;
LABEL_35:
        WPP_SF_d(v13[12], v14, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids, updated);
        goto LABEL_10;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 69, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids, v19);
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_250;
  }
  LastError = GetLastError();
  HandleTable = LastError;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    v11 = 62;
    goto LABEL_217;
  }
LABEL_218:
  if ( HandleTable )
  {
LABEL_10:
    WlanLogServiceFailure(HandleTable);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 80, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids);
    v5 = *(_DWORD **)(wil::details::static_lazy<WlanTriageProvider>::get() + 8);
    if ( *v5 > 2u && (unsigned __int8)tlgKeywordOn(v5, 1, v5) )
    {
      LODWORD(v30) = HandleTable;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)byte_180275455,
        v6,
        v7,
        (__int64)&v30);
    }
    if ( g_hWlanServiceStatusHandle )
    {
      *(_QWORD *)&g_WlanServiceStatus.dwCurrentState = 3;
      g_WlanServiceStatus.dwCheckPoint = 0;
      g_WlanServiceStatus.dwWaitHint = 60000;
      WlanSvcUpdateStatus();
      WlanSvcShutdown(HandleTable);
      g_nThreads = 0;
      WlanStopSqmIfNeeded();
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        while ( v8 )
        {
          v27 = v8[1];
          if ( v27 )
          {
            UnregisterTraceGuids(v27);
            v8[1] = 0;
          }
          v8 = (_QWORD *)*v8;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
      *(_QWORD *)&g_WlanServiceStatus.dwCurrentState = 1;
      *(_QWORD *)&g_WlanServiceStatus.dwCheckPoint = 0;
      g_WlanServiceStatus.dwWin32ExitCode = HandleTable;
      g_WlanServiceStatus.dwServiceSpecificExitCode = 0;
      WlanSvcUpdateStatus();
    }
    else
    {
      g_nThreads = 0;
      WlanStopSqmIfNeeded();
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        while ( v28 )
        {
          v29 = v28[1];
          if ( v29 )
          {
            UnregisterTraceGuids(v29);
            v28[1] = 0;
          }
          v28 = (_QWORD *)*v28;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
    return;
  }
LABEL_294:
  WlanLogServiceEvent(0);
  WimLoadInterfaces();
  if ( (unsigned int)CompleteMigrationNeeded() )
  {
    _m_prefetchw(&g_WlanMigrationStatus);
    if ( (_InterlockedOr(&g_WlanMigrationStatus, 1u) & 1) == 0 )
      CompleteMigration();
  }
  inited = NlaWPlgInitRegTimer();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 81, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids, inited);
  }
  _InterlockedDecrement((volatile signed __int32 *)&g_nThreads);
}

```

## disassembly

```asm
0x180117260  push    rbx
0x180117262  push    rbp
0x180117263  push    rsi
0x180117264  push    rdi
0x180117265  push    r14
0x180117267  push    r15
0x180117269  sub     rsp, 48h
0x18011726d  mov     esi, 1
0x180117272  mov     cs:?g_nThreads@@3KA, esi; ulong g_nThreads
0x180117278  call    ?WlanSvcInitTracing@@YAXXZ; WlanSvcInitTracing(void)
0x18011727d  call    ?get@?$static_lazy@VWlanTriageProvider@@@details@wil@@QEAAPEAVWlanTriageProvider@@P6AXXZ@Z; wil::details::static_lazy<WlanTriageProvider>::get(void (*)(void))
0x180117282  xor     r14d, r14d
0x180117285  lea     r15d, [rsi+3]
0x180117289  mov     r8, [rax+8]
0x18011728d  mov     eax, [r8]
0x180117290  cmp     eax, r15d
0x180117293  jbe     short loc_1801172B2
0x180117295  mov     edx, esi
0x180117297  mov     rcx, r8
0x18011729a  call    _tlgKeywordOn
0x18011729f  test    al, al
0x1801172a1  jz      short loc_1801172B2
0x1801172a3  lea     rdx, byte_180275493
0x1801172aa  mov     rcx, r8
0x1801172ad  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801172b2  call    WlanStartSqmIfNeeded
0x1801172b7  lea     r8, ?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1801172be  mov     edx, 64h ; 'd'
0x1801172c3  xor     ecx, ecx
0x1801172c5  call    cs:__imp_HtCreateHandleTable
0x1801172cb  lea     rbp, WPP_GLOBAL_Control
0x1801172d2  mov     ebx, eax
0x1801172d4  lea     rdi, WPP_4807d55182733ccb6293e4561fe140a1_Traceguids
0x1801172db  test    eax, eax
0x1801172dd  jnz     short loc_180117312
0x1801172df  cmp     cs:?g_svcHostGlobalData@@3PEAU_SVCHOST_GLOBAL_DATA@@EA, r14; _SVCHOST_GLOBAL_DATA * g_svcHostGlobalData
0x1801172e6  jnz     loc_1801173D5
0x1801172ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1801172f3  cmp     rcx, rbp
0x1801172f6  jz      short loc_18011730D
0x1801172f8  test    [rcx+6Ch], sil
0x1801172fc  jz      short loc_18011730D
0x1801172fe  mov     rcx, [rcx+60h]
0x180117302  lea     edx, [rax+0Ch]
0x180117305  mov     r8, rdi
0x180117308  call    WPP_SF_
0x18011730d  mov     ebx, 0Dh
0x180117312  mov     ecx, ebx; unsigned int
0x180117314  call    ?WlanLogServiceFailure@@YAKK@Z; WlanLogServiceFailure(ulong)
0x180117319  mov     rcx, cs:WPP_GLOBAL_Control
0x180117320  cmp     rcx, rbp
0x180117323  jz      short loc_18011733C
0x180117325  test    [rcx+6Ch], sil
0x180117329  jz      short loc_18011733C
0x18011732b  mov     rcx, [rcx+60h]
0x18011732f  mov     edx, 50h ; 'P'
0x180117334  mov     r8, rdi
0x180117337  call    WPP_SF_
0x18011733c  call    ?get@?$static_lazy@VWlanTriageProvider@@@details@wil@@QEAAPEAVWlanTriageProvider@@P6AXXZ@Z; wil::details::static_lazy<WlanTriageProvider>::get(void (*)(void))
0x180117341  mov     r8, [rax+8]
0x180117345  mov     eax, [r8]
0x180117348  cmp     eax, 2
0x18011734b  jbe     short loc_18011737F
0x18011734d  mov     rdx, rsi
0x180117350  mov     rcx, r8
0x180117353  call    _tlgKeywordOn
0x180117358  test    al, al
0x18011735a  jz      short loc_18011737F
0x18011735c  lea     rax, [rsp+78h+arg_10]
0x180117364  mov     dword ptr [rsp+78h+arg_10], ebx
0x18011736b  lea     rdx, byte_180275455
0x180117372  mov     [rsp+78h+var_58], rax
0x180117377  mov     rcx, r8
0x18011737a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18011737f  cmp     cs:?g_hWlanServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, r14; SERVICE_STATUS_HANDLE__ * g_hWlanServiceStatusHandle
0x180117386  jz      loc_1801181AC
0x18011738c  mov     qword ptr cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_WlanServiceStatus ...
0x180117397  mov     cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14d; _SERVICE_STATUS g_WlanServiceStatus ...
0x18011739e  mov     cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS g_WlanServiceStatus ...
0x1801173a8  call    ?WlanSvcUpdateStatus@@YAKXZ; WlanSvcUpdateStatus(void)
0x1801173ad  mov     ecx, ebx; unsigned int
0x1801173af  call    ?WlanSvcShutdown@@YAXK@Z; WlanSvcShutdown(ulong)
0x1801173b4  mov     cs:?g_nThreads@@3KA, r14d; ulong g_nThreads
0x1801173bb  call    WlanStopSqmIfNeeded
0x1801173c0  mov     rdi, cs:WPP_GLOBAL_Control
0x1801173c7  cmp     rdi, rbp
0x1801173ca  jz      loc_18011818A
0x1801173d0  jmp     loc_18011817E
0x1801173d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1801173dc  cmp     rcx, rbp
0x1801173df  jz      short loc_1801173FE
0x1801173e1  cmp     [rcx+69h], r15b
0x1801173e5  jb      short loc_1801173FE
0x1801173e7  test    [rcx+6Ch], sil
0x1801173eb  jz      short loc_1801173FE
0x1801173ed  mov     rcx, [rcx+60h]
0x1801173f1  mov     edx, 0Dh
0x1801173f6  mov     r8, rdi
0x1801173f9  call    WPP_SF_
0x1801173fe  xor     r8d, r8d; lpContext
0x180117401  lea     rdx, ?NhScmNotificationHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180117408  lea     rcx, aWlansvc_1; "wlansvc"
0x18011740f  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180117415  mov     cs:?g_hWlanServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hWlanServiceStatusHandle
0x18011741c  test    rax, rax
0x18011741f  jnz     short loc_18011744D
0x180117421  call    cs:__imp_GetLastError
0x180117427  mov     ebx, eax
0x180117429  mov     rcx, cs:WPP_GLOBAL_Control
0x180117430  cmp     rcx, rbp
0x180117433  jz      loc_180117D68
0x180117439  test    [rcx+6Ch], sil
0x18011743d  jz      loc_180117D68
0x180117443  mov     edx, 0Eh
0x180117448  jmp     loc_180117D59
0x18011744d  mov     cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_WlanServiceStatus ...
0x180117457  mov     qword ptr cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS g_WlanServiceStatus ...
0x180117462  mov     cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, r14d; _SERVICE_STATUS g_WlanServiceStatus ...
0x180117469  mov     cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0FA0h; _SERVICE_STATUS g_WlanServiceStatus ...
0x180117473  mov     qword ptr cs:?g_WlanServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, r14; _SERVICE_STATUS g_WlanServiceStatus ...
0x18011747a  mov     rcx, cs:WPP_GLOBAL_Control
0x180117481  cmp     rcx, rbp
0x180117484  jz      short loc_1801174A3
0x180117486  cmp     [rcx+69h], r15b
0x18011748a  jb      short loc_1801174A3
0x18011748c  test    [rcx+6Ch], sil
0x180117490  jz      short loc_1801174A3
0x180117492  mov     rcx, [rcx+60h]
0x180117496  mov     edx, 0Fh
0x18011749b  mov     r8, rdi
0x18011749e  call    WPP_SF_
0x1801174a3  call    ?WlanSvcUpdateStatus@@YAKXZ; WlanSvcUpdateStatus(void)
0x1801174a8  mov     ebx, eax
0x1801174aa  test    eax, eax
0x1801174ac  jz      short loc_1801174E1
0x1801174ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1801174b5  cmp     rcx, rbp
0x1801174b8  jz      loc_180117312
0x1801174be  test    [rcx+6Ch], sil
0x1801174c2  jz      loc_180117312
0x1801174c8  mov     edx, 10h
0x1801174cd  mov     rcx, [rcx+60h]
0x1801174d1  mov     r9d, eax
0x1801174d4  mov     r8, rdi
0x1801174d7  call    WPP_SF_d
0x1801174dc  jmp     loc_180117312
0x1801174e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1801174e8  cmp     rcx, rbp
0x1801174eb  jz      short loc_18011750A
0x1801174ed  cmp     [rcx+69h], r15b
0x1801174f1  jb      short loc_18011750A
0x1801174f3  test    [rcx+6Ch], sil
0x1801174f7  jz      short loc_18011750A
0x1801174f9  mov     rcx, [rcx+60h]
0x1801174fd  mov     edx, 11h
0x180117502  mov     r8, rdi
0x180117505  call    WPP_SF_
0x18011750a  call    ?AnqpCacheInitialize@@YAXXZ; AnqpCacheInitialize(void)
0x18011750f  mov     rcx, cs:WPP_GLOBAL_Control
0x180117516  cmp     rcx, rbp
0x180117519  jz      short loc_180117538
0x18011751b  cmp     [rcx+69h], r15b
0x18011751f  jb      short loc_180117538
0x180117521  test    [rcx+6Ch], sil
0x180117525  jz      short loc_180117538
0x180117527  mov     rcx, [rcx+60h]
0x18011752b  mov     edx, 12h
0x180117530  mov     r8, rdi
0x180117533  call    WPP_SF_
0x180117538  call    ?WlanSvcPAL_Initialize@@YAKXZ; WlanSvcPAL_Initialize(void)
0x18011753d  mov     ebx, eax
0x18011753f  test    eax, eax
0x180117541  jz      short loc_180117567
0x180117543  mov     rcx, cs:WPP_GLOBAL_Control
0x18011754a  cmp     rcx, rbp
0x18011754d  jz      loc_180117312
0x180117553  test    [rcx+6Ch], sil
0x180117557  jz      loc_180117312
0x18011755d  mov     edx, 13h
0x180117562  jmp     loc_1801174CD
0x180117567  mov     rcx, cs:WPP_GLOBAL_Control
0x18011756e  cmp     rcx, rbp
0x180117571  jz      short loc_180117590
0x180117573  cmp     [rcx+69h], r15b
0x180117577  jb      short loc_180117590
0x180117579  test    [rcx+6Ch], sil
0x18011757d  jz      short loc_180117590
0x18011757f  mov     rcx, [rcx+60h]
0x180117583  mov     edx, 14h
0x180117588  mov     r8, rdi
0x18011758b  call    WPP_SF_
0x180117590  call    ?StInit@@YAKXZ; StInit(void)
0x180117595  mov     ebx, eax
0x180117597  test    eax, eax
0x180117599  jz      short loc_1801175BF
0x18011759b  mov     rcx, cs:WPP_GLOBAL_Control
0x1801175a2  cmp     rcx, rbp
0x1801175a5  jz      loc_180117312
0x1801175ab  test    [rcx+6Ch], sil
0x1801175af  jz      loc_180117312
0x1801175b5  mov     edx, 15h
0x1801175ba  jmp     loc_1801174CD
0x1801175bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1801175c6  cmp     rcx, rbp
0x1801175c9  jz      short loc_1801175E8
0x1801175cb  cmp     [rcx+69h], r15b
0x1801175cf  jb      short loc_1801175E8
0x1801175d1  test    [rcx+6Ch], sil
0x1801175d5  jz      short loc_1801175E8
0x1801175d7  mov     rcx, [rcx+60h]
0x1801175db  mov     edx, 16h
0x1801175e0  mov     r8, rdi
0x1801175e3  call    WPP_SF_
0x1801175e8  call    ?WlanSvcContextInit@@YAKXZ; WlanSvcContextInit(void)
0x1801175ed  mov     ebx, eax
0x1801175ef  test    eax, eax
0x1801175f1  jz      short loc_180117617
0x1801175f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1801175fa  cmp     rcx, rbp
0x1801175fd  jz      loc_180117312
0x180117603  test    [rcx+6Ch], sil
0x180117607  jz      loc_180117312
0x18011760d  mov     edx, 17h
0x180117612  jmp     loc_1801174CD
0x180117617  mov     rcx, cs:WPP_GLOBAL_Control
0x18011761e  cmp     rcx, rbp
0x180117621  jz      short loc_180117640
0x180117623  cmp     [rcx+69h], r15b
0x180117627  jb      short loc_180117640
0x180117629  test    [rcx+6Ch], sil
0x18011762d  jz      short loc_180117640
0x18011762f  mov     rcx, [rcx+60h]
0x180117633  mov     edx, 18h
0x180117638  mov     r8, rdi
0x18011763b  call    WPP_SF_
0x180117640  call    ?AcmInitSessionContext@@YAKXZ; AcmInitSessionContext(void)
0x180117645  mov     ebx, eax
0x180117647  test    eax, eax
0x180117649  jz      short loc_18011766F
0x18011764b  mov     rcx, cs:WPP_GLOBAL_Control
0x180117652  cmp     rcx, rbp
0x180117655  jz      loc_180117312
0x18011765b  test    [rcx+6Ch], sil
0x18011765f  jz      loc_180117312
0x180117665  mov     edx, 19h
0x18011766a  jmp     loc_1801174CD
0x18011766f  call    ?TmInit@@YAKXZ; TmInit(void)
0x180117674  mov     ebx, eax
0x180117676  test    eax, eax
0x180117678  jz      short loc_1801176AA
0x18011767a  mov     rcx, cs:WPP_GLOBAL_Control
0x180117681  cmp     rcx, rbp
0x180117684  jz      loc_180117312
0x18011768a  test    [rcx+6Ch], sil
0x18011768e  jz      loc_180117312
0x180117694  mov     rcx, [rcx+60h]
0x180117698  mov     edx, 1Ah
0x18011769d  mov     r8, rdi
0x1801176a0  call    WPP_SF_
0x1801176a5  jmp     loc_180117312
0x1801176aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1801176b1  cmp     rcx, rbp
0x1801176b4  jz      short loc_1801176D3
0x1801176b6  cmp     [rcx+69h], r15b
0x1801176ba  jb      short loc_1801176D3
0x1801176bc  test    [rcx+6Ch], sil
0x1801176c0  jz      short loc_1801176D3
0x1801176c2  mov     rcx, [rcx+60h]
0x1801176c6  mov     edx, 1Bh
0x1801176cb  mov     r8, rdi
0x1801176ce  call    WPP_SF_
0x1801176d3  call    ?Init@profile@wlansvc@@YAKXZ; wlansvc::profile::Init(void)
0x1801176d8  mov     ebx, eax
0x1801176da  test    eax, eax
0x1801176dc  jz      short loc_180117702
0x1801176de  mov     rcx, cs:WPP_GLOBAL_Control
0x1801176e5  cmp     rcx, rbp
0x1801176e8  jz      loc_180117312
0x1801176ee  test    [rcx+6Ch], sil
0x1801176f2  jz      loc_180117312
0x1801176f8  mov     edx, 1Ch
0x1801176fd  jmp     loc_1801174CD
0x180117702  mov     rcx, cs:WPP_GLOBAL_Control
0x180117709  cmp     rcx, rbp
0x18011770c  jz      short loc_18011772B
0x18011770e  cmp     [rcx+69h], r15b
0x180117712  jb      short loc_18011772B
0x180117714  test    [rcx+6Ch], sil
0x180117718  jz      short loc_18011772B
0x18011771a  mov     rcx, [rcx+60h]
0x18011771e  mov     edx, 1Dh
0x180117723  mov     r8, rdi
0x180117726  call    WPP_SF_
0x18011772b  lea     rcx, stru_1802A2660; lpCriticalSection
0x180117732  call    cs:__imp_InitializeCriticalSection
0x180117738  lea     rax, qword_1802A2688
0x18011773f  mov     cs:qword_1802A269C, r14
0x180117746  xor     r9d, r9d; lpName
0x180117749  mov     cs:qword_1802A2690, rax
0x180117750  mov     r8d, esi; bInitialState
  ... truncated ...
```
