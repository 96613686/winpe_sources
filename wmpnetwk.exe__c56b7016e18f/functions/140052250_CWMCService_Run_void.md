# CWMCService::Run(void)

- ea: `0x140052250`
- end: `0x140053874`
- name: `?Run@CWMCService@@UEAAXXZ`
- size: `5668`
- prototype: `void __fastcall(CWMCService *__hidden this)`
- caller_count: `0`
- callee_count: `60`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1400028cc`
- `0x140006d70`
- `0x140008eac`
- `0x14000b3b0`
- `0x14000c920`
- `0x14000cb08`
- `0x14000faac`
- `0x140018df0`
- `0x140024688`
- `0x14002f644`
- `0x140030cec`
- `0x140032eec`
- `0x1400369c0`
- `0x140036e40`
- `0x140037334`
- `0x140037824`
- `0x1400378e0`
- `0x1400398e4`
- `0x14003af24`
- `0x14003b2b8`
- `0x14003b324`
- `0x14003b690`
- `0x14003b8f4`
- `0x14003bf64`
- `0x14003c444`
- `0x14003c590`
- `0x14003d754`
- `0x14003d9ec`
- `0x14003e064`
- `0x14003f17c`
- `0x14003f1bc`
- `0x140045f20`
- `0x140046020`
- `0x140046358`
- `0x14004639c`
- `0x140046d00`
- `0x140047798`
- `0x1400488f4`
- `0x14004a834`
- `0x14004aa4c`
- `0x14004af64`
- `0x14004b730`
- `0x14004c6ac`
- `0x14004cb48`
- `0x14004d1e4`
- `0x140052250`
- `0x14005387c`
- `0x140054490`
- `0x140056c8c`
- `0x140064508`

## import_xrefs

- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400529a9`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140052a2d`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140052ab1`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14005313f`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140053404`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140053514`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400529a9`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140052a2d`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140052ab1`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14005313f`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140053404`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140053514`
- `KERNEL32!GetCurrentProcess` at `0x140052cc0`
- `KERNEL32!GetCurrentProcess` at `0x140052cc0`
- `KERNEL32!EnterCriticalSection` at `0x140052b06`
- `KERNEL32!EnterCriticalSection` at `0x140052bd2`
- `KERNEL32!EnterCriticalSection` at `0x140053450`
- `KERNEL32!EnterCriticalSection` at `0x140052b06`
- `KERNEL32!EnterCriticalSection` at `0x140052bd2`
- `KERNEL32!EnterCriticalSection` at `0x140053450`
- `KERNEL32!LeaveCriticalSection` at `0x140052b35`
- `KERNEL32!LeaveCriticalSection` at `0x140052c30`
- `KERNEL32!LeaveCriticalSection` at `0x1400534d7`
- `KERNEL32!LeaveCriticalSection` at `0x140052b35`
- `KERNEL32!LeaveCriticalSection` at `0x140052c30`
- `KERNEL32!LeaveCriticalSection` at `0x1400534d7`
- `KERNEL32!SetProcessWorkingSetSize` at `0x140052cd3`
- `KERNEL32!SetProcessWorkingSetSize` at `0x140052cd3`
- `KERNEL32!ResetEvent` at `0x140053120`
- `KERNEL32!ResetEvent` at `0x140053120`
- `KERNEL32!GetTickCount64` at `0x140052b20`
- `KERNEL32!GetTickCount64` at `0x140052b95`
- `KERNEL32!GetTickCount64` at `0x140052bb1`
- `KERNEL32!GetTickCount64` at `0x140052bc6`
- `KERNEL32!GetTickCount64` at `0x140052c58`
- `KERNEL32!GetTickCount64` at `0x140052ce1`
- `KERNEL32!GetTickCount64` at `0x140052b20`
- `KERNEL32!GetTickCount64` at `0x140052b95`
- `KERNEL32!GetTickCount64` at `0x140052bb1`
- `KERNEL32!GetTickCount64` at `0x140052bc6`
- `KERNEL32!GetTickCount64` at `0x140052c58`
- `KERNEL32!GetTickCount64` at `0x140052ce1`
- `KERNEL32!CreateEventW` at `0x1400527f8`
- `KERNEL32!CreateEventW` at `0x14005280f`
- `KERNEL32!CreateEventW` at `0x140052826`
- `KERNEL32!CreateEventW` at `0x140052848`
- `KERNEL32!CreateEventW` at `0x14005286d`
- `KERNEL32!CreateEventW` at `0x140052884`
- `KERNEL32!CreateEventW` at `0x1400527f8`
- `KERNEL32!CreateEventW` at `0x14005280f`
- `KERNEL32!CreateEventW` at `0x140052826`
- `KERNEL32!CreateEventW` at `0x140052848`
- `KERNEL32!CreateEventW` at `0x14005286d`
- `KERNEL32!CreateEventW` at `0x140052884`
- `KERNEL32!SetLastError` at `0x1400536dd`
- `KERNEL32!SetLastError` at `0x1400536dd`
- `KERNEL32!CloseHandle` at `0x1400535ef`
- `KERNEL32!CloseHandle` at `0x140053608`
- `KERNEL32!CloseHandle` at `0x140053621`
- `KERNEL32!CloseHandle` at `0x14005363a`
- `KERNEL32!CloseHandle` at `0x1400536ce`
- `KERNEL32!CloseHandle` at `0x1400535ef`
- `KERNEL32!CloseHandle` at `0x140053608`
- `KERNEL32!CloseHandle` at `0x140053621`
- `KERNEL32!CloseHandle` at `0x14005363a`
- `KERNEL32!CloseHandle` at `0x1400536ce`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140052ddd`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x140052ddd`
- `USER32!PeekMessageW` at `0x140052d4e`
- `USER32!PeekMessageW` at `0x140052d7c`
- `USER32!PeekMessageW` at `0x140052d4e`
- `USER32!PeekMessageW` at `0x140052d7c`
- `USER32!DispatchMessageW` at `0x140052d5f`
- `USER32!DispatchMessageW` at `0x140052d5f`
- `USERENV!RegisterGPNotification` at `0x140052988`
- `USERENV!RegisterGPNotification` at `0x140052988`
- `USERENV!UnregisterGPNotification` at `0x140052eb0`
- `USERENV!UnregisterGPNotification` at `0x140052eb0`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x14005323c`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1400532d0`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x14005323c`
- `HTTPAPI!HttpQueryServiceConfiguration` at `0x1400532d0`
- `HTTPAPI!HttpInitialize` at `0x140053190`
- `HTTPAPI!HttpInitialize` at `0x140053190`
- `HTTPAPI!HttpTerminate` at `0x140053379`
- `HTTPAPI!HttpTerminate` at `0x140053379`

