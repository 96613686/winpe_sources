# DesktopStoreRemediationHandler::ActivateExtensionFailed(long,ushort const *,IServiceProvider *)

- ea: `0x18015aec0`
- end: `0x18015b712`
- name: `?ActivateExtensionFailed@DesktopStoreRemediationHandler@@UEAAJJPEBGPEAUIServiceProvider@@@Z`
- size: `2130`
- prototype: `int(DesktopStoreRemediationHandler *__hidden this, int, const unsigned __int16 *, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008acc`
- `0x18000c350`
- `0x1800215d0`
- `0x18003c5e4`
- `0x18003c898`
- `0x180052980`
- `0x1800542a8`
- `0x1800fc80c`
- `0x180124428`
- `0x18013d330`
- `0x18015a804`
- `0x18015aec0`
- `0x18015ddf4`
- `0x18015dea4`
- `0x18015df08`
- `0x18015f6ac`
- `0x18015f6d0`
- `0x18015f6ec`
- `0x180359cec`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015b2d1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18015b2d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b50b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b66c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b483`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b50b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b66c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015b6b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18015b46c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18015b4dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18015b46c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18015b4dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b0f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b22f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b660`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b6a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b6c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b0f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b22f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b660`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b6a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18015b6c1`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18015b14b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18015b14b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18015b17f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18015b17f`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18015b1c9`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18015b1c9`

## string_xrefs

- `0x18015b1f3`: `Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices`
- `0x18015b175`: `GamingServices`
- `0x18015b4b9`: `page=SettingsPageInstalledApps&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=`
- `0x18015b448`: `page=SettingsPageAppsSizes&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DesktopStoreRemediationHandler::ActivateExtensionFailed(
        DesktopStoreRemediationHandler *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        struct IServiceProvider *a4)
{
  HRESULT (__stdcall *QueryService)(IServiceProvider *, const GUID *const, const IID *const, void **); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // r14d
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, LPVOID *); // rbx
  char v16; // bl
  SC_HANDLE v17; // rax
  const char *v18; // r9
  SC_HANDLE v19; // rax
  const char *v20; // r9
  const char *v21; // r9
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  unsigned int v26; // edi
  __int64 v27; // rcx
  HSTRING v28; // rbx
  HRESULT v29; // eax
  __int64 v30; // rdx
  HSTRING v31; // rbx
  int SettingsAppAumid; // eax
  int v33; // eax
  __int64 v34; // r14
  __int64 (__fastcall *v35)(__int64, _QWORD, HSTRING, _QWORD); // rsi
  HSTRING v36; // rdi
  unsigned __int16 *v37; // rbx
  __int64 v38; // rax
  int v39; // eax
  int v40; // edi
  int bIgnoreCase; // [rsp+20h] [rbp-108h]
  int bIgnoreCasea; // [rsp+20h] [rbp-108h]
  int *bIgnoreCaseb; // [rsp+20h] [rbp-108h]
  LPVOID pv; // [rsp+40h] [rbp-E8h] BYREF
  char v45; // [rsp+48h] [rbp-E0h] BYREF
  _BYTE v46[7]; // [rsp+49h] [rbp-DFh] BYREF
  HSTRING string; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v48; // [rsp+58h] [rbp-D0h] BYREF
  int v49; // [rsp+60h] [rbp-C8h] BYREF
  unsigned int v50; // [rsp+64h] [rbp-C4h] BYREF
  unsigned int v51; // [rsp+68h] [rbp-C0h] BYREF
  __int64 v52; // [rsp+70h] [rbp-B8h] BYREF
  unsigned __int16 *v53; // [rsp+78h] [rbp-B0h] BYREF
  unsigned int v54; // [rsp+80h] [rbp-A8h] BYREF
  int v55; // [rsp+84h] [rbp-A4h] BYREF
  unsigned __int16 *v56; // [rsp+88h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+90h] [rbp-98h] BYREF
  const unsigned __int16 *v58; // [rsp+98h] [rbp-90h] BYREF
  SC_HANDLE v59; // [rsp+A0h] [rbp-88h] BYREF
  _BYTE ServiceStatus[32]; // [rsp+A8h] [rbp-80h] BYREF
  _BYTE v61[32]; // [rsp+C8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  LODWORD(v53) = a2;
  v58 = a3;
  v48 = 0;
  QueryService = a4->lpVtbl->QueryService;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  v9 = ((__int64 (__fastcall *)(struct IServiceProvider *, GUID *, GUID *, __int64 *))QueryService)(
         a4,
         &GUID_23655ae6_d92b_416f_b4d6_7c8218038718,
         &GUID_23655ae6_d92b_416f_b4d6_7c8218038718,
         &v48);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v9,
      bIgnoreCase);
