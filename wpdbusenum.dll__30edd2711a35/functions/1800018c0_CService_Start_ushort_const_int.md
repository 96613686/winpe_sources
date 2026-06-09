# CService::Start(ushort const *,int)

- ea: `0x1800018c0`
- end: `0x1800022af`
- name: `?Start@CService@@QEAAJPEBGH@Z`
- size: `2543`
- prototype: `__int64 __fastcall(CService *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800017c0`

## callees

- `0x1800018c0`
- `0x1800022c0`
- `0x1800027c0`
- `0x180002a70`
- `0x180002b00`
- `0x180002c70`
- `0x180003150`
- `0x1800036f0`
- `0x1800038d0`
- `0x180003b60`
- `0x180003ed0`
- `0x180006360`
- `0x1800067c0`
- `0x180007f28`
- `0x1800089c4`
- `0x180009394`
- `0x1800097d0`
- `0x18000e1b8`
- `0x18000e204`
- `0x18000e53c`
- `0x18000eab0`
- `0x18000ec30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000192f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001cce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001e2d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000192f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001cce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180001e2d`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001d8f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180001d8f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001957`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001fdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002128`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800019cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800019cd`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001afc`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001afc`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001a31`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001a31`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001c5a`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001f5a`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001c5a`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x180001f5a`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180001d33`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180001fd3`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180001d33`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180001fd3`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180001d66`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180001dc1`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180001d66`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180001dc1`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800021f4`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180002207`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800021f4`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180002207`

## string_xrefs

- `0x180001aa3`: `SERVICE_START_PENDING`

## pseudocode

```c
__int64 __fastcall CService::Start(CService *this, const unsigned __int16 *a2, int a3)
{
  unsigned __int16 *v4; // rbx
  unsigned int v5; // edi
  CPnPNotification *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  signed int LastError; // eax
  CPnPNotification *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  SERVICE_STATUS_HANDLE v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  int v16; // eax
  void *v17; // rdi
  CPnPNotification *v18; // rax
  __int64 ClassDevsW; // r14
  __int64 v20; // r12
  CGroupPolicy *v21; // rcx
  signed int v22; // eax
  DWORD i; // esi
  BOOL v24; // ebx
  DWORD v25; // eax
  BOOL DeviceInterfaceDetailW; // ebx
  DWORD v27; // eax
  __int64 v28; // r8
  DWORD v29; // ebp
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v30; // rax
  CWPDBus *v31; // rcx
  __int64 v32; // r9
  CWPDBus *v33; // rcx
  signed int v34; // eax
  CPnPNotification *v35; // rcx
  __int64 v36; // rdx
  CPnPNotification *v37; // rcx
  __int64 v38; // rdx
  signed int v39; // eax
  DWORD v40; // esi
  BOOL v41; // edi
  DWORD v42; // ebp
  CPnPNotification *v43; // rcx
  signed int v44; // eax
  int v45; // eax
  __int64 v46; // r8
  int v47; // eax
  CPnPNotification *v48; // rcx
  __int64 v49; // rdx
  signed int v50; // eax
  const unsigned __int16 *v51; // rdx
  CPnPNotification *v52; // rcx
  void (*v53)(void *, unsigned __int8); // r9
  CPnPNotification *v54; // rcx
  __int64 v55; // rdx
  const char *v56; // r9
  PSP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+20h] [rbp-88h]
  DWORD RequiredSize[2]; // [rsp+30h] [rbp-78h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA v60; // [rsp+38h] [rbp-70h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA v61; // [rsp+58h] [rbp-50h] BYREF

  v4 = 0;
  if ( !qword_18001F298 )
  {
    v5 = -2147418113;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 21;
LABEL_5:
      v8 = v5;
LABEL_6:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v8);
LABEL_7:
      free(0);
      Service_Release();
      goto LABEL_56;
    }
    goto LABEL_55;
  }
  Service_AddRef();
  if ( !a3 )
    Service_AddRef();
  hEvent = CreateEventW(0, 0, 0, 0);
  if ( !hEvent )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_55;
    v11 = 22;
    goto LABEL_16;
  }
  g_shutdownTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)ServiceShutdownTimerCallback, &_Service, 0);
  if ( !g_shutdownTimer )
  {
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_55;
    v11 = 23;
    goto LABEL_16;
  }
  v13 = RegisterServiceCtrlHandlerExW(L"WpdBusEnum", (LPHANDLER_FUNCTION_EX)CService::ServiceControlHandler, &_Service);
  _Service = (__int64)v13;
  if ( !v13 )
  {
    v14 = GetLastError();
    v5 = v14;
    if ( v14 > 0 )
      v5 = (unsigned __int16)v14 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_55;
    v11 = 24;
LABEL_16:
    WPP_SF_d(*((_QWORD *)v10 + 2), v11, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v5);
    goto LABEL_55;
  }
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      63,
      &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
      L"SERVICE_START_PENDING");
    v13 = (SERVICE_STATUS_HANDLE)_Service;
  }
  ServiceStatus.dwServiceType = 48;
  *(_QWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwCheckPoint = 1;
  ServiceStatus.dwWaitHint = 10000;
  if ( SetServiceStatus(v13, &ServiceStatus) )
    goto LABEL_42;
  v15 = GetLastError();
  v5 = v15;
  if ( v15 > 0 )
    v5 = (unsigned __int16)v15 | 0x80070000;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v5);
    v6 = WPP_GLOBAL_Control;
  }
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_42:
    v16 = CGroupPolicy::Create((struct CGroupPolicy **)v6);
    v5 = v16;
    if ( v16 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v7 = 26;
        v8 = (unsigned int)v16;
        goto LABEL_6;
      }
      goto LABEL_55;
    }
    *(_QWORD *)RequiredSize = operator new(4u);
    v17 = *(void **)RequiredSize;
    if ( *(_QWORD *)RequiredSize )
    {
      **(_DWORD **)RequiredSize = CWPDBus::IsOpticalEnabled();
      g_WPDBus = v17;
      v18 = (CPnPNotification *)operator new(0x18u);
      *(_QWORD *)RequiredSize = v18;
      if ( v18 )
      {
        *(_QWORD *)v18 = 0;
        *((_QWORD *)v18 + 1) = 0;
        *((_QWORD *)v18 + 2) = 0;
        g_PnPNotification = v18;
        ClassDevsW = -1;
        v20 = -1;
        *(_QWORD *)v18 = _Service;
        if ( (unsigned int)IsPortableDeviceAPIPresent() )
        {
          ClassDevsW = (__int64)SetupDiGetClassDevsW(&GUID_DEVINTERFACE_VOLUME, 0, 0, 0x12u);
          if ( ClassDevsW == -1 )
          {
            v22 = GetLastError();
            v5 = v22;
            if ( v22 > 0 )
              v5 = (unsigned __int16)v22 | 0x80070000;
            if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v5);
            }
            goto LABEL_55;
          }
          for ( i = 0; ; ++i )
          {
            RequiredSize[0] = 0;
            v60.cbSize = 32;
            memset(&v60.InterfaceClassGuid, 0, 28);
            v24 = SetupDiEnumDeviceInterfaces((HDEVINFO)ClassDevsW, 0, &GUID_DEVINTERFACE_VOLUME, i, &v60);
            v25 = GetLastError();
            if ( !v24 )
              break;
            DeviceInterfaceDetailW = SetupDiGetDeviceInterfaceDetailW((HDEVINFO)ClassDevsW, &v60, 0, 0, RequiredSize, 0);
            v27 = GetLastError();
            v29 = v27;
            if ( v27 != 122 && DeviceInterfaceDetailW )
            {
              v5 = -2147418113;
              if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, v28, v27, -2147418113);
                v4 = 0;
                goto LABEL_138;
              }
LABEL_126:
              v4 = 0;
              goto LABEL_138;
            }
            if ( !RequiredSize[0] )
            {
              v5 = -2147024883;
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
                goto LABEL_126;
              }
              v38 = 33;
              goto LABEL_125;
            }
            v30 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)malloc(RequiredSize[0]);
            v4 = (unsigned __int16 *)v30;
            if ( !v30 )
            {
              v5 = -2147024882;
              if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  34,
                  &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
                  "pDiDetailData");
              }
              goto LABEL_138;
            }
            v30->cbSize = 8;
            if ( !SetupDiGetDeviceInterfaceDetailW((HDEVINFO)ClassDevsW, &v60, v30, RequiredSize[0], 0, 0) )
            {
              v34 = GetLastError();
              v5 = v34;
              if ( v34 > 0 )
                v5 = (unsigned __int16)v34 | 0x80070000;
              v35 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
                goto LABEL_138;
              }
              v36 = 35;