## string_xrefs

- `0x14005295b`: `SYSTEM\CurrentControlSet\Services\HTTP\Parameters\UrlAclInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall CWMCService::Run(CWMCService *this)
{
  CWMCService *v2; // rcx
  CWMCService *v3; // rcx
  PVOID *v4; // rcx
  CMACAddressControl *v5; // rax
  int v6; // r14d
  __int64 v7; // xmm0_8
  __int16 v8; // ax
  int v9; // eax
  unsigned int started; // eax
  unsigned int v11; // ebx
  int v12; // eax
  int MediaDevices; // eax
  unsigned int v14; // edx
  CServiceControl *v15; // rcx
  HANDLE v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // edx
  unsigned int v19; // eax
  unsigned int v20; // edx
  unsigned int v21; // eax
  unsigned int v22; // edx
  struct _RTL_CRITICAL_SECTION *v23; // r13
  char *v24; // rbx
  ULONGLONG TickCount64; // rax
  PVOID *v26; // r10
  DWORD v27; // r15d
  unsigned int v28; // r15d
  __int64 v29; // rcx
  ULONGLONG v30; // rbx
  HANDLE CurrentProcess; // rax
  DWORD v32; // eax
  __int64 v33; // r8
  __int64 v34; // rcx
  unsigned int v35; // ebx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r8
  __int64 v39; // r9
  unsigned int v40; // edx
  ULONG v41; // ebx
  unsigned int v42; // ecx
  ULONG v43; // ebx
  unsigned int v44; // edx
  void *v45; // r15
  unsigned int v46; // edx
  __int64 v47; // r9
  __int64 v48; // r9
  unsigned int v49; // ecx
  __int64 v50; // rdx
  unsigned int v51; // eax
  unsigned int v52; // edx
  CMediaServer ***NextValue; // rax
  CMediaServer **v54; // rbx
  int v55; // eax
  unsigned int v56; // ecx
  CNetworkEvents *v57; // rbx
  CNetworkEvents *v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  PVOID *v62; // r10
  __int64 v63; // rcx
  int v64; // eax
  __int64 v65; // rcx
  ULONG fAsynchronous; // [rsp+20h] [rbp-E0h]
  CNetworkEvents *v67; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pReturnLength[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v69; // [rsp+50h] [rbp-B0h] BYREF
  int v70; // [rsp+54h] [rbp-ACh]
  unsigned __int16 *v71; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v72; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+68h] [rbp-98h]
  __int64 v74; // [rsp+70h] [rbp-90h] BYREF
  __int64 v75; // [rsp+78h] [rbp-88h]
  int v76; // [rsp+80h] [rbp-80h]
  int v77; // [rsp+84h] [rbp-7Ch]
  CMACAddressControl *v78; // [rsp+88h] [rbp-78h] BYREF
  __int64 v79; // [rsp+90h] [rbp-70h] BYREF
  ULONGLONG v80; // [rsp+98h] [rbp-68h]
  HKEY v81[3]; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v82[3]; // [rsp+B8h] [rbp-48h] BYREF
  HKEY hKey[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 pInput; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v85; // [rsp+F8h] [rbp-8h]
  __int128 v86; // [rsp+100h] [rbp+0h]
  int v87; // [rsp+110h] [rbp+10h]
  __int64 v88; // [rsp+118h] [rbp+18h] BYREF
  __int64 v89; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v90[8]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v91; // [rsp+130h] [rbp+30h] BYREF
  __int128 v92; // [rsp+138h] [rbp+38h] BYREF
  __int64 v93; // [rsp+148h] [rbp+48h]
  __int128 v94; // [rsp+150h] [rbp+50h]
  int v95; // [rsp+160h] [rbp+60h]
  _BYTE v96[16]; // [rsp+168h] [rbp+68h] BYREF
  __int128 pOutput; // [rsp+178h] [rbp+78h] BYREF
  tagMSG Msg; // [rsp+188h] [rbp+88h] BYREF
  struct _EVENT_DESCRIPTOR v99; // [rsp+1B8h] [rbp+B8h] BYREF
  HANDLE hEvent; // [rsp+1D0h] [rbp+D0h] BYREF
  HANDLE hObject; // [rsp+1D8h] [rbp+D8h]
  HANDLE EventW; // [rsp+1E0h] [rbp+E0h]
  __int64 v103; // [rsp+1E8h] [rbp+E8h]
  HANDLE v104; // [rsp+1F0h] [rbp+F0h]
  __int64 v105; // [rsp+1F8h] [rbp+F8h]
  void *v106; // [rsp+200h] [rbp+100h]
  HANDLE v107; // [rsp+208h] [rbp+108h]
  _QWORD v108[3]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v109[16]; // [rsp+228h] [rbp+128h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  memset(v108, 0, sizeof(v108));
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)v108,
                        HKEY_LOCAL_MACHINE,
                        L"SOFTWARE\\Microsoft\\Windows Media Player NSS\\3.0\\Devices",
                        0x20106u) )
  {
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v108, L"AliveDeviceCount", 0);
    ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v108, L"FunctionalDMRCount", 0);
    ATL::CRegKey::Close((ATL::CRegKey *)v108);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v108);
  if ( !CWMCService::AnySessions(v2) && !(unsigned int)CWMCService::AnyUsersWantSharing(v3) )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
        WPP_SF_(v4[2], 90, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
    }
    return;
  }
  v77 = 0;
  v76 = 0;
  v89 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v88);
  v99 = 0;
  v78 = (CMACAddressControl *)operator new(0x268u);
  v5 = CMACAddressControl::CMACAddressControl(v78);
  *((_QWORD *)this + 43) = v5;
  if ( !v5 )
  {
    v6 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
    }
    v99.Id = 14321;
    v7 = *(_QWORD *)((char *)&WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY + 2);
    *(_DWORD *)((char *)&v99.Keyword + 2) = *(_DWORD *)((char *)&WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY + 10);
    v8 = HIWORD(WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY);
LABEL_50:
    HIWORD(v99.Keyword) = v8;
    *(_QWORD *)&v99.Version = v7;
    goto LABEL_51;
  }
  (*(void (__fastcall **)(__int64))(*((_QWORD *)v5 + 1) + 8LL))((__int64)v5 + 8);
  v9 = CMACAddressControl::Init(*((CMACAddressControl **)this + 43), &v99);
  v6 = v9;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v9 >> 31) & 0xFFFFFFFD) + 5) )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      92,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      (unsigned int)v9);
  }
  if ( v6 >= 0 )
  {
    CRendererDevicesDB::CRendererDevicesDB((CRendererDevicesDB *)&v78);
    if ( (unsigned int)IsWindowsSetupComplete() )
    {
      v72 = 0;
      v73 = 0;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        (void **)&v67,
        (char *)L"00-00-00-00-00-00");
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
        &v72,
        &v67);
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v67);
      v92 = 0;
      v93 = 0;
      v94 = 0;
      v95 = 10;
      v74 = 0;
      v75 = 0;
      CDevicesDB::DeleteAllNewDevices((CDevicesDB *)&v78, (__int64)&v74);
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v74);
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v74);
      ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v92);
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v72);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
    }
    CDevicesDB::CreateDevice((CDevicesDB *)&v78, L"00-00-00-00-00-00");
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v79);
    v77 = 1;
    v6 = InitializeNetworkMonitoring(&v99);
    if ( v6 >= 0 )
    {
      started = StartNetworkMonitoring();
      v11 = started;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, started);
      }
      if ( v11 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v67);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
          &v67,
          L"%d",
          v11);
        CNTService::LogEvent(this, &WMC_W_SERVICE_IPV4_DISABLED, (const unsigned __int16 *)v67, 0, 0);
        *((_DWORD *)this + 35) = 1;
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v67);
      }
      else
      {
        v76 = 1;
      }
      v12 = CWMCService::CreateContentProviderFactories(this, &v99);
      v6 = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v12 >> 31) & 0xFFFFFFFD) + 5) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
          (unsigned int)v12);
      }
      if ( v6 >= 0 )
      {
        MediaDevices = CWMCService::CreateMediaDevices(this);
        v6 = MediaDevices;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((MediaDevices >> 31) & 0xFFFFFFFD) + 5) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
            (unsigned int)MediaDevices);
        }
        v99.Id = 14337;
        v7 = 133120;
        *(_DWORD *)((char *)&v99.Keyword + 2) = 0;
        v8 = 0x4000;
        goto LABEL_50;
      }
    }
  }
LABEL_51:
  CServiceControl::CServiceControl((CServiceControl *)&v92);
  CServiceControl::SetSubStatus(v15, v14);
  if ( v6 < 0 )
  {
    if ( !v99.Id )
    {
      v99.Id = 14333;
      *(_QWORD *)&v99.Version = 133120;
      *(_DWORD *)((char *)&v99.Keyword + 2) = 0;
      HIWORD(v99.Keyword) = 0x4000;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v67);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
      &v67,
      L"0x%08x",
      (unsigned int)v6);
    CNTService::LogEvent(this, &v99, *((const unsigned __int16 **)this + 5), (const unsigned __int16 *)v67, 0);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v67);
    goto LABEL_244;
  }
  v67 = 0;
  memset_0(&hEvent, 0, 0x40u);
  hEvent = CreateEventW(0, 0, 0, 0);
  hObject = CreateEventW(0, 0, 0, 0);
  EventW = CreateEventW(0, 1, 0, 0);
  v103 = *((_QWORD *)this + 11);
  v104 = CreateEventW(0, 0, 0, 0);
  v105 = *((_QWORD *)this + 80);
  v106 = CreateEventW(0, 0, 0, 0);
  v16 = CreateEventW(0, 0, 0, 0);
  v107 = v16;
  if ( !hEvent || !hObject || !EventW || !v103 || !v104 || !v105 || !v106 || !v16 )
  {
    v6 = -2147024882;
    v99.Id = 14321;
    *(_QWORD *)&v99.Version = *(_QWORD *)((char *)&WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY + 2);
    *(_DWORD *)((char *)&v99.Keyword + 2) = *(_DWORD *)((char *)&WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY + 10);
    HIWORD(v99.Keyword) = HIWORD(WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY);
    goto LABEL_223;
  }
  v6 = CNetworkEvents::CreateInstance(hObject, v106, &v67);
  v99.Id = 14333;
  *(_QWORD *)&v99.Version = 133120;
  *(_DWORD *)((char *)&v99.Keyword + 2) = 0;
  HIWORD(v99.Keyword) = 0x4000;
  if ( v6 < 0 )
  {
LABEL_223:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(&v71);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
      &v71,
      L"0x%08x",
      (unsigned int)v6);
    CNTService::LogEvent(this, &v99, *((const unsigned __int16 **)this + 5), v71, 0);
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v71);
    goto LABEL_224;
  }
  memset(hKey, 0, sizeof(hKey));
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)hKey,
                        HKEY_LOCAL_MACHINE,
                        L"SYSTEM\\CurrentControlSet\\Services\\HTTP\\Parameters\\UrlAclInfo",
                        0x110u) )
  {
    RegisterGPNotification(hEvent, 1);
    v17 = RegNotifyChangeKeyValue(hKey[0], 0, 4u, EventW, 1);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v18 = 5;
      if ( v17 )
        v18 = 2;
      if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v18 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v17);
    }
    memset(v82, 0, sizeof(v82));
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)v82,
                          HKEY_LOCAL_MACHINE,
                          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winsat",
                          0x110u) )
    {
      v19 = RegNotifyChangeKeyValue(v82[0], 0, 4u, v104, 1);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v20 = 5;
        if ( v19 )
          v20 = 2;
        if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v20 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v19);
      }
    }
    memset(v81, 0, sizeof(v81));
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)v81,
                          HKEY_LOCAL_MACHINE,
                          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Setup\\State",
                          0x110u) )
    {
      v21 = RegNotifyChangeKeyValue(v81[0], 0, 4u, v107, 1);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v22 = 5;
        if ( v21 )
          v22 = 2;
        if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v22 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v21);
      }
    }
    v70 = 0;
    v80 = 0;
    v23 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    v24 = (char *)this + 272;
    if ( ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetStartPosition((char *)this + 272) )
    {
      TickCount64 = GetTickCount64();
      MyInterlockedExchangeMax64((volatile unsigned __int64 *)this + 14, TickCount64);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    *((_DWORD *)this + 158) = 1;
    if ( *((_DWORD *)this + 18) == 1 )
    {
      v26 = (PVOID *)WPP_GLOBAL_Control;
      do
      {
        if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 2) != 0 && *((_BYTE *)v26 + 25) >= 4u )
          WPP_SF_(v26[2], 100, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
        v27 = -1;
        CNTService::UpdatePowerManagementSettings(this);
        if ( !*((_DWORD *)this + 27)
          && *((_QWORD *)this + 14) + 1000 * (unsigned __int64)g_dwIdleSecondsUntilSleep > GetTickCount64() )
        {
          GetTickCount64();
          v28 = *((_DWORD *)this + 28) + 1000 * g_dwIdleSecondsUntilSleep;
          v27 = v28 - GetTickCount64();
        }
        EnterCriticalSection(v23);
        *(_QWORD *)pReturnLength = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetStartPosition(v24);
        while ( *(_QWORD *)pReturnLength )
        {
          v29 = *(_QWORD *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNextValue(
                             v24,
                             pReturnLength);
          v69 = 0;
          (*(void (__fastcall **)(_QWORD, DWORD *))(**(_QWORD **)(v29 + 8) + 248LL))(*(_QWORD *)(v29 + 8), &v69);
          if ( v27 >= v69 )
            v27 = v69;
        }
        LeaveCriticalSection(v23);
        if ( v70 )
        {
          if ( *((_QWORD *)this + 14) > v80 )
          {
            if ( v27 >= g_dwIdleMillisecondsUntilMemoryFlush )
              v27 = g_dwIdleMillisecondsUntilMemoryFlush;
            v70 = 0;
          }
        }
        else if ( !*((_DWORD *)this + 27) )
        {
          v30 = g_dwIdleMillisecondsUntilMemoryFlush + *((_QWORD *)this + 14);
          if ( v30 < GetTickCount64() )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
            }
            ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
              (__int64)v96,
              (struct _RTL_CRITICAL_SECTION *)((char *)this + 648));
            ATL::CComPtrBase<INetworkConnection>::Release((char *)this + 688);
            ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)v96);
            CurrentProcess = GetCurrentProcess();
            SetProcessWorkingSetSize(CurrentProcess, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFFFFFFFFFFuLL);
            v70 = 1;
            v80 = GetTickCount64();
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
            }
          }
          v24 = (char *)this + 272;
        }
        memset(&Msg, 0, sizeof(Msg));
        if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          do
            DispatchMessageW(&Msg);
          while ( PeekMessageW(&Msg, 0, 0, 0, 1u) );
          v23 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v27);
        }
        v32 = MsgWaitForMultipleObjectsEx(8u, &hEvent, v27, 0x1CFFu, 2u);
        if ( v32 )
        {
          switch ( v32 )
          {
            case 1u:
              if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
                McGenEventWrite_EventWriteTransfer(1, WMC_Handle_Network_Change_Start, v33, 1, v109);
              if ( (unsigned int)IsWindowsSetupComplete() )
              {
                v74 = 0;
                v75 = 0;
                CMACAddressControl::GetRecentDeviceIDs(*((CMACAddressControl **)this + 43));
                ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
                  (void **)&v78,
                  (char *)L"00-00-00-00-00-00");
                ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Add(
                  &v74,
                  &v78);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v78);
                pInput = 0;
                v85 = 0;
                v86 = 0;
                v87 = 10;
                CNetworkEvents::GetListOfDisconnectedNetworks(v67, &pInput);
                v72 = 0;
                v73 = 0;
                if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
                  McTemplateU0qq_EventWriteTransfer(v34, WMC_Cleanup_Devices_Start, 0, (unsigned int)v85);
                CRendererDevicesDB::CRendererDevicesDB((CRendererDevicesDB *)v90);
                CDevicesDB::DeleteAllNewDevices((CDevicesDB *)v90, (__int64)&v72);
                v35 = v73;
                ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v72);
                if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
                  McTemplateU0qq_EventWriteTransfer(v36, WMC_Cleanup_Devices_Stop, 0, v35);
                ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v91);
                ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v72);
                ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&pInput);
                ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::RemoveAll(&v74);
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
              }
              CWMCService::UpdateSharingStatus(this);
              if ( (Microsoft_Windows_WMPNSS_ServiceEnableBits & 0x20) != 0 )
                McGenEventWrite_EventWriteTransfer(v37, WMC_Handle_Network_Change_Stop, v38, 1, v108);
              goto LABEL_130;
            case 2u:
              ResetEvent(EventW);
              v39 = (unsigned int)RegNotifyChangeKeyValue(hKey[0], 0, 4u, EventW, 1);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v40 = 5;
                if ( (_DWORD)v39 )
                  v40 = 2;
                if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v40 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    108,
                    &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    v39);
              }
              LODWORD(v71) = 1;
              v41 = HttpInitialize((HTTPAPI_VERSION)1, 2u, 0);
              v26 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v42 = 5;
                if ( v41 )
                  v42 = 2;
                if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v42 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    109,
                    &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    v41);
                  v26 = (PVOID *)WPP_GLOBAL_Control;
                }
              }
              if ( v41 )
                goto LABEL_131;
              *(_QWORD *)&pInput = 0;
              v85 = 0;
              pOutput = 0;
              *((_QWORD *)&pInput + 1) = L"http://+:10243/WMPNSSv4/";
              pReturnLength[0] = 0;
              v43 = HttpQueryServiceConfiguration(
                      0,
                      HttpServiceConfigUrlAclInfo,
                      &pInput,
                      0x18u,
                      &pOutput,
                      0x10u,
                      pReturnLength,
                      0);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v44 = 5;
                if ( v43 )
                  v44 = 2;
                if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v44 )
                {
                  fAsynchronous = pReturnLength[0];
                  WPP_SF_Dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    110,
                    &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    v43);
                }
              }
              if ( v43 == 122 )
              {
                v45 = operator new[](pReturnLength[0]);
                v43 = HttpQueryServiceConfiguration(
                        0,
                        HttpServiceConfigUrlAclInfo,
                        &pInput,
                        0x18u,
                        v45,
                        pReturnLength[0],
                        pReturnLength,
                        0);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v46 = 5;
                  if ( v43 )
                    v46 = 2;
                  if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v46 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      111,
                      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                      v43);
                }
                operator delete(v45);
              }
              if ( !v43 )
              {
                v47 = (unsigned int)CWMCService::CreateMediaDevices(this);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)((((int)v47 >> 31) & 0xFFFFFFFD) + 5) )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    112,
                    &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    v47);
                }
              }
              v48 = HttpTerminate(2u, 0);
              v26 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
                goto LABEL_131;
              v49 = 5;
              if ( (_DWORD)v48 )
                v49 = 2;
              if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) < v49 )
                goto LABEL_131;
              v50 = 113;
LABEL_196:
              WPP_SF_d(v26[2], v50, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v48);
              goto LABEL_130;
            case 3u:
              goto LABEL_198;
            case 4u:
              v51 = RegNotifyChangeKeyValue(v82[0], 0, 4u, v104, 1);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v52 = 5;
                if ( v51 )
                  v52 = 2;
                if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v52 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    114,
                    &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    v51);
              }
              EnterCriticalSection(v23);
              for ( *(_QWORD *)pReturnLength = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetStartPosition(v24);
                    *(_QWORD *)pReturnLength;
                    v24 = (char *)this + 272 )
              {
                NextValue = (CMediaServer ***)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNextValue(
                                                v24,
                                                pReturnLength);
                v54 = *NextValue;
                v55 = CMediaServer::OnWinSATChanged(**NextValue);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                  && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v55 >> 31) & 0xFFFFFFFD) + 5) )
                {
                  WPP_SF_dS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    115,
                    (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
                    v55,
                    (__int64)v54[2]);
                }
              }
              LeaveCriticalSection(v23);
              v6 = 0;
              goto LABEL_130;
          }
          if ( v32 != 5 )
          {
            if ( v32 == 6 )
            {
LABEL_198:
              CWMCService::UpdateSharingStatus(this);
              goto LABEL_130;
            }
            if ( v32 != 7 )
              goto LABEL_130;
            v48 = (unsigned int)RegNotifyChangeKeyValue(v81[0], 0, 4u, v107, 1);
            v26 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_131;
            v56 = 5;
            if ( (_DWORD)v48 )
              v56 = 2;
            if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) < v56 )
              goto LABEL_131;
            v50 = 116;
            goto LABEL_196;
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
          }
          if ( (unsigned int)IsHMEAllowedByGroupPolicy() )
          {
            v26 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            {
              goto LABEL_131;
            }
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
          }
          else
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
            }
            CNTService::LogEvent(
              this,
              &WMC_E_SERVICE_GROUP_POLICY_SHUTDOWN,
              *((const unsigned __int16 **)this + 5),
              0,
              0);
            CNTService::HandlerEx(5u, 0, 0, this);
          }
        }
LABEL_130:
        v26 = (PVOID *)WPP_GLOBAL_Control;
LABEL_131:
        v24 = (char *)this + 272;
      }
      while ( *((_DWORD *)this + 18) == 1 );
    }
    *((_DWORD *)this + 158) = 0;
    UnregisterGPNotification(hEvent);
    ATL::CRegKey::Close((ATL::CRegKey *)v81);
    ATL::CRegKey::Close((ATL::CRegKey *)v82);
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_224:
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( EventW )
  {
    CloseHandle(EventW);
    EventW = 0;
  }
  if ( v104 )
  {
    CloseHandle(v104);
    v104 = 0;
  }
  v57 = v67;
  if ( v67 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_cbeafb788a223e71a32231e8bae35356_Traceguids);
    CNetworkEvents::DisconnectNetProfile(v57);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_cbeafb788a223e71a32231e8bae35356_Traceguids);
    v58 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(CNetworkEvents *))(*(_QWORD *)v58 + 16LL))(v58);
    }
  }
  if ( v107 )
  {
    CloseHandle(v107);
    v107 = 0;
  }
  SetLastError(0);
  ShellAggregateResultItem::~ShellAggregateResultItem((ShellAggregateResultItem *)&v67);
LABEL_244:
  CWMCService::DestroyMediaDevices(this);
  v62 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, 0);
    v62 = (PVOID *)WPP_GLOBAL_Control;
  }
  v63 = *((_QWORD *)this + 45);
  if ( !v63 )
    goto LABEL_253;
  v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 64LL))(v63);
  v61 = (unsigned int)v64;
  v62 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (int)(((v64 >> 31) & 0xFFFFFFFD) + 5) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        118,
        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        (unsigned int)v64);
      v62 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_253:
    if ( v62 != &WPP_GLOBAL_Control && (*((_BYTE *)v62 + 28) & 2) != 0 && *((_BYTE *)v62 + 25) >= 5u )
    {
      WPP_SF_q(v62[2], 119, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, *((_QWORD *)this + 45));
      v62 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v65 = *((_QWORD *)this + 45);
  if ( v65 )
  {
    *((_QWORD *)this + 45) = 0;
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64, ULONG))(*(_QWORD *)v65 + 16LL))(
      v65,
      v59,
      v60,
      v61,
      fAsynchronous);
    v62 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v76 )
  {
    StopNetworkMonitoring();
    v62 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v77 )
  {
    ShutdownNetworkMonitoring();
    v62 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v62 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v62 + 28) & 1) != 0
    && *((unsigned __int8 *)v62 + 25) >= (int)(((v6 >> 31) & 0xFFFFFFFD) + 5) )
  {
    WPP_SF_d(v62[2], 120, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, (unsigned int)v6);
  }
  CServiceControl::~CServiceControl((CServiceControl *)&v92);
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v88);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v89);
}

```