LABEL_33:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
    return v10;
  }
  v55 = 0;
  v49 = 0;
  v54 = 0;
  pv = 0;
  v57 = 0;
  v51 = 0;
  v50 = 0;
  v45 = 0;
  v46[0] = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v48 + 24LL))(v48, &v49);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 444;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
    goto LABEL_20;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 32LL))(v48, &v54);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 445;
    goto LABEL_19;
  }
  v13 = v54;
  LODWORD(v52) = v54;
  v14 = v48;
  v15 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v48 + 40LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v11 = v15(v14, &pv);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 447;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v48 + 64LL))(v48, &v57);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 448;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 48LL))(v48, &v51);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 449;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 80LL))(v48, &v50);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 450;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v48 + 88LL))(v48, &v45);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 451;
    goto LABEL_19;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v48 + 96LL))(v48, v46);
  v10 = v11;
  if ( v11 < 0 )
  {
    v12 = 452;
    goto LABEL_19;
  }
  if ( (v49 & 0x10003) != 0 || !v45 || (v49 & 0x80000) != 0 )
    goto LABEL_43;
  if ( v46[0] )
  {
    v16 = 1;
    v17 = OpenSCManagerW(0, 0, 1u);
    v56 = (unsigned __int16 *)v17;
    if ( !v17 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1D6,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        v18);
    v19 = OpenServiceW(v17, L"GamingServices", 4u);
    v59 = v19;
    if ( !v19 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        v20);
    memset(ServiceStatus, 0, 28);
    if ( !QueryServiceStatus(v19, (LPSERVICE_STATUS)ServiceStatus) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        v21);
    if ( *(_DWORD *)&ServiceStatus[4] != 4 )
    {
      v10 = MaybeShowActivationErrorPopupIfCritical(
              2147943462LL,
              v13,
              L"Microsoft.GamingServices_8wekyb3d8bbwe!GamingServices",
              v50);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v59);
      wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v56);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_33;
    }
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v59);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v56);
    if ( a2 == -2147024894 )
    {
      v10 = LaunchStoreForError(2147942402LL, pv, a3, v51, v13, v57, 1);
      goto LABEL_20;
    }
  }
  else
  {
    v16 = 1;
  }
  if ( CompareStringOrdinal(a3, -1, L"Microsoft.WindowsStore_8wekyb3d8bbwe!App", -1, 1) == 2 )
  {
    if ( a2 != -2147023636 && a2 != -2144927149 )
    {
      if ( a2 == -2147009284 )
      {
        v23 = AttemptStoreRepairAsync();
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1F7,
            (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
            (const char *)(unsigned int)v23,
            bIgnoreCasea);
      }
LABEL_43:
      if ( pv )
        CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      return a2;
    }
    goto LABEL_48;
  }
  if ( a2 != -2147009284 || !GetPackageArchitectureIsArmFromPackageFullName((char *)pv) )