LABEL_80:
              WPP_SF_d(*((_QWORD *)v35 + 2), v36, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v5);
              goto LABEL_138;
            }
            if ( (unsigned int)CWPDBus::IsValidWPDVolume(v31, v4 + 2) )
            {
              v32 = (unsigned int)_InterlockedIncrement(&g_RefCount);
              v33 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v32);
              }
              if ( (int)CWPDBus::AddPersistedVolumeShadowDevice(v33, v4 + 2) < 0 )
                Service_Release();
            }
            free(v4);
            v4 = 0;
            if ( v29 == 259 )
              goto LABEL_89;
          }
          if ( v25 != 259 )
          {
            v50 = GetLastError();
            v5 = v50;
            if ( v50 > 0 )
              v5 = (unsigned __int16)v50 | 0x80070000;
            v37 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            {
              goto LABEL_126;
            }
            v38 = 31;
LABEL_125:
            WPP_SF_d(*((_QWORD *)v37 + 2), v38, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v5);
            goto LABEL_126;
          }
          v4 = 0;
LABEL_89:
          v20 = (__int64)SetupDiGetClassDevsW(&GUID_DEVINTERFACE_BUSENUM_MTPBTH, 0, 0, 0x12u);
          if ( v20 == -1 )
          {
            v39 = GetLastError();
            v5 = v39;
            if ( v39 > 0 )
              v5 = (unsigned __int16)v39 | 0x80070000;
            v35 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            {
              goto LABEL_138;
            }
            v36 = 36;
            goto LABEL_80;
          }
          v40 = 0;
          while ( 1 )
          {
            v61.cbSize = 32;
            memset(&v61.InterfaceClassGuid, 0, 28);
            v41 = SetupDiEnumDeviceInterfaces((HDEVINFO)v20, 0, &GUID_DEVINTERFACE_BUSENUM_MTPBTH, v40, &v61);
            v42 = GetLastError();
            if ( !v41 )
              break;
            ++v40;
            Service_AddRef();
            v43 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v40);
              v43 = WPP_GLOBAL_Control;
            }
            if ( v42 == 259 )
              goto LABEL_109;
          }
          if ( v42 == 259 )
          {
            v43 = WPP_GLOBAL_Control;
LABEL_109:
            if ( v43 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_DWORD *)v43 + 7) & 0x200) != 0 )
              WPP_SF_dd(
                *((_QWORD *)v43 + 2),
                39,
                &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
                (unsigned int)g_RefCount,
                v40);
            v45 = CBthActiveConnector::CreateAndStart(
                    (struct CBthActiveConnector **)v43,
                    (struct SERVICE_STATUS_HANDLE__ *)_Service);
            if ( v45 < 0 )
            {
              v21 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  40,
                  &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids,
                  (unsigned int)v45);
              }
            }
            goto LABEL_116;
          }
          v44 = GetLastError();
          v5 = v44;
          if ( v44 > 0 )
            v5 = (unsigned __int16)v44 | 0x80070000;
          v35 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v36 = 37;
            goto LABEL_80;
          }
