# SsdpMainStop(void *,int)

- ea: `0x18002d870`
- end: `0x18002dced`
- name: `?SsdpMainStop@@YAXPEAXH@Z`
- size: `1149`
- prototype: `void __fastcall(struct ServiceContext *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x180027e20`

## callees

- `0x18000936c`
- `0x18000b03c`
- `0x180015d9c`
- `0x18002021c`
- `0x180022868`
- `0x18002735c`
- `0x180028000`
- `0x18002d818`
- `0x18002d870`
- `0x18002f1f8`
- `0x18002f680`
- `0x18002ff24`
- `0x180030130`
- `0x18003040c`
- `0x180031738`
- `0x180032184`
- `0x180032f2c`
- `0x180033af8`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002dcad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002dcad`
- `ntdll!EtwUnregisterTraceGuids` at `0x18002dcca`
- `ntdll!EtwUnregisterTraceGuids` at `0x18002dcca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002db29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002daf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002daf5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002dbd6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002dbd6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d912`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d912`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d91f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d91f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d900`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d900`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002dab6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18002dab6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002daa9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002daa9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002da9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002da9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d951`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002da25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d951`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002da25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dba8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002dc66`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002d938`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002d938`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d965`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002d965`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002db8f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002db8f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002dca4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18002dca4`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18002d9da`
- `POWRPROF!PowerSettingUnregisterNotification` at `0x18002d9da`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002d9bc`
- `IPHLPAPI!CancelMibChangeNotify2` at `0x18002d9bc`
- `WINHTTP!WinHttpCloseHandle` at `0x18002dc7f`
- `WINHTTP!WinHttpCloseHandle` at `0x18002dc7f`

## pseudocode

