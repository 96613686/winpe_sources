# StartObjectExporter

- ea: `0x1800ba878`
- end: `0x1800bb49f`
- name: `StartObjectExporter`
- size: `3111`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b7d10`

## callees

- `0x1800015d8`
- `0x18000b310`
- `0x180034540`
- `0x180065240`
- `0x18007cf74`
- `0x18007e3d4`
- `0x180086db8`
- `0x180088670`
- `0x180088d3c`
- `0x1800989b0`
- `0x1800a1e98`
- `0x1800b27e0`
- `0x1800b2bb0`
- `0x1800b3110`
- `0x1800b3128`
- `0x1800b37ec`
- `0x1800b6a88`
- `0x1800b6f10`
- `0x1800ba428`
- `0x1800ba4a0`
- `0x1800ba508`
- `0x1800ba558`
- `0x1800ba588`
- `0x1800ba5ac`
- `0x1800ba878`
- `0x1800bba44`
- `0x1800bfddc`
- `0x1800c41c4`

## import_xrefs

- `ntdll!RtlInitializeCriticalSection` at `0x1800ba9f6`
- `ntdll!RtlInitializeCriticalSection` at `0x1800ba9f6`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800bb247`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800bb2d4`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800bb247`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800bb2d4`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800bb343`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800bb3bf`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800bb343`
- `RPCRT4!RpcServerRegisterIfEx` at `0x1800bb3bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba9a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba8d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba951`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba9a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb420`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bb420`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb017`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb1cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb42e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb017`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb100`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb1cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bb42e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ba9c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baa14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baa5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baaaf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baaff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bab47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bab94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800babe7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bac34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bac81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bacd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bad33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bad85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800badb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bae0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bae35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bae5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bafb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb03f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb16b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ba9c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baa14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baa5e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baaaf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800baaff`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bab47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bab94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800babe7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bac34`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bac81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bacd3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bad33`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bad85`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800badb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bae0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bae35`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bae5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bafb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb03f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb16b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bb08f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800bb08f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800ba9e2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800ba9e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ba8a4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ba8a4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ba921`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ba96b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ba921`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800ba96b`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800baf89`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800bb2a3`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800bb43d`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800baf89`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800bb2a3`
- `ext-ms-win-core-winrt-remote-l1-1-0!RemoteWinRTActivation` at `0x1800bb43d`

## string_xrefs

- `0x1800ba8fd`: `onecore\com\combase\rpcss\objex\objex.cxx`
- `0x1800bb0e4`: `onecore\com\combase\rpcss\objex\objex.cxx`
- `0x1800bb28a`: `onecore\com\combase\rpcss\objex\objex.cxx`
- `0x1800bb317`: `onecore\com\combase\rpcss\objex\objex.cxx`
- `0x1800bb386`: `onecore\com\combase\rpcss\objex\objex.cxx`
- `0x1800bb3cf`: `onecore\com\combase\rpcss\objex\objex.cxx`
- `0x1800bb06a`: `DCOM Protocols`

## pseudocode

