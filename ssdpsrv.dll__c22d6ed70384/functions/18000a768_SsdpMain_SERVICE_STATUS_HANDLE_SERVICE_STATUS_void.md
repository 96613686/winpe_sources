# SsdpMain(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *,void * *)

- ea: `0x18000a768`
- end: `0x18000b034`
- name: `?SsdpMain@@YAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@PEAPEAX@Z`
- size: `2252`
- prototype: `__int64 __fastcall(struct SERVICE_STATUS_HANDLE__ *, struct _SERVICE_STATUS *, struct ServiceContext **)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180027e20`

## callees

- `0x18000936c`
- `0x18000a768`
- `0x18000b03c`
- `0x18000b064`
- `0x18000b2a0`
- `0x18000b384`
- `0x18000b47c`
- `0x18000b4f4`
- `0x18000b5c8`
- `0x18000b71c`
- `0x18000b7c4`
- `0x18000ba40`
- `0x18000babc`
- `0x18000bc38`
- `0x18000bd40`
- `0x18000d990`
- `0x18000dc54`
- `0x18000eec0`
- `0x18001f9ec`
- `0x180024750`
- `0x180024a20`
- `0x1800255a8`
- `0x180028000`
- `0x180036010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a7de`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000a7de`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ab28`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ad02`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ad4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ab28`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ad02`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000ad4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000abc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ad79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a900`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a91b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a8e5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a900`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a91b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a8c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a8c5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a95b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a95b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ade8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ade8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ad92`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ad92`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000aba1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000aba1`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a832`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000afa6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000a832`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000afa6`

## string_xrefs

- `0x18000a8bc`: `FirewallAPI.dll`
- `0x18000a8db`: `IcfChangeNotificationCreate`
- `0x18000a90d`: `IcfAddrChangeNotificationCreate`

## pseudocode

```c
__int64 __fastcall SsdpMain(struct SERVICE_STATUS_HANDLE__ *a1, struct _SERVICE_STATUS *a2, struct ServiceContext **a3)
{
  SERVICE_STATUS_HANDLE v3; // r15
  struct ServiceContext *v6; // rax
  unsigned int v7; // ebx
  struct ServiceContext *v8; // rdi
  DWORD LastError; // eax
  int v10; // eax
  LPCSTR v11; // rcx
  __int64 v12; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v15; // rcx
  bool v16; // zf
  LPCSTR v17; // rcx
  __int64 v18; // rdx
  HANDLE EventA; // rax
  DWORD v20; // eax
  DWORD v21; // eax
  unsigned int v22; // eax
  LPCSTR v23; // rcx
  __int64 v24; // rdx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _SVCHOST_GLOBAL_DATA *v26; // rax
  unsigned int v28; // [rsp+40h] [rbp-28h] BYREF
  void *v29; // [rsp+48h] [rbp-20h]
  __int64 v30; // [rsp+50h] [rbp-18h]
  _FILETIME pftDueTime; // [rsp+B0h] [rbp+48h] BYREF

  pftDueTime = (_FILETIME)a1;
  v3 = hServiceStatus;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids);
  v28 = 0;
  operator delete(0);
  v29 = 0;
  v30 = 0;
  v6 = (struct ServiceContext *)malloc(0x20u);
  v7 = 1;
  v8 = v6;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids, LastError);
    }
    a2->dwCurrentState = 1;
    *(_QWORD *)&a2->dwCheckPoint = 0;
    SetServiceStatus(v3, a2);
    goto LABEL_137;
  }
  *(_QWORD *)v6 = 0;
  *((_DWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 2) = v3;
  *((_QWORD *)v6 + 3) = a2;
  g_lSsdpRef = 0;
  g_hAddrChange = 0;
  g_hNqmNotification = 0;
  *a3 = v6;
  g_shutdownTimer = 0;
  g_fShutdownTimerSet = 0;
  v10 = InitializeListNetwork();
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_137;
    v12 = 28;
    goto LABEL_13;
  }
  UpdateServiceCheckPoint(v8);
  Library = LoadLibraryExW(L"FirewallAPI.dll", 0, 0);
  hLibModule = Library;
  if ( Library )
  {
    qword_1800425F0 = (__int64)GetProcAddress(Library, "IcfChangeNotificationCreate");
    qword_1800425A8 = (__int64)GetProcAddress(hLibModule, "IcfChangeNotificationDestroy");
    ProcAddress = GetProcAddress(hLibModule, "IcfAddrChangeNotificationCreate");
    qword_1800425D8 = (__int64)ProcAddress;
    if ( !qword_1800425F0 || !qword_1800425A8 || !ProcAddress )
    {
      qword_1800425F0 = 0;
      qword_1800425A8 = 0;
      qword_1800425D8 = 0;
      FreeLibrary(hLibModule);
      hLibModule = 0;
    }
  }
  UpdateServiceCheckPoint(v8);
  v10 = InitializeEventingClasses();
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_137;
    v12 = 29;
    goto LABEL_13;
  }
  v10 = CWorkItem::HrSyncInitialize();
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_137;
    v12 = 30;
    goto LABEL_13;
  }
  v10 = CTimerQueue::HrInitialize((struct _RTL_CRITICAL_SECTION *)CTimerQueue::s_instance);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_137;
    v12 = 31;
    goto LABEL_13;
  }
  v10 = CSsdpNotifyRequestManager::HrInitialize((CSsdpNotifyRequestManager *)&CSsdpNotifyRequestManager::s_instance);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_137;
    v12 = 32;
    goto LABEL_13;
  }
  dword_180041968 = 0;
  dword_180041A20 = 0;
  if ( (int)CInterfaceHelper::HrInitialize((CInterfaceHelper *)&CInterfaceHelper::s_instance) < 0 )
    goto LABEL_137;
  v10 = CUPnPInterfaceList::HrInitialize(&CUPnPInterfaceList::s_instance);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_137;
    v12 = 34;
    goto LABEL_13;
  }
  UpdateServiceCheckPoint(v8);
  CNetworkCfgRegSettings::ReadScopeSettings((BYTE *)&v28);
  if ( !(unsigned int)SocketInit(v15, v28) )
  {
    if ( (int)GetNetworkAddress() < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v18 = 36;
      goto LABEL_136;
    }
    UpdateServiceCheckPoint(v8);
    if ( hLibModule )
    {
      EventA = CreateEventA(0, 0, 0, 0);
      hObject = EventA;
      if ( EventA )
        goto LABEL_140;
      if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
      {
        v20 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids, v20);
        EventA = hObject;
      }
      if ( EventA )
      {
LABEL_140:
        if ( !RegisterWaitForSingleObject(&WaitHandle, EventA, SsdpFirewallChangeCallback, 0, 0xFFFFFFFF, 0) )
        {
          WaitHandle = 0;
          if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
          {
            v21 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids, v21);
          }
        }
        if ( hObject && WaitHandle )
        {
          v22 = ((__int64 (__fastcall *)(HANDLE, __int64 *))qword_1800425F0)(hObject, &qword_1800425B0);
          if ( v22 )
          {
            qword_1800425B0 = 0;
            v23 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
            {
              v24 = 39;
LABEL_71:
              WPP_SF_d(*((_QWORD *)v23 + 2), v24, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids, v22);
            }
          }
          else
          {
            v22 = ((__int64 (__fastcall *)(HANDLE, __int64 *))qword_1800425D8)(hObject, &qword_180042598);
            if ( v22 )
            {
              qword_180042598 = 0;
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
              {
                v24 = 40;
                goto LABEL_71;
              }
            }
          }
        }
      }
    }
    UpdateServiceCheckPoint(v8);
    v10 = CSsdpSearchRequestManager::HrInitialize((char *)&CSsdpSearchRequestManager::s_instance);
    if ( v10 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v12 = 41;
      goto LABEL_13;
    }
    if ( (unsigned int)GetNetworks() )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v18 = 42;
      goto LABEL_136;
    }
    UpdateServiceCheckPoint(v8);
    ShutDownEvent = CreateEventA(0, 1, 0, 0);
    if ( !ShutDownEvent )
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v10 = GetLastError();
      v12 = 43;
