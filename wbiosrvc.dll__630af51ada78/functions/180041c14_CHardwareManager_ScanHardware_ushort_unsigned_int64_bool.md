# CHardwareManager::ScanHardware(ushort *,unsigned __int64,bool)

- ea: `0x180041c14`
- end: `0x180042a06`
- name: `?ScanHardware@CHardwareManager@@AEAAJPEAG_K_N@Z`
- size: `3570`
- prototype: `__int64 __fastcall(CHardwareManager *this, unsigned __int16 *, __int64, char)`
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180045d10`

## callees

- `0x18000513c`
- `0x18000b760`
- `0x180010a3c`
- `0x18001119c`
- `0x1800120a0`
- `0x18001434c`
- `0x18001451c`
- `0x180014854`
- `0x180014894`
- `0x1800176d8`
- `0x18001aef8`
- `0x18001b920`
- `0x18001be8c`
- `0x18001ca14`
- `0x18001d630`
- `0x180023d88`
- `0x18002d3b4`
- `0x18002e950`
- `0x180030d14`
- `0x18003aee8`
- `0x18003f2dc`
- `0x180041c14`
- `0x180055878`
- `0x1800559c8`
- `0x180060254`
- `0x1800604c0`
- `0x180068f60`
- `0x18006963c`
- `0x180069cc8`
- `0x18006e4c4`
- `0x1800721f0`
- `0x1800728e0`
- `0x18007d06c`
- `0x180080ff4`
- `0x180081a80`
- `0x1800be44c`
- `0x1800bf920`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041eba`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180041eba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041f5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041f5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041f4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041ea9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041f4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041d70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041f12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042939`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042356`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004243b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004249f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800424ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180041f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042356`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004243b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004249f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800424ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004221b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004232a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042413`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004221b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004232a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042413`
- `ntdll!RtlPublishWnfStateData` at `0x180042013`
- `ntdll!RtlPublishWnfStateData` at `0x180042013`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180041d2c`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180041d2c`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004295f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18004295f`
- `DEVOBJ!DevObjGetClassDevs` at `0x180041d66`
- `DEVOBJ!DevObjGetClassDevs` at `0x180041d66`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180041dc6`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x180041dc6`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041e88`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041f08`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041e88`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x180041f08`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180041fa8`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180042071`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180042701`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180041fa8`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180042071`
- `DEVOBJ!DevObjGetDeviceRegistryProperty` at `0x180042701`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180042183`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180042183`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800420f8`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800420f8`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180041fcc`
- `DEVOBJ!DevObjGetDeviceInstanceId` at `0x180041fcc`

## string_xrefs

