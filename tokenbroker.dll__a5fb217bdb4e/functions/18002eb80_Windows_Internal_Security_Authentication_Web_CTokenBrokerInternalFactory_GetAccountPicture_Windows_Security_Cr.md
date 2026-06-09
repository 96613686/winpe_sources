# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountPicture(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ *,Windows::Security::Credentials::WebAccountPictureSize,Windows::Storage::Streams::IRandomAccessStream * *)

- ea: `0x18002eb80`
- end: `0x18002f3a4`
- name: `?GetAccountPicture@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebAccountProvider@Credentials@46@PEAUHSTRING__@@W4WebAccountPictureSize@846@PEAPEAUIRandomAccessStream@Streams@Storage@6@@Z`
- size: `2084`
- prototype: `int __high(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING, enum Windows::Security::Credentials::WebAccountPictureSize, struct Windows::Storage::Streams::IRandomAccessStream **)`
- caller_count: `0`
- callee_count: `30`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001e700`
- `0x1800200b4`
- `0x180020620`
- `0x18002071c`
- `0x180020c60`
- `0x180021750`
- `0x1800228a8`
- `0x180023090`
- `0x1800231c0`
- `0x180023a80`
- `0x180024000`
- `0x1800256ac`
- `0x1800262f0`
- `0x180026728`
- `0x1800269f4`
- `0x18002dc94`
- `0x18002ea58`
- `0x18002ea84`
- `0x18002eb00`
- `0x18002eb80`
- `0x18002f3ac`
- `0x18002fbf0`
- `0x180030a78`
- `0x18004f560`
- `0x18007f1e4`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002eeb2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ef66`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f1c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f326`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002eeb2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002ef66`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f1c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002f326`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ef51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f29c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f311`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ef51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f0dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f1ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f29c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f311`

## string_xrefs

- `0x18002ec2b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002ec86`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002eccc`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002ed26`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002ed81`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002ee0b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002ee92`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002ef35`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002f027`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002f0b4`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002f189`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002f26a`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18002ec01`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountPicture`
- `0x18002ebbb`: `TokenBrokerInternalGetAccountPicture`
- `0x18002f233`: `Windows.Storage.Streams.InMemoryRandomAccessStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountPicture(
        __int64 a1,
        Windows::Internal::Security::Authentication::TokenBroker *a2,
        __int64 a3,
        int a4,
        _QWORD *a5)
{
  struct IUnknown *v8; // r14
  __int64 v9; // rcx
  unsigned __int64 *v10; // r8
  int UserContextFromProvider; // eax
  unsigned int v13; // ebx
  __int64 *v14; // rsi
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int PluginPFN; // eax
  bool IsCallerAppContainer; // di
  HSTRING CallerPackageFamilyName; // rax
  HSTRING v22; // rbx
  unsigned int v23; // r14d
  int IsPluginMultiUserAware; // eax
  unsigned int v25; // edi
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *AccountManagerInstance; // rax
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v27; // rdi
  __int64 (__fastcall *v28)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD); // r15
  __int64 v29; // rax
  int v30; // eax
  unsigned int v31; // esi
  __int64 v32; // rcx
  int v33; // eax
  unsigned int v34; // esi
  __int64 v35; // rax
  __int64 v36; // rcx
  int v37; // [rsp+20h] [rbp-228h]
  int v38; // [rsp+20h] [rbp-228h]
  bool v39; // [rsp+40h] [rbp-208h] BYREF
  Windows::Internal::Security::Authentication::Web::CallerContext *v40; // [rsp+48h] [rbp-200h] BYREF
  __int64 v41; // [rsp+50h] [rbp-1F8h] BYREF
  HANDLE Token; // [rsp+58h] [rbp-1F0h] BYREF
  char v43; // [rsp+60h] [rbp-1E8h]
  _BYTE v44[8]; // [rsp+68h] [rbp-1E0h] BYREF
  _BYTE v45[8]; // [rsp+70h] [rbp-1D8h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1D0h] BYREF
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v47; // [rsp+80h] [rbp-1C8h] BYREF
  unsigned __int64 v48; // [rsp+88h] [rbp-1C0h] BYREF
  _QWORD v49[42]; // [rsp+90h] [rbp-1B8h] BYREF
  HSTRING v50; // [rsp+1E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  LODWORD(v41) = a4;
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v49,
    "TokenBrokerInternalGetAccountPicture");
  v49[0] = &TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable';
  TbLogProvider::TokenBrokerInternalGetAccountPicture::StartActivity((TbLogProvider::TokenBrokerInternalGetAccountPicture *)v49);
  v8 = (struct IUnknown *)(a1 & -(__int64)(a1 != 40));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v9,
    (__int64)v44,
    v8,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetAccountPicture",
    0);
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v37);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    v49[0] = &TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable';
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v49);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AE,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v37);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture((TbLogProvider::TokenBrokerInternalGetAccountPicture *)v49);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AF,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v37);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture((TbLogProvider::TokenBrokerInternalGetAccountPicture *)v49);
    return 2147942487LL;
  }
  v48 = 0;
  UserContextFromProvider = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(
                              a2,
                              (struct Windows::Security::Credentials::IWebAccountProvider *)&v48,
                              v10);
  v13 = UserContextFromProvider;
  if ( UserContextFromProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B3,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)UserContextFromProvider,
      v37);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture((TbLogProvider::TokenBrokerInternalGetAccountPicture *)v49);
    return v13;
  }
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v40, v45);
  v14 = (__int64 *)v40;
  if ( !v40 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B6,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v37);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v40,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    v49[0] = &TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable';
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v49);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v40 )
  {
    v15 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v40, v8, v48, 0);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B9,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v15,
        v37);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v40,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
      v49[0] = &TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable';
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v49);
      return v16;
    }
  }
  Token = 0;
  v43 = 0;
  v17 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&Token, v14[2]);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v17,
      v37);
    if ( v43 )
      SetThreadToken(0, Token);
LABEL_17:
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v40,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    v49[0] = &TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable';
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v49);
    return v18;
  }
  string = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
                (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v14,
                a2,
                &string);
  v18 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)PluginPFN,
      v37);
    if ( string )
      WindowsDeleteString(string);
    if ( v43 )
      SetThreadToken(0, Token);
    goto LABEL_17;
  }
  IsCallerAppContainer = Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v14);
  if ( !IsCallerAppContainer )
  {
    v22 = string;
LABEL_28:
    v23 = 0;
    if ( IsCallerAppContainer )
      goto LABEL_30;
    goto LABEL_29;
  }
  CallerPackageFamilyName = Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(
                              (Windows::Internal::Security::Authentication::Web::CallerContext *)v14,
                              0);
  v22 = string;
  if ( !ComparePfns(CallerPackageFamilyName, string) )
    goto LABEL_28;
LABEL_29:
  v23 = 7;
LABEL_30:
  v39 = 0;
  IsPluginMultiUserAware = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(
                             (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v14,
                             v22,
                             &v39);
  v25 = IsPluginMultiUserAware;
  if ( IsPluginMultiUserAware < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)IsPluginMultiUserAware,
      v37);
    if ( v22 )
      WindowsDeleteString(v22);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v40,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture((TbLogProvider::TokenBrokerInternalGetAccountPicture *)v49);
    return v25;
  }
  v47 = 0;
  AccountManagerInstance = Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(
                             v39,
                             v14[2]);
  v27 = AccountManagerInstance;
  v47 = AccountManagerInstance;
  if ( !AccountManagerInstance )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v37);
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>(&v47);
    if ( v22 )
      WindowsDeleteString(v22);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v40,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
    TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture((TbLogProvider::TokenBrokerInternalGetAccountPicture *)v49);
    return 2147942414LL;
  }
  v28 = *(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD))(*(_QWORD *)AccountManagerInstance + 72LL);
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v14) )
    v29 = v14[9];
  else
    LODWORD(v29) = 0;
  v38 = v29;
  v30 = v28(v27, a3, v22, v23);
  v31 = v30;
  if ( v30 < 0 )
  {
    if ( v30 != -2147024891 && v30 != -2147024894 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E6,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v30,
        v38);
      std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator()(
        v32,
        v27);
      if ( v22 )
        WindowsDeleteString(v22);
      if ( v43 )
        SetThreadToken(0, Token);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&Token);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v40,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
      v49[0] = &TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable';
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v49);
      return v31;
    }
    v41 = 0;
    Windows::Internal::StringReference::StringReference(&v50, L"Windows.Storage.Streams.InMemoryRandomAccessStream");
    v33 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>(
            v50,
            &v41);
    v34 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3ED,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v33,
        v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>(&v47);
      if ( v22 )
        WindowsDeleteString(v22);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&Token);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v40,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
      TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture((TbLogProvider::TokenBrokerInternalGetAccountPicture *)v49);
      return v34;
    }
    v35 = v41;
    v41 = 0;
    *a5 = v35;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  }
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v49);
  std::default_delete<Windows::Internal::Security::Authentication::TokenBroker::StoredObjectInfo>::operator()(v36, v27);
  if ( v22 )
    WindowsDeleteString(v22);
  if ( v43 )
    SetThreadToken(0, Token);
  Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&Token);
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    &v40,
    0);
  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v44);
  v49[0] = &TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable';
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v49);
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v49);
  return 0;
}

```

