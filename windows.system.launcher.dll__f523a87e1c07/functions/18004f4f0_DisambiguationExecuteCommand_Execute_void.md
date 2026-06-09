# DisambiguationExecuteCommand::Execute(void)

- ea: `0x18004f4f0`
- end: `0x180050309`
- name: `?Execute@DisambiguationExecuteCommand@@UEAAJXZ`
- size: `3609`
- prototype: `__int64 __fastcall(DisambiguationExecuteCommand *__hidden this)`
- caller_count: `1`
- callee_count: `62`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004f310`

## callees

- `0x18000f194`
- `0x18004a888`
- `0x18004acdc`
- `0x18004be54`
- `0x18004c62c`
- `0x18004c690`
- `0x18004e198`
- `0x18004e378`
- `0x18004e39c`
- `0x18004e50c`
- `0x18004e550`
- `0x18004e664`
- `0x18004e6a0`
- `0x18004e734`
- `0x18004e790`
- `0x18004e7cc`
- `0x18004ee50`
- `0x18004f008`
- `0x18004f054`
- `0x18004f4f0`
- `0x180050310`
- `0x1800503e0`
- `0x18005042c`
- `0x18005044c`
- `0x1800504f4`
- `0x1800505e4`
- `0x1800550d8`
- `0x18005cf50`
- `0x18005d02c`
- `0x18005d098`
- `0x1800795e0`
- `0x18007cd2c`
- `0x1800814e0`
- `0x180083df4`
- `0x18008a030`
- `0x18008a9d8`
- `0x18008df9c`
- `0x1800f4848`
- `0x1800f48e8`
- `0x1800f4b9c`
- `0x1800f4e2c`
- `0x1800f4f44`
- `0x1800f5174`
- `0x1800f528c`
- `0x1800f59c4`
- `0x1800f5fcc`
- `0x1800f6148`
- `0x1800f642c`
- `0x1800f645c`
- `0x1800f6488`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fd89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ffd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004fd89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004ffd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fdbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ff10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004fdbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ff10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050007`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050235`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004fc6d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004fcd6`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004fc6d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18004fcd6`

## string_xrefs

- `0x18004f56e`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004f5c7`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004f61f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004f66d`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004f924`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004f95f`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004fb93`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004fbdd`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004fc33`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004fca2`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18004fd08`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x1800500e1`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x180050115`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x1800501f6`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\disambiguationexecutecommand.cpp`
- `0x18005008e`: `Windows.Internal.PlatformExtensionContracts.AppResolverContract`

## pseudocode