LABEL_138:
          SetupDiDestroyDeviceInfoList((HDEVINFO)ClassDevsW);
          goto LABEL_139;
        }
LABEL_116:
        CGroupPolicy::StartProcessGPSettings(v21);
        v47 = CService::ReportStatus((CService *)&_Service, 4, v46, 0, 0);
        v5 = v47;
        if ( v47 >= 0 )
        {
          if ( (unsigned int)IsPortableDeviceAPIPresent()
            && (v47 = CPnPNotification::RegisterNotification(v52), v5 = v47, v47 < 0) )
          {
            v48 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v49 = 42;
              goto LABEL_136;
            }
          }
          else
          {
            v47 = RegisterServiceStopCallback(
                    &qword_18001F2A0,
                    v51,
                    hEvent,
                    v53,
                    DeviceInterfaceData,
                    (__int64 (__fastcall **)(void **, const WCHAR *, void *, void (__fastcall *)(void *, unsigned __int8), __int64 *, int))qword_18001F298);
            v5 = v47;
            if ( v47 < 0 )
            {
              v48 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v49 = 44;
                goto LABEL_136;
              }
            }
          }
        }
        else
        {
          v48 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v49 = 41;
LABEL_136:
            WPP_SF_d(*((_QWORD *)v48 + 2), v49, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, (unsigned int)v47);
          }
        }
        if ( ClassDevsW != -1 )
          goto LABEL_138;