LABEL_84:
      v11 = WPP_GLOBAL_Control;
      goto LABEL_13;
    }
    g_hServiceStopEvent = CreateEventA(0, 0, 0, 0);
    if ( !g_hServiceStopEvent )
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v10 = GetLastError();
      v12 = 44;
      goto LABEL_84;
    }
    ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)ServiceShutdownTimerCallback, 0, 0);
    g_shutdownTimer = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
    {
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v10 = GetLastError();
      v12 = 45;
      goto LABEL_84;
    }
    pftDueTime.dwHighDateTime = -2;
    pftDueTime.dwLowDateTime = -1705032704;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    g_fShutdownTimerSet = 1;
    UpdateServiceCheckPoint(v8);
    if ( a2 )
    {
      if ( (unsigned int)RpcServerStart() )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
          goto LABEL_137;
        v18 = 46;
        goto LABEL_136;
      }
      *(_DWORD *)v8 = 1;
    }
    v10 = CReceiveDataManager::HrInitialize((CReceiveDataManager *)&CReceiveDataManager::s_instance);
    if ( v10 >= 0 )
    {
      v10 = CSsdpCacheEntryManager::HrInitialize((CSsdpCacheEntryManager *)&CSsdpCacheEntryManager::s_instance);
      if ( v10 >= 0 )
      {
        if ( ListenOnAllNetworks() )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
            goto LABEL_137;
          v18 = 49;
        }
        else
        {
          UpdateServiceCheckPoint(v8);
          if ( (unsigned int)RegisterAddrChange() )
          {
            *((_DWORD *)v8 + 1) = 1;
            if ( (unsigned int)RegisterNQMNotification() )
            {
              v26 = g_pSvchostSharedGlobals;
              *((_DWORD *)v8 + 2) = 1;
              if ( v26 )
              {
                if ( (*((unsigned int (__fastcall **)(HANDLE *, const wchar_t *, HANDLE, void (__fastcall *)(struct ServiceContext *, int), struct ServiceContext *, _DWORD))v26
                      + 24))(
                       &g_hStopWait,
                       L"ssdpsrv",
                       g_hServiceStopEvent,
                       SsdpMainStop,
                       v8,
                       0) )
                {
                  v17 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
                    goto LABEL_137;
                  v18 = 52;
                }
                else
                {
                  if ( !a2
                    || (a2->dwCurrentState = 4,
                        *(_QWORD *)&a2->dwCheckPoint = 0,
                        a2->dwControlsAccepted = 5,
                        SetServiceStatus(v3, a2)) )
                  {
                    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 8) != 0 )
                      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids);
                    v7 = 0;
                    goto LABEL_137;
                  }
                  v17 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
                    goto LABEL_137;
                  v18 = 54;
                }
              }
              else
              {
                v17 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
                  goto LABEL_137;
                v18 = 53;
              }
            }
            else
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
                goto LABEL_137;
              v18 = 51;
            }
          }
          else
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
              goto LABEL_137;
            v18 = 50;
          }
        }