## disassembly

```asm
0x18002eb80  push    rbx
0x18002eb82  push    rsi
0x18002eb83  push    rdi
0x18002eb84  push    r12
0x18002eb86  push    r13
0x18002eb88  push    r14
0x18002eb8a  push    r15
0x18002eb8c  sub     rsp, 210h
0x18002eb93  mov     rax, cs:__security_cookie
0x18002eb9a  xor     rax, rsp
0x18002eb9d  mov     [rsp+248h+var_48], rax
0x18002eba5  mov     dword ptr [rsp+248h+var_1F8], r9d
0x18002ebaa  mov     r13, r8
0x18002ebad  mov     rdi, rdx
0x18002ebb0  mov     rbx, rcx
0x18002ebb3  mov     r12, [rsp+248h+arg_20]
0x18002ebbb  lea     rdx, aTokenbrokerint_8; "TokenBrokerInternalGetAccountPicture"
0x18002ebc2  lea     rcx, [rsp+248h+var_1B8]
0x18002ebca  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18002ebcf  lea     rsi, ??_7TokenBrokerInternalGetAccountPicture@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable'
0x18002ebd6  mov     [rsp+248h+var_1B8], rsi
0x18002ebde  lea     rcx, [rsp+248h+var_1B8]; this
0x18002ebe6  call    ?StartActivity@TokenBrokerInternalGetAccountPicture@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalGetAccountPicture::StartActivity(void)
0x18002ebeb  nop
0x18002ebec  lea     rax, [rbx-28h]
0x18002ebf0  neg     rax
0x18002ebf3  sbb     r14, r14
0x18002ebf6  and     r14, rbx
0x18002ebf9  xor     r15d, r15d
0x18002ebfc  mov     byte ptr [rsp+248h+var_228], r15b; int
0x18002ec01  lea     r9, aWindowsInterna_80; "Windows::Internal::Security::Authentica"...
0x18002ec08  mov     r8, r14
0x18002ec0b  lea     rdx, [rsp+248h+var_1E0]
0x18002ec10  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x18002ec15  nop
0x18002ec16  test    rdi, rdi
0x18002ec19  jnz     short loc_18002EC71
0x18002ec1b  mov     rcx, [rsp+248h]; this
0x18002ec23  mov     ebx, 80070057h
0x18002ec28  mov     r9d, ebx; char *
0x18002ec2b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ec32  mov     edx, 3ADh; void *
0x18002ec37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec3c  nop
0x18002ec3d  lea     rcx, [rsp+248h+var_1E0]; this
0x18002ec42  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002ec47  nop
0x18002ec48  mov     [rsp+248h+var_1B8], rsi
0x18002ec50  lea     rcx, [rsp+248h+var_1B8]
0x18002ec58  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002ec5d  lea     rcx, [rsp+248h+var_1B8]
0x18002ec65  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002ec6a  mov     eax, ebx
0x18002ec6c  jmp     loc_18002F380
0x18002ec71  test    r13, r13
0x18002ec74  jnz     short loc_18002ECB7
0x18002ec76  mov     rcx, [rsp+248h]; this
0x18002ec7e  mov     ebx, 80070057h
0x18002ec83  mov     r9d, ebx; char *
0x18002ec86  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ec8d  mov     edx, 3AEh; void *
0x18002ec92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ec97  nop
0x18002ec98  lea     rcx, [rsp+248h+var_1E0]; this
0x18002ec9d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002eca2  nop
0x18002eca3  lea     rcx, [rsp+248h+var_1B8]; this
0x18002ecab  call    ??1TokenBrokerInternalGetAccountPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture(void)
0x18002ecb0  mov     eax, ebx
0x18002ecb2  jmp     loc_18002F380
0x18002ecb7  test    r12, r12
0x18002ecba  jnz     short loc_18002ECFD
0x18002ecbc  mov     rcx, [rsp+248h]; this
0x18002ecc4  mov     ebx, 80070057h
0x18002ecc9  mov     r9d, ebx; char *
0x18002eccc  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ecd3  mov     edx, 3AFh; void *
0x18002ecd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ecdd  nop
0x18002ecde  lea     rcx, [rsp+248h+var_1E0]; this
0x18002ece3  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002ece8  nop
0x18002ece9  lea     rcx, [rsp+248h+var_1B8]; this
0x18002ecf1  call    ??1TokenBrokerInternalGetAccountPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture(void)
0x18002ecf6  mov     eax, ebx
0x18002ecf8  jmp     loc_18002F380
0x18002ecfd  mov     [rsp+248h+var_1C0], r15
0x18002ed05  lea     rdx, [rsp+248h+var_1C0]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18002ed0d  mov     rcx, rdi; this
0x18002ed10  call    ?GetUserContextFromProvider@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(Windows::Security::Credentials::IWebAccountProvider *,unsigned __int64 &)
0x18002ed15  mov     ebx, eax
0x18002ed17  test    eax, eax
0x18002ed19  jns     short loc_18002ED57
0x18002ed1b  mov     rcx, [rsp+248h]; this
0x18002ed23  mov     r9d, eax; char *
0x18002ed26  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ed2d  mov     edx, 3B3h; void *
0x18002ed32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ed37  nop
0x18002ed38  lea     rcx, [rsp+248h+var_1E0]; this
0x18002ed3d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002ed42  nop
0x18002ed43  lea     rcx, [rsp+248h+var_1B8]; this
0x18002ed4b  call    ??1TokenBrokerInternalGetAccountPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture(void)
0x18002ed50  mov     eax, ebx
0x18002ed52  jmp     loc_18002F380
0x18002ed57  lea     rdx, [rsp+248h+var_1D8]
0x18002ed5c  lea     rcx, [rsp+248h+var_200]
0x18002ed61  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x18002ed66  nop
0x18002ed67  mov     rsi, [rsp+248h+var_200]
0x18002ed6c  test    rsi, rsi
0x18002ed6f  jnz     short loc_18002EDDB
0x18002ed71  mov     rcx, [rsp+248h]; this
0x18002ed79  mov     edi, 8007000Eh
0x18002ed7e  mov     r9d, edi; char *
0x18002ed81  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ed88  mov     edx, 3B6h; void *
0x18002ed8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ed92  nop
0x18002ed93  xor     edx, edx
0x18002ed95  lea     rcx, [rsp+248h+var_200]
0x18002ed9a  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002ed9f  nop
0x18002eda0  lea     rcx, [rsp+248h+var_1E0]; this
0x18002eda5  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002edaa  nop
0x18002edab  lea     rax, ??_7TokenBrokerInternalGetAccountPicture@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable'
0x18002edb2  mov     [rsp+248h+var_1B8], rax
0x18002edba  lea     rcx, [rsp+248h+var_1B8]
0x18002edc2  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002edc7  lea     rcx, [rsp+248h+var_1B8]
0x18002edcf  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002edd4  mov     eax, edi
0x18002edd6  jmp     loc_18002F380
0x18002eddb  cmp     [rsi], r15b
0x18002edde  jnz     loc_18002EE65
0x18002ede4  xor     r9d, r9d; bool
0x18002ede7  mov     r8, [rsp+248h+var_1C0]; unsigned __int64
0x18002edef  mov     rdx, r14; struct IUnknown *
0x18002edf2  mov     rcx, rsi; this
0x18002edf5  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x18002edfa  mov     ebx, eax
0x18002edfc  test    eax, eax
0x18002edfe  jns     short loc_18002EE65
0x18002ee00  mov     rcx, [rsp+248h]; this
0x18002ee08  mov     r9d, eax; char *
0x18002ee0b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ee12  mov     edx, 3B9h; void *
0x18002ee17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee1c  nop
0x18002ee1d  xor     edx, edx
0x18002ee1f  lea     rcx, [rsp+248h+var_200]
0x18002ee24  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002ee29  nop
0x18002ee2a  lea     rcx, [rsp+248h+var_1E0]; this
0x18002ee2f  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002ee34  nop
0x18002ee35  lea     rax, ??_7TokenBrokerInternalGetAccountPicture@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable'
0x18002ee3c  mov     [rsp+248h+var_1B8], rax
0x18002ee44  lea     rcx, [rsp+248h+var_1B8]
0x18002ee4c  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002ee51  lea     rcx, [rsp+248h+var_1B8]
0x18002ee59  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002ee5e  mov     eax, ebx
0x18002ee60  jmp     loc_18002F380
0x18002ee65  mov     [rsp+248h+Token], r15
0x18002ee6a  mov     [rsp+248h+var_1E8], r15b
0x18002ee6f  mov     rdx, [rsi+10h]; unsigned __int64
0x18002ee73  lea     rcx, [rsp+248h+Token]; TokenHandle
0x18002ee78  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x18002ee7d  mov     ebx, eax
0x18002ee7f  test    eax, eax
0x18002ee81  jns     loc_18002EF0B
0x18002ee87  mov     rcx, [rsp+248h]; this
0x18002ee8f  mov     r9d, eax; char *
0x18002ee92  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ee99  mov     edx, 3BDh; void *
0x18002ee9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002eea3  nop
0x18002eea4  cmp     [rsp+248h+var_1E8], r15b
0x18002eea9  jz      short loc_18002EEB8
0x18002eeab  mov     rdx, [rsp+248h+Token]; Token
0x18002eeb0  xor     ecx, ecx; Thread
0x18002eeb2  call    cs:__imp_SetThreadToken
0x18002eeb8  lea     rcx, [rsp+248h+Token]; this
0x18002eebd  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18002eec2  nop
0x18002eec3  xor     edx, edx
0x18002eec5  lea     rcx, [rsp+248h+var_200]
0x18002eeca  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002eecf  nop
0x18002eed0  lea     rcx, [rsp+248h+var_1E0]; this
0x18002eed5  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002eeda  nop
0x18002eedb  lea     rax, ??_7TokenBrokerInternalGetAccountPicture@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable'
0x18002eee2  mov     [rsp+248h+var_1B8], rax
0x18002eeea  lea     rcx, [rsp+248h+var_1B8]
0x18002eef2  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002eef7  lea     rcx, [rsp+248h+var_1B8]
0x18002eeff  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002ef04  mov     eax, ebx
0x18002ef06  jmp     loc_18002F380
0x18002ef0b  mov     [rsp+248h+string], r15
0x18002ef10  lea     r8, [rsp+248h+string]; HSTRING *
0x18002ef15  mov     rdx, rdi; struct Windows::Security::Credentials::IWebAccountProvider *
0x18002ef18  mov     rcx, rsi; this
0x18002ef1b  call    ?GetPluginPFN@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18002ef20  mov     ebx, eax
0x18002ef22  test    eax, eax
0x18002ef24  jns     loc_18002EFBF
0x18002ef2a  mov     rcx, [rsp+248h]; this
0x18002ef32  mov     r9d, eax; char *
0x18002ef35  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002ef3c  mov     edx, 3C7h; void *
0x18002ef41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ef46  nop
0x18002ef47  mov     rcx, [rsp+248h+string]; string
0x18002ef4c  test    rcx, rcx
0x18002ef4f  jz      short loc_18002EF58
0x18002ef51  call    cs:__imp_WindowsDeleteString
0x18002ef57  nop
0x18002ef58  cmp     [rsp+248h+var_1E8], r15b
0x18002ef5d  jz      short loc_18002EF6C
0x18002ef5f  mov     rdx, [rsp+248h+Token]; Token
0x18002ef64  xor     ecx, ecx; Thread
0x18002ef66  call    cs:__imp_SetThreadToken
0x18002ef6c  lea     rcx, [rsp+248h+Token]; this
0x18002ef71  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x18002ef76  nop
0x18002ef77  xor     edx, edx
0x18002ef79  lea     rcx, [rsp+248h+var_200]
0x18002ef7e  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002ef83  nop
0x18002ef84  lea     rcx, [rsp+248h+var_1E0]; this
0x18002ef89  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002ef8e  nop
0x18002ef8f  lea     rax, ??_7TokenBrokerInternalGetAccountPicture@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetAccountPicture::`vftable'
0x18002ef96  mov     [rsp+248h+var_1B8], rax
0x18002ef9e  lea     rcx, [rsp+248h+var_1B8]
0x18002efa6  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18002efab  lea     rcx, [rsp+248h+var_1B8]
0x18002efb3  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18002efb8  mov     eax, ebx
0x18002efba  jmp     loc_18002F380
0x18002efbf  mov     rcx, rsi; this
0x18002efc2  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x18002efc7  mov     dil, al
0x18002efca  test    al, al
0x18002efcc  jz      short loc_18002EFEE
0x18002efce  xor     edx, edx; bool
0x18002efd0  mov     rcx, rsi; this
0x18002efd3  call    ?GetCallerPackageFamilyName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAPEAUHSTRING__@@_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(bool)
0x18002efd8  mov     rcx, rax; string
0x18002efdb  mov     rbx, [rsp+248h+string]
0x18002efe0  mov     rdx, rbx; HSTRING
0x18002efe3  call    ?ComparePfns@@YA_NPEAUHSTRING__@@0@Z; ComparePfns(HSTRING__ *,HSTRING__ *)
0x18002efe8  test    al, al
0x18002efea  jz      short loc_18002EFF3
0x18002efec  jmp     short loc_18002EFFB
0x18002efee  mov     rbx, [rsp+248h+string]
0x18002eff3  test    dil, dil
0x18002eff6  mov     r14d, r15d
0x18002eff9  jnz     short loc_18002F001
0x18002effb  mov     r14d, 7
0x18002f001  mov     [rsp+248h+var_208], r15b
0x18002f006  lea     r8, [rsp+248h+var_208]; bool *
0x18002f00b  mov     rdx, rbx; HSTRING
0x18002f00e  mov     rcx, rsi; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x18002f011  call    ?IsPluginMultiUserAware@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,bool *)
0x18002f016  mov     edi, eax
0x18002f018  test    eax, eax
0x18002f01a  jns     short loc_18002F07F
0x18002f01c  mov     rcx, [rsp+248h]; this
0x18002f024  mov     r9d, eax; char *
0x18002f027  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002f02e  mov     edx, 3D9h; void *
0x18002f033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f038  nop
0x18002f039  test    rbx, rbx
0x18002f03c  jz      short loc_18002F048
0x18002f03e  mov     rcx, rbx; string
0x18002f041  call    cs:__imp_WindowsDeleteString
0x18002f047  nop
0x18002f048  lea     rcx, [rsp+248h+Token]; this
0x18002f04d  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18002f052  nop
0x18002f053  xor     edx, edx
0x18002f055  lea     rcx, [rsp+248h+var_200]
0x18002f05a  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18002f05f  nop
0x18002f060  lea     rcx, [rsp+248h+var_1E0]; this
0x18002f065  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18002f06a  nop
0x18002f06b  lea     rcx, [rsp+248h+var_1B8]; this
0x18002f073  call    ??1TokenBrokerInternalGetAccountPicture@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetAccountPicture::~TokenBrokerInternalGetAccountPicture(void)
0x18002f078  mov     eax, edi
0x18002f07a  jmp     loc_18002F380
0x18002f07f  mov     [rsp+248h+var_1C8], r15
0x18002f087  mov     rdx, [rsi+10h]; unsigned __int64
  ... truncated ...
```