```c
NTSTATUS StartObjectExporter()
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  int v2; // r8d
  NTSTATUS result; // eax
  RTL_SRWLOCK *v4; // rax
  struct CTaskThreadStateList *v5; // rbx
  CPingSetQuotaManager *v6; // rax
  struct CPingSetQuotaManager *v7; // rax
  struct CPingSetQuotaManager *v8; // rdi
  DWORD v9; // ebx
  ObjexHashTable::CHashTable *v10; // rax
  unsigned int v11; // edx
  ObjexHashTable::CHashTable *v12; // rax
  ObjexHashTable::CHashTable *v13; // rax
  unsigned int v14; // edx
  ObjexHashTable::CHashTable *v15; // rax
  CServerSetTable *v16; // rax
  CServerSetTable *v17; // rax
  ObjexHashTable::CHashTable *v18; // rax
  unsigned int v19; // edx
  ObjexHashTable::CHashTable *v20; // rax
  ObjexHashTable::CHashTable *v21; // rax
  unsigned int v22; // edx
  ObjexHashTable::CHashTable *v23; // rax
  ObjexHashTable::CHashTable *v24; // rax
  unsigned int v25; // edx
  ObjexHashTable::CHashTable *v26; // rax
  ObjexHashTable::CHashTable *v27; // rax
  unsigned int v28; // edx
  ObjexHashTable::CHashTable *v29; // rax
  CPList *v30; // rax
  unsigned int v31; // edx
  CPList *v32; // rax
  CPList *v33; // rax
  CPList *v34; // rdi
  CPList *v35; // rax
  unsigned int v36; // edx
  CPList *v37; // rax
  CBList *v38; // rax
  struct CBList *v39; // rax
  ObjexHashTable::CHashTable *v40; // rax
  CGuidTable *v41; // rdi
  _QWORD *v42; // rax
  _QWORD *v43; // rax
  CPingSetQuotaManager *v44; // rax
  __int64 v45; // rcx
  struct CRpcSecurityCallbackManager *v46; // rax
  WCHAR *v47; // r11
  DWORD v48; // ebx
  LPCWSTR v49; // r11
  SIZE_T v50; // r14
  WCHAR *v51; // rax
  WCHAR *v52; // rsi
  LSTATUS ValueW; // eax
  LSTATUS v54; // r8d
  int v55; // r14d
  unsigned __int64 v56; // r14
  SIZE_T v57; // r15
  unsigned __int16 *v58; // rax
  unsigned __int16 *v59; // rsi
  WCHAR *v60; // r8
  wchar_t *v61; // rcx
  __int64 v62; // rcx
  __int64 Sd; // rax
  void *v64; // rsi
  __int64 v65; // rcx
  int v66; // r8d
  int v67; // r8d
  RPC_STATUS v68; // ebx
  unsigned int v69; // eax
  int v70; // ecx
  int v71; // r8d
  int v72; // r9d
  HANDLE ProcessHeap; // rax
  __int64 v74; // rcx
  CSuspendMonitor *v75; // rcx
  unsigned int pdwType; // [rsp+20h] [rbp-58h]
  PVOID pvData; // [rsp+28h] [rbp-50h]
  PVOID pvDataa; // [rsp+28h] [rbp-50h]
  PVOID pvDatab; // [rsp+28h] [rbp-50h]
  PVOID pvDatac; // [rsp+28h] [rbp-50h]
  DWORD pcbData; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v82[30]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  EventW = CreateEventW(0, 0, 0, 0);
  gWorkerThreadWaitEvent = EventW;
  if ( !EventW )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return GetLastError();
    LastError = GetLastError();
    v2 = 1152;
LABEL_6:
    ComTraceMessageT<int>(
      (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\objex.cxx",
      (unsigned int)"StartObjectExporter",
      v2,
      0,
      (__int64)L"%!WINERROR!",
      LastError);
    return GetLastError();
  }
  gWorkerThreadTimer = CreateThreadpoolTimer(TaskOrWorkerThreadTimerCallback, EventW, 0);
  if ( !gWorkerThreadTimer )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return GetLastError();
    LastError = GetLastError();
    v2 = 1159;
    goto LABEL_6;
  }
  gLowPowerEpochExitTimer = CreateThreadpoolTimer(LowPowerEpochExitTimerCallback, 0, 0);
  if ( !gLowPowerEpochExitTimer )
  {
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      return GetLastError();
    LastError = GetLastError();
    v2 = 1166;
    goto LABEL_6;
  }
  v4 = (RTL_SRWLOCK *)HeapAlloc(g_hHeap, 0, 0x18u);
  v5 = (struct CTaskThreadStateList *)v4;
  if ( !v4 )
  {
    gTaskThreadStateList = 0;
    return 14;
  }
  v4->Ptr = 0;
  v4[1].Ptr = 0;
  InitializeSRWLock(v4 + 2);
  gTaskThreadStateList = v5;
  result = RtlInitializeCriticalSection(&gcsFastProcessLock);
  if ( result < 0 )
    return result;
  pcbData = 0;
  v6 = (CPingSetQuotaManager *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( !v6 )
  {
    gpPingSetQuotaManager = 0;
    goto LABEL_188;
  }
  v7 = CPingSetQuotaManager::CPingSetQuotaManager(v6, (int *)&pcbData);
  gpPingSetQuotaManager = v7;
  v8 = v7;
  if ( !v7 )
  {
LABEL_188:
    gpPingSetQuotaManager = 0;
    return 14;
  }
  v9 = pcbData;
  if ( pcbData )
  {
    CPingSetQuotaManager::~CPingSetQuotaManager(v7);
    operator delete(v8, 0x18u);
    goto LABEL_188;
  }
  ComputeSecurity();
  v10 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v10 )
  {
    v12 = (ObjexHashTable::CHashTable *)ObjexHashTable::CHashTable::CHashTable(v10, (int *)&pcbData, 0x10u);
    v9 = pcbData;
  }
  else
  {
    v12 = 0;
  }
  gpServerOxidTable = v12;
  if ( v9 )
  {
    if ( v12 )
      ObjexHashTable::CHashTable::`scalar deleting destructor'(v12, v11);
    gpServerOxidTable = 0;
  }
  v13 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v13 )
  {
    v15 = (ObjexHashTable::CHashTable *)ObjexHashTable::CHashTable::CHashTable(v13, (int *)&pcbData, 0xB0u);
    v9 = pcbData;
  }
  else
  {
    v15 = 0;
  }
  gpServerOidTable = v15;
  if ( v9 )
  {
    if ( v15 )
      ObjexHashTable::CHashTable::`scalar deleting destructor'(v15, v14);
    gpServerOidTable = 0;
  }
  v16 = (CServerSetTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v16 )
  {
    v17 = CServerSetTable::CServerSetTable(v16, (int *)&pcbData);
    v9 = pcbData;
  }
  else
  {
    v17 = 0;
  }
  gpServerSetTable = v17;
  if ( v9 )
  {
    operator delete(v17, 0x18u);
    gpServerSetTable = 0;
  }
  v18 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v18 )
  {
    v20 = (ObjexHashTable::CHashTable *)ObjexHashTable::CHashTable::CHashTable(v18, (int *)&pcbData, 0x10u);
    v9 = pcbData;
  }
  else
  {
    v20 = 0;
  }
  gpClientOxidTable = v20;
  if ( v9 )
  {
    if ( v20 )
      ObjexHashTable::CHashTable::`scalar deleting destructor'(v20, v19);
    gpClientOxidTable = 0;
  }
  v21 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v21 )
  {
    v23 = (ObjexHashTable::CHashTable *)ObjexHashTable::CHashTable::CHashTable(v21, (int *)&pcbData, 0x40u);
    v9 = pcbData;
  }
  else
  {
    v23 = 0;
  }
  gpClientOidTable = v23;
  if ( v9 )
  {
    if ( v23 )
      ObjexHashTable::CHashTable::`scalar deleting destructor'(v23, v22);
    gpClientOidTable = 0;
  }
  v24 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v24 )
  {
    v26 = (ObjexHashTable::CHashTable *)ObjexHashTable::CHashTable::CHashTable(v24, (int *)&pcbData, 0x10u);
    v9 = pcbData;
  }
  else
  {
    v26 = 0;
  }
  gpClientSetTable = v26;
  if ( v9 )
  {
    if ( v26 )
      ObjexHashTable::CHashTable::`scalar deleting destructor'(v26, v25);
    gpClientSetTable = 0;
  }
  v27 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v27 )
  {
    v29 = (ObjexHashTable::CHashTable *)ObjexHashTable::CHashTable::CHashTable(v27, (int *)&pcbData, 0x10u);
    v9 = pcbData;
  }
  else
  {
    v29 = 0;
  }
  gpMidTable = v29;
  if ( v9 )
  {
    if ( v29 )
      ObjexHashTable::CHashTable::`scalar deleting destructor'(v29, v28);
    gpMidTable = 0;
  }
  v30 = (CPList *)HeapAlloc(g_hHeap, 0, 0x40u);
  if ( v30 )
  {
    v32 = CPList::CPList(v30, (int *)&pcbData, g_usBasePingInterval);
    v9 = pcbData;
  }
  else
  {
    v32 = 0;
  }
  gpClientOxidPList = v32;
  if ( v9 )
  {
    if ( v32 )
      CPList::`scalar deleting destructor'(v32, v31);
    gpClientOxidPList = 0;
  }
  v33 = (CPList *)HeapAlloc(g_hHeap, 0, 0x40u);
  v34 = v33;
  if ( v33 )
  {
    CPList::CPList(v33, (int *)&pcbData, g_usBaseTimeoutInterval);
    v9 = pcbData;
  }
  else
  {
    v34 = 0;
  }
  gpServerOidPList = v34;
  if ( v9 )
  {
    if ( v34 )
    {
      CPList::~CPList(v34);
      operator delete(v34, 0x40u);
    }
    gpServerOidPList = 0;
  }
  v35 = (CPList *)HeapAlloc(g_hHeap, 0, 0x40u);
  if ( v35 )
  {
    v37 = CPList::CPList(v35, (int *)&pcbData, g_usBasePingInterval);
    v9 = pcbData;
  }
  else
  {
    v37 = 0;
  }
  gpClientSetRemotePList = v37;
  if ( v9 )
  {
    if ( v37 )
      CPList::`scalar deleting destructor'(v37, v36);
    gpClientSetRemotePList = 0;
  }
  v38 = (CBList *)HeapAlloc(g_hHeap, 0, 0x10u);
  if ( v38 )
    v39 = CBList::CBList(v38, 0x80u);
  else
    v39 = 0;
  gpProcessList = v39;
  v40 = (ObjexHashTable::CHashTable *)HeapAlloc(g_hHeap, 0, 0x18u);
  v41 = v40;
  if ( v40 )
  {
    ObjexHashTable::CHashTable::CHashTable(v40, (int *)&pcbData, 0x20u);
    v9 = pcbData;
  }
  else
  {
    v41 = 0;
  }
  gpProcessIdTable = v41;
  if ( v9 )
  {
    if ( v41 )
      operator delete(v41, 0x18u);
    gpProcessIdTable = 0;
  }
  v42 = HeapAlloc(g_hHeap, 0, 0x10u);
  if ( v42 )
  {
    *v42 = 0;
    v42[1] = 0;
  }
  else
  {
    v42 = 0;
  }
  gpServerPinnedOidList = (__int64)v42;
  v43 = HeapAlloc(g_hHeap, 0, 0x10u);
  if ( v43 )
  {
    *v43 = 0;
    v43[1] = 0;
  }
  else
  {
    v43 = 0;
  }
  gpFastRundownOidList = (__int64)v43;
  v44 = (CPingSetQuotaManager *)HeapAlloc(g_hHeap, 0, 0x18u);
  if ( v44 )
  {
    v46 = CPingSetQuotaManager::CPingSetQuotaManager(v44, (int *)&pcbData);
    v9 = pcbData;
  }
  else
  {
    v46 = 0;
  }
  gpCRpcSecurityCallbackMgr = v46;
  if ( v9 )
  {
    if ( v46 )
      operator delete(v46, 0x18u);
    gpCRpcSecurityCallbackMgr = 0;
    return 14;
  }
  if ( !gpServerOxidTable
    || !gpClientOxidTable
    || !gpClientOxidPList
    || !gpServerOidTable
    || !gpServerOidPList
    || !gpClientOidTable
    || !gpMidTable
    || !gpServerSetTable
    || !gpClientSetTable
    || !gpClientSetRemotePList
    || !gpTokenList
    || !gpProcessList
    || !gpProcessIdTable
    || !gpServerPinnedOidList
    || !v46
    || !gpFastRundownOidList )
  {
    return 14;
  }
  if ( !(unsigned __int8)IsWinRTPerMachineSingleInstancingPresent(v45) || (unsigned int)RemoteWinRTActivation() != 1 )
  {
    pcbData = 118;
    while ( 1 )
    {
      HeapFree(g_hHeap, 0, (LPVOID)gpwstrProtseqs);
      v48 = (pcbData + 1) >> 1;
      v50 = 2LL * v48;
      if ( !is_mul_ok(v48, 2u) )
        v50 = -1;
      v51 = (WCHAR *)HeapAlloc(g_hHeap, 0, v50);
      v52 = v51;
      if ( !v51 )
        goto LABEL_134;
      memset_0(v51, 0, v50);
      gpwstrProtseqs = v52;
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Rpc", L"DCOM Protocols", 0x20u, 0, v52, &pcbData);
      v54 = ValueW;
      if ( ValueW != 234 )
      {
        if ( ValueW )
        {
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
          {
            LODWORD(pvData) = v54;
            ComTraceMessageT<long>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\objex.cxx",
              (unsigned int)"StartObjectExporter",
              1369,
              0,
              (__int64)L"%!WINERROR!",
              pvData);
          }
          HeapFree(g_hHeap, 0, (LPVOID)gpwstrProtseqs);
          v49 = 0;
          gpwstrProtseqs = 0;
          v48 = 0;
        }
        else
        {
          v49 = gpwstrProtseqs;
        }
        goto LABEL_147;
      }
    }
  }
  *(_OWORD *)v82 = *(_OWORD *)L"ncacn_np";
  *(_WORD *)&v82[16] = aNcacnNp_0[8];
  v47 = (WCHAR *)HeapAlloc(g_hHeap, 0, 0x14u);
  if ( !v47 )
  {
LABEL_134:
    gpwstrProtseqs = 0;
    return 14;
  }
  gpwstrProtseqs = v47;
  v48 = 10;
  *(_OWORD *)v47 = 0;
  *((_DWORD *)v47 + 4) = 0;
  StringCchCopyW(v47, 0xAu, (const unsigned __int16 *)v82);
  *((_WORD *)v49 + 9) = 0;
LABEL_147:
  if ( s_fEnableContainerDCOM )
  {
    v55 = v48;
    if ( !v49 )
      v55 = 1;
    *(_OWORD *)v82 = *(_OWORD *)L"ncacn_hvsocket";
    v56 = (unsigned int)(v55 + 15);
    *(_OWORD *)&v82[14] = *(_OWORD *)L"vsocket";
    v57 = 2 * v56;
    if ( !is_mul_ok(v56, 2u) )
      v57 = -1;
    v58 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v57);
    v59 = v58;
    if ( !v58 )
      return 14;
    memset_0(v58, 0, v57);
    StringCchCopyW(v59, (unsigned int)v56, (const unsigned __int16 *)v82);
    v60 = (WCHAR *)gpwstrProtseqs;
    v61 = v59 + 15;
    if ( gpwstrProtseqs )
    {
      o_wmemcpy_s_0(v61, v56 - 15, gpwstrProtseqs, v48);
      v60 = (WCHAR *)gpwstrProtseqs;
    }
    else
    {
      *v61 = 0;
    }
    HeapFree(g_hHeap, 0, v60);
    gpwstrProtseqs = v59;
  }
  result = UseProtseqIfNecessary(16);
  if ( !result )
  {
    RegisterAuthInfoIfNecessary();
    result = StartListeningIfNecessary();
    if ( !result )
    {
      LOBYTE(v62) = 1;
      Sd = CreateSd(v62);
      v64 = (void *)Sd;
      if ( Sd )
      {
        v66 = RpcServerRegisterIf3(qword_180113450, 0, 0, 32, 1234, 0, LocalInterfaceOnlySecCallback, Sd);
        if ( v66 )
        {
          v65 = (unsigned int)dword_18014E4B8;
          if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
          {
            LODWORD(pvDataa) = v66;
            ComTraceMessageT<long>(
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\objex.cxx",
              (unsigned int)"StartObjectExporter",
              1453,
              0,
              (__int64)L"%!WINERROR!",
              pvDataa);
          }
        }
        if ( (unsigned __int8)IsWinRTPerMachineSingleInstancingPresent(v65) )
        {
          if ( (unsigned int)RemoteWinRTActivation() == 1 )
          {
            v67 = RpcServerRegisterIf3(qword_180113520, 0, 0, 32, 1, 0, LocalInterfaceOnlySecCallback, v64);
            if ( v67 )
            {
              if ( dword_18014E4B8
                || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled((unsigned int)dword_18014E4B8) )
              {
                LODWORD(pvDatab) = v67;
                ComTraceMessageT<long>(
                  (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\objex.cxx",
                  (unsigned int)"StartObjectExporter",
                  1470,
                  0,
                  (__int64)L"%!WINERROR!",
                  pvDatab);
              }
            }
          }
        }
        v68 = RpcServerRegisterIfEx(qword_180113240, 0, 0, 0x10u, 0x4D2u, IObjectExporterSecCallback);
        if ( v68 && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
        {
          LODWORD(pvDatac) = v68;
          ComTraceMessageT<long>(
            (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\objex.cxx",
            (unsigned int)"StartObjectExporter",
            1484,
            0,
            (__int64)L"%!WINERROR!",
            pvDatac);
        }
        if ( s_fEnableContainerDCOM )
        {
          v69 = RpcServerRegisterIfEx(qword_1801135D0, 0, 0, 0x10u, 0x4D2u, CrossContainerObjectResolverSecCallback);
          v68 = v69;
          if ( v69 )
          {
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x5DE,
              (unsigned int)"onecore\\com\\combase\\rpcss\\objex\\objex.cxx",
              (const char *)v69,
              pdwType);
            if ( (unsigned int)dword_18014E4B8 > 2 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_18014E4B8, 0x400000000000LL) )
              {
                pcbData = v68;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  v70,
                  (unsigned int)word_18013EBFA,
                  v71,
                  v72,
                  (__int64)&pcbData);
              }
            }
          }
        }
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v64);
        if ( (unsigned __int8)IsWinRTPerMachineSingleInstancingPresent(v74)
          && (unsigned int)RemoteWinRTActivation() == 1 )
        {
          CSuspendMonitor::Start(v75);
        }
        return v68;
      }
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800ba878  push    rbp
0x1800ba87a  push    rbx
0x1800ba87b  push    rsi
0x1800ba87c  push    rdi
0x1800ba87d  push    r12
0x1800ba87f  push    r13
0x1800ba881  push    r14
0x1800ba883  push    r15
0x1800ba885  mov     rbp, rsp
0x1800ba888  sub     rsp, 78h
0x1800ba88c  mov     rax, cs:__security_cookie
0x1800ba893  xor     rax, rsp
0x1800ba896  mov     [rbp+var_10], rax
0x1800ba89a  xor     r9d, r9d; lpName
0x1800ba89d  xor     r8d, r8d; bInitialState
0x1800ba8a0  xor     edx, edx; bManualReset
0x1800ba8a2  xor     ecx, ecx; lpEventAttributes
0x1800ba8a4  call    cs:__imp_CreateEventW
0x1800ba8aa  xor     r12d, r12d
0x1800ba8ad  mov     cs:gWorkerThreadWaitEvent, rax
0x1800ba8b4  test    rax, rax
0x1800ba8b7  jnz     short loc_1800BA914
0x1800ba8b9  mov     eax, cs:dword_18014E4B8
0x1800ba8bf  test    eax, eax
0x1800ba8c1  jnz     short loc_1800BA8D7
0x1800ba8c3  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800ba8ca  jz      short loc_1800BA909
0x1800ba8cc  xor     ecx, ecx
0x1800ba8ce  call    IsWppLevelEnabled
0x1800ba8d3  test    al, al
0x1800ba8d5  jz      short loc_1800BA909
0x1800ba8d7  call    cs:__imp_GetLastError
0x1800ba8dd  mov     r8d, 480h
0x1800ba8e3  mov     dword ptr [rsp+78h+pvData], eax
0x1800ba8e7  lea     rdi, aWinerror; "%!WINERROR!"
0x1800ba8ee  xor     r9d, r9d
0x1800ba8f1  mov     [rsp+78h+pdwType], rdi
0x1800ba8f6  lea     rdx, aStartobjectexp; "StartObjectExporter"
0x1800ba8fd  lea     rcx, aOnecoreComComb_8; "onecore\\com\\combase\\rpcss\\objex\\ob"...
0x1800ba904  call    ??$ComTraceMessageT@H@@YAXPEBD0HW4TraceLevel@@PEBGH@Z; ComTraceMessageT<int>(char const *,char const *,int,TraceLevel,ushort const *,int)
0x1800ba909  call    cs:__imp_GetLastError
0x1800ba90f  jmp     loc_1800BB482
0x1800ba914  xor     r8d, r8d; pcbe
0x1800ba917  lea     rcx, ?TaskOrWorkerThreadTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800ba91e  mov     rdx, rax; pv
0x1800ba921  call    cs:__imp_CreateThreadpoolTimer
0x1800ba927  mov     cs:gWorkerThreadTimer, rax
0x1800ba92e  test    rax, rax
0x1800ba931  jnz     short loc_1800BA95F
0x1800ba933  mov     eax, cs:dword_18014E4B8
0x1800ba939  test    eax, eax
0x1800ba93b  jnz     short loc_1800BA951
0x1800ba93d  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800ba944  jz      short loc_1800BA909
0x1800ba946  xor     ecx, ecx
0x1800ba948  call    IsWppLevelEnabled
0x1800ba94d  test    al, al
0x1800ba94f  jz      short loc_1800BA909
0x1800ba951  call    cs:__imp_GetLastError
0x1800ba957  mov     r8d, 487h
0x1800ba95d  jmp     short loc_1800BA8E3
0x1800ba95f  xor     r8d, r8d; pcbe
0x1800ba962  lea     rcx, ?LowPowerEpochExitTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800ba969  xor     edx, edx; pv
0x1800ba96b  call    cs:__imp_CreateThreadpoolTimer
0x1800ba971  mov     cs:gLowPowerEpochExitTimer, rax
0x1800ba978  test    rax, rax
0x1800ba97b  jnz     short loc_1800BA9B4
0x1800ba97d  mov     eax, cs:dword_18014E4B8
0x1800ba983  test    eax, eax
0x1800ba985  jnz     short loc_1800BA9A3
0x1800ba987  cmp     cs:?gfEnableTracing@@3HA, r12d; int gfEnableTracing
0x1800ba98e  jz      loc_1800BA909
0x1800ba994  xor     ecx, ecx
0x1800ba996  call    IsWppLevelEnabled
0x1800ba99b  test    al, al
0x1800ba99d  jz      loc_1800BA909
0x1800ba9a3  call    cs:__imp_GetLastError
0x1800ba9a9  mov     r8d, 48Eh
0x1800ba9af  jmp     loc_1800BA8E3
0x1800ba9b4  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800ba9bb  mov     esi, 18h
0x1800ba9c0  mov     r8d, esi; dwBytes
0x1800ba9c3  xor     edx, edx; dwFlags
0x1800ba9c5  call    cs:__imp_HeapAlloc
0x1800ba9cb  mov     rbx, rax
0x1800ba9ce  test    rax, rax
0x1800ba9d1  jz      loc_1800BB476
0x1800ba9d7  lea     rcx, [rax+10h]; SRWLock
0x1800ba9db  mov     [rax], r12
0x1800ba9de  mov     [rax+8], r12
0x1800ba9e2  call    cs:__imp_InitializeSRWLock
0x1800ba9e8  lea     rcx, ?gcsFastProcessLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800ba9ef  mov     cs:?gTaskThreadStateList@@3PEAVCTaskThreadStateList@@EA, rbx; CTaskThreadStateList * gTaskThreadStateList
0x1800ba9f6  call    cs:__imp_RtlInitializeCriticalSection
0x1800ba9fc  test    eax, eax
0x1800ba9fe  js      loc_1800BB482
0x1800baa04  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800baa0b  mov     r8d, esi; dwBytes
0x1800baa0e  xor     edx, edx; dwFlags
0x1800baa10  mov     [rbp+var_38], r12d
0x1800baa14  call    cs:__imp_HeapAlloc
0x1800baa1a  test    rax, rax
0x1800baa1d  jz      loc_1800BB466
0x1800baa23  lea     rdx, [rbp+var_38]; int *
0x1800baa27  mov     rcx, rax; this
0x1800baa2a  call    ??0CPingSetQuotaManager@@QEAA@AEAJ@Z; CPingSetQuotaManager::CPingSetQuotaManager(long &)
0x1800baa2f  mov     cs:?gpPingSetQuotaManager@@3PEAVCPingSetQuotaManager@@EA, rax; CPingSetQuotaManager * gpPingSetQuotaManager
0x1800baa36  mov     rdi, rax
0x1800baa39  test    rax, rax
0x1800baa3c  jz      loc_1800BB46D
0x1800baa42  mov     ebx, [rbp+var_38]
0x1800baa45  test    ebx, ebx
0x1800baa47  jnz     loc_1800BB451
0x1800baa4d  call    ComputeSecurity
0x1800baa52  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800baa59  mov     r8d, esi; dwBytes
0x1800baa5c  xor     edx, edx; dwFlags
0x1800baa5e  call    cs:__imp_HeapAlloc
0x1800baa64  lea     r13d, [rsi-8]
0x1800baa68  test    rax, rax
0x1800baa6b  jz      short loc_1800BAA81
0x1800baa6d  mov     r8d, r13d; unsigned int
0x1800baa70  lea     rdx, [rbp+var_38]; int *
0x1800baa74  mov     rcx, rax; this
0x1800baa77  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800baa7c  mov     ebx, [rbp+var_38]
0x1800baa7f  jmp     short loc_1800BAA84
0x1800baa81  mov     rax, r12
0x1800baa84  mov     cs:?gpServerOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA, rax; ObjexHashTable::CHashTable * gpServerOxidTable
0x1800baa8b  test    ebx, ebx
0x1800baa8d  jz      short loc_1800BAAA3
0x1800baa8f  test    rax, rax
0x1800baa92  jz      short loc_1800BAA9C
0x1800baa94  mov     rcx, rax; this
0x1800baa97  call    ??_GCHashTable@ObjexHashTable@@QEAAPEAXI@Z; ObjexHashTable::CHashTable::`scalar deleting destructor'(uint)
0x1800baa9c  mov     cs:?gpServerOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA, r12; ObjexHashTable::CHashTable * gpServerOxidTable
0x1800baaa3  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800baaaa  mov     r8, rsi; dwBytes
0x1800baaad  xor     edx, edx; dwFlags
0x1800baaaf  call    cs:__imp_HeapAlloc
0x1800baab5  test    rax, rax
0x1800baab8  jz      short loc_1800BAAD1
0x1800baaba  mov     r8d, 0B0h; unsigned int
0x1800baac0  lea     rdx, [rbp+var_38]; int *
0x1800baac4  mov     rcx, rax; this
0x1800baac7  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800baacc  mov     ebx, [rbp+var_38]
0x1800baacf  jmp     short loc_1800BAAD4
0x1800baad1  mov     rax, r12
0x1800baad4  mov     cs:?gpServerOidTable@@3PEAVCHashTable@ObjexHashTable@@EA, rax; ObjexHashTable::CHashTable * gpServerOidTable
0x1800baadb  test    ebx, ebx
0x1800baadd  jz      short loc_1800BAAF3
0x1800baadf  test    rax, rax
0x1800baae2  jz      short loc_1800BAAEC
0x1800baae4  mov     rcx, rax; this
0x1800baae7  call    ??_GCHashTable@ObjexHashTable@@QEAAPEAXI@Z; ObjexHashTable::CHashTable::`scalar deleting destructor'(uint)
0x1800baaec  mov     cs:?gpServerOidTable@@3PEAVCHashTable@ObjexHashTable@@EA, r12; ObjexHashTable::CHashTable * gpServerOidTable
0x1800baaf3  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800baafa  mov     r8, rsi; dwBytes
0x1800baafd  xor     edx, edx; dwFlags
0x1800baaff  call    cs:__imp_HeapAlloc
0x1800bab05  test    rax, rax
0x1800bab08  jz      short loc_1800BAB1B
0x1800bab0a  lea     rdx, [rbp+var_38]; int *
0x1800bab0e  mov     rcx, rax; this
0x1800bab11  call    ??0CServerSetTable@@QEAA@AEAJ@Z; CServerSetTable::CServerSetTable(long &)
0x1800bab16  mov     ebx, [rbp+var_38]
0x1800bab19  jmp     short loc_1800BAB1E
0x1800bab1b  mov     rax, r12
0x1800bab1e  mov     cs:?gpServerSetTable@@3PEAVCServerSetTable@@EA, rax; CServerSetTable * gpServerSetTable
0x1800bab25  test    ebx, ebx
0x1800bab27  jz      short loc_1800BAB3B
0x1800bab29  mov     rdx, rsi; unsigned __int64
0x1800bab2c  mov     rcx, rax; void *
0x1800bab2f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800bab34  mov     cs:?gpServerSetTable@@3PEAVCServerSetTable@@EA, r12; CServerSetTable * gpServerSetTable
0x1800bab3b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800bab42  mov     r8, rsi; dwBytes
0x1800bab45  xor     edx, edx; dwFlags
0x1800bab47  call    cs:__imp_HeapAlloc
0x1800bab4d  test    rax, rax
0x1800bab50  jz      short loc_1800BAB66
0x1800bab52  mov     r8d, r13d; unsigned int
0x1800bab55  lea     rdx, [rbp+var_38]; int *
0x1800bab59  mov     rcx, rax; this
0x1800bab5c  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800bab61  mov     ebx, [rbp+var_38]
0x1800bab64  jmp     short loc_1800BAB69
0x1800bab66  mov     rax, r12
0x1800bab69  mov     cs:?gpClientOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA, rax; ObjexHashTable::CHashTable * gpClientOxidTable
0x1800bab70  test    ebx, ebx
0x1800bab72  jz      short loc_1800BAB88
0x1800bab74  test    rax, rax
0x1800bab77  jz      short loc_1800BAB81
0x1800bab79  mov     rcx, rax; this
0x1800bab7c  call    ??_GCHashTable@ObjexHashTable@@QEAAPEAXI@Z; ObjexHashTable::CHashTable::`scalar deleting destructor'(uint)
0x1800bab81  mov     cs:?gpClientOxidTable@@3PEAVCHashTable@ObjexHashTable@@EA, r12; ObjexHashTable::CHashTable * gpClientOxidTable
0x1800bab88  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800bab8f  mov     r8, rsi; dwBytes
0x1800bab92  xor     edx, edx; dwFlags
0x1800bab94  call    cs:__imp_HeapAlloc
0x1800bab9a  mov     r14d, 40h ; '@'
0x1800baba0  test    rax, rax
0x1800baba3  jz      short loc_1800BABB9
0x1800baba5  mov     r8d, r14d; unsigned int
0x1800baba8  lea     rdx, [rbp+var_38]; int *
0x1800babac  mov     rcx, rax; this
0x1800babaf  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800babb4  mov     ebx, [rbp+var_38]
0x1800babb7  jmp     short loc_1800BABBC
0x1800babb9  mov     rax, r12
0x1800babbc  mov     cs:?gpClientOidTable@@3PEAVCHashTable@ObjexHashTable@@EA, rax; ObjexHashTable::CHashTable * gpClientOidTable
0x1800babc3  test    ebx, ebx
0x1800babc5  jz      short loc_1800BABDB
0x1800babc7  test    rax, rax
0x1800babca  jz      short loc_1800BABD4
0x1800babcc  mov     rcx, rax; this
0x1800babcf  call    ??_GCHashTable@ObjexHashTable@@QEAAPEAXI@Z; ObjexHashTable::CHashTable::`scalar deleting destructor'(uint)
0x1800babd4  mov     cs:?gpClientOidTable@@3PEAVCHashTable@ObjexHashTable@@EA, r12; ObjexHashTable::CHashTable * gpClientOidTable
0x1800babdb  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800babe2  mov     r8, rsi; dwBytes
0x1800babe5  xor     edx, edx; dwFlags
0x1800babe7  call    cs:__imp_HeapAlloc
0x1800babed  test    rax, rax
0x1800babf0  jz      short loc_1800BAC06
0x1800babf2  mov     r8d, r13d; unsigned int
0x1800babf5  lea     rdx, [rbp+var_38]; int *
0x1800babf9  mov     rcx, rax; this
0x1800babfc  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800bac01  mov     ebx, [rbp+var_38]
0x1800bac04  jmp     short loc_1800BAC09
0x1800bac06  mov     rax, r12
0x1800bac09  mov     cs:?gpClientSetTable@@3PEAVCHashTable@ObjexHashTable@@EA, rax; ObjexHashTable::CHashTable * gpClientSetTable
0x1800bac10  test    ebx, ebx
0x1800bac12  jz      short loc_1800BAC28
0x1800bac14  test    rax, rax
0x1800bac17  jz      short loc_1800BAC21
0x1800bac19  mov     rcx, rax; this
0x1800bac1c  call    ??_GCHashTable@ObjexHashTable@@QEAAPEAXI@Z; ObjexHashTable::CHashTable::`scalar deleting destructor'(uint)
0x1800bac21  mov     cs:?gpClientSetTable@@3PEAVCHashTable@ObjexHashTable@@EA, r12; ObjexHashTable::CHashTable * gpClientSetTable
0x1800bac28  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800bac2f  mov     r8, rsi; dwBytes
0x1800bac32  xor     edx, edx; dwFlags
0x1800bac34  call    cs:__imp_HeapAlloc
0x1800bac3a  test    rax, rax
0x1800bac3d  jz      short loc_1800BAC53
0x1800bac3f  mov     r8d, r13d; unsigned int
0x1800bac42  lea     rdx, [rbp+var_38]; int *
0x1800bac46  mov     rcx, rax; this
0x1800bac49  call    ??0CHashTable@ObjexHashTable@@QEAA@AEAJI@Z; ObjexHashTable::CHashTable::CHashTable(long &,uint)
0x1800bac4e  mov     ebx, [rbp+var_38]
0x1800bac51  jmp     short loc_1800BAC56
0x1800bac53  mov     rax, r12
0x1800bac56  mov     cs:?gpMidTable@@3PEAVCHashTable@ObjexHashTable@@EA, rax; ObjexHashTable::CHashTable * gpMidTable
0x1800bac5d  test    ebx, ebx
0x1800bac5f  jz      short loc_1800BAC75
0x1800bac61  test    rax, rax
0x1800bac64  jz      short loc_1800BAC6E
0x1800bac66  mov     rcx, rax; this
0x1800bac69  call    ??_GCHashTable@ObjexHashTable@@QEAAPEAXI@Z; ObjexHashTable::CHashTable::`scalar deleting destructor'(uint)
0x1800bac6e  mov     cs:?gpMidTable@@3PEAVCHashTable@ObjexHashTable@@EA, r12; ObjexHashTable::CHashTable * gpMidTable
0x1800bac75  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800bac7c  mov     r8, r14; dwBytes
0x1800bac7f  xor     edx, edx; dwFlags
0x1800bac81  call    cs:__imp_HeapAlloc
0x1800bac87  test    rax, rax
0x1800bac8a  jz      short loc_1800BACA5
0x1800bac8c  movzx   r8d, cs:?g_usBasePingInterval@@3GA; unsigned int
0x1800bac94  lea     rdx, [rbp+var_38]; int *
0x1800bac98  mov     rcx, rax; this
0x1800bac9b  call    ??0CPList@@QEAA@AEAJK@Z; CPList::CPList(long &,ulong)
0x1800baca0  mov     ebx, [rbp+var_38]
0x1800baca3  jmp     short loc_1800BACA8
0x1800baca5  mov     rax, r12
0x1800baca8  mov     cs:?gpClientOxidPList@@3PEAVCPList@@EA, rax; CPList * gpClientOxidPList
0x1800bacaf  test    ebx, ebx
0x1800bacb1  jz      short loc_1800BACC7
0x1800bacb3  test    rax, rax
0x1800bacb6  jz      short loc_1800BACC0
0x1800bacb8  mov     rcx, rax; this
0x1800bacbb  call    ??_GCPList@@QEAAPEAXI@Z; CPList::`scalar deleting destructor'(uint)
0x1800bacc0  mov     cs:?gpClientOxidPList@@3PEAVCPList@@EA, r12; CPList * gpClientOxidPList
0x1800bacc7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800bacce  mov     r8, r14; dwBytes
0x1800bacd1  xor     edx, edx; dwFlags
0x1800bacd3  call    cs:__imp_HeapAlloc
0x1800bacd9  mov     rdi, rax
0x1800bacdc  test    rax, rax
0x1800bacdf  jz      short loc_1800BACFA
0x1800bace1  movzx   r8d, cs:?g_usBaseTimeoutInterval@@3GA; unsigned int
0x1800bace9  lea     rdx, [rbp+var_38]; int *
0x1800baced  mov     rcx, rax; this
0x1800bacf0  call    ??0CPList@@QEAA@AEAJK@Z; CPList::CPList(long &,ulong)
0x1800bacf5  mov     ebx, [rbp+var_38]
0x1800bacf8  jmp     short loc_1800BACFD
0x1800bacfa  mov     rdi, r12
0x1800bacfd  mov     cs:?gpServerOidPList@@3PEAVCServerOidPList@@EA, rdi; CServerOidPList * gpServerOidPList
0x1800bad04  test    ebx, ebx
0x1800bad06  jz      short loc_1800BAD27
  ... truncated ...
```