LABEL_136:
        WPP_SF_(*((_QWORD *)v17 + 2), v18, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids);
        goto LABEL_137;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v12 = 48;
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_137;
      v12 = 47;
    }
LABEL_13:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids, (unsigned int)v10);
    goto LABEL_137;
  }
  v10 = GetLastError();
  v16 = v10 == 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v16 = v10 == 0;
  }
  if ( !v16 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      v12 = 35;
      goto LABEL_13;
    }
  }
LABEL_137:
  operator delete(v29);
  return v7;
}

```

## disassembly

```asm
0x18000a768  mov     qword ptr [rsp-40h+pftDueTime.dwLowDateTime], rcx
0x18000a76d  push    rbp
0x18000a76e  push    rbx
0x18000a76f  push    rsi
0x18000a770  push    rdi
0x18000a771  push    r12
0x18000a773  push    r13
0x18000a775  push    r14
0x18000a777  push    r15
0x18000a779  mov     rbp, rsp
0x18000a77c  sub     rsp, 68h
0x18000a780  mov     r15, cs:hServiceStatus
0x18000a787  mov     r14, r8
0x18000a78a  mov     rsi, rdx
0x18000a78d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a794  lea     r13, WPP_GLOBAL_Control
0x18000a79b  cmp     rcx, r13
0x18000a79e  jz      short loc_18000A7BB
0x18000a7a0  test    byte ptr [rcx+1Ch], 8
0x18000a7a4  jz      short loc_18000A7BB
0x18000a7a6  mov     rcx, [rcx+10h]
0x18000a7aa  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000a7b1  mov     edx, 1Ah
0x18000a7b6  call    WPP_SF_
0x18000a7bb  xor     r12d, r12d
0x18000a7be  xor     ecx, ecx; void *
0x18000a7c0  mov     [rbp+var_20], r12
0x18000a7c4  mov     [rbp+var_18], r12
0x18000a7c8  mov     [rbp+var_28], r12d
0x18000a7cc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a7d1  lea     ecx, [r12+20h]; Size
0x18000a7d6  mov     [rbp+var_20], r12
0x18000a7da  mov     [rbp+var_18], r12
0x18000a7de  call    cs:__imp_malloc
0x18000a7e4  lea     ebx, [r12+1]
0x18000a7e9  mov     rdi, rax
0x18000a7ec  test    rax, rax
0x18000a7ef  jnz     short loc_18000A83D
0x18000a7f1  mov     rax, cs:WPP_GLOBAL_Control
0x18000a7f8  cmp     rax, r13
0x18000a7fb  jz      short loc_18000A825
0x18000a7fd  test    [rax+1Ch], bl
0x18000a800  jz      short loc_18000A825
0x18000a802  call    cs:__imp_GetLastError
0x18000a808  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a80f  lea     edx, [rdi+1Bh]
0x18000a812  mov     r9d, eax
0x18000a815  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000a81c  mov     rcx, [rcx+10h]
0x18000a820  call    WPP_SF_d
0x18000a825  mov     rdx, rsi; lpServiceStatus
0x18000a828  mov     [rsi+4], ebx
0x18000a82b  mov     rcx, r15; hServiceStatus
0x18000a82e  mov     [rsi+14h], r12
0x18000a832  call    cs:__imp_SetServiceStatus
0x18000a838  jmp     loc_18000B018
0x18000a83d  mov     [rax], r12
0x18000a840  mov     [rax+8], r12d
0x18000a844  mov     [rax+10h], r15
0x18000a848  mov     [rax+18h], rsi
0x18000a84c  mov     cs:?g_lSsdpRef@@3JA, r12d; long g_lSsdpRef
0x18000a853  mov     cs:?g_hAddrChange@@3PEAXEA, r12; void * g_hAddrChange
0x18000a85a  mov     cs:?g_hNqmNotification@@3PEAXEA, r12; void * g_hNqmNotification
0x18000a861  mov     [r14], rdi
0x18000a864  mov     cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA, r12; _TP_TIMER * g_shutdownTimer
0x18000a86b  mov     cs:?g_fShutdownTimerSet@@3HA, r12d; int g_fShutdownTimerSet
0x18000a872  call    ?InitializeListNetwork@@YAJXZ; InitializeListNetwork(void)
0x18000a877  test    eax, eax
0x18000a879  jns     short loc_18000A8B1
0x18000a87b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a882  cmp     rcx, r13
0x18000a885  jz      loc_18000B018
0x18000a88b  test    [rcx+1Ch], bl
0x18000a88e  jz      loc_18000B018
0x18000a894  mov     edx, 1Ch
0x18000a899  mov     rcx, [rcx+10h]
0x18000a89d  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000a8a4  mov     r9d, eax
0x18000a8a7  call    WPP_SF_d
0x18000a8ac  jmp     loc_18000B018
0x18000a8b1  mov     rcx, rdi; struct ServiceContext *
0x18000a8b4  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000a8b9  xor     r8d, r8d; dwFlags
0x18000a8bc  lea     rcx, LibFileName; "FirewallAPI.dll"
0x18000a8c3  xor     edx, edx; hFile
0x18000a8c5  call    cs:__imp_LoadLibraryExW
0x18000a8cb  mov     cs:hLibModule, rax
0x18000a8d2  test    rax, rax
0x18000a8d5  jz      loc_18000A968
0x18000a8db  lea     rdx, ProcName; "IcfChangeNotificationCreate"
0x18000a8e2  mov     rcx, rax; hModule
0x18000a8e5  call    cs:__imp_GetProcAddress
0x18000a8eb  mov     rcx, cs:hLibModule; hModule
0x18000a8f2  lea     rdx, aIcfchangenotif_0; "IcfChangeNotificationDestroy"
0x18000a8f9  mov     cs:qword_1800425F0, rax
0x18000a900  call    cs:__imp_GetProcAddress
0x18000a906  mov     rcx, cs:hLibModule; hModule
0x18000a90d  lea     rdx, aIcfaddrchangen; "IcfAddrChangeNotificationCreate"
0x18000a914  mov     cs:qword_1800425A8, rax
0x18000a91b  call    cs:__imp_GetProcAddress
0x18000a921  cmp     cs:qword_1800425F0, r12
0x18000a928  mov     cs:qword_1800425D8, rax
0x18000a92f  jz      short loc_18000A93F
0x18000a931  cmp     cs:qword_1800425A8, r12
0x18000a938  jz      short loc_18000A93F
0x18000a93a  test    rax, rax
0x18000a93d  jnz     short loc_18000A968
0x18000a93f  mov     rcx, cs:hLibModule; hLibModule
0x18000a946  mov     cs:qword_1800425F0, r12
0x18000a94d  mov     cs:qword_1800425A8, r12
0x18000a954  mov     cs:qword_1800425D8, r12
0x18000a95b  call    cs:__imp_FreeLibrary
0x18000a961  mov     cs:hLibModule, r12
0x18000a968  mov     rcx, rdi; struct ServiceContext *
0x18000a96b  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000a970  call    ?InitializeEventingClasses@@YAJXZ; InitializeEventingClasses(void)
0x18000a975  test    eax, eax
0x18000a977  jns     short loc_18000A99C
0x18000a979  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a980  cmp     rcx, r13
0x18000a983  jz      loc_18000B018
0x18000a989  test    [rcx+1Ch], bl
0x18000a98c  jz      loc_18000B018
0x18000a992  mov     edx, 1Dh
0x18000a997  jmp     loc_18000A899
0x18000a99c  call    ?HrSyncInitialize@CWorkItem@@SAJXZ; CWorkItem::HrSyncInitialize(void)
0x18000a9a1  test    eax, eax
0x18000a9a3  jns     short loc_18000A9C8
0x18000a9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9ac  cmp     rcx, r13
0x18000a9af  jz      loc_18000B018
0x18000a9b5  test    [rcx+1Ch], bl
0x18000a9b8  jz      loc_18000B018
0x18000a9be  mov     edx, 1Eh
0x18000a9c3  jmp     loc_18000A899
0x18000a9c8  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x18000a9cf  call    ?HrInitialize@CTimerQueue@@QEAAJXZ; CTimerQueue::HrInitialize(void)
0x18000a9d4  test    eax, eax
0x18000a9d6  jns     short loc_18000A9FB
0x18000a9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9df  cmp     rcx, r13
0x18000a9e2  jz      loc_18000B018
0x18000a9e8  test    [rcx+1Ch], bl
0x18000a9eb  jz      loc_18000B018
0x18000a9f1  mov     edx, 1Fh
0x18000a9f6  jmp     loc_18000A899
0x18000a9fb  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x18000aa02  call    ?HrInitialize@CSsdpNotifyRequestManager@@QEAAJXZ; CSsdpNotifyRequestManager::HrInitialize(void)
0x18000aa07  test    eax, eax
0x18000aa09  jns     short loc_18000AA2E
0x18000aa0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa12  cmp     rcx, r13
0x18000aa15  jz      loc_18000B018
0x18000aa1b  test    [rcx+1Ch], bl
0x18000aa1e  jz      loc_18000B018
0x18000aa24  mov     edx, 20h ; ' '
0x18000aa29  jmp     loc_18000A899
0x18000aa2e  lea     rcx, ?s_instance@CInterfaceHelper@@0V1@A; this
0x18000aa35  mov     cs:dword_180041968, r12d
0x18000aa3c  mov     cs:dword_180041A20, r12d
0x18000aa43  call    ?HrInitialize@CInterfaceHelper@@QEAAJXZ; CInterfaceHelper::HrInitialize(void)
0x18000aa48  test    eax, eax
0x18000aa4a  js      loc_18000B018
0x18000aa50  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x18000aa57  call    ?HrInitialize@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrInitialize(void)
0x18000aa5c  test    eax, eax
0x18000aa5e  jns     short loc_18000AA83
0x18000aa60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa67  cmp     rcx, r13
0x18000aa6a  jz      loc_18000B018
0x18000aa70  test    [rcx+1Ch], bl
0x18000aa73  jz      loc_18000B018
0x18000aa79  mov     edx, 22h ; '"'
0x18000aa7e  jmp     loc_18000A899
0x18000aa83  mov     rcx, rdi; struct ServiceContext *
0x18000aa86  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000aa8b  lea     rcx, [rbp+var_28]; this
0x18000aa8f  call    ?ReadScopeSettings@CNetworkCfgRegSettings@@QEAAXXZ; CNetworkCfgRegSettings::ReadScopeSettings(void)
0x18000aa94  mov     edx, [rbp+var_28]; unsigned int
0x18000aa97  call    ?SocketInit@@YAHKK@Z; SocketInit(ulong,ulong)
0x18000aa9c  test    eax, eax
0x18000aa9e  jz      short loc_18000AADD
0x18000aaa0  call    cs:__imp_GetLastError
0x18000aaa6  test    eax, eax
0x18000aaa8  jle     short loc_18000AAB4
0x18000aaaa  movzx   eax, ax
0x18000aaad  or      eax, 80070000h
0x18000aab2  test    eax, eax
0x18000aab4  jz      loc_18000B018
0x18000aaba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aac1  cmp     rcx, r13
0x18000aac4  jz      loc_18000B018
0x18000aaca  test    [rcx+1Ch], bl
0x18000aacd  jz      loc_18000B018
0x18000aad3  mov     edx, 23h ; '#'
0x18000aad8  jmp     loc_18000A899
0x18000aadd  call    ?GetNetworkAddress@@YAJXZ; GetNetworkAddress(void)
0x18000aae2  test    eax, eax
0x18000aae4  jns     short loc_18000AB09
0x18000aae6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaed  cmp     rcx, r13
0x18000aaf0  jz      loc_18000B018
0x18000aaf6  test    [rcx+1Ch], bl
0x18000aaf9  jz      loc_18000B018
0x18000aaff  mov     edx, 24h ; '$'
0x18000ab04  jmp     loc_18000B008
0x18000ab09  mov     rcx, rdi; struct ServiceContext *
0x18000ab0c  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000ab11  cmp     cs:hLibModule, r12
0x18000ab18  jz      loc_18000AC89
0x18000ab1e  xor     r9d, r9d; lpName
0x18000ab21  xor     r8d, r8d; bInitialState
0x18000ab24  xor     edx, edx; bManualReset
0x18000ab26  xor     ecx, ecx; lpEventAttributes
0x18000ab28  call    cs:__imp_CreateEventA
0x18000ab2e  mov     cs:hObject, rax
0x18000ab35  test    rax, rax
0x18000ab38  jnz     short loc_18000AB80
0x18000ab3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab41  cmp     rcx, r13
0x18000ab44  jz      short loc_18000AB77
0x18000ab46  test    [rcx+1Ch], bl
0x18000ab49  jz      short loc_18000AB77
0x18000ab4b  call    cs:__imp_GetLastError
0x18000ab51  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab58  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000ab5f  mov     edx, 25h ; '%'
0x18000ab64  mov     r9d, eax
0x18000ab67  mov     rcx, [rcx+10h]
0x18000ab6b  call    WPP_SF_d
0x18000ab70  mov     rax, cs:hObject
0x18000ab77  test    rax, rax
0x18000ab7a  jz      loc_18000AC89
0x18000ab80  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x18000ab85  lea     r8, ?SsdpFirewallChangeCallback@@YAXPEAXE@Z; Callback
0x18000ab8c  xor     r9d, r9d; Context
0x18000ab8f  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000ab97  mov     rdx, rax; hObject
0x18000ab9a  lea     rcx, WaitHandle; phNewWaitObject
0x18000aba1  call    cs:__imp_RegisterWaitForSingleObject
0x18000aba7  test    eax, eax
0x18000aba9  jnz     short loc_18000ABE8
0x18000abab  mov     cs:WaitHandle, r12
0x18000abb2  mov     rax, cs:WPP_GLOBAL_Control
0x18000abb9  cmp     rax, r13
0x18000abbc  jz      short loc_18000ABE8
0x18000abbe  test    [rax+1Ch], bl
0x18000abc1  jz      short loc_18000ABE8
0x18000abc3  call    cs:__imp_GetLastError
0x18000abc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abd0  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000abd7  mov     edx, 26h ; '&'
0x18000abdc  mov     r9d, eax
0x18000abdf  mov     rcx, [rcx+10h]
0x18000abe3  call    WPP_SF_d
0x18000abe8  mov     rcx, cs:hObject
0x18000abef  test    rcx, rcx
0x18000abf2  jz      loc_18000AC89
0x18000abf8  cmp     cs:WaitHandle, r12
0x18000abff  jz      loc_18000AC89
0x18000ac05  mov     rax, cs:qword_1800425F0
0x18000ac0c  lea     rdx, qword_1800425B0
0x18000ac13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac18  test    eax, eax
0x18000ac1a  jz      short loc_18000AC3B
0x18000ac1c  mov     cs:qword_1800425B0, r12
0x18000ac23  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac2a  cmp     rcx, r13
0x18000ac2d  jz      short loc_18000AC89
0x18000ac2f  test    [rcx+1Ch], bl
0x18000ac32  jz      short loc_18000AC89
0x18000ac34  mov     edx, 27h ; '''
0x18000ac39  jmp     short loc_18000AC76
0x18000ac3b  mov     rcx, cs:hObject
0x18000ac42  lea     rdx, qword_180042598
0x18000ac49  mov     rax, cs:qword_1800425D8
0x18000ac50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac55  test    eax, eax
0x18000ac57  jz      short loc_18000AC89
0x18000ac59  mov     cs:qword_180042598, r12
0x18000ac60  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac67  cmp     rcx, r13
0x18000ac6a  jz      short loc_18000AC89
0x18000ac6c  test    [rcx+1Ch], bl
0x18000ac6f  jz      short loc_18000AC89
0x18000ac71  mov     edx, 28h ; '('
0x18000ac76  mov     rcx, [rcx+10h]
0x18000ac7a  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000ac81  mov     r9d, eax
0x18000ac84  call    WPP_SF_d
0x18000ac89  mov     rcx, rdi; struct ServiceContext *
0x18000ac8c  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000ac91  lea     rcx, ?s_instance@CSsdpSearchRequestManager@@0V1@A; lpCriticalSection
0x18000ac98  call    ?HrInitialize@CSsdpSearchRequestManager@@QEAAJXZ; CSsdpSearchRequestManager::HrInitialize(void)
0x18000ac9d  test    eax, eax
0x18000ac9f  jns     short loc_18000ACC4
0x18000aca1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aca8  cmp     rcx, r13
0x18000acab  jz      loc_18000B018
0x18000acb1  test    [rcx+1Ch], bl
  ... truncated ...
```
