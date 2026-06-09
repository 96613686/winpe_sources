# SsdpMain(SERVICE_STATUS_HANDLE__ *,_SERVICE_STATUS *,void * *)

- ea: `0x18000c078`
- end: `0x18000c9c6`
- name: `?SsdpMain@@YAHPEAUSERVICE_STATUS_HANDLE__@@PEAU_SERVICE_STATUS@@PEAPEAX@Z`
- size: `2382`
- prototype: `int(struct SERVICE_STATUS_HANDLE__ *, struct _SERVICE_STATUS *, void **)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180029bf0`

## callees

- `0x18000a9ac`
- `0x18000c078`
- `0x18000c9cc`
- `0x18000c9fc`
- `0x18000cc58`
- `0x18000cd48`
- `0x18000ce58`
- `0x18000cee0`
- `0x18000cfc8`
- `0x18000d140`
- `0x18000d214`
- `0x18000d4cc`
- `0x18000d550`
- `0x18000d6f4`
- `0x18000d80c`
- `0x18000ece0`
- `0x18000eff4`
- `0x180010390`
- `0x180021060`
- `0x180026260`
- `0x180026550`
- `0x1800271fc`
- `0x180029df0`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c0ee`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000c0ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c46e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c660`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c6b8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c46e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c660`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000c6b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c51b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c118`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c3e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c51b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c6e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c739`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c20d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c22e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c24f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c20d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c22e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c24f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c1e7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c1e7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c295`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c295`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c76a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c76a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c708`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c708`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c4f3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18000c4f3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c14e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c931`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c14e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000c931`

## string_xrefs

- `0x18000c1de`: `FirewallAPI.dll`
- `0x18000c203`: `IcfChangeNotificationCreate`
- `0x18000c241`: `IcfAddrChangeNotificationCreate`

## pseudocode

```c
__int64 __fastcall SsdpMain(struct SERVICE_STATUS_HANDLE__ *a1, struct _SERVICE_STATUS *a2, struct ServiceContext **a3)
{
  SERVICE_STATUS_HANDLE v3; // r15
  struct ServiceContext *v6; // rax
  unsigned int v7; // ebx
  struct ServiceContext *v8; // rdi
  DWORD LastError; // eax
  signed int v10; // eax
  LPCSTR v11; // rcx
  __int64 v12; // rdx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  unsigned int v15; // ecx
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
    qword_1800456D0 = (__int64)GetProcAddress(Library, "IcfChangeNotificationCreate");
    qword_180045688 = (__int64)GetProcAddress(hLibModule, "IcfChangeNotificationDestroy");
    ProcAddress = GetProcAddress(hLibModule, "IcfAddrChangeNotificationCreate");
    qword_1800456B8 = (__int64)ProcAddress;
    if ( !qword_1800456D0 || !qword_180045688 || !ProcAddress )
    {
      qword_1800456D0 = 0;
      qword_180045688 = 0;
      qword_1800456B8 = 0;
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
  v10 = CTimerQueue::HrInitialize((CTimerQueue *)&CTimerQueue::s_instance);
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
  dword_180044A68 = 0;
  dword_180044B20 = 0;
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
  CNetworkCfgRegSettings::ReadScopeSettings((CNetworkCfgRegSettings *)&v28);
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
          v22 = ((__int64 (__fastcall *)(HANDLE, __int64 *))qword_1800456D0)(hObject, &qword_180045690);
          if ( v22 )
          {
            qword_180045690 = 0;
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
            v22 = ((__int64 (__fastcall *)(HANDLE, __int64 *))qword_1800456B8)(hObject, &qword_180045678);
            if ( v22 )
            {
              qword_180045678 = 0;
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
    v10 = CSsdpSearchRequestManager::HrInitialize(&CSsdpSearchRequestManager::s_instance);
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
    ThreadpoolTimer = CreateThreadpoolTimer(ServiceShutdownTimerCallback, 0, 0);
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
        if ( (unsigned int)ListenOnAllNetworks() )
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
0x18000c078  mov     qword ptr [rsp-40h+pftDueTime.dwLowDateTime], rcx
0x18000c07d  push    rbp
0x18000c07e  push    rbx
0x18000c07f  push    rsi
0x18000c080  push    rdi
0x18000c081  push    r12
0x18000c083  push    r13
0x18000c085  push    r14
0x18000c087  push    r15
0x18000c089  mov     rbp, rsp
0x18000c08c  sub     rsp, 68h
0x18000c090  mov     r15, cs:hServiceStatus
0x18000c097  mov     r14, r8
0x18000c09a  mov     rsi, rdx
0x18000c09d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0a4  lea     r13, WPP_GLOBAL_Control
0x18000c0ab  cmp     rcx, r13
0x18000c0ae  jz      short loc_18000C0CB
0x18000c0b0  test    byte ptr [rcx+1Ch], 8
0x18000c0b4  jz      short loc_18000C0CB
0x18000c0b6  mov     rcx, [rcx+10h]
0x18000c0ba  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000c0c1  mov     edx, 1Ah
0x18000c0c6  call    WPP_SF_
0x18000c0cb  xor     r12d, r12d
0x18000c0ce  xor     ecx, ecx; void *
0x18000c0d0  mov     [rbp+var_20], r12
0x18000c0d4  mov     [rbp+var_18], r12
0x18000c0d8  mov     [rbp+var_28], r12d
0x18000c0dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c0e1  lea     ecx, [r12+20h]; Size
0x18000c0e6  mov     [rbp+var_20], r12
0x18000c0ea  mov     [rbp+var_18], r12
0x18000c0ee  call    cs:__imp_malloc
0x18000c0f5  nop     dword ptr [rax+rax+00h]
0x18000c0fa  lea     ebx, [r12+1]
0x18000c0ff  mov     rdi, rax
0x18000c102  test    rax, rax
0x18000c105  jnz     short loc_18000C15F
0x18000c107  mov     rax, cs:WPP_GLOBAL_Control
0x18000c10e  cmp     rax, r13
0x18000c111  jz      short loc_18000C141
0x18000c113  test    [rax+1Ch], bl
0x18000c116  jz      short loc_18000C141
0x18000c118  call    cs:__imp_GetLastError
0x18000c11f  nop     dword ptr [rax+rax+00h]
0x18000c124  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c12b  lea     edx, [rdi+1Bh]
0x18000c12e  mov     r9d, eax
0x18000c131  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000c138  mov     rcx, [rcx+10h]
0x18000c13c  call    WPP_SF_d
0x18000c141  mov     rdx, rsi; lpServiceStatus
0x18000c144  mov     [rsi+4], ebx
0x18000c147  mov     rcx, r15; hServiceStatus
0x18000c14a  mov     [rsi+14h], r12
0x18000c14e  call    cs:__imp_SetServiceStatus
0x18000c155  nop     dword ptr [rax+rax+00h]
0x18000c15a  jmp     loc_18000C9A9
0x18000c15f  mov     [rax], r12
0x18000c162  mov     [rax+8], r12d
0x18000c166  mov     [rax+10h], r15
0x18000c16a  mov     [rax+18h], rsi
0x18000c16e  mov     cs:?g_lSsdpRef@@3JA, r12d; long g_lSsdpRef
0x18000c175  mov     cs:?g_hAddrChange@@3PEAXEA, r12; void * g_hAddrChange
0x18000c17c  mov     cs:?g_hNqmNotification@@3PEAXEA, r12; void * g_hNqmNotification
0x18000c183  mov     [r14], rdi
0x18000c186  mov     cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA, r12; _TP_TIMER * g_shutdownTimer
0x18000c18d  mov     cs:?g_fShutdownTimerSet@@3HA, r12d; int g_fShutdownTimerSet
0x18000c194  call    ?InitializeListNetwork@@YAJXZ; InitializeListNetwork(void)
0x18000c199  test    eax, eax
0x18000c19b  jns     short loc_18000C1D3
0x18000c19d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1a4  cmp     rcx, r13
0x18000c1a7  jz      loc_18000C9A9
0x18000c1ad  test    [rcx+1Ch], bl
0x18000c1b0  jz      loc_18000C9A9
0x18000c1b6  mov     edx, 1Ch
0x18000c1bb  mov     rcx, [rcx+10h]
0x18000c1bf  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000c1c6  mov     r9d, eax
0x18000c1c9  call    WPP_SF_d
0x18000c1ce  jmp     loc_18000C9A9
0x18000c1d3  mov     rcx, rdi; struct ServiceContext *
0x18000c1d6  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000c1db  xor     r8d, r8d; dwFlags
0x18000c1de  lea     rcx, LibFileName; "FirewallAPI.dll"
0x18000c1e5  xor     edx, edx; hFile
0x18000c1e7  call    cs:__imp_LoadLibraryExW
0x18000c1ee  nop     dword ptr [rax+rax+00h]
0x18000c1f3  mov     cs:hLibModule, rax
0x18000c1fa  test    rax, rax
0x18000c1fd  jz      loc_18000C2A8
0x18000c203  lea     rdx, ProcName; "IcfChangeNotificationCreate"
0x18000c20a  mov     rcx, rax; hModule
0x18000c20d  call    cs:__imp_GetProcAddress
0x18000c214  nop     dword ptr [rax+rax+00h]
0x18000c219  mov     rcx, cs:hLibModule; hModule
0x18000c220  lea     rdx, aIcfchangenotif_0; "IcfChangeNotificationDestroy"
0x18000c227  mov     cs:qword_1800456D0, rax
0x18000c22e  call    cs:__imp_GetProcAddress
0x18000c235  nop     dword ptr [rax+rax+00h]
0x18000c23a  mov     rcx, cs:hLibModule; hModule
0x18000c241  lea     rdx, aIcfaddrchangen; "IcfAddrChangeNotificationCreate"
0x18000c248  mov     cs:qword_180045688, rax
0x18000c24f  call    cs:__imp_GetProcAddress
0x18000c256  nop     dword ptr [rax+rax+00h]
0x18000c25b  cmp     cs:qword_1800456D0, r12
0x18000c262  mov     cs:qword_1800456B8, rax
0x18000c269  jz      short loc_18000C279
0x18000c26b  cmp     cs:qword_180045688, r12
0x18000c272  jz      short loc_18000C279
0x18000c274  test    rax, rax
0x18000c277  jnz     short loc_18000C2A8
0x18000c279  mov     rcx, cs:hLibModule; hLibModule
0x18000c280  mov     cs:qword_1800456D0, r12
0x18000c287  mov     cs:qword_180045688, r12
0x18000c28e  mov     cs:qword_1800456B8, r12
0x18000c295  call    cs:__imp_FreeLibrary
0x18000c29c  nop     dword ptr [rax+rax+00h]
0x18000c2a1  mov     cs:hLibModule, r12
0x18000c2a8  mov     rcx, rdi; struct ServiceContext *
0x18000c2ab  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000c2b0  call    ?InitializeEventingClasses@@YAJXZ; InitializeEventingClasses(void)
0x18000c2b5  test    eax, eax
0x18000c2b7  jns     short loc_18000C2DC
0x18000c2b9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2c0  cmp     rcx, r13
0x18000c2c3  jz      loc_18000C9A9
0x18000c2c9  test    [rcx+1Ch], bl
0x18000c2cc  jz      loc_18000C9A9
0x18000c2d2  mov     edx, 1Dh
0x18000c2d7  jmp     loc_18000C1BB
0x18000c2dc  call    ?HrSyncInitialize@CWorkItem@@SAJXZ; CWorkItem::HrSyncInitialize(void)
0x18000c2e1  test    eax, eax
0x18000c2e3  jns     short loc_18000C308
0x18000c2e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2ec  cmp     rcx, r13
0x18000c2ef  jz      loc_18000C9A9
0x18000c2f5  test    [rcx+1Ch], bl
0x18000c2f8  jz      loc_18000C9A9
0x18000c2fe  mov     edx, 1Eh
0x18000c303  jmp     loc_18000C1BB
0x18000c308  lea     rcx, ?s_instance@CTimerQueue@@0V1@A; this
0x18000c30f  call    ?HrInitialize@CTimerQueue@@QEAAJXZ; CTimerQueue::HrInitialize(void)
0x18000c314  test    eax, eax
0x18000c316  jns     short loc_18000C33B
0x18000c318  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c31f  cmp     rcx, r13
0x18000c322  jz      loc_18000C9A9
0x18000c328  test    [rcx+1Ch], bl
0x18000c32b  jz      loc_18000C9A9
0x18000c331  mov     edx, 1Fh
0x18000c336  jmp     loc_18000C1BB
0x18000c33b  lea     rcx, ?s_instance@CSsdpNotifyRequestManager@@0V1@A; this
0x18000c342  call    ?HrInitialize@CSsdpNotifyRequestManager@@QEAAJXZ; CSsdpNotifyRequestManager::HrInitialize(void)
0x18000c347  test    eax, eax
0x18000c349  jns     short loc_18000C36E
0x18000c34b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c352  cmp     rcx, r13
0x18000c355  jz      loc_18000C9A9
0x18000c35b  test    [rcx+1Ch], bl
0x18000c35e  jz      loc_18000C9A9
0x18000c364  mov     edx, 20h ; ' '
0x18000c369  jmp     loc_18000C1BB
0x18000c36e  lea     rcx, ?s_instance@CInterfaceHelper@@0V1@A; this
0x18000c375  mov     cs:dword_180044A68, r12d
0x18000c37c  mov     cs:dword_180044B20, r12d
0x18000c383  call    ?HrInitialize@CInterfaceHelper@@QEAAJXZ; CInterfaceHelper::HrInitialize(void)
0x18000c388  test    eax, eax
0x18000c38a  js      loc_18000C9A9
0x18000c390  lea     rcx, ?s_instance@CUPnPInterfaceList@@0V1@A; lpCriticalSection
0x18000c397  call    ?HrInitialize@CUPnPInterfaceList@@QEAAJXZ; CUPnPInterfaceList::HrInitialize(void)
0x18000c39c  test    eax, eax
0x18000c39e  jns     short loc_18000C3C3
0x18000c3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3a7  cmp     rcx, r13
0x18000c3aa  jz      loc_18000C9A9
0x18000c3b0  test    [rcx+1Ch], bl
0x18000c3b3  jz      loc_18000C9A9
0x18000c3b9  mov     edx, 22h ; '"'
0x18000c3be  jmp     loc_18000C1BB
0x18000c3c3  mov     rcx, rdi; struct ServiceContext *
0x18000c3c6  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000c3cb  lea     rcx, [rbp+var_28]; this
0x18000c3cf  call    ?ReadScopeSettings@CNetworkCfgRegSettings@@QEAAXXZ; CNetworkCfgRegSettings::ReadScopeSettings(void)
0x18000c3d4  mov     edx, [rbp+var_28]; unsigned int
0x18000c3d7  call    ?SocketInit@@YAHKK@Z; SocketInit(ulong,ulong)
0x18000c3dc  test    eax, eax
0x18000c3de  jz      short loc_18000C423
0x18000c3e0  call    cs:__imp_GetLastError
0x18000c3e7  nop     dword ptr [rax+rax+00h]
0x18000c3ec  test    eax, eax
0x18000c3ee  jle     short loc_18000C3FA
0x18000c3f0  movzx   eax, ax
0x18000c3f3  or      eax, 80070000h
0x18000c3f8  test    eax, eax
0x18000c3fa  jz      loc_18000C9A9
0x18000c400  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c407  cmp     rcx, r13
0x18000c40a  jz      loc_18000C9A9
0x18000c410  test    [rcx+1Ch], bl
0x18000c413  jz      loc_18000C9A9
0x18000c419  mov     edx, 23h ; '#'
0x18000c41e  jmp     loc_18000C1BB
0x18000c423  call    ?GetNetworkAddress@@YAJXZ; GetNetworkAddress(void)
0x18000c428  test    eax, eax
0x18000c42a  jns     short loc_18000C44F
0x18000c42c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c433  cmp     rcx, r13
0x18000c436  jz      loc_18000C9A9
0x18000c43c  test    [rcx+1Ch], bl
0x18000c43f  jz      loc_18000C9A9
0x18000c445  mov     edx, 24h ; '$'
0x18000c44a  jmp     loc_18000C999
0x18000c44f  mov     rcx, rdi; struct ServiceContext *
0x18000c452  call    ?UpdateServiceCheckPoint@@YAXPEAUServiceContext@@@Z; UpdateServiceCheckPoint(ServiceContext *)
0x18000c457  cmp     cs:hLibModule, r12
0x18000c45e  jz      loc_18000C5E7
0x18000c464  xor     r9d, r9d; lpName
0x18000c467  xor     r8d, r8d; bInitialState
0x18000c46a  xor     edx, edx; bManualReset
0x18000c46c  xor     ecx, ecx; lpEventAttributes
0x18000c46e  call    cs:__imp_CreateEventA
0x18000c475  nop     dword ptr [rax+rax+00h]
0x18000c47a  mov     cs:hObject, rax
0x18000c481  test    rax, rax
0x18000c484  jnz     short loc_18000C4D2
0x18000c486  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c48d  cmp     rcx, r13
0x18000c490  jz      short loc_18000C4C9
0x18000c492  test    [rcx+1Ch], bl
0x18000c495  jz      short loc_18000C4C9
0x18000c497  call    cs:__imp_GetLastError
0x18000c49e  nop     dword ptr [rax+rax+00h]
0x18000c4a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4aa  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000c4b1  mov     edx, 25h ; '%'
0x18000c4b6  mov     r9d, eax
0x18000c4b9  mov     rcx, [rcx+10h]
0x18000c4bd  call    WPP_SF_d
0x18000c4c2  mov     rax, cs:hObject
0x18000c4c9  test    rax, rax
0x18000c4cc  jz      loc_18000C5E7
0x18000c4d2  mov     [rsp+68h+dwFlags], r12d; dwFlags
0x18000c4d7  lea     r8, ?SsdpFirewallChangeCallback@@YAXPEAXE@Z; Callback
0x18000c4de  xor     r9d, r9d; Context
0x18000c4e1  mov     [rsp+68h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18000c4e9  mov     rdx, rax; hObject
0x18000c4ec  lea     rcx, WaitHandle; phNewWaitObject
0x18000c4f3  call    cs:__imp_RegisterWaitForSingleObject
0x18000c4fa  nop     dword ptr [rax+rax+00h]
0x18000c4ff  test    eax, eax
0x18000c501  jnz     short loc_18000C546
0x18000c503  mov     cs:WaitHandle, r12
0x18000c50a  mov     rax, cs:WPP_GLOBAL_Control
0x18000c511  cmp     rax, r13
0x18000c514  jz      short loc_18000C546
0x18000c516  test    [rax+1Ch], bl
0x18000c519  jz      short loc_18000C546
0x18000c51b  call    cs:__imp_GetLastError
0x18000c522  nop     dword ptr [rax+rax+00h]
0x18000c527  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c52e  lea     r8, WPP_3f85806d784c378f4118a3193d123bc5_Traceguids
0x18000c535  mov     edx, 26h ; '&'
0x18000c53a  mov     r9d, eax
0x18000c53d  mov     rcx, [rcx+10h]
0x18000c541  call    WPP_SF_d
0x18000c546  mov     rcx, cs:hObject
0x18000c54d  test    rcx, rcx
0x18000c550  jz      loc_18000C5E7
0x18000c556  cmp     cs:WaitHandle, r12
0x18000c55d  jz      loc_18000C5E7
0x18000c563  mov     rax, cs:qword_1800456D0
0x18000c56a  lea     rdx, qword_180045690
0x18000c571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c576  test    eax, eax
0x18000c578  jz      short loc_18000C599
0x18000c57a  mov     cs:qword_180045690, r12
0x18000c581  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c588  cmp     rcx, r13
0x18000c58b  jz      short loc_18000C5E7
0x18000c58d  test    [rcx+1Ch], bl
0x18000c590  jz      short loc_18000C5E7
0x18000c592  mov     edx, 27h ; '''
0x18000c597  jmp     short loc_18000C5D4
0x18000c599  mov     rcx, cs:hObject
0x18000c5a0  lea     rdx, qword_180045678
0x18000c5a7  mov     rax, cs:qword_1800456B8
0x18000c5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5b3  test    eax, eax
0x18000c5b5  jz      short loc_18000C5E7
0x18000c5b7  mov     cs:qword_180045678, r12
0x18000c5be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5c5  cmp     rcx, r13
0x18000c5c8  jz      short loc_18000C5E7
0x18000c5ca  test    [rcx+1Ch], bl
0x18000c5cd  jz      short loc_18000C5E7
0x18000c5cf  mov     edx, 28h ; '('
0x18000c5d4  mov     rcx, [rcx+10h]
  ... truncated ...
```
