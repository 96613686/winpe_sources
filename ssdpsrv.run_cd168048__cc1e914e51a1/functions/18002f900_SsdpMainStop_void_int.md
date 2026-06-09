# SsdpMainStop(void *,int)

- ea: `0x18002f900`
- end: `0x18002fe22`
- name: `?SsdpMainStop@@YAXPEAXH@Z`
- size: `1314`
- prototype: `void __fastcall(struct ServiceContext *, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180029bf0`

## callees

- `0x18000a9ac`
- `0x18000c9cc`
- `0x180018128`
- `0x1800218ac`
- `0x180024254`
- `0x18002911c`
- `0x180029df0`
- `0x18002f89c`
- `0x18002f900`
- `0x180031468`
- `0x180031944`
- `0x18003224c`
- `0x180032480`
- `0x18003278c`
- `0x180033fe0`
- `0x180034ac4`
- `0x180035930`
- `0x180036598`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fdd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002fdd4`
- `ntdll!EtwUnregisterTraceGuids` at `0x18002fdf7`
- `ntdll!EtwUnregisterTraceGuids` at `0x18002fdf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fc07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbcd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fbcd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fcc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fcc9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f9ae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f9ae`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002f9c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002f9c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f999`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f999`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002fb88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002fb88`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002fb75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002fb75`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002fb62`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002fb62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002faea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fd7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f9ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002faea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fd7f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002f9e0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002f9e0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fa19`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002fa19`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002fc76`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002fc76`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002fdc5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002fdc5`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18002fa9a`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18002fa9a`
- `WS2_32!__imp_WSACleanup` at `0x18002fcef`
- `WS2_32!__imp_WSACleanup` at `0x18002fcef`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002fa76`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002fa76`
- `WINHTTP!WinHttpCloseHandle` at `0x18002fd9e`
- `WINHTTP!WinHttpCloseHandle` at `0x18002fd9e`

## pseudocode

```c
void __fastcall SsdpMainStop(struct ServiceContext *a1)
{
  LPCSTR v2; // rcx
  void *v3; // rdx
  void (__fastcall *v4)(__int64 *); // rax
  int v5; // ecx
  DelayedLoadCryptoRandom *v6; // rdi
  __int64 v7; // rdx
  SERVICE_STATUS_HANDLE v8; // rcx
  LPCSTR v9; // rbx

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    UpdateServiceCheckPoint(a1);
    if ( g_shutdownTimer )
    {
      SetThreadpoolTimer(g_shutdownTimer, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(g_shutdownTimer, 1);
      CloseThreadpoolTimer(g_shutdownTimer);
      g_shutdownTimer = 0;
    }
    if ( g_hStopWait )
    {
      UnregisterWait(g_hStopWait);
      g_hStopWait = 0;
    }
    if ( g_hServiceStopEvent )
    {
      CloseHandle(g_hServiceStopEvent);
      g_hServiceStopEvent = 0;
    }
    while ( g_lCallbackCount > 0 )
      Sleep(0xAu);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids);
    UpdateServiceCheckPoint(a1);
    if ( *(_DWORD *)a1 )
      RpcServerStop();
    if ( *((_DWORD *)a1 + 1) && g_hAddrChange )
    {
      CancelMibChangeNotify2(g_hAddrChange);
      g_hAddrChange = 0;
    }
    if ( *((_DWORD *)a1 + 2) && g_hNqmNotification )
    {
      PowerSettingUnregisterNotification(g_hNqmNotification);
      g_hNqmNotification = 0;
    }
    CReceiveDataManager::HrShutdown(&CReceiveDataManager::s_instance);
    CSsdpCacheEntryManager::HrShutdown(&CSsdpCacheEntryManager::s_instance);
    CSsdpNotifyRequestManager::HrRemoveInternal(
      (CSsdpNotifyRequestManager *)&CSsdpNotifyRequestManager::s_instance,
      0,
      1,
      0,
      0);
    if ( *((_QWORD *)&xmmword_1800446D0 + 1) )
    {
      CloseHandle(*((HANDLE *)&xmmword_1800446D0 + 1));
      *((_QWORD *)&xmmword_1800446D0 + 1) = 0;
    }
    CSsdpServiceManager::HrRemoveServiceInternal(&CSsdpServiceManager::s_instance, 0, 1, 0, 1);
    CStaleWorkItemsTracking::HrShutdown(&CSsdpByebye::s_WorkItemTracking);
    CStaleWorkItemsTracking::HrShutdown(&CSsdpSearchResponse::s_WorkItemTracking);
    CSsdpSearchRequestManager::HrShutdown(&CSsdpSearchRequestManager::s_instance);
    CFirewallManager::HrShutdown((CFirewallManager *)&CFirewallManager::s_instance);
    UpdateServiceCheckPoint(a1);
    if ( CWorkItem::s_tpEnviron )
    {
      CloseThreadpoolCleanupGroupMembers(*(&CWorkItem::s_tpEnviron + 1), 0, 0);
      CloseThreadpoolCleanupGroup(*(&CWorkItem::s_tpEnviron + 1));
      CloseThreadpool(CWorkItem::s_tpEnviron);
      memset_0(&CWorkItem::s_tpEnviron, 0, 0x58u);
    }
    UpdateServiceCheckPoint(a1);
    CTimerQueue::HrShutdown((CTimerQueue *)&CTimerQueue::s_instance, v3);
    CUPnPInterfaceList::HrShutdown(&CUPnPInterfaceList::s_instance);
    EnterCriticalSection(&stru_180044128);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9c29e5a395c43598115319381ae1359a_Traceguids);
    LeaveCriticalSection(&stru_180044128);
    v4 = (void (__fastcall *)(__int64 *))qword_180045688;
    if ( qword_180045690 && qword_180045688 )
    {
      qword_180045688(&qword_180045690);
      v4 = (void (__fastcall *)(__int64 *))qword_180045688;
      qword_180045690 = 0;
    }
    if ( qword_180045678 && v4 )
    {
      v4(&qword_180045678);
      qword_180045678 = 0;
    }
    if ( WaitHandle )
    {
      UnregisterWaitEx(WaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      WaitHandle = 0;
    }
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    v5 = (int)hLibModule;
    if ( hLibModule )
    {
      qword_1800456D0 = 0;
      qword_180045688 = 0;
      qword_1800456B8 = 0;
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    CleanupListNetwork(v5);
    if ( _InterlockedDecrement(&dword_180045718) < 0 )
    {
      _InterlockedAdd(&dword_180045718, 1u);
    }
    else
    {
      WSACleanup();
      CleanupLocalAddrList();
    }
    if ( g_pEventHTTPListener )
      (**(void (__fastcall ***)(BaseHttpListener *, __int64))g_pEventHTTPListener)(g_pEventHTTPListener, 1);
    v6 = g_pRandomGenerator;
    g_pEventHTTPListener = 0;
    if ( g_pRandomGenerator )
    {
      DelayedLoadCryptoRandom::~DelayedLoadCryptoRandom(g_pRandomGenerator);
      operator delete(v6);
    }
    g_pRandomGenerator = 0;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids);
    if ( ShutDownEvent )
    {
      CloseHandle(ShutDownEvent);
      ShutDownEvent = 0;
    }
    if ( g_hInetSess )
    {
      WinHttpCloseHandle(g_hInetSess);
      g_hInetSess = 0;
    }
    v7 = *((_QWORD *)a1 + 3);
    if ( v7 )
    {
      v8 = (SERVICE_STATUS_HANDLE)*((_QWORD *)a1 + 2);
      *(_DWORD *)(v7 + 4) = 1;
      *(_QWORD *)(v7 + 20) = 0;
      SetServiceStatus(v8, (LPSERVICE_STATUS)v7);
    }
    free(a1);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      while ( v9 )
      {
        if ( *((_QWORD *)v9 + 1) )
        {
          EtwUnregisterTraceGuids();
          *((_QWORD *)v9 + 1) = 0;
        }
        v9 = *(LPCSTR *)v9;
      }
      WPP_GLOBAL_Control = (LPCSTR)&WPP_GLOBAL_Control;
    }
  }
  else if ( v2 != (LPCSTR)&WPP_GLOBAL_Control && (v2[28] & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v2 + 2), 57, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids);
  }
}