- `0x18004202f`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x18004281e`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x18004299c`: `onecore\ds\security\biometrics\service\server\hardwaremanager.cpp`
- `0x180041d07`: `Service Providers`
- `0x18004241d`: `Service Providers`
- `0x180041c9d`: `Configurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CHardwareManager::ScanHardware(CHardwareManager *this, unsigned __int16 *a2, __int64 a3, char a4)
{
  CHardwareManager *v4; // rbx
  __int64 DeviceInfoList; // rax
  __int64 v6; // r13
  signed int LastError; // eax
  unsigned int v8; // esi
  unsigned int i; // eax
  __int64 v10; // r14
  unsigned int v11; // ebx
  HANDLE v12; // rax
  _DWORD *v13; // rax
  void *v14; // r14
  HANDLE ProcessHeap; // rax
  CHardwareManager *v16; // rcx
  int v17; // eax
  signed int v18; // eax
  unsigned int v19; // ebx
  signed int v20; // eax
  const WCHAR *v21; // rax
  CSensorConfigSelector *v22; // rax
  unsigned int v23; // edx
  int v24; // ebx
  const WCHAR *v25; // rax
  CHardwareManager *v26; // rcx
  int v27; // ebx
  CDatabaseManager *v28; // rax
  const WCHAR *v29; // rax
  CHardwareManager *v30; // rcx
  __int64 v31; // rcx
  int PhysicalSensorAttributes; // r14d
  int v33; // ebx
  __int64 v34; // r8
  __int64 v35; // r8
  CHardwareManager *v36; // rcx
  signed int v37; // eax
  int v38; // r9d
  int IsFingerprintSensor; // eax
  signed int v40; // eax
  __int64 v41; // rcx
  int v42; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-1A48h]
  CSensorConfigSelector **phkResulta; // [rsp+20h] [rbp-1A48h]
  __int64 v46; // [rsp+28h] [rbp-1A40h]
  __int64 v47; // [rsp+28h] [rbp-1A40h]
  CBiometricUnit **v48; // [rsp+28h] [rbp-1A40h]
  CHardwareManager *v49; // [rsp+40h] [rbp-1A28h]
  SIZE_T dwBytes; // [rsp+48h] [rbp-1A20h] BYREF
  __int64 v51; // [rsp+50h] [rbp-1A18h] BYREF
  unsigned int v52; // [rsp+58h] [rbp-1A10h]
  __int64 v53; // [rsp+60h] [rbp-1A08h]
  CBiometricUnit *v54[2]; // [rsp+68h] [rbp-1A00h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-19F0h] BYREF
  int v56; // [rsp+80h] [rbp-19E8h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-19E0h]
  HKEY v58; // [rsp+90h] [rbp-19D8h] BYREF
  HKEY v59; // [rsp+98h] [rbp-19D0h] BYREF
  CSensorConfigSelector *v60; // [rsp+A0h] [rbp-19C8h] BYREF
  int v61; // [rsp+A8h] [rbp-19C0h] BYREF
  int v62; // [rsp+ACh] [rbp-19BCh] BYREF
  int v63; // [rsp+B0h] [rbp-19B8h] BYREF
  __int64 v64; // [rsp+B8h] [rbp-19B0h]
  CHardwareManager *v65; // [rsp+C0h] [rbp-19A8h]
  _OWORD v66[2]; // [rsp+C8h] [rbp-19A0h] BYREF
  _OWORD v67[3]; // [rsp+E8h] [rbp-1980h] BYREF
  _BYTE v68[32]; // [rsp+118h] [rbp-1950h] BYREF
  _BYTE v69[32]; // [rsp+138h] [rbp-1930h] BYREF
  _BYTE v70[32]; // [rsp+158h] [rbp-1910h] BYREF
  _BYTE v71[32]; // [rsp+178h] [rbp-18F0h] BYREF
  _BYTE v72[32]; // [rsp+198h] [rbp-18D0h] BYREF
  _OWORD v73[3]; // [rsp+1B8h] [rbp-18B0h] BYREF
  struct _WINBIO_UNIT_SCHEMA v74; // [rsp+1F0h] [rbp-1878h] BYREF
  struct _WINBIO_UNIT_SCHEMA v75; // [rsp+C10h] [rbp-E58h] BYREF
  unsigned __int16 v76[256]; // [rsp+1630h] [rbp-438h] BYREF
  unsigned __int16 v77[256]; // [rsp+1830h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A68h] [rbp+0h]

  v4 = this;
  v49 = this;
  v65 = this;
  memset(v66, 0, sizeof(v66));
  std::wstring::wstring(v70, L"WinBio");
  std::wstring::append(v70, L"\\");
  std::wstring::append(v70, L"Configurations");
  std::wstring::wstring(v69, L"WinBio");
  std::wstring::append(v69, L"\\");
  std::wstring::append(v69, L"Databases");
  std::wstring::wstring(v68, L"WinBio");
  std::wstring::append(v68, L"\\");
  std::wstring::append(v68, L"Service Providers");
  LODWORD(phkResult) = 0;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0);
  v6 = DeviceInfoList;
  v64 = DeviceInfoList;
  if ( (unsigned __int64)(DeviceInfoList - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LODWORD(phkResult) = 0;
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_BIOMETRIC_READER, 0, 18) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_92:
      DevObjDestroyDeviceInfoList(v6);
      goto LABEL_93;
    }
    v8 = 0;
    LODWORD(v66[0]) = 32;
    for ( i = 0; ; i = v52 + 1 )
    {
      v52 = i;
      phkResult = (PHKEY)v66;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v6, 0, &GUID_DEVINTERFACE_BIOMETRIC_READER, i) )
        goto LABEL_92;
      memset(v67, 0, sizeof(v67));
      memset(v73, 0, sizeof(v73));
      LODWORD(dwBytes) = 0;
      memset_0(v77, 0, sizeof(v77));
      memset_0(v76, 0, sizeof(v76));
      v10 = -1;
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      v58 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      v59 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      v60 = 0;
      v56 = 0;
      *(_OWORD *)v54 = 0;
      if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v6, v66, 0, 0, &dwBytes, 0) )
        break;
      lpMem = 0;
      if ( GetLastError() == 122 )
        break;
LABEL_13:
      if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        RegCloseKey(hKey);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      if ( v10 != -1 )
        RegCloseKey((HKEY)v10);
      v14 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v14);
      }
      if ( v54[1] )
        std::_Ref_count_base::_Decref(v54[1]);
    }
    v11 = dwBytes;
    v12 = GetProcessHeap();
    v13 = HeapAlloc(v12, 8u, v11);
    lpMem = v13;
    v53 = (__int64)v13;
    if ( !v13 )
      goto LABEL_12;
    *v13 = 8;
    LODWORD(v67[0]) = 48;
    if ( !(unsigned int)DevObjGetDeviceInterfaceDetail(v6, v66, v13, (unsigned int)dwBytes, 0, v67)
      || (LODWORD(v46) = 512,
          DevObjGetDeviceRegistryProperty(v6, v67, 0, 0, v77, v46, 0),
          !(unsigned int)DevObjGetDeviceInstanceId(v6, v67, v76, 256, 0)) )
    {
      GetLastError();
      goto LABEL_12;
    }
    if ( CHardwareManager::IsDeviceAlreadyRegistered(v16, v76) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
      {
        v17 = RtlPublishWnfStateData(WNF_WBIO_BIO_UNITS_STATE_CHANGE, 0, 0, 0) | 0x10000000;
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x897,
            (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
            (const char *)(unsigned int)v17,
            0);
      }
      goto LABEL_12;
    }
    LODWORD(v47) = 4;
    DevObjGetDeviceRegistryProperty(v6, v67, 26, 0, &v56, v47, 0);
    if ( !v56 )
      goto LABEL_28;
    LODWORD(v73[0]) = 48;
    if ( !(unsigned int)DevObjEnumDeviceInfo(v6, v52, v73) )
    {
      v18 = GetLastError();
      v19 = v18;
      if ( v18 > 0 )
        v19 = (unsigned __int16)v18 | 0x80070000;
      goto LABEL_33;
    }
    v10 = DevObjOpenDevRegKey(v6, v73, 1, 0, 1, 131097);
    v51 = v10;
    if ( v10 == -1 )
    {
      v20 = GetLastError();
      v19 = v20;
      if ( v20 > 0 )
        v19 = (unsigned __int16)v20 | 0x80070000;
LABEL_33:
      CEtwEvent::CEtwEvent((CEtwEvent *)&v74);
      CEtwEvent::CaptureSensorInfo((CEtwEvent *)&v74, v77, v76);
      *(_DWORD *)&v74.DeviceInstanceId[170] = v19;
      CEtwEvent::Write(&v74, 1111, 1);
LABEL_29:
      CEtwEvent::~CEtwEvent((CEtwEvent *)&v74);
LABEL_12:
      v4 = v49;
      goto LABEL_13;
    }
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v70);
    if ( RegOpenKeyExW((HKEY)v10, v21, 0, 0x20019u, &hKey) )
    {
LABEL_28:
      CEtwEvent::CEtwEvent((CEtwEvent *)&v74);
      CEtwEvent::CaptureSensorInfo((CEtwEvent *)&v74, v77, v76);
      *(_DWORD *)&v74.DeviceInstanceId[170] = -2147023885;
      CEtwEvent::Write(&v74, 1110, 1);
      goto LABEL_29;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v22 = (CSensorConfigSelector *)operator new(0x68u);
      v60 = CSensorConfigSelector::CSensorConfigSelector(v22);
      v24 = CSensorConfigSelector::CaptureDeviceSpecificConfigurations(v60, hKey);
      if ( v24 < 0 )
      {
        CEtwEvent::CEtwEvent((CEtwEvent *)&v74);
        CEtwEvent::CaptureSensorInfo((CEtwEvent *)&v74, v77, v76);
        *(_DWORD *)&v74.DeviceInstanceId[170] = v24;
        CEtwEvent::Write(&v74, 1110, 1);
        CEtwEvent::~CEtwEvent((CEtwEvent *)&v74);
      }
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        CEtwEvent::CEtwEvent((CEtwEvent *)&v74);
        CEtwEvent::CaptureSensorInfo((CEtwEvent *)&v74, v77, v76);
        *(_DWORD *)&v74.DeviceInstanceId[170] = -2147024882;
        CEtwEvent::Write(&v74, 1111, 1);
        CEtwEvent::~CEtwEvent((CEtwEvent *)&v74);
        v8 = 0;
        v6 = v64;
        lpMem = (LPVOID)v53;
        v10 = v51;
        v4 = v65;
        v49 = v65;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180042901);
LABEL_46:
        if ( v60 )
          CSensorConfigSelector::`scalar deleting destructor'(v60, v23);
        goto LABEL_13;
      }
    }
    if ( v24 < 0 )
    {
LABEL_45:
      v4 = v49;
      goto LABEL_46;
    }
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v69);
    if ( !RegOpenKeyExW((HKEY)v10, v25, 0, 0x20019u, &v58) )
    {
      v27 = CHardwareManager::SetupDeviceServiceKey(v26, v58, L"Databases");
      RegCloseKey(v58);
      v58 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      if ( v27 < 0 )
      {
LABEL_44:
        CEtwEvent::CEtwEvent((CEtwEvent *)&v74);
        CEtwEvent::CaptureSensorInfo((CEtwEvent *)&v74, v77, v76);
        *(_DWORD *)&v74.DeviceInstanceId[170] = v27;
        CEtwEvent::Write(&v74, 1110, 1);
        CEtwEvent::~CEtwEvent((CEtwEvent *)&v74);
        goto LABEL_45;
      }
      v28 = CDatabaseManager::Instance();
      CDatabaseManager::RegisterAll(v28);
    }
    v29 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v68);
    if ( !RegOpenKeyExW((HKEY)v10, v29, 0, 0x20019u, &v59) )
    {
      v27 = CHardwareManager::SetupDeviceServiceKey(v30, v59, L"Service Providers");
      RegCloseKey(v59);
      v59 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      if ( v27 < 0 )
        goto LABEL_44;
    }
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    RegCloseKey((HKEY)v10);
    v53 = -1;
    v4 = v49;
    v31 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)v49 + 4);
    v48 = v54;
    phkResulta = &v60;
    PhysicalSensorAttributes = CHardwareManager::Create(v31, v77, v76, (char *)lpMem + 4);
    if ( PhysicalSensorAttributes >= 0 )
    {
      PhysicalSensorAttributes = CBiometricUnit::LoadPhysicalSensorAttributes(v54[0]);
      if ( PhysicalSensorAttributes >= 0 )
      {
        if ( *((_DWORD *)v54[0] + 22) == 8 )
        {
          LODWORD(v51) = 0;
          LODWORD(v48) = 4;
          if ( (unsigned int)DevObjGetDeviceRegistryProperty(v6, v67, 15, 0, &v51, v48, 0) )
          {
            *((_DWORD *)v54[0] + 746) = v51;
            if ( (unsigned int)dword_18010F170 > 4 )
            {
              v61 = *((_DWORD *)v54[0] + 20);
              v62 = v51 & 4;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                (int)&dword_18010F170,
                (int)byte_1800ECC0B,
                0,
                0,
                (__int64)&v62,
                (__int64)&v61);
            }
          }
          else if ( (unsigned int)dword_18010F170 > 3 )
          {
            v37 = GetLastError();
            if ( v37 > 0 )
              v37 = (unsigned __int16)v37 | 0x80070000;
            v63 = v37;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18010F170,
              (unsigned int)&dword_1800ECBCC,
              0,
              v38,
              (__int64)&v63);
          }
        }
        if ( !(unsigned __int8)CServer::AcceptBiometricUnit(v54) )
        {
          PhysicalSensorAttributes = -2146861020;
          _InterlockedOr((volatile signed __int32 *)v54[0] + 10, 1u);
          CHardwareManager::Delete(v54);
          goto LABEL_72;
        }
        if ( a4 )
          CHardwareManager::PublishFrameworkNotificationUnitArrivalRemoval(
            *((_DWORD *)v54[0] + 20),
            *((_DWORD *)v54[0] + 22),
            1);
      }
      else
      {
        CEtwEvent::CEtwEvent((CEtwEvent *)&v74);
        CEtwEvent::CaptureSensorInfo((CEtwEvent *)&v74, v54[0]);
        *(_DWORD *)&v74.DeviceInstanceId[170] = PhysicalSensorAttributes;
        CEtwEvent::Write(&v74, 1103, 1);
        CHardwareManager::Delete(v54);
        CEtwEvent::~CEtwEvent((CEtwEvent *)&v74);
      }
    }
    else
    {
      CEtwEvent::CEtwEvent((CEtwEvent *)&v74);
      CEtwEvent::CaptureSensorInfo((CEtwEvent *)&v74, v77, v76);
      *(_DWORD *)&v74.DeviceInstanceId[170] = PhysicalSensorAttributes;
      CEtwEvent::Write(&v74, 1111, 1);
      std::wstring::wstring(v72, byte_1800DC1E0);
      std::wstring::wstring(v71, byte_1800DC1E0);
      if ( v54[0] )
      {
        CBiometricUnit::GetSchema(v54[0], &v75);
        v33 = *((_DWORD *)v54[0] + 745);
        v34 = -1;
        do
          ++v34;
        while ( v75.Manufacturer[v34] );
        std::wstring::_Assign<unsigned short>(v72, v75.Manufacturer);
        v35 = -1;
        do
          ++v35;
        while ( v75.Model[v35] );
        std::wstring::_Assign<unsigned short>(v71, v75.Model);
      }
      else
      {
        v33 = -1;
      }
      CBioTraceLogging::OnBiometricUnitStateChanged(PhysicalSensorAttributes, 0, 0, 0, v33, (__int64)v72, (__int64)v71);
      std::wstring::_Tidy_deallocate(v71);
      std::wstring::_Tidy_deallocate(v72);
      CEtwEvent::~CEtwEvent((CEtwEvent *)&v74);
      v4 = v49;
    }
    if ( PhysicalSensorAttributes >= 0 )
    {
      CBiometricUnit::GetSchema(v54[0], &v74);
      CBioTraceLogging::OnHardwareDiscovery(
        v74.DeviceInstanceId,
        v74.Capabilities,
        v74.BiometricFactor,
        v74.SensorSubType);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
      {
        if ( v74.BiometricFactor != 8 )
        {
          if ( v74.BiometricFactor == 2 )
          {
            *((_BYTE *)v4 + 192) = 1;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
      }
      else if ( v74.BiometricFactor != 8 )
      {
        goto LABEL_87;
      }
      *((_BYTE *)v4 + 185) = 1;
      *((_DWORD *)v4 + 47) = 0;
      goto LABEL_86;
    }
LABEL_72:
    if ( !*((_BYTE *)v4 + 185) )
    {
      IsFingerprintSensor = CHardwareManager::IsFingerprintSensor(v36, (unsigned __int16 *)lpMem + 2, (bool *)v4 + 185);
      if ( IsFingerprintSensor < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xA25,
          (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
          (const char *)(unsigned int)IsFingerprintSensor,
          (int)phkResulta);
      if ( *((_BYTE *)v4 + 185) )
      {
        v4 = v49;
        *((_DWORD *)v49 + 47) = PhysicalSensorAttributes;
LABEL_86:
        v10 = v53;
        goto LABEL_46;
      }
    }
LABEL_87:
    v10 = v53;
    goto LABEL_45;
  }
  v40 = GetLastError();
  v8 = v40;
  if ( v40 > 0 )
    v8 = (unsigned __int16)v40 | 0x80070000;
  if ( v6 != -1 && v6 )
    goto LABEL_92;
LABEL_93:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
  {
    v42 = winbio::SetBioRegKeyValue(v41, 6, *((_BYTE *)v4 + 192) != 0);
    if ( v42 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA60,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\server\\hardwaremanager.cpp",
        (const char *)(unsigned int)v42,
        (int)phkResult);
  }
  std::wstring::_Tidy_deallocate(v68);
  std::wstring::_Tidy_deallocate(v69);
  std::wstring::_Tidy_deallocate(v70);
  return v8;
}

```

## disassembly

```asm
0x180041c14  mov     [rsp+arg_8], rbx
0x180041c19  mov     [rsp+arg_10], rsi
0x180041c1e  mov     [rsp+arg_18], r9b
0x180041c23  push    rdi
0x180041c24  push    r12
0x180041c26  push    r13
0x180041c28  push    r14
0x180041c2a  push    r15
0x180041c2c  mov     eax, 1A40h
0x180041c31  call    _alloca_probe
0x180041c36  sub     rsp, rax
0x180041c39  mov     rax, cs:__security_cookie
0x180041c40  xor     rax, rsp
0x180041c43  mov     [rsp+1A68h+var_38], rax
0x180041c4b  mov     rbx, rcx
0x180041c4e  mov     [rsp+1A68h+var_1A28], rcx
0x180041c53  mov     [rsp+1A68h+var_19A8], rcx
0x180041c5b  xorps   xmm0, xmm0
0x180041c5e  movups  [rsp+1A68h+var_19A0], xmm0
0x180041c66  movups  [rsp+1A68h+var_1990], xmm0
0x180041c6e  lea     rsi, aWinbio; "WinBio"
0x180041c75  mov     rdx, rsi
0x180041c78  lea     rcx, [rsp+1A68h+var_1910]
0x180041c80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041c85  nop
0x180041c86  lea     rdi, asc_1800DC1E4; "\\"
0x180041c8d  mov     rdx, rdi
0x180041c90  lea     rcx, [rsp+1A68h+var_1910]
0x180041c98  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041c9d  lea     rdx, aConfigurations; "Configurations"
0x180041ca4  lea     rcx, [rsp+1A68h+var_1910]
0x180041cac  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041cb1  mov     rdx, rsi
0x180041cb4  lea     rcx, [rsp+1A68h+var_1930]
0x180041cbc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041cc1  nop
0x180041cc2  mov     rdx, rdi
0x180041cc5  lea     rcx, [rsp+1A68h+var_1930]
0x180041ccd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041cd2  lea     rdx, aDatabases; "Databases"
0x180041cd9  lea     rcx, [rsp+1A68h+var_1930]
0x180041ce1  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041ce6  mov     rdx, rsi
0x180041ce9  lea     rcx, [rsp+1A68h+var_1950]
0x180041cf1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041cf6  nop
0x180041cf7  mov     rdx, rdi
0x180041cfa  lea     rcx, [rsp+1A68h+var_1950]
0x180041d02  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041d07  lea     rdx, aServiceProvide; "Service Providers"
0x180041d0e  lea     rcx, [rsp+1A68h+var_1950]
0x180041d16  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180041d1b  xor     edi, edi
0x180041d1d  mov     [rsp+1A68h+phkResult], rdi; int
0x180041d22  xor     r9d, r9d
0x180041d25  xor     r8d, r8d
0x180041d28  xor     edx, edx
0x180041d2a  xor     ecx, ecx
0x180041d2c  call    cs:__imp_DevObjCreateDeviceInfoList
0x180041d32  mov     r13, rax
0x180041d35  mov     [rsp+1A68h+var_19B0], rax
0x180041d3d  lea     rcx, [rax-1]
0x180041d41  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180041d45  ja      loc_180042939
0x180041d4b  mov     [rsp+1A68h+var_1A40], rdi
0x180041d50  mov     [rsp+1A68h+phkResult], rdi
0x180041d55  lea     r9d, [rdi+12h]
0x180041d59  xor     r8d, r8d
0x180041d5c  lea     rdx, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180041d63  mov     rcx, rax
0x180041d66  call    cs:__imp_DevObjGetClassDevs
0x180041d6c  test    eax, eax
0x180041d6e  jnz     short loc_180041D8E
0x180041d70  call    cs:__imp_GetLastError
0x180041d76  mov     esi, eax
0x180041d78  test    eax, eax
0x180041d7a  jle     loc_18004295C
0x180041d80  movzx   esi, ax
0x180041d83  or      esi, 80070000h
0x180041d89  jmp     loc_18004295C
0x180041d8e  mov     esi, edi
0x180041d90  mov     dword ptr [rsp+1A68h+var_19A0], 20h ; ' '
0x180041d9b  mov     eax, edi
0x180041d9d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180041da1  lea     r15d, [r12+2]
0x180041da6  mov     [rsp+1A68h+var_1A10], eax
0x180041daa  lea     rcx, [rsp+1A68h+var_19A0]
0x180041db2  mov     [rsp+1A68h+phkResult], rcx
0x180041db7  mov     r9d, eax
0x180041dba  lea     r8, GUID_DEVINTERFACE_BIOMETRIC_READER
0x180041dc1  xor     edx, edx
0x180041dc3  mov     rcx, r13
0x180041dc6  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180041dcc  test    eax, eax
0x180041dce  jz      loc_18004295C
0x180041dd4  xorps   xmm0, xmm0
0x180041dd7  movups  [rsp+1A68h+var_1980], xmm0
0x180041ddf  movups  [rsp+1A68h+var_1970], xmm0
0x180041de7  movups  [rsp+1A68h+var_1960], xmm0
0x180041def  xorps   xmm1, xmm1
0x180041df2  movups  [rsp+1A68h+var_18B0], xmm1
0x180041dfa  movups  [rsp+1A68h+var_18A0], xmm1
0x180041e02  movups  [rsp+1A68h+var_1890], xmm1
0x180041e0a  mov     dword ptr [rsp+1A68h+dwBytes], edi
0x180041e0e  xor     edx, edx; Val
0x180041e10  mov     r8d, 200h; Size
0x180041e16  lea     rcx, [rsp+1A68h+var_238]; void *
0x180041e1e  call    memset_0
0x180041e23  xor     edx, edx; Val
0x180041e25  mov     r8d, 200h; Size
0x180041e2b  lea     rcx, [rsp+1A68h+var_438]; void *
0x180041e33  call    memset_0
0x180041e38  mov     r14, r12
0x180041e3b  mov     [rsp+1A68h+hKey], r12
0x180041e40  mov     [rsp+1A68h+var_19D8], r12
0x180041e48  mov     [rsp+1A68h+var_19D0], r12
0x180041e50  mov     [rsp+1A68h+var_19C8], rdi
0x180041e58  mov     [rsp+1A68h+var_19E8], edi
0x180041e5f  xorps   xmm0, xmm0
0x180041e62  movdqu  xmmword ptr [rsp+1A68h+var_1A00], xmm0
0x180041e68  mov     [rsp+1A68h+var_1A40], rdi
0x180041e6d  lea     rax, [rsp+1A68h+dwBytes]
0x180041e72  mov     [rsp+1A68h+phkResult], rax
0x180041e77  xor     r9d, r9d
0x180041e7a  xor     r8d, r8d
0x180041e7d  lea     rdx, [rsp+1A68h+var_19A0]
0x180041e85  mov     rcx, r13
0x180041e88  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180041e8e  test    eax, eax
0x180041e90  jnz     short loc_180041EA5
0x180041e92  mov     [rsp+1A68h+lpMem], rdi
0x180041e9a  call    cs:__imp_GetLastError
0x180041ea0  cmp     eax, 7Ah ; 'z'
0x180041ea3  jnz     short loc_180041F1D
0x180041ea5  mov     ebx, dword ptr [rsp+1A68h+dwBytes]
0x180041ea9  call    cs:__imp_GetProcessHeap
0x180041eaf  mov     r8d, ebx; dwBytes
0x180041eb2  mov     edx, 8; dwFlags
0x180041eb7  mov     rcx, rax; hHeap
0x180041eba  call    cs:__imp_HeapAlloc
0x180041ec0  mov     [rsp+1A68h+lpMem], rax
0x180041ec8  mov     [rsp+1A68h+var_1A08], rax
0x180041ecd  test    rax, rax
0x180041ed0  jz      short loc_180041F18
0x180041ed2  mov     dword ptr [rax], 8
0x180041ed8  mov     dword ptr [rsp+1A68h+var_1980], 30h ; '0'
0x180041ee3  lea     rcx, [rsp+1A68h+var_1980]
0x180041eeb  mov     [rsp+1A68h+var_1A40], rcx
0x180041ef0  mov     [rsp+1A68h+phkResult], rdi
0x180041ef5  mov     r9d, dword ptr [rsp+1A68h+dwBytes]
0x180041efa  mov     r8, rax
0x180041efd  lea     rdx, [rsp+1A68h+var_19A0]
0x180041f05  mov     rcx, r13
0x180041f08  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180041f0e  test    eax, eax
0x180041f10  jnz     short loc_180041F7D
0x180041f12  call    cs:__imp_GetLastError
0x180041f18  mov     rbx, [rsp+1A68h+var_1A28]
0x180041f1d  mov     rcx, [rsp+1A68h+hKey]; hKey
0x180041f22  cmp     rcx, r12
0x180041f25  jz      short loc_180041F32
0x180041f27  call    cs:__imp_RegCloseKey
0x180041f2d  mov     [rsp+1A68h+hKey], r12
0x180041f32  cmp     r14, r12
0x180041f35  jz      short loc_180041F40
0x180041f37  mov     rcx, r14; hKey
0x180041f3a  call    cs:__imp_RegCloseKey
0x180041f40  mov     r14, [rsp+1A68h+lpMem]
0x180041f48  test    r14, r14
0x180041f4b  jz      short loc_180041F62
0x180041f4d  call    cs:__imp_GetProcessHeap
0x180041f53  mov     rcx, rax; hHeap
0x180041f56  mov     r8, r14; lpMem
0x180041f59  xor     edx, edx; dwFlags
0x180041f5b  call    cs:__imp_HeapFree
0x180041f61  nop
0x180041f62  mov     rcx, [rsp+1A68h+var_1A00+8]; this
0x180041f67  test    rcx, rcx
0x180041f6a  jz      short loc_180041F71
0x180041f6c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180041f71  mov     eax, [rsp+1A68h+var_1A10]
0x180041f75  add     eax, r15d
0x180041f78  jmp     loc_180041DA6
0x180041f7d  mov     [rsp+1A68h+var_1A38], rdi
0x180041f82  mov     dword ptr [rsp+1A68h+var_1A40], 200h
0x180041f8a  lea     rax, [rsp+1A68h+var_238]
0x180041f92  mov     [rsp+1A68h+phkResult], rax
0x180041f97  xor     r9d, r9d
0x180041f9a  xor     r8d, r8d
0x180041f9d  lea     rdx, [rsp+1A68h+var_1980]
0x180041fa5  mov     rcx, r13
0x180041fa8  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180041fae  mov     [rsp+1A68h+phkResult], rdi
0x180041fb3  mov     r9d, 100h
0x180041fb9  lea     r8, [rsp+1A68h+var_438]
0x180041fc1  lea     rdx, [rsp+1A68h+var_1980]
0x180041fc9  mov     rcx, r13
0x180041fcc  call    cs:__imp_DevObjGetDeviceInstanceId
0x180041fd2  test    eax, eax
0x180041fd4  jz      loc_180041F12
0x180041fda  lea     rdx, [rsp+1A68h+var_438]; unsigned __int16 *
0x180041fe2  call    ?IsDeviceAlreadyRegistered@CHardwareManager@@AEAA_NPEAG@Z; CHardwareManager::IsDeviceAlreadyRegistered(ushort *)
0x180041fe7  test    al, al
0x180041fe9  jz      short loc_180042045
0x180041feb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180041ff2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180041ff7  test    al, al
0x180041ff9  jz      loc_180041F18
0x180041fff  mov     [rsp+1A68h+phkResult], rdi; int
0x180042004  xor     r9d, r9d
0x180042007  xor     r8d, r8d
0x18004200a  xor     edx, edx
0x18004200c  mov     rcx, cs:WNF_WBIO_BIO_UNITS_STATE_CHANGE
0x180042013  call    cs:__imp_RtlPublishWnfStateData
0x180042019  or      eax, 10000000h
0x18004201e  mov     rcx, [rsp+1A68h]; this
0x180042026  jge     loc_180041F18
0x18004202c  mov     r9d, eax; char *
0x18004202f  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\biometrics\\serv"...
0x180042036  mov     edx, 897h; void *
0x18004203b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180042040  jmp     loc_180041F18
0x180042045  mov     [rsp+1A68h+var_1A38], rdi
0x18004204a  mov     dword ptr [rsp+1A68h+var_1A40], 4
0x180042052  lea     rax, [rsp+1A68h+var_19E8]
0x18004205a  mov     [rsp+1A68h+phkResult], rax
0x18004205f  xor     r9d, r9d
0x180042062  lea     r8d, [r9+1Ah]
0x180042066  lea     rdx, [rsp+1A68h+var_1980]
0x18004206e  mov     rcx, r13
0x180042071  call    cs:__imp_DevObjGetDeviceRegistryProperty
0x180042077  cmp     [rsp+1A68h+var_19E8], edi
0x18004207e  jnz     short loc_1800420DE
0x180042080  lea     rcx, [rsp+1A68h+var_1878]; this
0x180042088  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x18004208d  nop
0x18004208e  lea     r8, [rsp+1A68h+var_438]; unsigned __int16 *
0x180042096  lea     rdx, [rsp+1A68h+var_238]; unsigned __int16 *
0x18004209e  lea     rcx, [rsp+1A68h+var_1878]; this
0x1800420a6  call    ?CaptureSensorInfo@CEtwEvent@@QEAAXPEBG0@Z; CEtwEvent::CaptureSensorInfo(ushort const *,ushort const *)
0x1800420ab  mov     dword ptr [rsp+1A68h+var_1878.DeviceInstanceId+154h], 800703F3h
0x1800420b6  mov     r8d, r15d
0x1800420b9  mov     edx, 456h
0x1800420be  lea     rcx, [rsp+1A68h+var_1878]
0x1800420c6  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x1800420cb  nop
0x1800420cc  lea     rcx, [rsp+1A68h+var_1878]; this
0x1800420d4  call    ??1CEtwEvent@@QEAA@XZ; CEtwEvent::~CEtwEvent(void)
0x1800420d9  jmp     loc_180041F18
0x1800420de  mov     dword ptr [rsp+1A68h+var_18B0], 30h ; '0'
0x1800420e9  lea     r8, [rsp+1A68h+var_18B0]
0x1800420f1  mov     edx, [rsp+1A68h+var_1A10]
0x1800420f5  mov     rcx, r13
0x1800420f8  call    cs:__imp_DevObjEnumDeviceInfo
0x1800420fe  test    eax, eax
0x180042100  jnz     short loc_180042164
0x180042102  call    cs:__imp_GetLastError
0x180042108  mov     ebx, eax
0x18004210a  test    eax, eax
0x18004210c  jle     short loc_180042117
0x18004210e  movzx   ebx, ax
0x180042111  or      ebx, 80070000h
0x180042117  lea     rcx, [rsp+1A68h+var_1878]; this
0x18004211f  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x180042124  nop
0x180042125  lea     r8, [rsp+1A68h+var_438]; unsigned __int16 *
0x18004212d  lea     rdx, [rsp+1A68h+var_238]; unsigned __int16 *
0x180042135  lea     rcx, [rsp+1A68h+var_1878]; this
0x18004213d  call    ?CaptureSensorInfo@CEtwEvent@@QEAAXPEBG0@Z; CEtwEvent::CaptureSensorInfo(ushort const *,ushort const *)
0x180042142  mov     dword ptr [rsp+1A68h+var_1878.DeviceInstanceId+154h], ebx
0x180042149  mov     r8d, r15d
0x18004214c  mov     edx, 457h
0x180042151  lea     rcx, [rsp+1A68h+var_1878]
0x180042159  call    ?Write@CEtwEvent@@QEAAJKW4WBioEventLevel@@@Z; CEtwEvent::Write(ulong,WBioEventLevel)
0x18004215e  nop
0x18004215f  jmp     loc_1800420CC
0x180042164  mov     ebx, 20019h
0x180042169  mov     dword ptr [rsp+1A68h+var_1A40], ebx
0x18004216d  mov     dword ptr [rsp+1A68h+phkResult], r15d
0x180042172  xor     r9d, r9d
0x180042175  mov     r8d, r15d
0x180042178  lea     rdx, [rsp+1A68h+var_18B0]
0x180042180  mov     rcx, r13
0x180042183  call    cs:__imp_DevObjOpenDevRegKey
0x180042189  mov     r14, rax
0x18004218c  mov     [rsp+1A68h+var_1A18], rax
0x180042191  cmp     rax, r12
0x180042194  jnz     short loc_1800421F8
0x180042196  call    cs:__imp_GetLastError
0x18004219c  mov     ebx, eax
0x18004219e  test    eax, eax
0x1800421a0  jle     short loc_1800421AB
0x1800421a2  movzx   ebx, ax
0x1800421a5  or      ebx, 80070000h
0x1800421ab  lea     rcx, [rsp+1A68h+var_1878]; this
0x1800421b3  call    ??0CEtwEvent@@QEAA@XZ; CEtwEvent::CEtwEvent(void)
0x1800421b8  nop
0x1800421b9  lea     r8, [rsp+1A68h+var_438]; unsigned __int16 *
0x1800421c1  lea     rdx, [rsp+1A68h+var_238]; unsigned __int16 *
0x1800421c9  lea     rcx, [rsp+1A68h+var_1878]; this
  ... truncated ...
```