```c
void __fastcall SsdpMainStop(struct ServiceContext *a1)
{
  LPCSTR v2; // rcx
  void *v3; // rdx
  void (__fastcall *v4)(__int64 *); // rax
  DelayedLoadCryptoRandom *v5; // rdi
  __int64 v6; // rdx
  SERVICE_STATUS_HANDLE v7; // rcx
  LPCSTR v8; // rbx

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
    if ( *((_QWORD *)&xmmword_1800415D0 + 1) )
    {
      CloseHandle(*((HANDLE *)&xmmword_1800415D0 + 1));
      *((_QWORD *)&xmmword_1800415D0 + 1) = 0;
    }
    CSsdpServiceManager::HrRemoveServiceInternal(&CSsdpServiceManager::s_instance, 0, 1, 0, 1);
    CStaleWorkItemsTracking::HrShutdown(&CSsdpByebye::s_WorkItemTracking);
    CStaleWorkItemsTracking::HrShutdown(&CSsdpSearchResponse::s_WorkItemTracking);
    CSsdpSearchRequestManager::HrShutdown((char *)&CSsdpSearchRequestManager::s_instance);
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
    CTimerQueue::HrShutdown((struct _RTL_CRITICAL_SECTION *)CTimerQueue::s_instance, v3);
    CUPnPInterfaceList::HrShutdown(&CUPnPInterfaceList::s_instance);
    EnterCriticalSection(&stru_180041028);
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9c29e5a395c43598115319381ae1359a_Traceguids);
    LeaveCriticalSection(&stru_180041028);
    v4 = (void (__fastcall *)(__int64 *))qword_1800425A8;
    if ( qword_1800425B0 && qword_1800425A8 )
    {
      qword_1800425A8(&qword_1800425B0);
      v4 = (void (__fastcall *)(__int64 *))qword_1800425A8;
      qword_1800425B0 = 0;
    }
    if ( qword_180042598 && v4 )
    {
      v4(&qword_180042598);
      qword_180042598 = 0;
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
    if ( hLibModule )
    {
      qword_1800425F0 = 0;
      qword_1800425A8 = 0;
      qword_1800425D8 = 0;
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
    CleanupListNetwork();
    SocketFinish();
    if ( g_pEventHTTPListener )
      (**(void (__fastcall ***)(BaseHttpListener *, __int64))g_pEventHTTPListener)(g_pEventHTTPListener, 1);
    v5 = g_pRandomGenerator;
    g_pEventHTTPListener = 0;
    if ( g_pRandomGenerator )
    {
      DelayedLoadCryptoRandom::~DelayedLoadCryptoRandom(g_pRandomGenerator);
      operator delete(v5);
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
    v6 = *((_QWORD *)a1 + 3);
    if ( v6 )
    {
      v7 = (SERVICE_STATUS_HANDLE)*((_QWORD *)a1 + 2);
      *(_DWORD *)(v6 + 4) = 1;
      *(_QWORD *)(v6 + 20) = 0;
      SetServiceStatus(v7, (LPSERVICE_STATUS)v6);
    }
    free(a1);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control )
    {
      while ( v8 )
      {
        if ( *((_QWORD *)v8 + 1) )
        {
          EtwUnregisterTraceGuids();
          *((_QWORD *)v8 + 1) = 0;
        }
        v8 = *(LPCSTR *)v8;
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
0x18002d870  push    rbx
0x18002d872  push    rbp
0x18002d873  push    rdi
0x18002d874  push    r14
0x18002d876  sub     rsp, 38h
0x18002d87a  mov     rbx, rcx
0x18002d87d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d884  lea     r14, WPP_GLOBAL_Control
0x18002d88b  cmp     rcx, r14
0x18002d88e  jz      short loc_18002D8B2
0x18002d890  test    byte ptr [rcx+1Ch], 8
0x18002d894  jz      short loc_18002D8B2
0x18002d896  mov     rcx, [rcx+10h]
0x18002d89a  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002d8a1  mov     edx, 38h ; '8'
0x18002d8a6  call    WPP_SF_
0x18002d8ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d8b2  xor     ebp, ebp
0x18002d8b4  test    rbx, rbx
0x18002d8b7  jnz     short loc_18002D8E4
0x18002d8b9  cmp     rcx, r14
0x18002d8bc  jz      loc_18002DCE3
0x18002d8c2  test    byte ptr [rcx+1Ch], 1
0x18002d8c6  jz      loc_18002DCE3
0x18002d8cc  mov     rcx, [rcx+10h]
0x18002d8d0  lea     edx, [rbp+39h]
0x18002d8d3  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002d8da  call    WPP_SF_
0x18002d8df  jmp     loc_18002DCE3
0x18002d8e4  mov     rcx, rbx; struct ServiceContext *
0x18002d8e7  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002d8ec  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002d8f3  test    rcx, rcx
0x18002d8f6  jz      short loc_18002D92C
0x18002d8f8  xor     r9d, r9d; msWindowLength
0x18002d8fb  xor     r8d, r8d; msPeriod
0x18002d8fe  xor     edx, edx; pftDueTime
0x18002d900  call    cs:__imp_SetThreadpoolTimer
0x18002d906  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002d90d  mov     edx, 1; fCancelPendingCallbacks
0x18002d912  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002d918  mov     rcx, cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA; pti
0x18002d91f  call    cs:__imp_CloseThreadpoolTimer
0x18002d925  mov     cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA, rbp; _TP_TIMER * g_shutdownTimer
0x18002d92c  mov     rcx, cs:?g_hStopWait@@3PEAXEA; WaitHandle
0x18002d933  test    rcx, rcx
0x18002d936  jz      short loc_18002D945
0x18002d938  call    cs:__imp_UnregisterWait
0x18002d93e  mov     cs:?g_hStopWait@@3PEAXEA, rbp; void * g_hStopWait
0x18002d945  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hObject
0x18002d94c  test    rcx, rcx
0x18002d94f  jz      short loc_18002D96B
0x18002d951  call    cs:__imp_CloseHandle
0x18002d957  mov     cs:?g_hServiceStopEvent@@3PEAXEA, rbp; void * g_hServiceStopEvent
0x18002d95e  jmp     short loc_18002D96B
0x18002d960  mov     ecx, 0Ah; dwMilliseconds
0x18002d965  call    cs:__imp_Sleep
0x18002d96b  cmp     cs:?g_lCallbackCount@@3JA, ebp; long g_lCallbackCount
0x18002d971  jg      short loc_18002D960
0x18002d973  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d97a  cmp     rcx, r14
0x18002d97d  jz      short loc_18002D99A
0x18002d97f  test    byte ptr [rcx+1Ch], 8
0x18002d983  jz      short loc_18002D99A
0x18002d985  mov     rcx, [rcx+10h]
0x18002d989  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002d990  mov     edx, 3Ah ; ':'
0x18002d995  call    WPP_SF_
0x18002d99a  mov     rcx, rbx; struct ServiceContext *
0x18002d99d  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002d9a2  cmp     [rbx], ebp
0x18002d9a4  jz      short loc_18002D9AB
0x18002d9a6  call    ?RpcServerStop@@YAHXZ; RpcServerStop(void)
0x18002d9ab  cmp     [rbx+4], ebp
0x18002d9ae  jz      short loc_18002D9C9
0x18002d9b0  mov     rcx, cs:?g_hAddrChange@@3PEAXEA; NotificationHandle
0x18002d9b7  test    rcx, rcx
0x18002d9ba  jz      short loc_18002D9C9
0x18002d9bc  call    cs:__imp_CancelMibChangeNotify2
0x18002d9c2  mov     cs:?g_hAddrChange@@3PEAXEA, rbp; void * g_hAddrChange
0x18002d9c9  cmp     [rbx+8], ebp
0x18002d9cc  jz      short loc_18002D9E7
0x18002d9ce  mov     rcx, cs:?g_hNqmNotification@@3PEAXEA; RegistrationHandle
0x18002d9d5  test    rcx, rcx
0x18002d9d8  jz      short loc_18002D9E7
0x18002d9da  call    cs:__imp_PowerSettingUnregisterNotification
0x18002d9e0  mov     cs:?g_hNqmNotification@@3PEAXEA, rbp; void * g_hNqmNotification
0x18002d9e7  lea     rcx, ?s_instance@CReceiveDataManager@@0V1@A; lpCriticalSection
0x18002d9ee  call    ?HrShutdown@CReceiveDataManager@@QEAAJXZ; CReceiveDataManager::HrShutdown(void)
0x18002d9f3  lea     rcx, ?s_instance@CSsdpCacheEntryManager@@0V1@A; lpCriticalSection
0x18002d9fa  call    ?HrShutdown@CSsdpCacheEntryManager@@QEAAJXZ; CSsdpCacheEntryManager::HrShutdown(void)
0x18002d9ff  xor     r9d, r9d; void *
0x18002da02  mov     [rsp+58h+var_38], rbp; struct CSsdpNotifyRequest *
0x18002da07  xor     edx, edx; int
0x18002da09  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x18002da10  lea     r8d, [r9+1]; int
0x18002da14  call    ?HrRemoveInternal@CSsdpNotifyRequestManager@@AEAAJHHPEAXPEAVCSsdpNotifyRequest@@@Z; CSsdpNotifyRequestManager::HrRemoveInternal(int,int,void *,CSsdpNotifyRequest *)
0x18002da19  mov     rcx, qword ptr cs:xmmword_1800415D0+8; hObject
0x18002da20  test    rcx, rcx
0x18002da23  jz      short loc_18002DA32
0x18002da25  call    cs:__imp_CloseHandle
0x18002da2b  mov     qword ptr cs:xmmword_1800415D0+8, rbp
0x18002da32  xor     r9d, r9d; int
0x18002da35  mov     dword ptr [rsp+58h+var_38], 1; int
0x18002da3d  xor     edx, edx; struct CSsdpService *
0x18002da3f  lea     rcx, ?s_instance@CSsdpServiceManager@@0V1@A; lpCriticalSection
0x18002da46  lea     r8d, [r9+1]; int
0x18002da4a  call    ?HrRemoveServiceInternal@CSsdpServiceManager@@AEAAJPEAVCSsdpService@@HHH@Z; CSsdpServiceManager::HrRemoveServiceInternal(CSsdpService *,int,int,int)
0x18002da4f  lea     rcx, ?s_WorkItemTracking@CSsdpByebye@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18002da56  call    ?HrShutdown@CStaleWorkItemsTracking@@QEAAJXZ; CStaleWorkItemsTracking::HrShutdown(void)
0x18002da5b  lea     rcx, ?s_WorkItemTracking@CSsdpSearchResponse@@2VCStaleWorkItemsTracking@@A; lpCriticalSection
0x18002da62  call    ?HrShutdown@CStaleWorkItemsTracking@@QEAAJXZ; CStaleWorkItemsTracking::HrShutdown(void)
0x18002da67  lea     rcx, ?s_instance@CSsdpSearchRequestManager@@0V1@A; lpCriticalSection
0x18002da6e  call    ?HrShutdown@CSsdpSearchRequestManager@@QEAAJXZ; CSsdpSearchRequestManager::HrShutdown(void)
0x18002da73  lea     rcx, ?s_instance@CFirewallManager@@0V1@A; this
0x18002da7a  call    ?HrShutdown@CFirewallManager@@QEAAJXZ; CFirewallManager::HrShutdown(void)
0x18002da7f  mov     rcx, rbx; struct ServiceContext *
0x18002da82  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002da87  cmp     qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A, rbp; CWorkItem::_Threadpool_Environment CWorkItem::s_tpEnviron
0x18002da8e  jz      short loc_18002DACE
0x18002da90  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x18002da97  xor     r8d, r8d; pvCleanupContext
0x18002da9a  xor     edx, edx; fCancelPendingCallbacks
0x18002da9c  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002daa2  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A+8; ptpcg
0x18002daa9  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002daaf  mov     rcx, qword ptr cs:?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; ptpp
0x18002dab6  call    cs:__imp_CloseThreadpool
0x18002dabc  xor     edx, edx; Val
0x18002dabe  lea     rcx, ?s_tpEnviron@CWorkItem@@0U_Threadpool_Environment@1@A; void *
0x18002dac5  lea     r8d, [rdx+58h]; Size
0x18002dac9  call    memset_0
0x18002dace  mov     rcx, rbx; struct ServiceContext *
0x18002dad1  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18002dad6  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x18002dadd  call    ?HrShutdown@CTimerQueue@@QEAAJPEAX@Z; CTimerQueue::HrShutdown(void *)
0x18002dae2  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x18002dae9  call    ?HrShutdown@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrShutdown(void)
0x18002daee  lea     rcx, stru_180041028; lpCriticalSection
0x18002daf5  call    cs:__imp_EnterCriticalSection
0x18002dafb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db02  cmp     rcx, r14
0x18002db05  jz      short loc_18002DB22
0x18002db07  test    byte ptr [rcx+1Ch], 8
0x18002db0b  jz      short loc_18002DB22
0x18002db0d  mov     rcx, [rcx+10h]
0x18002db11  lea     r8, WPP_9c29e5a395c43598115319381ae1359a_Traceguids
0x18002db18  mov     edx, 0Dh
0x18002db1d  call    WPP_SF_
0x18002db22  lea     rcx, stru_180041028; lpCriticalSection
0x18002db29  call    cs:__imp_LeaveCriticalSection
0x18002db2f  cmp     cs:qword_1800425B0, rbp
0x18002db36  mov     rax, cs:qword_1800425A8
0x18002db3d  jz      short loc_18002DB5E
0x18002db3f  test    rax, rax
0x18002db42  jz      short loc_18002DB5E
0x18002db44  lea     rcx, qword_1800425B0
0x18002db4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db50  mov     rax, cs:qword_1800425A8
0x18002db57  mov     cs:qword_1800425B0, rbp
0x18002db5e  cmp     cs:qword_180042598, rbp
0x18002db65  jz      short loc_18002DB7F
0x18002db67  test    rax, rax
0x18002db6a  jz      short loc_18002DB7F
0x18002db6c  lea     rcx, qword_180042598
0x18002db73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002db78  mov     cs:qword_180042598, rbp
0x18002db7f  mov     rcx, cs:WaitHandle; WaitHandle
0x18002db86  test    rcx, rcx
0x18002db89  jz      short loc_18002DB9C
0x18002db8b  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002db8f  call    cs:__imp_UnregisterWaitEx
0x18002db95  mov     cs:WaitHandle, rbp
0x18002db9c  mov     rcx, cs:hObject; hObject
0x18002dba3  test    rcx, rcx
0x18002dba6  jz      short loc_18002DBB5
0x18002dba8  call    cs:__imp_CloseHandle
0x18002dbae  mov     cs:hObject, rbp
0x18002dbb5  mov     rcx, cs:hLibModule; hLibModule
0x18002dbbc  test    rcx, rcx
0x18002dbbf  jz      short loc_18002DBE3
0x18002dbc1  mov     cs:qword_1800425F0, rbp
0x18002dbc8  mov     cs:qword_1800425A8, rbp
0x18002dbcf  mov     cs:qword_1800425D8, rbp
0x18002dbd6  call    cs:__imp_FreeLibrary
0x18002dbdc  mov     cs:hLibModule, rbp
0x18002dbe3  call    ?CleanupListNetwork@@YAXH@Z; CleanupListNetwork(int)
0x18002dbe8  call    ?SocketFinish@@YAXXZ; SocketFinish(void)
0x18002dbed  mov     rcx, cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA; BaseHttpListener * g_pEventHTTPListener
0x18002dbf4  test    rcx, rcx
0x18002dbf7  jz      short loc_18002DC09
0x18002dbf9  mov     rax, [rcx]
0x18002dbfc  mov     edx, 1
0x18002dc01  mov     rax, [rax]
0x18002dc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc09  mov     rdi, cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18002dc10  mov     cs:?g_pEventHTTPListener@@3PEAVBaseHttpListener@@EA, rbp; BaseHttpListener * g_pEventHTTPListener
0x18002dc17  test    rdi, rdi
0x18002dc1a  jz      short loc_18002DC2C
0x18002dc1c  mov     rcx, rdi; this
0x18002dc1f  call    ??1DelayedLoadCryptoRandom@@QEAA@XZ; DelayedLoadCryptoRandom::~DelayedLoadCryptoRandom(void)
0x18002dc24  mov     rcx, rdi; void *
0x18002dc27  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002dc2c  mov     cs:?g_pRandomGenerator@@3PEAVDelayedLoadCryptoRandom@@EA, rbp; DelayedLoadCryptoRandom * g_pRandomGenerator
0x18002dc33  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dc3a  cmp     rcx, r14
0x18002dc3d  jz      short loc_18002DC5A
0x18002dc3f  test    byte ptr [rcx+1Ch], 8
0x18002dc43  jz      short loc_18002DC5A
0x18002dc45  mov     rcx, [rcx+10h]
0x18002dc49  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18002dc50  mov     edx, 3Bh ; ';'
0x18002dc55  call    WPP_SF_
0x18002dc5a  mov     rcx, cs:?ShutDownEvent@@3PEAXEA; hObject
0x18002dc61  test    rcx, rcx
0x18002dc64  jz      short loc_18002DC73
0x18002dc66  call    cs:__imp_CloseHandle
0x18002dc6c  mov     cs:?ShutDownEvent@@3PEAXEA, rbp; void * ShutDownEvent
0x18002dc73  mov     rcx, cs:?g_hInetSess@@3PEAXEA; hInternet
0x18002dc7a  test    rcx, rcx
0x18002dc7d  jz      short loc_18002DC8C
0x18002dc7f  call    cs:__imp_WinHttpCloseHandle
0x18002dc85  mov     cs:?g_hInetSess@@3PEAXEA, rbp; void * g_hInetSess
0x18002dc8c  mov     rdx, [rbx+18h]; lpServiceStatus
0x18002dc90  test    rdx, rdx
0x18002dc93  jz      short loc_18002DCAA
0x18002dc95  mov     rcx, [rbx+10h]; hServiceStatus
0x18002dc99  mov     dword ptr [rdx+4], 1
0x18002dca0  mov     [rdx+14h], rbp
0x18002dca4  call    cs:__imp_SetServiceStatus
0x18002dcaa  mov     rcx, rbx; Block
0x18002dcad  call    cs:__imp_free
0x18002dcb3  mov     rbx, cs:WPP_GLOBAL_Control
0x18002dcba  cmp     rbx, r14
0x18002dcbd  jz      short loc_18002DCE3
0x18002dcbf  jmp     short loc_18002DCD7
0x18002dcc1  mov     rcx, [rbx+8]
0x18002dcc5  test    rcx, rcx
0x18002dcc8  jz      short loc_18002DCD4
0x18002dcca  call    cs:__imp_EtwUnregisterTraceGuids
0x18002dcd0  mov     [rbx+8], rbp
0x18002dcd4  mov     rbx, [rbx]
0x18002dcd7  test    rbx, rbx
0x18002dcda  jnz     short loc_18002DCC1
0x18002dcdc  mov     cs:WPP_GLOBAL_Control, r14
0x18002dce3  add     rsp, 38h
0x18002dce7  pop     r14
0x18002dce9  pop     rdi
0x18002dcea  pop     rbp
0x18002dceb  pop     rbx
0x18002dcec  retn
```