```c
// Hidden C++ exception states: #wind=34 #try_helpers=1
__int64 __fastcall DisambiguationExecuteCommand::Execute(DisambiguationExecuteCommand *this)
{
  __int64 v2; // rcx
  _QWORD *v3; // rbx
  int v4; // eax
  __int64 (__fastcall *v5)(_QWORD, __int64, _QWORD, GUID *); // rsi
  int v6; // eax
  int v7; // eax
  char IsFilePath; // r14
  __int64 v9; // rcx
  _QWORD *v10; // rsi
  const WCHAR *v11; // rax
  __int64 v12; // rdi
  __int64 FileFromPathAsync; // rax
  __int64 v14; // rax
  void (__fastcall ***v15)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  void (__fastcall ***v19)(_QWORD, __int64 *, __int64 **); // rcx
  void (__fastcall ***v20)(_QWORD, __int64 *, __int64 **); // rcx
  int v21; // eax
  __int64 v22; // rdi
  IUnknown *v23; // rbx
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  int v27; // eax
  bool v28; // zf
  _QWORD *v29; // rax
  HSTRING *OriginatingApplicationUserModelId; // rax
  void (__fastcall ***v31)(_QWORD, __int64 *, __int64 **); // rcx
  __int64 v32; // rax
  HSTRING *v33; // rax
  unsigned int v34; // edi
  int v35; // r12d
  unsigned int v36; // edi
  int v37; // eax
  _QWORD *v38; // rax
  _QWORD *v39; // rdi
  _QWORD *v40; // rdx
  int v41; // eax
  HSTRING *p_string; // [rsp+20h] [rbp-2F8h]
  int v44; // [rsp+20h] [rbp-2F8h]
  int v45[2]; // [rsp+30h] [rbp-2E8h] BYREF
  char v46; // [rsp+38h] [rbp-2E0h] BYREF
  _QWORD *v47; // [rsp+40h] [rbp-2D8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-2D0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-2C8h] BYREF
  int v50[2]; // [rsp+58h] [rbp-2C0h] BYREF
  IUnknown *punk; // [rsp+60h] [rbp-2B8h] BYREF
  __int64 v52; // [rsp+68h] [rbp-2B0h] BYREF
  __int64 v53; // [rsp+70h] [rbp-2A8h] BYREF
  void *v54; // [rsp+78h] [rbp-2A0h] BYREF
  void *ppvOut; // [rsp+80h] [rbp-298h] BYREF
  __int64 v56; // [rsp+88h] [rbp-290h] BYREF
  const WCHAR *v57; // [rsp+90h] [rbp-288h] BYREF
  _BYTE *v58; // [rsp+98h] [rbp-280h]
  _QWORD *v59; // [rsp+A0h] [rbp-278h]
  _QWORD v60[2]; // [rsp+B0h] [rbp-268h] BYREF
  _QWORD *v61; // [rsp+C0h] [rbp-258h] BYREF
  __int64 v62; // [rsp+C8h] [rbp-250h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-248h] BYREF
  _QWORD v64[4]; // [rsp+D8h] [rbp-240h] BYREF
  _QWORD v65[5]; // [rsp+F8h] [rbp-220h] BYREF
  HSTRING v66; // [rsp+120h] [rbp-1F8h]
  _BYTE v67[32]; // [rsp+128h] [rbp-1F0h] BYREF
  _BYTE v68[32]; // [rsp+148h] [rbp-1D0h] BYREF
  _QWORD v69[3]; // [rsp+168h] [rbp-1B0h] BYREF
  unsigned __int64 v70; // [rsp+180h] [rbp-198h]
  _QWORD v71[42]; // [rsp+190h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+0h]

  wil::ActivityBase<LauncherDesktopProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v71);
  v71[0] = &LauncherDesktopProvider::HandlerDisambiguation::`vftable';
  LauncherDesktopProvider::HandlerDisambiguation::StartActivity((LauncherDesktopProvider::HandlerDisambiguation *)v71);
  if ( !*((_QWORD *)this + 5) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = *((_QWORD *)this + 5);
  if ( !v2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
      (const char *)0x80070057LL,
      (int)p_string);
  v3 = (_QWORD *)((char *)this + 48);
  if ( !*((_QWORD *)this + 6) )
  {
    *(_QWORD *)v50 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *))(*(_QWORD *)v2 + 24LL))(
           v2,
           0,
           &BHID_AssociationArray,
           &GUID_d7d31033_ccb5_40e3_8efa_a668f231003f);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v4,
        (int)v50);
    v5 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, GUID *))(**(_QWORD **)v50 + 64LL);
    if ( *v3 )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref((char *)this + 48);
    LODWORD(p_string) = (_DWORD)this + 48;
    v6 = v5(*(_QWORD *)v50, 35651598, 0, &GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v6,
        (int)p_string);
  }
  v53 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**((_QWORD **)this + 5) + 64LL))(
         *((_QWORD *)this + 5),
         0,
         &v53);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
      (const char *)(unsigned int)v7,
      (int)p_string);
  IsFilePath = DisambiguationExecuteCommand::IsFilePath(retaddr, &v53);
  v46 = IsFilePath;
  DisambiguationExecuteCommand::GetFilePathOrUri(v9, v69, &v53);
  v10 = operator new(0x110u);
  memset_0(v10, 0, 0x110u);
  PendingLaunchRequest::PendingLaunchRequest((PendingLaunchRequest *)v10);
  *v10 = &PendingLaunchRequest::`vftable'{for `winrt::impl::producer_convert<PendingLaunchRequest,IObjectWithSite,void>'};
  v10[1] = &PendingLaunchRequest::`vftable'{for `winrt::impl::producer_convert<PendingLaunchRequest,IServiceProvider,void>'};
  v10[6] = &PendingLaunchRequest::`vftable';
  v61 = v10;
  v11 = (const WCHAR *)v69;
  if ( v70 > 7 )
    v11 = (const WCHAR *)v69[0];
  v57 = v11;
  v58 = (_BYTE *)v69[2];
  v12 = winrt::hstring::hstring(v45, &v57);
  v47 = (_QWORD *)v12;
  winrt::hstring::operator=(v10 + 9, v12);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v12);
  *(_QWORD *)v50 = 0;
  if ( IsFilePath )
  {
    winrt::param::hstring::hstring(&v57, v69);
    FileFromPathAsync = winrt::Windows::Storage::StorageFile::GetFileFromPathAsync((const struct winrt::param::hstring *)v45);
    winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Storage::StorageFile>::get(
      FileFromPathAsync,
      &v47);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v45);
    winrt::impl::consume_Windows_Storage_IStorageFile<winrt::Windows::Storage::IStorageFile>::FileType(&v47, &punk);
    v14 = winrt::hstring::hstring((winrt::hstring *)v45, (const struct winrt::hstring *)&punk);
    PendingLaunchRequest::SchemeOrExtension(v10, v14);
    *((_DWORD *)v10 + 25) = 2;
    winrt::param::hstring::hstring((winrt::param::hstring *)v67, &LocaleName);
    v57 = (const WCHAR *)punk;
    v60[0] = &v57;
    v60[1] = v67;
    *(_QWORD *)v45 = &qword_180161568;
    _InterlockedIncrement64(&qword_180161568);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics> )
    {
      _lambda_897320ef44830be241559856707be0c1_::operator()(
        v60,
        &string,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>);
      _InterlockedDecrement64(&qword_180161568);
    }
    else
    {
      _InterlockedDecrement64(&qword_180161568);
      winrt::impl::factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>::call<_lambda_5587ea74091e75e230748904aa055f31_ &>(
        v15,
        (__int64)&string,
        (__int64)v60);
    }
    winrt::Windows::Foundation::IUnknown::operator=(v50, &string);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&string);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&punk);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v47);
  }
  else
  {
    winrt::param::hstring::hstring(v67, v69);
    winrt::Windows::Foundation::Uri::Uri(
      (winrt::Windows::Foundation::Uri *)v45,
      (const struct winrt::param::hstring *)v67);
    winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::SchemeName(
      v45,
      &v47);
    v16 = winrt::hstring::hstring((winrt::hstring *)&StringRawBuffer, (const struct winrt::hstring *)&v47);
    PendingLaunchRequest::SchemeOrExtension(v10, v16);
    string = 0;
    p_string = &string;
    v17 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, GUID *))(*(_QWORD *)*v3 + 64LL))(
            *v3,
            35651613,
            0,
            &GUID_1bee549b_0bf4_4c81_88b3_ad5bf3ab0ac4);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v17,
        (int)&string);
    LODWORD(punk) = 0;
    v18 = (*(__int64 (__fastcall **)(HSTRING, IUnknown **))(*(_QWORD *)string + 32LL))(string, &punk);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v18,
        (int)&string);
    if ( ((unsigned __int16)punk & 0x4000) == 0 )
      goto LABEL_32;
    winrt::param::hstring::hstring((winrt::param::hstring *)v64, &LocaleName);
    winrt::param::hstring::hstring((winrt::param::hstring *)v68, &LocaleName);
    winrt::param::hstring::hstring(v67, v69);
    v57 = (const WCHAR *)v67;
    v58 = v68;
    v59 = v64;
    v60[0] = &qword_180161568;
    _InterlockedIncrement64(&qword_180161568);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics> )
    {
      _lambda_b7132158311bf1fb9a2533bdb51fa3f6_::operator()(
        &v57,
        &StringRawBuffer,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>);
      _InterlockedDecrement64(&qword_180161568);
    }
    else
    {
      _InterlockedDecrement64(&qword_180161568);
      winrt::impl::factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>::call<_lambda_b7132158311bf1fb9a2533bdb51fa3f6_ &>(
        v19,
        (__int64)&StringRawBuffer,
        (__int64)&v57);
    }
    winrt::Windows::Foundation::IUnknown::operator=(v50, &StringRawBuffer);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&StringRawBuffer);
    if ( *(_QWORD *)v50
      && (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::Internal::Launch::ExtensionInfo>,winrt::Windows::System::Internal::Launch::ExtensionInfo>::Size(v50) )
    {
      *((_DWORD *)v10 + 25) = 3;
    }
    else
    {
LABEL_32:
      *((_DWORD *)v10 + 25) = 1;
      winrt::param::hstring::hstring((winrt::param::hstring *)v68, &LocaleName);
      v64[0] = v47;
      v57 = (const WCHAR *)v64;
      v58 = v68;
      v60[0] = &qword_180161568;
      _InterlockedIncrement64(&qword_180161568);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics> )
      {
        _lambda_bdf625ef719f10884237daa82c9f6b8f_::operator()(
          &v57,
          &StringRawBuffer,
          &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>);
        _InterlockedDecrement64(&qword_180161568);
      }
      else
      {
        _InterlockedDecrement64(&qword_180161568);
        winrt::impl::factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>::call<_lambda_bdf625ef719f10884237daa82c9f6b8f_ &>(
          v20,
          (__int64)&StringRawBuffer,
          (__int64)&v57);
      }
      winrt::Windows::Foundation::IUnknown::operator=(v50, &StringRawBuffer);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&StringRawBuffer);
    }
    if ( string )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&string);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v47);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v45);
  }
  punk = 0;
  v21 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWRLObjectWithSite,IServiceProvider,IExecuteCommand,IObjectWithSelection,IObjectWithAssociationElement,IOpenWithLauncher>>(
          (__int64)this - 32,
          (__int64)&GUID_00000000_0000_0000_c000_000000000046,
          &punk);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
      (const char *)(unsigned int)v21,
      (int)p_string);
  winrt::impl::as<IObjectWithSite,PendingLaunchRequest,0>(
    v45,
    (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64 *))v10);
  v22 = *(_QWORD *)v45;
  v23 = punk;
  v24 = (*(__int64 (__fastcall **)(_QWORD, IUnknown *))(**(_QWORD **)v45 + 24LL))(*(_QWORD *)v45, punk);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
      (const char *)(unsigned int)v24,
      (int)p_string);
  if ( v22 )
    winrt::com_ptr<IPropertyBag>::unconditional_release_ref(v45);
  TelemetryCorrelationVectorServiceProvider::Increment(&v52, v23);
  v25 = v52;
  if ( !v52 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v25 = v52;
  }
  if ( !v25 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
      (const char *)0x80070057LL,
      (int)p_string);
  v63 = 0;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         v23,
         (const GUID *const)&SID_LaunchSourceViewSizePreference,
         &GUID_e5aa01f7_1fb8_4830_8720_4e6734cbd5f3,
         &ppvOut) >= 0 )
  {
    v26 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, &v63);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x95,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v26,
        (int)p_string);
  }
  v62 = 0;
  v54 = 0;
  if ( IUnknown_QueryService(
         v23,
         (const GUID *const)&SID_ApplicationUserContextTokenInfo,
         &GUID_cb738c08_8b2d_4349_a14d_b969e62e964c,
         &v54) >= 0 )
  {
    v27 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v54 + 24LL))(v54, &v62);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v27,
        (int)p_string);
  }
  CallerInformation::Capture(v65, v63, v62);
  v28 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::Internal::Launch::ExtensionInfo>,winrt::Windows::System::Internal::Launch::ExtensionInfo>::Size(v50) == 0;
  *(_QWORD *)v45 = v52;
  v29 = v69;
  if ( v28 )
  {
    if ( v70 > 7 )
      v29 = (_QWORD *)v69[0];
    v47 = v29;
    OriginatingApplicationUserModelId = (HSTRING *)CallerInformation::GetOriginatingApplicationUserModelId(v65, &string);
    StringRawBuffer = WindowsGetStringRawBuffer(*OriginatingApplicationUserModelId, 0);
    LauncherDesktopProvider::HandlerDisambiguation::UnknownHandlerDisambiguation<unsigned short const *,bool &,unsigned short const *,char *>(
      (unsigned int)v71,
      (unsigned int)&StringRawBuffer,
      (unsigned int)&v46,
      (unsigned int)&v47,
      (__int64)v45);
    WindowsDeleteString(string);
    v47 = (_QWORD *)v65[3];
    *(_QWORD *)v45 = v65[0];
    v57 = (const WCHAR *)v45;
    v58 = &v47;
    v60[0] = &qword_180161528;
    _InterlockedIncrement64(&qword_180161528);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::StoreLauncher,winrt::Windows::System::Internal::Launch::IStoreLauncherStatics> )
    {
      _lambda_31a01d5c464ecba06347330efb802a35_::operator()(
        &v57,
        &string,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::StoreLauncher,winrt::Windows::System::Internal::Launch::IStoreLauncherStatics>);
      _InterlockedDecrement64(&qword_180161528);
    }
    else
    {
      _InterlockedDecrement64(&qword_180161528);
      winrt::impl::factory_cache_entry<winrt::Windows::System::Internal::Launch::StoreLauncher,winrt::Windows::System::Internal::Launch::IStoreLauncherStatics>::call<_lambda_31a01d5c464ecba06347330efb802a35_ &>(
        v31,
        (__int64)&string,
        (__int64)&v57);
    }
    if ( IsFilePath )
    {
      winrt::param::hstring::hstring(v64, v69);
      v32 = winrt::Windows::Storage::StorageFile::GetFileFromPathAsync((const struct winrt::param::hstring *)&v47);
      winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Storage::StorageFile>::get(
        v32,
        v45);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&v47);
      winrt::impl::consume_Windows_System_Internal_Launch_IStoreLauncher<winrt::Windows::System::Internal::Launch::IStoreLauncher>::ShowProductResultsForStorageFile(
        &string,
        v45);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v45);
    }
    else
    {
      v64[0] = *(_QWORD *)PendingLaunchRequest::Scheme(v10, v45);
      winrt::impl::consume_Windows_System_Internal_Launch_IStoreLauncher<winrt::Windows::System::Internal::Launch::IStoreLauncher>::ShowProductResultsForSchemeOrExtension(
        &string,
        v64);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v45);
    }
    wil::ActivityBase<LauncherDesktopProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v71);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)&string);
    WindowsDeleteString(v66);
    v66 = 0;
    if ( v54 )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v54);
    if ( ppvOut )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&ppvOut);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v52);
    if ( v23 )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&punk);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v50);
    winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(&v61);
    std::wstring::_Tidy_deallocate(v69);
    if ( v53 )
LABEL_105:
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v53);
  }
  else
  {
    if ( v70 > 7 )
      v29 = (_QWORD *)v69[0];
    v47 = v29;
    v33 = (HSTRING *)CallerInformation::GetOriginatingApplicationUserModelId(v65, &string);
    StringRawBuffer = WindowsGetStringRawBuffer(*v33, 0);
    LauncherDesktopProvider::HandlerDisambiguation::UndecidedHandlerDisambiguation<unsigned short const *,bool &,unsigned short const *,char *>(
      (unsigned int)v71,
      (unsigned int)&StringRawBuffer,
      (unsigned int)&v46,
      (unsigned int)&v47,
      (__int64)v45);
    WindowsDeleteString(string);
    v34 = 0;
    v35 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::Internal::Launch::ExtensionInfo>,winrt::Windows::System::Internal::Launch::ExtensionInfo>::Size(v50);
    while ( v34 != v35 )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::Internal::Launch::ExtensionInfo>,winrt::Windows::System::Internal::Launch::ExtensionInfo>::GetAt(
        v50,
        v45,
        v34);
      winrt::impl::as<winrt::Windows::Foundation::IInspectable,winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type,0>(
        &v47,
        *(_QWORD *)v45);
      winrt::vector_base<winrt::agile_vector<winrt::Windows::Foundation::IInspectable>,winrt::Windows::Foundation::IInspectable>::Append(
        v10 + 24,
        &v47);
      if ( v47 )
        winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(&v47);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v45);
      ++v34;
    }
    v56 = 0;
    v36 = v65[0];
    v57 = L"Windows.Internal.PlatformExtensionContracts.AppResolverContract";
    v58 = (_BYTE *)std::_WChar_traits<unsigned short>::length();
    winrt::hstring::hstring(v45, &v57);
    v37 = Windows::Internal::PlatformExtensions::TryActivateContractExtension<Windows::Internal::PlatformExtensions::IAppResolverContract>(
            *(_QWORD *)v45,
            &v56,
            v36);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBA,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v37,
        v44);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v45);
    if ( !v56 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)0x80004002LL,
        v44);
    winrt::impl::as<winrt::Windows::Foundation::IUnknown,IShellItemArray,0>(&StringRawBuffer, *((_QWORD *)this + 5));
    winrt::agile_ref<winrt::Windows::Foundation::IUnknown>::agile_ref<winrt::Windows::Foundation::IUnknown>(
      &v47,
      &StringRawBuffer);
    winrt::Windows::Foundation::IUnknown::operator=(v10 + 8, &v47);
    if ( v47 )
      winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(&v47);
    if ( StringRawBuffer )
      winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(&StringRawBuffer);
    CallerInformation::operator=((CallerInformation *)(v10 + 13));
    v38 = (_QWORD *)std::string::string(v64, v52);
    v39 = v38;
    v60[0] = v38;
    if ( v10 + 29 != v38 )
    {
      if ( v38[3] <= 0xFu )
        v40 = v38;
      else
        v40 = (_QWORD *)*v38;
      std::string::assign(v10 + 29, v40, v38[2]);
    }
    std::string::_Tidy_deallocate(v39);
    v41 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v56 + 48LL))(v56, v10);
    if ( v41 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\disambiguationexecutecommand.cpp",
        (const char *)(unsigned int)v41,
        v44);
    wil::ActivityBase<LauncherDesktopProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v71);
    if ( v56 )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v56);
    WindowsDeleteString(v66);
    v66 = 0;
    if ( v54 )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&v54);
    if ( ppvOut )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&ppvOut);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v52);
    if ( v23 )
      winrt::com_ptr<IPropertyBag>::unconditional_release_ref(&punk);
    _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v50);
    if ( v10 )
      winrt::com_ptr<winrt::Windows::Foundation::IUnknown>::unconditional_release_ref(&v61);
    std::wstring::_Tidy_deallocate(v69);
    if ( v53 )
      goto LABEL_105;
  }
  LauncherDesktopProvider::HandlerDisambiguation::~HandlerDisambiguation((LauncherDesktopProvider::HandlerDisambiguation *)v71);
  return 0;
}

```