LABEL_139:
        if ( v20 != -1 )
          SetupDiDestroyDeviceInfoList((HDEVINFO)v20);
        goto LABEL_55;
      }
      g_PnPNotification = 0;
      v5 = -2147024882;
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_55;
      }
      v55 = 28;
      v56 = "g_PnPNotification";
    }
    else
    {
      g_WPDBus = 0;
      v5 = -2147024882;
      v54 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_55;
      }
      v55 = 27;
      v56 = "g_WPDBus";
    }
    WPP_SF_s(*((_QWORD *)v54 + 2), v55, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v56);
    goto LABEL_7;
  }
  if ( v6 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
  {
    v7 = 25;
    goto LABEL_5;
  }
LABEL_55:
  free(v4);
  Service_Release();
  if ( (v5 & 0x80000000) == 0 )
  {
    ResetTimerToSpawnThread();
    return v5;
  }
LABEL_56:
  CService::Stop((CService *)&_Service);
  return v5;
}

```

## disassembly

```asm
0x1800018c0  push    rbx
0x1800018c2  push    rdi
0x1800018c3  push    r13
0x1800018c5  push    r15
0x1800018c7  sub     rsp, 88h
0x1800018ce  mov     rax, cs:__security_cookie
0x1800018d5  xor     rax, rsp
0x1800018d8  mov     [rsp+0A8h+var_30], rax
0x1800018dd  xor     r13d, r13d
0x1800018e0  mov     edi, r8d
0x1800018e3  cmp     cs:qword_18001F298, r13
0x1800018ea  mov     ebx, r13d
0x1800018ed  jnz     short loc_18000193F
0x1800018ef  mov     edi, 8000FFFFh
0x1800018f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018fb  lea     r15, WPP_GLOBAL_Control
0x180001902  cmp     rcx, r15
0x180001905  jz      loc_180001CCB
0x18000190b  test    byte ptr [rcx+1Ch], 2
0x18000190f  jz      loc_180001CCB
0x180001915  mov     edx, 15h
0x18000191a  mov     r9d, edi
0x18000191d  mov     rcx, [rcx+10h]
0x180001921  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001928  call    WPP_SF_d
0x18000192d  xor     ecx, ecx; Block
0x18000192f  call    cs:__imp_free
0x180001935  call    ?Service_Release@@YAJXZ; Service_Release(void)
0x18000193a  jmp     loc_180001CE1
0x18000193f  call    ?Service_AddRef@@YAJXZ; Service_AddRef(void)
0x180001944  test    edi, edi
0x180001946  jnz     short loc_18000194D
0x180001948  call    ?Service_AddRef@@YAJXZ; Service_AddRef(void)
0x18000194d  xor     r9d, r9d; lpName
0x180001950  xor     r8d, r8d; bInitialState
0x180001953  xor     edx, edx; bManualReset
0x180001955  xor     ecx, ecx; lpEventAttributes
0x180001957  call    cs:__imp_CreateEventW
0x18000195d  mov     cs:hEvent, rax
0x180001964  test    rax, rax
0x180001967  jnz     short loc_1800019BC
0x180001969  call    cs:__imp_GetLastError
0x18000196f  mov     edi, eax
0x180001971  test    eax, eax
0x180001973  jle     short loc_18000197E
0x180001975  movzx   edi, ax
0x180001978  or      edi, 80070000h
0x18000197e  mov     rcx, cs:WPP_GLOBAL_Control
0x180001985  lea     r15, WPP_GLOBAL_Control
0x18000198c  cmp     rcx, r15
0x18000198f  jz      loc_180001CCB
0x180001995  test    byte ptr [rcx+1Ch], 2
0x180001999  jz      loc_180001CCB
0x18000199f  mov     edx, 16h
0x1800019a4  mov     rcx, [rcx+10h]
0x1800019a8  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x1800019af  mov     r9d, edi
0x1800019b2  call    WPP_SF_d
0x1800019b7  jmp     loc_180001CCB
0x1800019bc  xor     r8d, r8d; pcbe
0x1800019bf  lea     rdx, ?_Service@@3VCService@@A; pv
0x1800019c6  lea     rcx, ?ServiceShutdownTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800019cd  call    cs:__imp_CreateThreadpoolTimer
0x1800019d3  mov     cs:?g_shutdownTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * g_shutdownTimer
0x1800019da  test    rax, rax
0x1800019dd  jnz     short loc_180001A1C
0x1800019df  call    cs:__imp_GetLastError
0x1800019e5  mov     edi, eax
0x1800019e7  test    eax, eax
0x1800019e9  jle     short loc_1800019F4
0x1800019eb  movzx   edi, ax
0x1800019ee  or      edi, 80070000h
0x1800019f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019fb  lea     r15, WPP_GLOBAL_Control
0x180001a02  cmp     rcx, r15
0x180001a05  jz      loc_180001CCB
0x180001a0b  test    byte ptr [rcx+1Ch], 2
0x180001a0f  jz      loc_180001CCB
0x180001a15  mov     edx, 17h
0x180001a1a  jmp     short loc_1800019A4
0x180001a1c  lea     r8, ?_Service@@3VCService@@A; lpContext
0x180001a23  lea     rdx, ?ServiceControlHandler@CService@@SAKKKPEAX0@Z; lpHandlerProc
0x180001a2a  lea     rcx, ServiceName; "WpdBusEnum"
0x180001a31  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180001a37  mov     cs:?_Service@@3VCService@@A, rax; CService _Service
0x180001a3e  test    rax, rax
0x180001a41  jnz     short loc_180001A83
0x180001a43  call    cs:__imp_GetLastError
0x180001a49  mov     edi, eax
0x180001a4b  test    eax, eax
0x180001a4d  jle     short loc_180001A58
0x180001a4f  movzx   edi, ax
0x180001a52  or      edi, 80070000h
0x180001a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a5f  lea     r15, WPP_GLOBAL_Control
0x180001a66  cmp     rcx, r15
0x180001a69  jz      loc_180001CCB
0x180001a6f  test    byte ptr [rcx+1Ch], 2
0x180001a73  jz      loc_180001CCB
0x180001a79  mov     edx, 18h
0x180001a7e  jmp     loc_1800019A4
0x180001a83  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a8a  lea     r15, WPP_GLOBAL_Control
0x180001a91  cmp     rcx, r15
0x180001a94  jz      short loc_180001AC2
0x180001a96  test    dword ptr [rcx+1Ch], 200h
0x180001a9d  jz      short loc_180001AC2
0x180001a9f  mov     rcx, [rcx+10h]
0x180001aa3  lea     r9, aServiceStartPe; "SERVICE_START_PENDING"
0x180001aaa  mov     edx, 3Fh ; '?'
0x180001aaf  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001ab6  call    WPP_SF_S
0x180001abb  mov     rax, cs:?_Service@@3VCService@@A; CService _Service
0x180001ac2  lea     rdx, ServiceStatus; lpServiceStatus
0x180001ac9  mov     cs:ServiceStatus.dwServiceType, 30h ; '0'
0x180001ad3  mov     rcx, rax; hServiceStatus
0x180001ad6  mov     qword ptr cs:ServiceStatus.dwWin32ExitCode, r13
0x180001add  mov     qword ptr cs:ServiceStatus.dwCurrentState, 2
0x180001ae8  mov     cs:ServiceStatus.dwCheckPoint, 1
0x180001af2  mov     cs:ServiceStatus.dwWaitHint, 2710h
0x180001afc  call    cs:__imp_SetServiceStatus
0x180001b02  test    eax, eax
0x180001b04  jnz     short loc_180001B6D
0x180001b06  call    cs:__imp_GetLastError
0x180001b0c  mov     edi, eax
0x180001b0e  test    eax, eax
0x180001b10  jle     short loc_180001B1B
0x180001b12  movzx   edi, ax
0x180001b15  or      edi, 80070000h
0x180001b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b22  cmp     rcx, r15
0x180001b25  jz      short loc_180001B4C
0x180001b27  test    byte ptr [rcx+1Ch], 2
0x180001b2b  jz      short loc_180001B4C
0x180001b2d  mov     rcx, [rcx+10h]
0x180001b31  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001b38  mov     edx, 41h ; 'A'
0x180001b3d  mov     r9d, edi
0x180001b40  call    WPP_SF_d
0x180001b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b4c  test    edi, edi
0x180001b4e  jns     short loc_180001B6D
0x180001b50  cmp     rcx, r15
0x180001b53  jz      loc_180001CCB
0x180001b59  test    byte ptr [rcx+1Ch], 2
0x180001b5d  jz      loc_180001CCB
0x180001b63  mov     edx, 19h
0x180001b68  jmp     loc_18000191A
0x180001b6d  call    ?Create@CGroupPolicy@@SAJPEAPEAV1@@Z; CGroupPolicy::Create(CGroupPolicy * *)
0x180001b72  mov     edi, eax
0x180001b74  test    eax, eax
0x180001b76  jns     short loc_180001B9F
0x180001b78  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b7f  cmp     rcx, r15
0x180001b82  jz      loc_180001CCB
0x180001b88  test    byte ptr [rcx+1Ch], 2
0x180001b8c  jz      loc_180001CCB
0x180001b92  mov     edx, 1Ah
0x180001b97  mov     r9d, eax
0x180001b9a  jmp     loc_18000191D
0x180001b9f  mov     ecx, 4; Size
0x180001ba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001ba9  mov     qword ptr [rsp+0A8h+RequiredSize], rax
0x180001bae  mov     rdi, rax
0x180001bb1  test    rax, rax
0x180001bb4  jz      loc_180002246
0x180001bba  call    ?IsOpticalEnabled@CWPDBus@@KAHXZ; CWPDBus::IsOpticalEnabled(void)
0x180001bbf  mov     [rdi], eax
0x180001bc1  mov     cs:?g_WPDBus@@3PEAVCWPDBus@@EA, rdi; CWPDBus * g_WPDBus
0x180001bc8  test    rdi, rdi
0x180001bcb  jz      loc_18000224D
0x180001bd1  mov     ecx, 18h; Size
0x180001bd6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001bdb  mov     qword ptr [rsp+0A8h+RequiredSize], rax
0x180001be0  mov     rcx, rax
0x180001be3  test    rax, rax
0x180001be6  jz      loc_180002212
0x180001bec  mov     [rax], r13
0x180001bef  mov     [rax+8], r13
0x180001bf3  mov     [rax+10h], r13
0x180001bf7  mov     cs:?g_PnPNotification@@3PEAVCPnPNotification@@EA, rax; CPnPNotification * g_PnPNotification
0x180001bfe  test    rax, rax
0x180001c01  jz      loc_180002219
0x180001c07  mov     rax, cs:?_Service@@3VCService@@A; CService _Service
0x180001c0e  mov     [rsp+0A8h+arg_10], r12
0x180001c16  mov     [rsp+0A8h+var_28], r14
0x180001c1e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180001c25  mov     [rsp+0A8h+arg_0], rbp
0x180001c2d  mov     r12, r14
0x180001c30  mov     [rsp+0A8h+arg_8], rsi
0x180001c38  mov     [rcx], rax
0x180001c3b  call    ?IsPortableDeviceAPIPresent@@YAHXZ; IsPortableDeviceAPIPresent(void)
0x180001c40  test    eax, eax
0x180001c42  jz      loc_1800020E0
0x180001c48  mov     r9d, 12h; Flags
0x180001c4e  lea     rcx, GUID_DEVINTERFACE_VOLUME; ClassGuid
0x180001c55  xor     r8d, r8d; hwndParent
0x180001c58  xor     edx, edx; Enumerator
0x180001c5a  call    cs:__imp_SetupDiGetClassDevsW
0x180001c60  mov     r14, rax
0x180001c63  cmp     rax, r12
0x180001c66  jnz     loc_180001CF2
0x180001c6c  call    cs:__imp_GetLastError
0x180001c72  mov     edi, eax
0x180001c74  test    eax, eax
0x180001c76  jle     short loc_180001C81
0x180001c78  movzx   edi, ax
0x180001c7b  or      edi, 80070000h
0x180001c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c88  cmp     rcx, r15
0x180001c8b  jz      short loc_180001CAB
0x180001c8d  test    byte ptr [rcx+1Ch], 2
0x180001c91  jz      short loc_180001CAB
0x180001c93  mov     rcx, [rcx+10h]
0x180001c97  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001c9e  mov     edx, 1Eh
0x180001ca3  mov     r9d, edi
0x180001ca6  call    WPP_SF_d
0x180001cab  mov     rsi, [rsp+0A8h+arg_8]
0x180001cb3  mov     rbp, [rsp+0A8h+arg_0]
0x180001cbb  mov     r12, [rsp+0A8h+arg_10]
0x180001cc3  mov     r14, [rsp+0A8h+var_28]
0x180001ccb  mov     rcx, rbx; Block
0x180001cce  call    cs:__imp_free
0x180001cd4  call    ?Service_Release@@YAJXZ; Service_Release(void)
0x180001cd9  test    edi, edi
0x180001cdb  jns     loc_18000228D
0x180001ce1  lea     rcx, ?_Service@@3VCService@@A; this
0x180001ce8  call    ?Stop@CService@@QEAAJXZ; CService::Stop(void)
0x180001ced  jmp     loc_180002292
0x180001cf2  mov     esi, r13d
0x180001cf5  nop     word ptr [rax+rax+00000000h]
0x180001d00  xorps   xmm0, xmm0
0x180001d03  mov     [rsp+0A8h+RequiredSize], r13d
0x180001d08  lea     rax, [rsp+0A8h+var_70]
0x180001d0d  mov     [rsp+0A8h+var_70.cbSize], 20h ; ' '
0x180001d15  movups  xmmword ptr [rsp+0A8h+var_70.InterfaceClassGuid.Data1], xmm0
0x180001d1a  mov     r9d, esi; MemberIndex
0x180001d1d  mov     [rsp+0A8h+DeviceInterfaceData], rax; DeviceInterfaceData
0x180001d22  lea     r8, GUID_DEVINTERFACE_VOLUME; InterfaceClassGuid
0x180001d29  xor     edx, edx; DeviceInfoData
0x180001d2b  mov     rcx, r14; DeviceInfoSet
0x180001d2e  movups  xmmword ptr [rsp+0A8h+var_70.InterfaceClassGuid.Data4+4], xmm0
0x180001d33  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x180001d39  mov     ebx, eax
0x180001d3b  call    cs:__imp_GetLastError
0x180001d41  test    ebx, ebx
0x180001d43  jz      loc_180001F3A
0x180001d49  lea     rax, [rsp+0A8h+RequiredSize]
0x180001d4e  mov     [rsp+0A8h+DeviceInfoData], r13; DeviceInfoData
0x180001d53  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x180001d56  mov     [rsp+0A8h+DeviceInterfaceData], rax; RequiredSize
0x180001d5b  xor     r8d, r8d; DeviceInterfaceDetailData
0x180001d5e  lea     rdx, [rsp+0A8h+var_70]; DeviceInterfaceData
0x180001d63  mov     rcx, r14; DeviceInfoSet
0x180001d66  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180001d6c  mov     ebx, eax
0x180001d6e  call    cs:__imp_GetLastError
0x180001d74  mov     ebp, eax
0x180001d76  cmp     eax, 7Ah ; 'z'
0x180001d79  jz      short loc_180001D83
0x180001d7b  test    ebx, ebx
0x180001d7d  jnz     loc_180001E49
0x180001d83  mov     ecx, [rsp+0A8h+RequiredSize]; Size
0x180001d87  test    ecx, ecx
0x180001d89  jz      loc_180001F11
0x180001d8f  call    cs:__imp_malloc
0x180001d95  mov     rbx, rax
0x180001d98  test    rax, rax
0x180001d9b  jz      loc_180001ED1
0x180001da1  mov     dword ptr [rax], 8
0x180001da7  lea     rdx, [rsp+0A8h+var_70]; DeviceInterfaceData
0x180001dac  mov     r9d, [rsp+0A8h+RequiredSize]; DeviceInterfaceDetailDataSize
0x180001db1  mov     r8, rax; DeviceInterfaceDetailData
0x180001db4  mov     [rsp+0A8h+DeviceInfoData], r13; DeviceInfoData
0x180001db9  mov     rcx, r14; DeviceInfoSet
0x180001dbc  mov     [rsp+0A8h+DeviceInterfaceData], r13; RequiredSize
0x180001dc1  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180001dc7  test    eax, eax
0x180001dc9  jz      loc_180001E85
0x180001dcf  lea     rdx, [rbx+4]; unsigned __int16 *
0x180001dd3  call    ?IsValidWPDVolume@CWPDBus@@QEAAHPEBG@Z; CWPDBus::IsValidWPDVolume(ushort const *)
0x180001dd8  test    eax, eax
0x180001dda  jz      short loc_180001E2A
0x180001ddc  mov     r9d, 1
0x180001de2  lock xadd cs:?g_RefCount@@3JA, r9d; long g_RefCount
0x180001deb  inc     r9d
0x180001dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180001df5  cmp     rcx, r15
0x180001df8  jz      short loc_180001E18
0x180001dfa  test    dword ptr [rcx+1Ch], 200h
0x180001e01  jz      short loc_180001E18
0x180001e03  mov     rcx, [rcx+10h]
0x180001e07  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001e0e  mov     edx, 12h
0x180001e13  call    WPP_SF_d
0x180001e18  lea     rdx, [rbx+4]; unsigned __int16 *
0x180001e1c  call    ?AddPersistedVolumeShadowDevice@CWPDBus@@QEAAJPEBG@Z; CWPDBus::AddPersistedVolumeShadowDevice(ushort const *)
0x180001e21  test    eax, eax
0x180001e23  jns     short loc_180001E2A
  ... truncated ...
```