LABEL_48:
    v16 = 0;
  v24 = 2147958074LL;
  if ( !v16 )
    v24 = a2;
  bIgnoreCaseb = &v55;
  v25 = MaybeShowActivationErrorPopupIfCritical(v24, v13, a3, v50);
  v26 = v25;
  if ( v25 >= 0 )
    goto LABEL_77;
  if ( !ShouldLaunchStoreForError(v25) )
  {
    if ( v26 != -2147217655 )
      goto LABEL_77;
    string = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RenameSettingsPageAppsSizesReferences>::GetImpl'::`2'::impl) )
    {
      WindowsDeleteString(string);
      string = 0;
      v31 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v61, &v58) + 24);
      *(_QWORD *)&ServiceStatus[24] = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        (HSTRING_HEADER *)ServiceStatus,
        L"page=SettingsPageInstalledApps&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=",
        0x73u,
        0x72u);
      v29 = WindowsConcatString(*(HSTRING *)&ServiceStatus[24], v31, &string);
      v10 = v29;
      if ( v29 < 0 )
      {
        v30 = 527;
        goto LABEL_60;
      }
    }
    else
    {
      WindowsDeleteString(string);
      string = 0;
      v28 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v61, &v58) + 24);
      *(_QWORD *)&ServiceStatus[24] = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        (HSTRING_HEADER *)ServiceStatus,
        L"page=SettingsPageAppsSizes&target=SystemSettings_StorageSense_HiddenAppAdvancedPageLink&invoke=true&parameter=",
        0x6Fu,
        0x6Eu);
      v29 = WindowsConcatString(*(HSTRING *)&ServiceStatus[24], v28, &string);
      v10 = v29;
      if ( v29 < 0 )
      {
        v30 = 532;
LABEL_60:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
          (const char *)(unsigned int)v29,
          (int)&v55);
        goto LABEL_61;
      }
    }
    v53 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v53,
      0);
    SettingsAppAumid = GetSettingsAppAumid(&v53);
    v10 = SettingsAppAumid;
    if ( SettingsAppAumid >= 0 )
    {
      v52 = 0;
      *(_QWORD *)&ServiceStatus[24] = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        (HSTRING_HEADER *)ServiceStatus,
        L"Windows.ApplicationModel.Activation.Private.ApplicationActivation",
        0x42u,
        0x41u);
      v33 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::Private::IApplicationActivationStatics>>(
              *(_QWORD *)&ServiceStatus[24],
              &v52);
      v10 = v33;
      if ( v33 >= 0 )
      {
        v34 = v52;
        v35 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _QWORD))(*(_QWORD *)v52 + 48LL);
        v36 = string;
        v37 = v53;
        v56 = v53;
        v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v61, &v56);
        v39 = v35(v34, *(_QWORD *)(v38 + 24), v36, 0);
        v40 = v39;
        if ( v39 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x21F,
            (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
            (const char *)(unsigned int)v39,
            0);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
          if ( v37 )
            CoTaskMemFree(v37);
          WindowsDeleteString(string);
          string = 0;
          if ( pv )
            CoTaskMemFree(pv);
          v10 = v40;
          goto LABEL_33;
        }
        v26 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        if ( v37 )
          CoTaskMemFree(v37);
        WindowsDeleteString(string);
        goto LABEL_77;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21D,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)v33,
        (int)&v55);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x218,
        (unsigned int)"shell\\twinui\\activationerrorpopup\\lib\\desktopstoreremediationhandler.cpp",
        (const char *)(unsigned int)SettingsAppAumid,
        (int)&v55);
    }
    if ( v53 )
      CoTaskMemFree(v53);
LABEL_61:
    WindowsDeleteString(string);
    string = 0;
LABEL_20:
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_33;
  }
  LODWORD(bIgnoreCaseb) = v13;
  v26 = LaunchStoreForError(v27, pv, a3, v51, bIgnoreCaseb, v57, 0);
LABEL_77:
  if ( pv )
    CoTaskMemFree(pv);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
  return v26;
}