## disassembly

```asm
0x18004f4f0  mov     [rsp+arg_8], rbx
0x18004f4f5  mov     [rsp+arg_10], rsi
0x18004f4fa  push    rdi
0x18004f4fb  push    r12
0x18004f4fd  push    r13
0x18004f4ff  push    r14
0x18004f501  push    r15
0x18004f503  sub     rsp, 2F0h
0x18004f50a  mov     rax, cs:__security_cookie
0x18004f511  xor     rax, rsp
0x18004f514  mov     [rsp+318h+var_38], rax
0x18004f51c  mov     r15, rcx
0x18004f51f  xor     r13d, r13d
0x18004f522  lea     rcx, [rsp+318h+var_188]; struct wil::details::IFailureCallback *
0x18004f52a  call    ??0?$ActivityBase@VLauncherDesktopProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LauncherDesktopProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LauncherDesktopProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004f52f  lea     rax, ??_7HandlerDisambiguation@LauncherDesktopProvider@@6B@; const LauncherDesktopProvider::HandlerDisambiguation::`vftable'
0x18004f536  mov     [rsp+318h+var_188], rax
0x18004f53e  lea     rcx, [rsp+318h+var_188]; this
0x18004f546  call    ?StartActivity@HandlerDisambiguation@LauncherDesktopProvider@@QEAAXXZ; LauncherDesktopProvider::HandlerDisambiguation::StartActivity(void)
0x18004f54b  nop
0x18004f54c  cmp     [r15+28h], r13
0x18004f550  jnz     short loc_18004F557
0x18004f552  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004f557  mov     rax, [rsp+318h]
0x18004f55f  mov     rcx, [r15+28h]
0x18004f563  test    rcx, rcx
0x18004f566  jnz     short loc_18004F580
0x18004f568  mov     r9d, 80070057h; char *
0x18004f56e  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.system.launc"...
0x18004f575  lea     edx, [rcx+4Ah]; void *
0x18004f578  mov     rcx, rax; this
0x18004f57b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f580  lea     rbx, [r15+30h]
0x18004f584  cmp     [rbx], r13
0x18004f587  jnz     loc_18004F642
0x18004f58d  mov     qword ptr [rsp+318h+var_2C0], r13
0x18004f592  mov     rax, [rcx]
0x18004f595  lea     rdx, [rsp+318h+var_2C0]
0x18004f59a  mov     qword ptr [rsp+318h+var_2F8], rdx; int
0x18004f59f  lea     r9, _GUID_d7d31033_ccb5_40e3_8efa_a668f231003f
0x18004f5a6  lea     r8, BHID_AssociationArray
0x18004f5ad  xor     edx, edx
0x18004f5af  mov     rax, [rax+18h]
0x18004f5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5b8  mov     rcx, [rsp+318h]; this
0x18004f5c0  test    eax, eax
0x18004f5c2  jns     short loc_18004F5D8
0x18004f5c4  mov     r9d, eax; char *
0x18004f5c7  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.system.launc"...
0x18004f5ce  mov     edx, 4Fh ; 'O'; void *
0x18004f5d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f5d8  mov     rdi, qword ptr [rsp+318h+var_2C0]
0x18004f5dd  mov     rax, [rdi]
0x18004f5e0  mov     rsi, [rax+40h]
0x18004f5e4  cmp     [rbx], r13
0x18004f5e7  jz      short loc_18004F5F1
0x18004f5e9  mov     rcx, rbx
0x18004f5ec  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004f5f1  mov     qword ptr [rsp+318h+var_2F8], rbx; int
0x18004f5f6  lea     r9, _GUID_d8f6ad5b_b44f_4bcc_88fd_eb3473db7502
0x18004f5fd  xor     r8d, r8d
0x18004f600  mov     edx, 220000Eh
0x18004f605  mov     rcx, rdi
0x18004f608  mov     rax, rsi
0x18004f60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f610  mov     rcx, [rsp+318h]; this
0x18004f618  test    eax, eax
0x18004f61a  jns     short loc_18004F631
0x18004f61c  mov     r9d, eax; char *
0x18004f61f  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.system.launc"...
0x18004f626  mov     edx, 50h ; 'P'; void *
0x18004f62b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f631  cmp     qword ptr [rsp+318h+var_2C0], r13
0x18004f636  jz      short loc_18004F642
0x18004f638  lea     rcx, [rsp+318h+var_2C0]
0x18004f63d  call    ?unconditional_release_ref@?$com_ptr@UIPropertyBag@@@winrt@@AEAAXXZ; winrt::com_ptr<IPropertyBag>::unconditional_release_ref(void)
0x18004f642  mov     [rsp+318h+var_2A8], r13
0x18004f647  mov     rcx, [r15+28h]
0x18004f64b  mov     rax, [rcx]
0x18004f64e  lea     r8, [rsp+318h+var_2A8]
0x18004f653  xor     edx, edx
0x18004f655  mov     rax, [rax+40h]
0x18004f659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f65e  mov     rcx, [rsp+318h]; this
0x18004f666  test    eax, eax
0x18004f668  jns     short loc_18004F67E
0x18004f66a  mov     r9d, eax; char *
0x18004f66d  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.system.launc"...
0x18004f674  mov     edx, 54h ; 'T'; void *
0x18004f679  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f67e  lea     rdx, [rsp+318h+var_2A8]
0x18004f683  call    ?IsFilePath@DisambiguationExecuteCommand@@QEAA_NAEBU?$com_ptr@UIShellItem@@@winrt@@@Z; DisambiguationExecuteCommand::IsFilePath(winrt::com_ptr<IShellItem> const &)
0x18004f688  mov     r14b, al
0x18004f68b  mov     [rsp+318h+var_2E0], al
0x18004f68f  lea     r8, [rsp+318h+var_2A8]
0x18004f694  lea     rdx, [rsp+318h+var_1B0]
0x18004f69c  call    ?GetFilePathOrUri@DisambiguationExecuteCommand@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU?$com_ptr@UIShellItem@@@winrt@@@Z; DisambiguationExecuteCommand::GetFilePathOrUri(winrt::com_ptr<IShellItem> const &)
0x18004f6a1  nop
0x18004f6a2  mov     edi, 110h
0x18004f6a7  mov     ecx, edi; Size
0x18004f6a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f6ae  mov     rsi, rax
0x18004f6b1  mov     r8d, edi; Size
0x18004f6b4  xor     edx, edx; Val
0x18004f6b6  mov     rcx, rax; void *
0x18004f6b9  call    memset_0
0x18004f6be  mov     rcx, rsi; this
0x18004f6c1  call    ??0PendingLaunchRequest@@QEAA@XZ; PendingLaunchRequest::PendingLaunchRequest(void)
0x18004f6c6  lea     r11, ??_7PendingLaunchRequest@@6B?$producer_convert@VPendingLaunchRequest@@UIObjectWithSite@@X@impl@winrt@@@; const PendingLaunchRequest::`vftable'{for `winrt::impl::producer_convert<PendingLaunchRequest,IObjectWithSite,void>'}
0x18004f6cd  mov     [rsi], r11
0x18004f6d0  lea     rax, ??_7PendingLaunchRequest@@6B?$producer_convert@VPendingLaunchRequest@@UIServiceProvider@@X@impl@winrt@@@; const PendingLaunchRequest::`vftable'{for `winrt::impl::producer_convert<PendingLaunchRequest,IServiceProvider,void>'}
0x18004f6d7  mov     [rsi+8], rax
0x18004f6db  lea     rax, ??_7PendingLaunchRequest@@6B@; const PendingLaunchRequest::`vftable'
0x18004f6e2  mov     [rsi+30h], rax
0x18004f6e6  mov     [rsp+318h+var_258], rsi
0x18004f6ee  lea     rax, [rsp+318h+var_1B0]
0x18004f6f6  cmp     [rsp+318h+var_198], 7
0x18004f6ff  cmova   rax, [rsp+318h+var_1B0]
0x18004f708  mov     [rsp+318h+var_288], rax
0x18004f710  mov     rax, [rsp+318h+var_1A0]
0x18004f718  mov     [rsp+318h+var_280], rax
0x18004f720  lea     rdx, [rsp+318h+var_288]
0x18004f728  lea     rcx, [rsp+318h+var_2E8]
0x18004f72d  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18004f732  mov     rdi, rax
0x18004f735  mov     [rsp+318h+var_2D8], rax
0x18004f73a  lea     rcx, [rsi+48h]
0x18004f73e  mov     rdx, rax
0x18004f741  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x18004f746  nop
0x18004f747  mov     rcx, rdi
0x18004f74a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004f74f  mov     qword ptr [rsp+318h+var_2C0], r13
0x18004f754  lea     rdx, [rsp+318h+var_1B0]
0x18004f75c  test    r14b, r14b
0x18004f75f  jz      loc_18004F89E
0x18004f765  lea     rcx, [rsp+318h+var_288]
0x18004f76d  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18004f772  lea     rdx, [rsp+318h+var_288]
0x18004f77a  lea     rcx, [rsp+318h+var_2E8]; struct winrt::param::hstring *
0x18004f77f  call    ?GetFileFromPathAsync@StorageFile@Storage@Windows@winrt@@SA@AEBUhstring@param@4@@Z; winrt::Windows::Storage::StorageFile::GetFileFromPathAsync(winrt::param::hstring const &)
0x18004f784  nop
0x18004f785  lea     rdx, [rsp+318h+var_2D8]
0x18004f78a  mov     rcx, rax
0x18004f78d  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UStorageFile@Storage@Windows@winrt@@@Foundation@Windows@winrt@@UStorageFile@Storage@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Storage::StorageFile>,winrt::Windows::Storage::StorageFile>::get(void)
0x18004f792  nop
0x18004f793  lea     rcx, [rsp+318h+var_2E8]; this
0x18004f798  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004f79d  lea     rdx, [rsp+318h+punk]
0x18004f7a2  lea     rcx, [rsp+318h+var_2D8]
0x18004f7a7  call    ?FileType@?$consume_Windows_Storage_IStorageFile@UIStorageFile@Storage@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Storage_IStorageFile<winrt::Windows::Storage::IStorageFile>::FileType(void)
0x18004f7ac  nop
0x18004f7ad  lea     rdx, [rsp+318h+punk]; struct winrt::hstring *
0x18004f7b2  lea     rcx, [rsp+318h+var_2E8]; this
0x18004f7b7  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18004f7bc  mov     rdx, rax
0x18004f7bf  mov     rcx, rsi
0x18004f7c2  call    ?SchemeOrExtension@PendingLaunchRequest@@QEAAXUhstring@winrt@@@Z; PendingLaunchRequest::SchemeOrExtension(winrt::hstring)
0x18004f7c7  mov     dword ptr [rsi+64h], 2
0x18004f7ce  lea     rdx, LocaleName; unsigned __int16 *
0x18004f7d5  lea     rcx, [rsp+318h+var_1F0]; this
0x18004f7dd  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18004f7e2  mov     rax, [rsp+318h+punk]
0x18004f7e7  mov     [rsp+318h+var_288], rax
0x18004f7ef  lea     rax, [rsp+318h+var_288]
0x18004f7f7  mov     [rsp+318h+var_268], rax
0x18004f7ff  lea     rax, [rsp+318h+var_1F0]
0x18004f807  mov     [rsp+318h+var_260], rax
0x18004f80f  lea     rbx, qword_180161568
0x18004f816  mov     qword ptr [rsp+318h+var_2E8], rbx
0x18004f81b  lock inc cs:qword_180161568
0x18004f823  cmp     cs:??$factory_cache_entry_v@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@12@A, r13; factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>
0x18004f82a  jz      short loc_18004F850
0x18004f82c  lea     r8, ??$factory_cache_entry_v@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@12@A; factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>
0x18004f833  lea     rdx, [rsp+318h+string]
0x18004f838  lea     rcx, [rsp+318h+var_268]
0x18004f840  call    ??R_lambda_897320ef44830be241559856707be0c1_@@QEBA@AEBUILauncherQueryAssociationStatics@Launch@Internal@System@Windows@winrt@@@Z; _lambda_897320ef44830be241559856707be0c1_::operator()(winrt::Windows::System::Internal::Launch::ILauncherQueryAssociationStatics const &)
0x18004f845  nop
0x18004f846  lock dec cs:qword_180161568
0x18004f84e  jmp     short loc_18004F86A
0x18004f850  lock dec cs:qword_180161568
0x18004f858  lea     r8, [rsp+318h+var_268]
0x18004f860  lea     rdx, [rsp+318h+string]
0x18004f865  call    ??$call@AEAV_lambda_5587ea74091e75e230748904aa055f31_@@@?$factory_cache_entry@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_5587ea74091e75e230748904aa055f31_@@@Z
0x18004f86a  lea     rdx, [rsp+318h+string]
0x18004f86f  lea     rcx, [rsp+318h+var_2C0]
0x18004f874  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004f879  lea     rcx, [rsp+318h+string]; this
0x18004f87e  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004f883  nop
0x18004f884  lea     rcx, [rsp+318h+punk]
0x18004f889  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18004f88e  nop
0x18004f88f  lea     rcx, [rsp+318h+var_2D8]; this
0x18004f894  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004f899  jmp     loc_18004FB6A
0x18004f89e  lea     rcx, [rsp+318h+var_1F0]
0x18004f8a6  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18004f8ab  lea     rdx, [rsp+318h+var_1F0]; struct winrt::param::hstring *
0x18004f8b3  lea     rcx, [rsp+318h+var_2E8]; this
0x18004f8b8  call    ??0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@3@@Z; winrt::Windows::Foundation::Uri::Uri(winrt::param::hstring const &)
0x18004f8bd  nop
0x18004f8be  lea     rdx, [rsp+318h+var_2D8]
0x18004f8c3  lea     rcx, [rsp+318h+var_2E8]
0x18004f8c8  call    ?SchemeName@?$consume_Windows_Foundation_IUriRuntimeClass@UIUriRuntimeClass@Foundation@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IUriRuntimeClass<winrt::Windows::Foundation::IUriRuntimeClass>::SchemeName(void)
0x18004f8cd  nop
0x18004f8ce  lea     rdx, [rsp+318h+var_2D8]; struct winrt::hstring *
0x18004f8d3  lea     rcx, [rsp+318h+var_2D0]; this
0x18004f8d8  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18004f8dd  mov     rdx, rax
0x18004f8e0  mov     rcx, rsi
0x18004f8e3  call    ?SchemeOrExtension@PendingLaunchRequest@@QEAAXUhstring@winrt@@@Z; PendingLaunchRequest::SchemeOrExtension(winrt::hstring)
0x18004f8e8  mov     [rsp+318h+string], r13
0x18004f8ed  mov     rcx, [rbx]
0x18004f8f0  mov     rax, [rcx]
0x18004f8f3  lea     rdx, [rsp+318h+string]
0x18004f8f8  mov     qword ptr [rsp+318h+var_2F8], rdx; int
0x18004f8fd  lea     r9, _GUID_1bee549b_0bf4_4c81_88b3_ad5bf3ab0ac4
0x18004f904  xor     r8d, r8d
0x18004f907  mov     edx, 220001Dh
0x18004f90c  mov     rax, [rax+40h]
0x18004f910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f915  mov     rcx, [rsp+318h]; this
0x18004f91d  test    eax, eax
0x18004f91f  jns     short loc_18004F935
0x18004f921  mov     r9d, eax; char *
0x18004f924  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.system.launc"...
0x18004f92b  mov     edx, 6Fh ; 'o'; void *
0x18004f930  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f935  mov     dword ptr [rsp+318h+punk], r13d
0x18004f93a  mov     rcx, [rsp+318h+string]
0x18004f93f  mov     rax, [rcx]
0x18004f942  lea     rdx, [rsp+318h+punk]
0x18004f947  mov     rax, [rax+20h]
0x18004f94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f950  mov     rcx, [rsp+318h]; this
0x18004f958  test    eax, eax
0x18004f95a  jns     short loc_18004F970
0x18004f95c  mov     r9d, eax; char *
0x18004f95f  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\windows.system.launc"...
0x18004f966  mov     edx, 72h ; 'r'; void *
0x18004f96b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f970  test    dword ptr [rsp+318h+punk], 4000h
0x18004f978  jz      loc_18004FA83
0x18004f97e  lea     rdx, LocaleName; unsigned __int16 *
0x18004f985  lea     rcx, [rsp+318h+var_240]; this
0x18004f98d  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18004f992  lea     rdx, LocaleName; unsigned __int16 *
0x18004f999  lea     rcx, [rsp+318h+var_1D0]; this
0x18004f9a1  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18004f9a6  lea     rdx, [rsp+318h+var_1B0]
0x18004f9ae  lea     rcx, [rsp+318h+var_1F0]
0x18004f9b6  call    ??0hstring@param@winrt@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; winrt::param::hstring::hstring(std::wstring const &)
0x18004f9bb  lea     rax, [rsp+318h+var_1F0]
0x18004f9c3  mov     [rsp+318h+var_288], rax
0x18004f9cb  lea     rax, [rsp+318h+var_1D0]
0x18004f9d3  mov     [rsp+318h+var_280], rax
0x18004f9db  lea     rax, [rsp+318h+var_240]
0x18004f9e3  mov     [rsp+318h+var_278], rax
0x18004f9eb  lea     rbx, qword_180161568
0x18004f9f2  mov     [rsp+318h+var_268], rbx
0x18004f9fa  lock inc cs:qword_180161568
0x18004fa02  cmp     cs:??$factory_cache_entry_v@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@12@A, r13; factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>
0x18004fa09  jz      short loc_18004FA2F
0x18004fa0b  lea     r8, ??$factory_cache_entry_v@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@impl@winrt@@3U?$factory_cache_entry@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@12@A; factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Internal::Launch::QueryAssociationBroker,winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics>
0x18004fa12  lea     rdx, [rsp+318h+var_2D0]
0x18004fa17  lea     rcx, [rsp+318h+var_288]
0x18004fa1f  call    ??R_lambda_b7132158311bf1fb9a2533bdb51fa3f6_@@QEBA@AEBUIQueryAssociationBrokerStatics@Launch@Internal@System@Windows@winrt@@@Z; _lambda_b7132158311bf1fb9a2533bdb51fa3f6_::operator()(winrt::Windows::System::Internal::Launch::IQueryAssociationBrokerStatics const &)
0x18004fa24  nop
0x18004fa25  lock dec cs:qword_180161568
0x18004fa2d  jmp     short loc_18004FA49
0x18004fa2f  lock dec cs:qword_180161568
0x18004fa37  lea     r8, [rsp+318h+var_288]
0x18004fa3f  lea     rdx, [rsp+318h+var_2D0]
0x18004fa44  call    ??$call@AEAV_lambda_b7132158311bf1fb9a2533bdb51fa3f6_@@@?$factory_cache_entry@UQueryAssociationBroker@Launch@Internal@System@Windows@winrt@@UIQueryAssociationBrokerStatics@23456@@impl@winrt@@QEAA?A_PAEAV_lambda_b7132158311bf1fb9a2533bdb51fa3f6_@@@Z
0x18004fa49  lea     rdx, [rsp+318h+var_2D0]
0x18004fa4e  lea     rcx, [rsp+318h+var_2C0]
0x18004fa53  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18004fa58  lea     rcx, [rsp+318h+var_2D0]; this
0x18004fa5d  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18004fa62  cmp     qword ptr [rsp+318h+var_2C0], r13
0x18004fa67  jz      short loc_18004FA8A
0x18004fa69  lea     rcx, [rsp+318h+var_2C0]
0x18004fa6e  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UExtensionInfo@Launch@Internal@System@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UExtensionInfo@Launch@Internal@System@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::System::Internal::Launch::ExtensionInfo>,winrt::Windows::System::Internal::Launch::ExtensionInfo>::Size(void)
0x18004fa73  test    eax, eax
0x18004fa75  jz      short loc_18004FA8A
0x18004fa77  mov     dword ptr [rsi+64h], 3
0x18004fa7e  jmp     loc_18004FB43
0x18004fa83  lea     rbx, qword_180161568
0x18004fa8a  mov     dword ptr [rsi+64h], 1
0x18004fa91  lea     rdx, LocaleName; unsigned __int16 *
0x18004fa98  lea     rcx, [rsp+318h+var_1D0]; this
0x18004faa0  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18004faa5  mov     rax, [rsp+318h+var_2D8]
0x18004faaa  mov     [rsp+318h+var_240], rax
0x18004fab2  lea     rax, [rsp+318h+var_240]
0x18004faba  mov     [rsp+318h+var_288], rax
0x18004fac2  lea     rax, [rsp+318h+var_1D0]
0x18004faca  mov     [rsp+318h+var_280], rax
0x18004fad2  mov     [rsp+318h+var_268], rbx
  ... truncated ...
```