```

## disassembly

```asm
0x18002f900  push    rbx
0x18002f902  push    rbp
0x18002f903  push    rsi
0x18002f904  push    rdi
0x18002f905  push    r14
0x18002f907  sub     rsp, 30h
0x18002f90b  mov     rbx, rcx
0x18002f90e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f915  lea     r14, WPP_GLOBAL_Control
0x18002f91c  cmp     rcx, r14
0x18002f91f  jz      short loc_18002F943
0x18002f921  test    byte ptr [rcx+1Ch], 8
0x18002f925  jz      short loc_18002F943
0x18002f927  mov     rcx, [rcx+10h]
0x18002f92b  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002f932  mov     edx, 38h ; '8'
0x18002f937  call    WPP_SF_
0x18002f93c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f943  xor     ebp, ebp
0x18002f945  test    rbx, rbx
0x18002f948  jnz     short loc_18002F978
0x18002f94a  cmp     rcx, r14
0x18002f94d  jz      loc_18002FE16
0x18002f953  lea     esi, [rbp+1]
0x18002f956  test    [rcx+1Ch], sil
0x18002f95a  jz      loc_18002FE16
0x18002f960  mov     rcx, [rcx+10h]
0x18002f964  lea     edx, [rbp+39h]
0x18002f967  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002f96e  call    WPP_SF_
0x18002f973  jmp     loc_18002FE16
0x18002f978  mov     rcx, rbx; struct ServiceContext *
0x18002f97b  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002f980  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002f987  mov     esi, 1
0x18002f98c  test    rcx, rcx
0x18002f98f  jz      short loc_18002F9D4
0x18002f991  xor     r9d, r9d; msWindowLength
0x18002f994  xor     r8d, r8d; msPeriod
0x18002f997  xor     edx, edx; pftDueTime
0x18002f999  call    cs:__imp_SetThreadpoolTimer
0x18002f9a0  nop     dword ptr [rax+rax+00h]
0x18002f9a5  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002f9ac  mov     edx, esi; fCancelPendingCallbacks
0x18002f9ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002f9b5  nop     dword ptr [rax+rax+00h]
0x18002f9ba  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002f9c1  call    cs:__imp_CloseThreadpoolTimer
0x18002f9c8  nop     dword ptr [rax+rax+00h]
0x18002f9cd  mov     cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA, rbp; _TP_TIMER * g_shutdownTimer
0x18002f9d4  mov     rcx, cs:?g_hStopWait@@3PEAXEA; WaitHandle
0x18002f9db  test    rcx, rcx
0x18002f9de  jz      short loc_18002F9F3
0x18002f9e0  call    cs:__imp_UnregisterWait
0x18002f9e7  nop     dword ptr [rax+rax+00h]
0x18002f9ec  mov     cs:?g_hStopWait@@3PEAXEA, rbp; void * g_hStopWait
0x18002f9f3  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hObject
0x18002f9fa  test    rcx, rcx
0x18002f9fd  jz      short loc_18002FA25
0x18002f9ff  call    cs:__imp_CloseHandle
0x18002fa06  nop     dword ptr [rax+rax+00h]
0x18002fa0b  mov     cs:?g_hServiceStopEvent@@3PEAXEA, rbp; void * g_hServiceStopEvent
0x18002fa12  jmp     short loc_18002FA25
0x18002fa14  mov     ecx, 0Ah; dwMilliseconds
0x18002fa19  call    cs:__imp_Sleep
0x18002fa20  nop     dword ptr [rax+rax+00h]
0x18002fa25  cmp     cs:?g_lCallbackCount@@3JA, ebp; long g_lCallbackCount
0x18002fa2b  jg      short loc_18002FA14
0x18002fa2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa34  cmp     rcx, r14
0x18002fa37  jz      short loc_18002FA54
0x18002fa39  test    byte ptr [rcx+1Ch], 8
0x18002fa3d  jz      short loc_18002FA54
0x18002fa3f  mov     rcx, [rcx+10h]
0x18002fa43  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002fa4a  mov     edx, 3Ah ; ':'
0x18002fa4f  call    WPP_SF_
0x18002fa54  mov     rcx, rbx; struct ServiceContext *
0x18002fa57  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002fa5c  cmp     [rbx], ebp
0x18002fa5e  jz      short loc_18002FA65
0x18002fa60  call    ?RpcServerStop@@YAHXZ; RpcServerStop(void)
0x18002fa65  cmp     [rbx+4], ebp
0x18002fa68  jz      short loc_18002FA89
0x18002fa6a  mov     rcx, cs:?g_hAddrChange@@3PEAXEA; NotificationHandle
0x18002fa71  test    rcx, rcx
0x18002fa74  jz      short loc_18002FA89
0x18002fa76  call    cs:__imp_CancelMibChangeNotify2
0x18002fa7d  nop     dword ptr [rax+rax+00h]
0x18002fa82  mov     cs:?g_hAddrChange@@3PEAXEA, rbp; void * g_hAddrChange
0x18002fa89  cmp     [rbx+8], ebp
0x18002fa8c  jz      short loc_18002FAAD
0x18002fa8e  mov     rcx, cs:?g_hNqmNotification@@3PEAXEA; RegistrationHandle
0x18002fa95  test    rcx, rcx
0x18002fa98  jz      short loc_18002FAAD
0x18002fa9a  call    cs:__imp_PowerSettingUnregisterNotification
0x18002faa1  nop     dword ptr [rax+rax+00h]
0x18002faa6  mov     cs:?g_hNqmNotification@@3PEAXEA, rbp; void * g_hNqmNotification
0x18002faad  lea     rcx, ?s_instance@CReceiveDataManager@@0V1@A; lpCriticalSection
0x18002fab4  call    ?HrShutdown@CReceiveDataManager@@QEAAJXZ; CReceiveDataManager::HrShutdown(void)
0x18002fab9  lea     rcx, ?s_instance@CSsdpCacheEntryManager@@0V1@A; lpCriticalSection
0x18002fac0  call    ?HrShutdown@CSsdpCacheEntryManager@@QEAAJXZ; CSsdpCacheEntryManager::HrShutdown(void)
0x18002fac5  xor     r9d, r9d; void *
0x18002fac8  mov     [rsp+58h+var_38], rbp; struct CSsdpNotifyRequest *
0x18002facd  mov     r8d, esi; int
0x18002fad0  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x18002fad7  xor     edx, edx; int
0x18002fad9  call    ?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z; CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)
0x18002fade  mov     rcx, qword ptr cs:xmmword_1800446D0+8; hObject
0x18002fae5  test    rcx, rcx
0x18002fae8  jz      short loc_18002FAFD
0x18002faea  call    cs:__imp_CloseHandle
0x18002faf1  nop     dword ptr [rax+rax+00h]
0x18002faf6  mov     qword ptr cs:xmmword_1800446D0+8, rbp
0x18002fafd  xor     r9d, r9d; int
0x18002fb00  mov     dword ptr [rsp+58h+var_38], esi; int
0x18002fb04  mov     r8d, esi; int
0x18002fb07  lea     rcx, ?s_instance@CSsdpServiceManager@@0V1@A; lpCriticalSection
0x18002fb0e  xor     edx, edx; struct CSsdpService *
0x18002fb10  call    ?HrRemoveServiceInternal@CSsdpServiceManager@@AEAAJPEAVCSsdpService@@HHH@Z; CSsdpServiceManager::HrRemoveServiceInternal(CSsdpService *,int,int,int)
0x18002fb15  lea     rcx, ?s_WorkItemTracking@CSsdpByebye@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18002fb1c  call    ?HrShutdown@CStaleWorkItemsTracking@@QEAAJXZ; CStaleWorkItemsTracking::HrShutdown(void)
0x18002fb21  lea     rcx, ?s_WorkItemTracking@CSsdpSearchResponse@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18002fb28  call    ?HrShutdown@CStaleWorkItemsTracking@@QEAAJXZ; CStaleWorkItemsTracking::HrShutdown(void)
0x18002fb2d  lea     rcx, ?s_instance@CSsdpSearchRequestManager@@0V1@A; lpCriticalSection
0x18002fb34  call    ?HrShutdown@CSsdpSearchRequestManager@@QEAAJXZ; CSsdpSearchRequestManager::HrShutdown(void)
0x18002fb39  lea     rcx, ?s_instance@CFirewallManager@@0V1@A; this
0x18002fb40  call    ?HrShutdown@CFirewallManager@@QEAAJXZ; CFirewallManager::HrShutdown(void)
0x18002fb45  mov     rcx, rbx; struct ServiceContext *
0x18002fb48  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002fb4d  cmp     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, rbp; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18002fb54  jz      short loc_18002FBA6
0x18002fb56  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x18002fb5d  xor     r8d, r8d; pvCleanupContext
0x18002fb60  xor     edx, edx; fCancelPendingCallbacks
0x18002fb62  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002fb69  nop     dword ptr [rax+rax+00h]
0x18002fb6e  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x18002fb75  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002fb7c  nop     dword ptr [rax+rax+00h]
0x18002fb81  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x18002fb88  call    cs:__imp_CloseThreadpool
0x18002fb8f  nop     dword ptr [rax+rax+00h]
0x18002fb94  xor     edx, edx; Val
0x18002fb96  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x18002fb9d  lea     r8d, [rdx+58h]; Size
0x18002fba1  call    memset_0
0x18002fba6  mov     rcx, rbx; struct ServiceContext *
0x18002fba9  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002fbae  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x18002fbb5  call    ?HrShutdown@CTimerQueue@@QEAAJPEAX@Z; CTimerQueue::HrShutdown(void *)
0x18002fbba  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x18002fbc1  call    ?HrShutdown@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrShutdown(void)
0x18002fbc6  lea     rcx, stru_180044128; lpCriticalSection
0x18002fbcd  call    cs:__imp_EnterCriticalSection
0x18002fbd4  nop     dword ptr [rax+rax+00h]
0x18002fbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbe0  cmp     rcx, r14
0x18002fbe3  jz      short loc_18002FC00
0x18002fbe5  test    byte ptr [rcx+1Ch], 8
0x18002fbe9  jz      short loc_18002FC00
0x18002fbeb  mov     rcx, [rcx+10h]
0x18002fbef  lea     r8, WPP_9c29e5a395c43598115319381ae1359a_Traceguids
0x18002fbf6  mov     edx, 0Dh
0x18002fbfb  call    WPP_SF_
0x18002fc00  lea     rcx, stru_180044128; lpCriticalSection
0x18002fc07  call    cs:__imp_LeaveCriticalSection
0x18002fc0e  nop     dword ptr [rax+rax+00h]
0x18002fc13  cmp     cs:qword_180045690, rbp
0x18002fc1a  mov     rax, cs:qword_180045688
0x18002fc21  jz      short loc_18002FC42
0x18002fc23  test    rax, rax
0x18002fc26  jz      short loc_18002FC42
0x18002fc28  lea     rcx, qword_180045690
0x18002fc2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc34  mov     rax, cs:qword_180045688
0x18002fc3b  mov     cs:qword_180045690, rbp
0x18002fc42  cmp     cs:qword_180045678, rbp
0x18002fc49  jz      short loc_18002FC63
0x18002fc4b  test    rax, rax
0x18002fc4e  jz      short loc_18002FC63
0x18002fc50  lea     rcx, qword_180045678
0x18002fc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc5c  mov     cs:qword_180045678, rbp
0x18002fc63  mov     rcx, cs:WaitHandle; WaitHandle
0x18002fc6a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002fc6e  test    rcx, rcx
0x18002fc71  jz      short loc_18002FC89
0x18002fc73  mov     rdx, rdi; CompletionEvent
0x18002fc76  call    cs:__imp_UnregisterWaitEx
0x18002fc7d  nop     dword ptr [rax+rax+00h]
0x18002fc82  mov     cs:WaitHandle, rbp
0x18002fc89  mov     rcx, cs:hObject; hObject
0x18002fc90  test    rcx, rcx
0x18002fc93  jz      short loc_18002FCA8
0x18002fc95  call    cs:__imp_CloseHandle
0x18002fc9c  nop     dword ptr [rax+rax+00h]
0x18002fca1  mov     cs:hObject, rbp
0x18002fca8  mov     rcx, cs:hLibModule; hLibModule
0x18002fcaf  test    rcx, rcx
0x18002fcb2  jz      short loc_18002FCDC
0x18002fcb4  mov     cs:qword_1800456D0, rbp
0x18002fcbb  mov     cs:qword_180045688, rbp
0x18002fcc2  mov     cs:qword_1800456B8, rbp
0x18002fcc9  call    cs:__imp_FreeLibrary
0x18002fcd0  nop     dword ptr [rax+rax+00h]
0x18002fcd5  mov     cs:hLibModule, rbp
0x18002fcdc  call    ?CleanupListNetwork@@YAXH@Z; CleanupListNetwork(int)
0x18002fce1  mov     eax, edi
0x18002fce3  lock xadd cs:dword_180045718, eax
0x18002fceb  add     eax, edi
0x18002fced  js      short loc_18002FD02
0x18002fcef  call    cs:__imp_WSACleanup
0x18002fcf6  nop     dword ptr [rax+rax+00h]
0x18002fcfb  call    ?CleanupLocalAddrList@@YAXXZ; CleanupLocalAddrList(void)
0x18002fd00  jmp     short loc_18002FD09
0x18002fd02  lock add cs:dword_180045718, esi
0x18002fd09  mov     rcx, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x18002fd10  test    rcx, rcx
0x18002fd13  jz      short loc_18002FD22
0x18002fd15  mov     rax, [rcx]
0x18002fd18  mov     edx, esi
0x18002fd1a  mov     rax, [rax]
0x18002fd1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd22  mov     rdi, cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18002fd29  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, rbp; BaseHttpListener * g_pEventHTTPListener
0x18002fd30  test    rdi, rdi
0x18002fd33  jz      short loc_18002FD45
0x18002fd35  mov     rcx, rdi; this
0x18002fd38  call    ??1DelayedLoadCryptoRandom@@QEAA@XZ; DelayedLoadCryptoRandom::~DelayedLoadCryptoRandom(void)
0x18002fd3d  mov     rcx, rdi; void *
0x18002fd40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002fd45  mov     cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA, rbp; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18002fd4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fd53  cmp     rcx, r14
0x18002fd56  jz      short loc_18002FD73
0x18002fd58  test    byte ptr [rcx+1Ch], 8
0x18002fd5c  jz      short loc_18002FD73
0x18002fd5e  mov     rcx, [rcx+10h]
0x18002fd62  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002fd69  mov     edx, 3Bh ; ';'
0x18002fd6e  call    WPP_SF_
0x18002fd73  mov     rcx, cs:?ShutDownEvent@@3PEAXEA; hObject
0x18002fd7a  test    rcx, rcx
0x18002fd7d  jz      short loc_18002FD92
0x18002fd7f  call    cs:__imp_CloseHandle
0x18002fd86  nop     dword ptr [rax+rax+00h]
0x18002fd8b  mov     cs:?ShutDownEvent@@3PEAXEA, rbp; void * ShutDownEvent
0x18002fd92  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x18002fd99  test    rcx, rcx
0x18002fd9c  jz      short loc_18002FDB1
0x18002fd9e  call    cs:__imp_WinHttpCloseHandle
0x18002fda5  nop     dword ptr [rax+rax+00h]
0x18002fdaa  mov     cs:?g_hInetSess@@3PEAXEA, rbp; void * g_hInetSess
0x18002fdb1  mov     rdx, [rbx+18h]; lpServiceStatus
0x18002fdb5  test    rdx, rdx
0x18002fdb8  jz      short loc_18002FDD1
0x18002fdba  mov     rcx, [rbx+10h]; hServiceStatus
0x18002fdbe  mov     [rdx+4], esi
0x18002fdc1  mov     [rdx+14h], rbp
0x18002fdc5  call    cs:__imp_SetServiceStatus
0x18002fdcc  nop     dword ptr [rax+rax+00h]
0x18002fdd1  mov     rcx, rbx; Block
0x18002fdd4  call    cs:__imp_free
0x18002fddb  nop     dword ptr [rax+rax+00h]
0x18002fde0  mov     rbx, cs:WPP_GLOBAL_Control
0x18002fde7  cmp     rbx, r14
0x18002fdea  jz      short loc_18002FE16
0x18002fdec  jmp     short loc_18002FE0A
0x18002fdee  mov     rcx, [rbx+8]
0x18002fdf2  test    rcx, rcx
0x18002fdf5  jz      short loc_18002FE07
0x18002fdf7  call    cs:__imp_EtwUnregisterTraceGuids
0x18002fdfe  nop     dword ptr [rax+rax+00h]
0x18002fe03  mov     [rbx+8], rbp
0x18002fe07  mov     rbx, [rbx]
0x18002fe0a  test    rbx, rbx
0x18002fe0d  jnz     short loc_18002FDEE
0x18002fe0f  mov     cs:WPP_GLOBAL_Control, r14
0x18002fe16  add     rsp, 30h
0x18002fe1a  pop     r14
0x18002fe1c  pop     rdi
0x18002fe1d  pop     rsi
0x18002fe1e  pop     rbp
0x18002fe1f  pop     rbx
0x18002fe20  retn
```