```

## disassembly

```asm
0x18015aec0  push    rbx
0x18015aec2  push    rsi
0x18015aec3  push    rdi
0x18015aec4  push    r12
0x18015aec6  push    r13
0x18015aec8  push    r14
0x18015aeca  push    r15
0x18015aecc  sub     rsp, 0F0h
0x18015aed3  mov     rax, cs:__security_cookie
0x18015aeda  xor     rax, rsp
0x18015aedd  mov     [rsp+128h+var_40], rax
0x18015aee5  mov     rdi, r9
0x18015aee8  mov     r12, r8
0x18015aeeb  mov     r13d, edx
0x18015aeee  mov     esi, edx
0x18015aef0  mov     dword ptr [rsp+128h+var_B0], edx
0x18015aef4  mov     [rsp+128h+var_90], r8
0x18015aefc  xor     r15d, r15d
0x18015aeff  mov     [rsp+128h+var_D0], r15
0x18015af04  mov     rax, [r9]
0x18015af07  mov     rbx, [rax+18h]
0x18015af0b  lea     rcx, [rsp+128h+var_D0]
0x18015af10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015af15  lea     r9, [rsp+128h+var_D0]
0x18015af1a  lea     rdx, _GUID_23655ae6_d92b_416f_b4d6_7c8218038718
0x18015af21  mov     r8, rdx
0x18015af24  mov     rcx, rdi
0x18015af27  mov     rax, rbx
0x18015af2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015af2f  mov     ebx, eax
0x18015af31  test    eax, eax
0x18015af33  jns     short loc_18015AF56
0x18015af35  mov     rcx, [rsp+128h]; this
0x18015af3d  mov     r9d, eax; char *
0x18015af40  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015af47  mov     edx, 1AEh; void *
0x18015af4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015af51  jmp     loc_18015B0FC
0x18015af56  mov     [rsp+128h+var_A4], r15d
0x18015af5e  mov     [rsp+128h+var_C8], r15d
0x18015af63  mov     [rsp+128h+var_A8], r15d
0x18015af6b  mov     [rsp+128h+pv], r15
0x18015af70  mov     [rsp+128h+var_98], r15
0x18015af78  mov     [rsp+128h+var_C0], r15d
0x18015af7d  mov     [rsp+128h+var_C4], r15d
0x18015af82  mov     [rsp+128h+var_E0], r15b
0x18015af87  mov     [rsp+128h+var_DF], r15b
0x18015af8c  mov     rcx, [rsp+128h+var_D0]
0x18015af91  mov     rax, [rcx]
0x18015af94  lea     rdx, [rsp+128h+var_C8]
0x18015af99  mov     rax, [rax+18h]
0x18015af9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015afa2  mov     ebx, eax
0x18015afa4  test    eax, eax
0x18015afa6  jns     short loc_18015AFB2
0x18015afa8  mov     edx, 1BCh
0x18015afad  jmp     loc_18015B0D3
0x18015afb2  mov     rcx, [rsp+128h+var_D0]
0x18015afb7  mov     rax, [rcx]
0x18015afba  lea     rdx, [rsp+128h+var_A8]
0x18015afc2  mov     rax, [rax+20h]
0x18015afc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015afcb  mov     ebx, eax
0x18015afcd  test    eax, eax
0x18015afcf  jns     short loc_18015AFDB
0x18015afd1  mov     edx, 1BDh
0x18015afd6  jmp     loc_18015B0D3
0x18015afdb  mov     r14d, [rsp+128h+var_A8]
0x18015afe3  mov     dword ptr [rsp+128h+var_B8], r14d
0x18015afe8  mov     rdi, [rsp+128h+var_D0]
0x18015afed  mov     rax, [rdi]
0x18015aff0  mov     rbx, [rax+28h]
0x18015aff4  xor     edx, edx
0x18015aff6  lea     rcx, [rsp+128h+pv]
0x18015affb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18015b000  lea     rdx, [rsp+128h+pv]
0x18015b005  mov     rcx, rdi
0x18015b008  mov     rax, rbx
0x18015b00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b010  mov     ebx, eax
0x18015b012  test    eax, eax
0x18015b014  jns     short loc_18015B020
0x18015b016  mov     edx, 1BFh
0x18015b01b  jmp     loc_18015B0D3
0x18015b020  mov     rcx, [rsp+128h+var_D0]
0x18015b025  mov     rax, [rcx]
0x18015b028  lea     rdx, [rsp+128h+var_98]
0x18015b030  mov     rax, [rax+40h]
0x18015b034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b039  mov     ebx, eax
0x18015b03b  test    eax, eax
0x18015b03d  jns     short loc_18015B049
0x18015b03f  mov     edx, 1C0h
0x18015b044  jmp     loc_18015B0D3
0x18015b049  mov     rcx, [rsp+128h+var_D0]
0x18015b04e  mov     rax, [rcx]
0x18015b051  lea     rdx, [rsp+128h+var_C0]
0x18015b056  mov     rax, [rax+30h]
0x18015b05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b05f  mov     ebx, eax
0x18015b061  test    eax, eax
0x18015b063  jns     short loc_18015B06C
0x18015b065  mov     edx, 1C1h
0x18015b06a  jmp     short loc_18015B0D3
0x18015b06c  mov     rcx, [rsp+128h+var_D0]
0x18015b071  mov     rax, [rcx]
0x18015b074  lea     rdx, [rsp+128h+var_C4]
0x18015b079  mov     rax, [rax+50h]
0x18015b07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b082  mov     ebx, eax
0x18015b084  test    eax, eax
0x18015b086  jns     short loc_18015B08F
0x18015b088  mov     edx, 1C2h
0x18015b08d  jmp     short loc_18015B0D3
0x18015b08f  mov     rcx, [rsp+128h+var_D0]
0x18015b094  mov     rax, [rcx]
0x18015b097  lea     rdx, [rsp+128h+var_E0]
0x18015b09c  mov     rax, [rax+58h]
0x18015b0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b0a5  mov     ebx, eax
0x18015b0a7  test    eax, eax
0x18015b0a9  jns     short loc_18015B0B2
0x18015b0ab  mov     edx, 1C3h
0x18015b0b0  jmp     short loc_18015B0D3
0x18015b0b2  mov     rcx, [rsp+128h+var_D0]
0x18015b0b7  mov     rax, [rcx]
0x18015b0ba  lea     rdx, [rsp+128h+var_DF]
0x18015b0bf  mov     rax, [rax+60h]
0x18015b0c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015b0c8  mov     ebx, eax
0x18015b0ca  test    eax, eax
0x18015b0cc  jns     short loc_18015B10D
0x18015b0ce  mov     edx, 1C4h; void *
0x18015b0d3  mov     r9d, eax; char *
0x18015b0d6  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015b0dd  mov     rcx, [rsp+128h]; this
0x18015b0e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015b0ea  nop
0x18015b0eb  mov     rcx, [rsp+128h+pv]; pv
0x18015b0f0  test    rcx, rcx
0x18015b0f3  jz      short loc_18015B0FC
0x18015b0f5  call    cs:__imp_CoTaskMemFree
0x18015b0fb  nop
0x18015b0fc  lea     rcx, [rsp+128h+var_D0]
0x18015b101  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015b106  mov     eax, ebx
0x18015b108  jmp     loc_18015B343
0x18015b10d  test    [rsp+128h+var_C8], 10003h
0x18015b115  jnz     loc_18015B326
0x18015b11b  cmp     [rsp+128h+var_E0], r15b
0x18015b120  jz      loc_18015B326
0x18015b126  test    [rsp+128h+var_C8], 80000h
0x18015b12e  jnz     loc_18015B326
0x18015b134  cmp     [rsp+128h+var_DF], r15b
0x18015b139  jz      loc_18015B2B8
0x18015b13f  mov     ebx, 1
0x18015b144  mov     r8d, ebx; dwDesiredAccess
0x18015b147  xor     edx, edx; lpDatabaseName
0x18015b149  xor     ecx, ecx; lpMachineName
0x18015b14b  call    cs:__imp_OpenSCManagerW
0x18015b151  mov     [rsp+128h+var_A0], rax
0x18015b159  test    rax, rax
0x18015b15c  setz    dl
0x18015b15f  mov     rcx, [rsp+128h]; this
0x18015b167  test    dl, dl
0x18015b169  jnz     loc_18015B6D9
0x18015b16f  mov     r8d, 4; dwDesiredAccess
0x18015b175  lea     rdx, aGamingservices; "GamingServices"
0x18015b17c  mov     rcx, rax; hSCManager
0x18015b17f  call    cs:__imp_OpenServiceW
0x18015b185  mov     [rsp+128h+var_88], rax
0x18015b18d  test    rax, rax
0x18015b190  setz    dl
0x18015b193  mov     rcx, [rsp+128h]; this
0x18015b19b  test    dl, dl
0x18015b19d  jnz     loc_18015B6EB
0x18015b1a3  xorps   xmm0, xmm0
0x18015b1a6  movups  xmmword ptr [rsp+128h+ServiceStatus], xmm0
0x18015b1ae  movups  xmmword ptr [rsp+128h+ServiceStatus+0Ch], xmm0
0x18015b1b6  mov     rdi, [rsp+128h]
0x18015b1be  lea     rdx, [rsp+128h+ServiceStatus]; lpServiceStatus
0x18015b1c6  mov     rcx, rax; hService
0x18015b1c9  call    cs:__imp_QueryServiceStatus
0x18015b1cf  test    eax, eax
0x18015b1d1  jz      loc_18015B6FC
0x18015b1d7  cmp     dword ptr [rsp+128h+ServiceStatus+4], 4
0x18015b1df  jz      short loc_18015B247
0x18015b1e1  lea     rax, [rsp+128h+var_A4]
0x18015b1e9  mov     qword ptr [rsp+128h+bIgnoreCase], rax
0x18015b1ee  mov     r9d, [rsp+128h+var_C4]
0x18015b1f3  lea     r8, aMicrosoftGamin_0; "Microsoft.GamingServices_8wekyb3d8bbwe!"...
0x18015b1fa  mov     edx, r14d
0x18015b1fd  mov     ecx, 80070426h
0x18015b202  call    ?MaybeShowActivationErrorPopupIfCritical@@YAJJW4_PackageOrigin@@PEBGW4ACTIVATION_PHASE@@PEAW4ACTIVATIONERROR_DISMISS_METHOD@@@Z; MaybeShowActivationErrorPopupIfCritical(long,_PackageOrigin,ushort const *,ACTIVATION_PHASE,ACTIVATIONERROR_DISMISS_METHOD *)
0x18015b207  mov     ebx, eax
0x18015b209  lea     rcx, [rsp+128h+var_88]
0x18015b211  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18015b216  nop
0x18015b217  lea     rcx, [rsp+128h+var_A0]
0x18015b21f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18015b224  nop
0x18015b225  mov     rcx, [rsp+128h+pv]; pv
0x18015b22a  test    rcx, rcx
0x18015b22d  jz      short loc_18015B236
0x18015b22f  call    cs:__imp_CoTaskMemFree
0x18015b235  nop
0x18015b236  lea     rcx, [rsp+128h+var_D0]
0x18015b23b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015b240  mov     eax, ebx
0x18015b242  jmp     loc_18015B343
0x18015b247  lea     rcx, [rsp+128h+var_88]
0x18015b24f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18015b254  nop
0x18015b255  lea     rcx, [rsp+128h+var_A0]
0x18015b25d  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18015b262  nop
0x18015b263  jmp     short loc_18015B280
0x18015b265  xor     r15d, r15d
0x18015b268  lea     ebx, [r15+1]
0x18015b26c  mov     r14d, dword ptr [rsp+128h+var_B8]
0x18015b271  mov     esi, dword ptr [rsp+128h+var_B0]
0x18015b275  mov     r12, [rsp+128h+var_90]
0x18015b27d  mov     r13d, esi
0x18015b280  mov     ecx, 80070002h
0x18015b285  cmp     esi, ecx
0x18015b287  jnz     short loc_18015B2BD
0x18015b289  mov     rax, [rsp+128h+var_98]
0x18015b291  mov     [rsp+128h+var_F8], bl
0x18015b295  mov     [rsp+128h+var_100], rax
0x18015b29a  mov     [rsp+128h+bIgnoreCase], r14d
0x18015b29f  mov     r9d, [rsp+128h+var_C0]
0x18015b2a4  mov     r8, r12
0x18015b2a7  mov     rdx, [rsp+128h+pv]
0x18015b2ac  call    ?LaunchStoreForError@@YAJJPEBG0IW4_PackageOrigin@@_K_N@Z; LaunchStoreForError(long,ushort const *,ushort const *,uint,_PackageOrigin,unsigned __int64,bool)
0x18015b2b1  mov     ebx, eax
0x18015b2b3  jmp     loc_18015B0EB
0x18015b2b8  mov     ebx, 1
0x18015b2bd  mov     [rsp+128h+bIgnoreCase], ebx; int
0x18015b2c1  or      edx, 0FFFFFFFFh; cchCount1
0x18015b2c4  mov     r9d, edx; cchCount2
0x18015b2c7  lea     r8, aMicrosoftWindo_17; "Microsoft.WindowsStore_8wekyb3d8bbwe!Ap"...
0x18015b2ce  mov     rcx, r12; lpString1
0x18015b2d1  call    cs:__imp_CompareStringOrdinal
0x18015b2d7  cmp     eax, 2
0x18015b2da  jnz     loc_18015B366
0x18015b2e0  cmp     esi, 800704ECh
0x18015b2e6  jz      loc_18015B37C
0x18015b2ec  cmp     esi, 80270253h
0x18015b2f2  jz      loc_18015B37C
0x18015b2f8  cmp     esi, 80073CFCh
0x18015b2fe  jnz     short loc_18015B326
0x18015b300  call    ?AttemptStoreRepairAsync@@YAJXZ; AttemptStoreRepairAsync(void)
0x18015b305  mov     rcx, [rsp+128h]; this
0x18015b30d  test    eax, eax
0x18015b30f  jns     short loc_18015B326
0x18015b311  mov     r9d, eax; char *
0x18015b314  lea     r8, aShellTwinuiAct_0; "shell\\twinui\\activationerrorpopup\\li"...
0x18015b31b  mov     edx, 1F7h; void *
0x18015b320  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18015b325  nop
0x18015b326  mov     rcx, [rsp+128h+pv]; pv
0x18015b32b  test    rcx, rcx
0x18015b32e  jz      short loc_18015B337
0x18015b330  call    cs:__imp_CoTaskMemFree
0x18015b336  nop
0x18015b337  lea     rcx, [rsp+128h+var_D0]
0x18015b33c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18015b341  mov     eax, esi
0x18015b343  mov     rcx, [rsp+128h+var_40]
0x18015b34b  xor     rcx, rsp; StackCookie
0x18015b34e  call    __security_check_cookie
0x18015b353  add     rsp, 0F0h
0x18015b35a  pop     r15
0x18015b35c  pop     r14
0x18015b35e  pop     r13
0x18015b360  pop     r12
0x18015b362  pop     rdi
0x18015b363  pop     rsi
0x18015b364  pop     rbx
0x18015b365  retn
0x18015b366  cmp     esi, 80073CFCh
0x18015b36c  jnz     short loc_18015B37C
0x18015b36e  mov     rcx, [rsp+128h+pv]; char *
0x18015b373  call    ?GetPackageArchitectureIsArmFromPackageFullName@@YA_NPEBG@Z; GetPackageArchitectureIsArmFromPackageFullName(ushort const *)
0x18015b378  test    al, al
0x18015b37a  jnz     short loc_18015B37F
0x18015b37c  mov     bl, r15b
0x18015b37f  mov     ecx, 80073D3Ah
0x18015b384  test    bl, bl
0x18015b386  cmovz   ecx, r13d
0x18015b38a  lea     rax, [rsp+128h+var_A4]
0x18015b392  mov     qword ptr [rsp+128h+bIgnoreCase], rax; int
0x18015b397  mov     r9d, [rsp+128h+var_C4]
0x18015b39c  mov     r8, r12
0x18015b39f  mov     edx, r14d
0x18015b3a2  call    ?MaybeShowActivationErrorPopupIfCritical@@YAJJW4_PackageOrigin@@PEBGW4ACTIVATION_PHASE@@PEAW4ACTIVATIONERROR_DISMISS_METHOD@@@Z; MaybeShowActivationErrorPopupIfCritical(long,_PackageOrigin,ushort const *,ACTIVATION_PHASE,ACTIVATIONERROR_DISMISS_METHOD *)
0x18015b3a7  mov     edi, eax
0x18015b3a9  test    eax, eax
0x18015b3ab  jns     loc_18015B6B7
0x18015b3b1  mov     ecx, eax; int
  ... truncated ...
```