## disassembly

```asm
0x140052250  push    rbp
0x140052252  push    rbx
0x140052253  push    rsi
0x140052254  push    rdi
0x140052255  push    r12
0x140052257  push    r13
0x140052259  push    r14
0x14005225b  push    r15
0x14005225d  lea     rbp, [rsp-148h]
0x140052265  sub     rsp, 248h
0x14005226c  mov     rax, cs:__security_cookie
0x140052273  xor     rax, rsp
0x140052276  mov     [rbp+180h+var_48], rax
0x14005227d  mov     rsi, rcx
0x140052280  lea     r13, WPP_GLOBAL_Control
0x140052287  mov     ebx, 1
0x14005228c  lea     r12, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140052293  mov     rcx, cs:WPP_GLOBAL_Control
0x14005229a  cmp     rcx, r13
0x14005229d  jz      short loc_1400522B3
0x14005229f  test    [rcx+1Ch], bl
0x1400522a2  jz      short loc_1400522B3
0x1400522a4  lea     edx, [rbx+57h]
0x1400522a7  mov     r8, r12
0x1400522aa  mov     rcx, [rcx+10h]
0x1400522ae  call    WPP_SF_
0x1400522b3  xor     r15d, r15d
0x1400522b6  mov     [rbp+180h+var_70], r15
0x1400522bd  mov     [rbp+180h+var_68], r15
0x1400522c4  mov     [rbp+180h+var_60], r15
0x1400522cb  mov     r9d, 20106h; unsigned int
0x1400522d1  lea     r8, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows Media Play"...
0x1400522d8  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400522df  lea     rcx, [rbp+180h+var_70]; this
0x1400522e6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400522eb  test    eax, eax
0x1400522ed  jnz     short loc_140052327
0x1400522ef  xor     r8d, r8d; unsigned int
0x1400522f2  lea     rdx, aAlivedevicecou; "AliveDeviceCount"
0x1400522f9  lea     rcx, [rbp+180h+var_70]; this
0x140052300  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x140052305  xor     r8d, r8d; unsigned int
0x140052308  lea     rdx, aFunctionaldmrc; "FunctionalDMRCount"
0x14005230f  lea     rcx, [rbp+180h+var_70]; this
0x140052316  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14005231b  lea     rcx, [rbp+180h+var_70]; this
0x140052322  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140052327  lea     rcx, [rbp+180h+var_70]; this
0x14005232e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140052333  call    ?AnySessions@CWMCService@@AEAAHXZ; CWMCService::AnySessions(void)
0x140052338  test    eax, eax
0x14005233a  jnz     short loc_1400523AD
0x14005233c  call    ?AnyUsersWantSharing@CWMCService@@AEAAHXZ; CWMCService::AnyUsersWantSharing(void)
0x140052341  test    eax, eax
0x140052343  jnz     short loc_1400523AD
0x140052345  mov     rcx, cs:WPP_GLOBAL_Control
0x14005234c  cmp     rcx, r13
0x14005234f  jz      loc_140053851
0x140052355  lea     edi, [rax+2]
0x140052358  test    [rcx+1Ch], dil
0x14005235c  jz      short loc_140052385
0x14005235e  lea     r12d, [rax+4]
0x140052362  cmp     [rcx+19h], r12b
0x140052366  lea     r12, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x14005236d  jb      short loc_140052385
0x14005236f  lea     edx, [rax+59h]
0x140052372  mov     r8, r12
0x140052375  mov     rcx, [rcx+10h]
0x140052379  call    WPP_SF_
0x14005237e  mov     rcx, cs:WPP_GLOBAL_Control
0x140052385  cmp     rcx, r13
0x140052388  jz      loc_140053851
0x14005238e  test    [rcx+1Ch], bl
0x140052391  jz      loc_140053851
0x140052397  mov     edx, 5Ah ; 'Z'
0x14005239c  mov     r8, r12
0x14005239f  mov     rcx, [rcx+10h]
0x1400523a3  call    WPP_SF_
0x1400523a8  jmp     loc_140053851
0x1400523ad  mov     [rbp+180h+var_1FC], r15d
0x1400523b1  mov     [rbp+180h+var_200], r15d
0x1400523b5  mov     [rbp+180h+var_160], r15
0x1400523b9  lea     rcx, [rbp+180h+var_168]
0x1400523bd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x1400523c2  nop
0x1400523c3  xorps   xmm0, xmm0
0x1400523c6  movups  xmmword ptr [rbp+180h+var_C8.Id], xmm0
0x1400523cd  mov     ecx, 268h; Size
0x1400523d2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400523d7  mov     [rbp+180h+var_1F8], rax
0x1400523db  mov     rcx, rax; this
0x1400523de  call    ??0CMACAddressControl@@QEAA@XZ; CMACAddressControl::CMACAddressControl(void)
0x1400523e3  nop
0x1400523e4  mov     [rsi+158h], rax
0x1400523eb  test    rax, rax
0x1400523ee  jnz     short loc_14005244C
0x1400523f0  lea     edi, [rax+2]
0x1400523f3  mov     r14d, 8007000Eh
0x1400523f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140052400  cmp     rcx, r13
0x140052403  jz      short loc_140052420
0x140052405  test    [rcx+1Ch], dil
0x140052409  jz      short loc_140052420
0x14005240b  cmp     [rcx+19h], dil
0x14005240f  jb      short loc_140052420
0x140052411  lea     edx, [rax+5Bh]
0x140052414  mov     r8, r12
0x140052417  mov     rcx, [rcx+10h]
0x14005241b  call    WPP_SF_
0x140052420  mov     eax, 37F1h
0x140052425  mov     [rbp+180h+var_C8.Id], ax
0x14005242c  movsd   xmm0, qword ptr cs:WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY+2
0x140052434  mov     eax, dword ptr cs:WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY+0Ah
0x14005243a  mov     dword ptr [rbp+180h+var_C8.Keyword+2], eax
0x140052440  movzx   eax, word ptr cs:WMC_E_SERVICE_FAILED_STARTUP_OUTOFMEMORY+0Eh
0x140052447  jmp     loc_140052724
0x14005244c  lea     rcx, [rax+8]
0x140052450  mov     rax, [rcx]
0x140052453  mov     rax, [rax+8]
0x140052457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005245c  lea     rdx, [rbp+180h+var_C8]; struct _EVENT_DESCRIPTOR *
0x140052463  mov     rcx, [rsi+158h]; this
0x14005246a  call    ?Init@CMACAddressControl@@QEAAJAEAU_EVENT_DESCRIPTOR@@@Z; CMACAddressControl::Init(_EVENT_DESCRIPTOR &)
0x14005246f  mov     r14d, eax
0x140052472  mov     edi, 2
0x140052477  mov     rcx, cs:WPP_GLOBAL_Control
0x14005247e  cmp     rcx, r13
0x140052481  jz      short loc_1400524AE
0x140052483  test    [rcx+1Ch], dil
0x140052487  jz      short loc_1400524AE
0x140052489  mov     edx, eax
0x14005248b  sar     edx, 1Fh
0x14005248e  and     edx, 0FFFFFFFDh
0x140052491  add     edx, 5
0x140052494  movzx   eax, byte ptr [rcx+19h]
0x140052498  cmp     eax, edx
0x14005249a  jl      short loc_1400524AE
0x14005249c  lea     edx, [rdi+5Ah]
0x14005249f  mov     r9d, r14d
0x1400524a2  mov     r8, r12
0x1400524a5  mov     rcx, [rcx+10h]
0x1400524a9  call    WPP_SF_d
0x1400524ae  test    r14d, r14d
0x1400524b1  js      loc_140052733
0x1400524b7  lea     rcx, [rbp+180h+var_1F8]; this
0x1400524bb  call    ??0CRendererDevicesDB@@QEAA@XZ; CRendererDevicesDB::CRendererDevicesDB(void)
0x1400524c0  nop
0x1400524c1  call    ?IsWindowsSetupComplete@@YAHXZ; IsWindowsSetupComplete(void)
0x1400524c6  test    eax, eax
0x1400524c8  jnz     short loc_140052502
0x1400524ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400524d1  cmp     rcx, r13
0x1400524d4  jz      loc_1400525A4
0x1400524da  test    [rcx+1Ch], dil
0x1400524de  jz      loc_1400525A4
0x1400524e4  cmp     [rcx+19h], dil
0x1400524e8  jb      loc_1400525A4
0x1400524ee  lea     edx, [rax+5Dh]
0x1400524f1  mov     r8, r12
0x1400524f4  mov     rcx, [rcx+10h]
0x1400524f8  call    WPP_SF_
0x1400524fd  jmp     loc_1400525A4
0x140052502  mov     [rsp+280h+var_220], r15
0x140052507  mov     [rsp+280h+var_218], r15
0x14005250c  lea     rdx, a000000000000; "00-00-00-00-00-00"
0x140052513  lea     rcx, [rsp+280h+var_240]
0x140052518  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x14005251d  lea     rdx, [rsp+280h+var_240]
0x140052522  lea     rcx, [rsp+280h+var_220]
0x140052527  call    ?Add@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &)
0x14005252c  lea     rcx, [rsp+280h+var_240]
0x140052531  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140052536  xorps   xmm0, xmm0
0x140052539  movdqu  [rbp+180h+var_148], xmm0
0x14005253e  mov     [rbp+180h+var_138], r15
0x140052542  xorps   xmm1, xmm1
0x140052545  movdqu  [rbp+180h+var_130], xmm1
0x14005254a  mov     [rbp+180h+var_120], 0Ah
0x140052551  mov     [rsp+280h+var_210], r15
0x140052556  mov     [rsp+280h+var_208], r15
0x14005255b  lea     rax, [rsp+280h+var_210]
0x140052560  mov     qword ptr [rsp+280h+fAsynchronous], rax; __int64
0x140052565  mov     r9d, ebx
0x140052568  lea     r8, [rbp+180h+var_148]
0x14005256c  lea     rdx, [rsp+280h+var_220]
0x140052571  lea     rcx, [rbp+180h+var_1F8]; this
0x140052575  call    ?DeleteAllNewDevices@CDevicesDB@@QEAAJAEBV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@3@HAEAV23@@Z; CDevicesDB::DeleteAllNewDevices(ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> const &,ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> const &,int,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>> &)
0x14005257a  lea     rcx, [rsp+280h+var_210]
0x14005257f  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RemoveAll(void)
0x140052584  nop
0x140052585  lea     rcx, [rsp+280h+var_210]
0x14005258a  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RemoveAll(void)
0x14005258f  nop
0x140052590  lea     rcx, [rbp+180h+var_148]
0x140052594  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RemoveAll(void)
0x140052599  nop
0x14005259a  lea     rcx, [rsp+280h+var_220]
0x14005259f  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::RemoveAll(void)
0x1400525a4  lea     rdx, a000000000000; "00-00-00-00-00-00"
0x1400525ab  lea     rcx, [rbp+180h+var_1F8]; this
0x1400525af  call    ?CreateDevice@CDevicesDB@@QEAAJPEBG@Z; CDevicesDB::CreateDevice(ushort const *)
0x1400525b4  nop
0x1400525b5  lea     rcx, [rbp+180h+var_1F0]
0x1400525b9  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400525be  mov     [rbp+180h+var_1FC], ebx
0x1400525c1  lea     rcx, [rbp+180h+var_C8]; struct _EVENT_DESCRIPTOR *
0x1400525c8  call    ?InitializeNetworkMonitoring@@YAJAEAU_EVENT_DESCRIPTOR@@@Z; InitializeNetworkMonitoring(_EVENT_DESCRIPTOR &)
0x1400525cd  mov     r14d, eax
0x1400525d0  test    eax, eax
0x1400525d2  js      loc_140052733
0x1400525d8  call    ?StartNetworkMonitoring@@YAKXZ; StartNetworkMonitoring(void)
0x1400525dd  mov     ebx, eax
0x1400525df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400525e6  cmp     rcx, r13
0x1400525e9  jz      short loc_14005260B
0x1400525eb  test    [rcx+1Ch], dil
0x1400525ef  jz      short loc_14005260B
0x1400525f1  cmp     byte ptr [rcx+19h], 5
0x1400525f5  jb      short loc_14005260B
0x1400525f7  mov     edx, 5Eh ; '^'
0x1400525fc  mov     r9d, eax
0x1400525ff  mov     r8, r12
0x140052602  mov     rcx, [rcx+10h]
0x140052606  call    WPP_SF_d
0x14005260b  test    ebx, ebx
0x14005260d  jnz     short loc_140052619
0x14005260f  mov     ebx, 1
0x140052614  mov     [rbp+180h+var_200], ebx
0x140052617  jmp     short loc_140052669
0x140052619  lea     rcx, [rsp+280h+var_240]
0x14005261e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140052623  nop
0x140052624  mov     r8d, ebx
0x140052627  lea     rdx, aD; "%d"
0x14005262e  lea     rcx, [rsp+280h+var_240]
0x140052633  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x140052638  mov     qword ptr [rsp+280h+fAsynchronous], r15; unsigned __int16 *
0x14005263d  xor     r9d, r9d; unsigned __int16 *
0x140052640  mov     r8, [rsp+280h+var_240]; unsigned __int16 *
0x140052645  lea     rdx, WMC_W_SERVICE_IPV4_DISABLED; struct _EVENT_DESCRIPTOR *
0x14005264c  mov     rcx, rsi; this
0x14005264f  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x140052654  mov     ebx, 1
0x140052659  mov     [rsi+8Ch], ebx
0x14005265f  lea     rcx, [rsp+280h+var_240]
0x140052664  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140052669  lea     rdx, [rbp+180h+var_C8]; struct _EVENT_DESCRIPTOR *
0x140052670  mov     rcx, rsi; this
0x140052673  call    ?CreateContentProviderFactories@CWMCService@@AEAAJAEAU_EVENT_DESCRIPTOR@@@Z; CWMCService::CreateContentProviderFactories(_EVENT_DESCRIPTOR &)
0x140052678  mov     r14d, eax
0x14005267b  mov     rcx, cs:WPP_GLOBAL_Control
0x140052682  cmp     rcx, r13
0x140052685  jz      short loc_1400526B4
0x140052687  test    [rcx+1Ch], dil
0x14005268b  jz      short loc_1400526B4
0x14005268d  mov     edx, eax
0x14005268f  sar     edx, 1Fh
0x140052692  and     edx, 0FFFFFFFDh
0x140052695  add     edx, 5
0x140052698  movzx   eax, byte ptr [rcx+19h]
0x14005269c  cmp     eax, edx
0x14005269e  jl      short loc_1400526B4
0x1400526a0  mov     edx, 5Fh ; '_'
0x1400526a5  mov     r9d, r14d
0x1400526a8  mov     r8, r12
0x1400526ab  mov     rcx, [rcx+10h]
0x1400526af  call    WPP_SF_d
0x1400526b4  test    r14d, r14d
0x1400526b7  js      short loc_140052733
0x1400526b9  mov     rcx, rsi; this
0x1400526bc  call    ?CreateMediaDevices@CWMCService@@AEAAJXZ; CWMCService::CreateMediaDevices(void)
0x1400526c1  mov     r14d, eax
0x1400526c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400526cb  cmp     rcx, r13
0x1400526ce  jz      short loc_1400526FD
0x1400526d0  test    [rcx+1Ch], dil
0x1400526d4  jz      short loc_1400526FD
0x1400526d6  mov     edx, eax
0x1400526d8  sar     edx, 1Fh
0x1400526db  and     edx, 0FFFFFFFDh
0x1400526de  add     edx, 5
0x1400526e1  movzx   eax, byte ptr [rcx+19h]
0x1400526e5  cmp     eax, edx
0x1400526e7  jl      short loc_1400526FD
0x1400526e9  mov     edx, 60h ; '`'
0x1400526ee  mov     r9d, r14d
0x1400526f1  mov     r8, r12
0x1400526f4  mov     rcx, [rcx+10h]
0x1400526f8  call    WPP_SF_d
0x1400526fd  mov     eax, 3801h
0x140052702  mov     [rbp+180h+var_C8.Id], ax
0x140052709  movsd   xmm0, cs:qword_1400A7222
0x140052711  mov     eax, cs:dword_1400A722A
0x140052717  mov     dword ptr [rbp+180h+var_C8.Keyword+2], eax
0x14005271d  movzx   eax, cs:word_1400A722E
0x140052724  mov     word ptr [rbp+180h+var_C8.Keyword+6], ax
0x14005272b  movsd   qword ptr [rbp+180h+var_C8.Version], xmm0
0x140052733  lea     rcx, [rbp+180h+var_148]; this
0x140052737  call    ??0CServiceControl@@QEAA@XZ; CServiceControl::CServiceControl(void)
0x14005273c  nop
  ... truncated ...
```
