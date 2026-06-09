# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::SetWebAccountEnumerableState(HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::Security::Credentials::WebAccountEnumerableState)

- ea: `0x18006b0c0`
- end: `0x18006b98e`
- name: `?SetWebAccountEnumerableState@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUHSTRING__@@PEAUIWebAccountProvider@Credentials@46@W4WebAccountEnumerableState@9456@@Z`
- size: `2254`
- prototype: `int __high(HSTRING, struct Windows::Security::Credentials::IWebAccountProvider *, enum Windows::Internal::Security::Credentials::WebAccountEnumerableState)`
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001e700`
- `0x1800200b4`
- `0x180020620`
- `0x180020c60`
- `0x180021750`
- `0x1800231c0`
- `0x180023a80`
- `0x1800262f0`
- `0x180026728`
- `0x1800269f4`
- `0x18002d940`
- `0x18002ea84`
- `0x18002eb00`
- `0x18002fbf0`
- `0x180030a78`
- `0x180040980`
- `0x1800455a4`
- `0x18004f560`
- `0x18005d15c`
- `0x180060d84`
- `0x180060ef0`
- `0x180063a74`
- `0x18006b0c0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006b587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b49b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b52a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b5ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b6f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b8cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b92b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b3b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b49b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b52a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b5ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b6f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b815`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b8cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b92b`

## string_xrefs

- `0x18006b16b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b1b1`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b205`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b25a`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b2c1`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b328`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b397`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b476`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b505`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b5c7`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b644`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b6d7`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b762`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b7f0`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b8aa`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18006b0fb`: `TokenBrokerInternalSetWebAccountEnumerableState`
- `0x18006b141`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::SetWebAccountEnumerableState`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::SetWebAccountEnumerableState(
        __int64 a1,
        __int64 a2,
        Windows::Internal::Security::Authentication::TokenBroker *a3,
        unsigned int a4)
{
  struct IUnknown *v7; // rsi
  char v8; // r15
  __int64 v9; // rcx
  unsigned __int64 *v10; // r8
  int UserContextFromProvider; // eax
  unsigned int v13; // ebx
  __int64 *v14; // rdi
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  int PluginPFN; // eax
  unsigned int v20; // ebx
  bool IsCallerAppContainer; // r12
  HSTRING CallerPackageFamilyName; // rax
  HSTRING v23; // rbx
  __int64 (__fastcall *v24)(Windows::Internal::Security::Authentication::TokenBroker *, GUID *, struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager **); // rsi
  int v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  unsigned int v28; // esi
  const struct _tlgProvider_t *v29; // rax
  int v30; // edi
  int v31; // r9d
  int IsPluginMultiUserAware; // eax
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *AccountManagerInstance; // rax
  int v34; // eax
  unsigned int v35; // edi
  __int64 v36; // r14
  __int64 (__fastcall *v37)(__int64, HSTRING, __int64, __int64); // rsi
  __int64 v38; // rdi
  __int64 CurrentSystemTimeAsInt64; // rax
  int v40; // eax
  int v41; // [rsp+20h] [rbp-228h]
  bool v42[8]; // [rsp+30h] [rbp-218h] BYREF
  struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *v43; // [rsp+38h] [rbp-210h] BYREF
  __int64 *v44; // [rsp+40h] [rbp-208h] BYREF
  _BYTE v45[8]; // [rsp+48h] [rbp-200h] BYREF
  Windows::Internal::Security::Authentication::Web::CallerContext *v46; // [rsp+50h] [rbp-1F8h]
  unsigned int v47; // [rsp+58h] [rbp-1F0h]
  HSTRING string; // [rsp+60h] [rbp-1E8h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-1E0h] BYREF
  char v50; // [rsp+70h] [rbp-1D8h]
  unsigned __int64 v51; // [rsp+78h] [rbp-1D0h] BYREF
  __int64 v52; // [rsp+80h] [rbp-1C8h]
  _QWORD v53[5]; // [rsp+88h] [rbp-1C0h] BYREF
  _QWORD v54[34]; // [rsp+B0h] [rbp-198h] BYREF
  __int64 v55; // [rsp+1C0h] [rbp-88h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v47 = a4;
  v52 = a1;
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v54,
    "TokenBrokerInternalSetWebAccountEnumerableState");
  v54[0] = &TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::`vftable';
  TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::StartActivity((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
  v7 = (struct IUnknown *)(a1 & -(__int64)(a1 != 88));
  v8 = 0;
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v9,
    (__int64)v45,
    v7,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::SetWebAccountEnumerableState",
    0);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v41);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v41);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return 2147942487LL;
  }
  v51 = 0;
  UserContextFromProvider = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(
                              a3,
                              (struct Windows::Security::Credentials::IWebAccountProvider *)&v51,
                              v10);
  v13 = UserContextFromProvider;
  if ( UserContextFromProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x432,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)UserContextFromProvider,
      v41);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return v13;
  }
  v14 = (__int64 *)v46;
  v46 = 0;
  v44 = v14;
  if ( !v14 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x435,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v41);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v44,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return 2147942487LL;
  }
  if ( !*(_BYTE *)v14 )
  {
    v15 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
            (Windows::Internal::Security::Authentication::Web::CallerContext *)v14,
            v7,
            v51,
            0);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x438,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v15,
        v41);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v44,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
      TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
      return v16;
    }
  }
  TokenHandle = 0;
  v50 = 0;
  v17 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&TokenHandle, v14[2]);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v17,
      v41);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v44,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return v18;
  }
  string = 0;
  PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(
                (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v14,
                a3,
                &string);
  v20 = PluginPFN;
  if ( PluginPFN < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x440,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)PluginPFN,
      v41);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v44,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return v20;
  }
  IsCallerAppContainer = Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v14);
  if ( IsCallerAppContainer )
  {
    CallerPackageFamilyName = Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(
                                (Windows::Internal::Security::Authentication::Web::CallerContext *)v14,
                                0);
    v23 = string;
    if ( ComparePfns(CallerPackageFamilyName, string) )
      v8 = 1;
  }
  else
  {
    v23 = string;
  }
  if ( !IsProviderEnumerationCheckDisabled() )
  {
    v43 = 0;
    v24 = **(__int64 (__fastcall ***)(Windows::Internal::Security::Authentication::TokenBroker *, GUID *, struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager **))a3;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    v25 = v24(a3, &GUID_26af3d4c_8b79_408c_ae0f_df1aadbe137f, &v43);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x449,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v25,
        v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      if ( v23 )
        WindowsDeleteString(v23);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v44,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
      TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
      return v26;
    }
    v42[0] = 0;
    v27 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, bool *))(*(_QWORD *)v43 + 48LL))(
            v43,
            v42);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x44C,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v27,
        v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      if ( v23 )
        WindowsDeleteString(v23);
LABEL_30:
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v44,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
      TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
      return v28;
    }
    if ( !v42[0] )
    {
      v29 = TbLogProvider::Provider();
      v30 = (int)v29;
      if ( *(_DWORD *)v29 > 5u )
      {
        string = (HSTRING)WindowsGetStringRawBuffer(v23, 0);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v30,
          (unsigned int)&unk_18014B0E8,
          v55 + 8,
          v31,
          (__int64)&string);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x457,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)0x80070032LL,
        v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      if ( v23 )
        WindowsDeleteString(v23);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v44,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
      TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
      return 2147942450LL;
    }
    if ( IsCallerAppContainer && !v8 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)0x80070005LL,
        v41);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      if ( v23 )
        WindowsDeleteString(v23);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v44,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
      TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
      return 2147942405LL;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  }
  v42[0] = 0;
  IsPluginMultiUserAware = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::IsPluginMultiUserAware(
                             (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v14,
                             v23,
                             v42);
  v28 = IsPluginMultiUserAware;
  if ( IsPluginMultiUserAware < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)IsPluginMultiUserAware,
      v41);
    if ( v23 )
      WindowsDeleteString(v23);
    goto LABEL_30;
  }
  v43 = 0;
  AccountManagerInstance = Windows::Internal::Security::Authentication::TokenBroker::CAccountManagerFactory::GetAccountManagerInstance(
                             v42[0],
                             v14[2]);
  v43 = AccountManagerInstance;
  if ( !AccountManagerInstance )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x462,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v41);
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>(&v43);
    if ( v23 )
      WindowsDeleteString(v23);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v44,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return 2147942414LL;
  }
  v34 = (*(__int64 (__fastcall **)(struct Windows::Internal::Security::Authentication::TokenBroker::IAccountManager *, __int64, HSTRING, _QWORD))(*(_QWORD *)AccountManagerInstance + 136LL))(
          AccountManagerInstance,
          a2,
          v23,
          v47);
  v35 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x465,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v34,
      v41);
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>(&v43);
    if ( v23 )
      WindowsDeleteString(v23);
LABEL_54:
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v44,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
    TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
    return v35;
  }
  v36 = v52;
  v37 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64))(*(_QWORD *)(v52 - 8) + 48LL);
  Windows::Internal::StringReference::_ConstructorHelper(
    (Windows::Internal::StringReference *)v53,
    L"EnumApiCacheExpiration");
  v38 = v53[0];
  CurrentSystemTimeAsInt64 = GetCurrentSystemTimeAsInt64();
  v40 = v37(v36 - 8, v23, CurrentSystemTimeAsInt64, v38);
  v35 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x467,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v40,
      v41);
    std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>(&v43);
    if ( v23 )
      WindowsDeleteString(v23);
    goto LABEL_54;
  }
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54);
  std::unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>::~unique_ptr<Windows::Internal::Security::Authentication::TokenBroker::IAccountManager>(&v43);
  if ( v23 )
    WindowsDeleteString(v23);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    &v44,
    0);
  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v45);
  TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState((TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState *)v54);
  return 0;
}

```

## disassembly

```asm
0x18006b0c0  push    rbx
0x18006b0c2  push    rsi
0x18006b0c3  push    rdi
0x18006b0c4  push    r12
0x18006b0c6  push    r13
0x18006b0c8  push    r14
0x18006b0ca  push    r15
0x18006b0cc  sub     rsp, 210h
0x18006b0d3  mov     rax, cs:__security_cookie
0x18006b0da  xor     rax, rsp
0x18006b0dd  mov     [rsp+248h+var_48], rax
0x18006b0e5  mov     [rsp+248h+var_1F0], r9d
0x18006b0ea  mov     r14, r8
0x18006b0ed  mov     r13, rdx
0x18006b0f0  mov     rbx, rcx
0x18006b0f3  mov     [rsp+248h+var_1C8], rcx
0x18006b0fb  lea     rdx, aTokenbrokerint_23; "TokenBrokerInternalSetWebAccountEnumera"...
0x18006b102  lea     rcx, [rsp+248h+var_198]
0x18006b10a  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18006b10f  lea     rax, ??_7TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::`vftable'
0x18006b116  mov     [rsp+248h+var_198], rax
0x18006b11e  lea     rcx, [rsp+248h+var_198]; this
0x18006b126  call    ?StartActivity@TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::StartActivity(void)
0x18006b12b  nop
0x18006b12c  lea     rax, [rbx-58h]
0x18006b130  neg     rax
0x18006b133  sbb     rsi, rsi
0x18006b136  and     rsi, rbx
0x18006b139  xor     r15d, r15d
0x18006b13c  mov     byte ptr [rsp+248h+var_228], r15b; int
0x18006b141  lea     r9, aWindowsInterna_82; "Windows::Internal::Security::Authentica"...
0x18006b148  mov     r8, rsi
0x18006b14b  lea     rdx, [rsp+248h+var_200]
0x18006b150  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x18006b155  nop
0x18006b156  test    r14, r14
0x18006b159  jnz     short loc_18006B19C
0x18006b15b  mov     rcx, [rsp+248h]; this
0x18006b163  mov     ebx, 80070057h
0x18006b168  mov     r9d, ebx; char *
0x18006b16b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b172  mov     edx, 42Dh; void *
0x18006b177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b17c  nop
0x18006b17d  lea     rcx, [rsp+248h+var_200]; this
0x18006b182  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b187  nop
0x18006b188  lea     rcx, [rsp+248h+var_198]; this
0x18006b190  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b195  mov     eax, ebx
0x18006b197  jmp     loc_18006B96A
0x18006b19c  test    r13, r13
0x18006b19f  jnz     short loc_18006B1E2
0x18006b1a1  mov     rcx, [rsp+248h]; this
0x18006b1a9  mov     ebx, 80070057h
0x18006b1ae  mov     r9d, ebx; char *
0x18006b1b1  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b1b8  mov     edx, 42Eh; void *
0x18006b1bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b1c2  nop
0x18006b1c3  lea     rcx, [rsp+248h+var_200]; this
0x18006b1c8  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b1cd  nop
0x18006b1ce  lea     rcx, [rsp+248h+var_198]; this
0x18006b1d6  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b1db  mov     eax, ebx
0x18006b1dd  jmp     loc_18006B96A
0x18006b1e2  mov     [rsp+248h+var_1D0], r15
0x18006b1e7  lea     rdx, [rsp+248h+var_1D0]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18006b1ec  mov     rcx, r14; this
0x18006b1ef  call    ?GetUserContextFromProvider@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccountProvider@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromProvider(Windows::Security::Credentials::IWebAccountProvider *,unsigned __int64 &)
0x18006b1f4  mov     ebx, eax
0x18006b1f6  test    eax, eax
0x18006b1f8  jns     short loc_18006B236
0x18006b1fa  mov     rcx, [rsp+248h]; this
0x18006b202  mov     r9d, eax; char *
0x18006b205  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b20c  mov     edx, 432h; void *
0x18006b211  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b216  nop
0x18006b217  lea     rcx, [rsp+248h+var_200]; this
0x18006b21c  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b221  nop
0x18006b222  lea     rcx, [rsp+248h+var_198]; this
0x18006b22a  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b22f  mov     eax, ebx
0x18006b231  jmp     loc_18006B96A
0x18006b236  mov     rdi, [rsp+248h+var_1F8]
0x18006b23b  mov     [rsp+248h+var_1F8], r15
0x18006b240  mov     [rsp+248h+var_208], rdi
0x18006b245  test    rdi, rdi
0x18006b248  jnz     short loc_18006B298
0x18006b24a  mov     rcx, [rsp+248h]; this
0x18006b252  mov     ebx, 80070057h
0x18006b257  mov     r9d, ebx; char *
0x18006b25a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b261  mov     edx, 435h; void *
0x18006b266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b26b  nop
0x18006b26c  xor     edx, edx
0x18006b26e  lea     rcx, [rsp+248h+var_208]
0x18006b273  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18006b278  nop
0x18006b279  lea     rcx, [rsp+248h+var_200]; this
0x18006b27e  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b283  nop
0x18006b284  lea     rcx, [rsp+248h+var_198]; this
0x18006b28c  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b291  mov     eax, ebx
0x18006b293  jmp     loc_18006B96A
0x18006b298  cmp     [rdi], r15b
0x18006b29b  jnz     short loc_18006B2FF
0x18006b29d  xor     r9d, r9d; bool
0x18006b2a0  mov     r8, [rsp+248h+var_1D0]; unsigned __int64
0x18006b2a5  mov     rdx, rsi; struct IUnknown *
0x18006b2a8  mov     rcx, rdi; this
0x18006b2ab  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x18006b2b0  mov     ebx, eax
0x18006b2b2  test    eax, eax
0x18006b2b4  jns     short loc_18006B2FF
0x18006b2b6  mov     rcx, [rsp+248h]; this
0x18006b2be  mov     r9d, eax; char *
0x18006b2c1  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b2c8  mov     edx, 438h; void *
0x18006b2cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b2d2  nop
0x18006b2d3  xor     edx, edx
0x18006b2d5  lea     rcx, [rsp+248h+var_208]
0x18006b2da  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18006b2df  nop
0x18006b2e0  lea     rcx, [rsp+248h+var_200]; this
0x18006b2e5  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b2ea  nop
0x18006b2eb  lea     rcx, [rsp+248h+var_198]; this
0x18006b2f3  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b2f8  mov     eax, ebx
0x18006b2fa  jmp     loc_18006B96A
0x18006b2ff  mov     [rsp+248h+TokenHandle], r15
0x18006b304  mov     [rsp+248h+var_1D8], r15b
0x18006b309  mov     rdx, [rdi+10h]; unsigned __int64
0x18006b30d  lea     rcx, [rsp+248h+TokenHandle]; TokenHandle
0x18006b312  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x18006b317  mov     ebx, eax
0x18006b319  test    eax, eax
0x18006b31b  jns     short loc_18006B371
0x18006b31d  mov     rcx, [rsp+248h]; this
0x18006b325  mov     r9d, eax; char *
0x18006b328  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b32f  mov     edx, 43Ch; void *
0x18006b334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b339  nop
0x18006b33a  lea     rcx, [rsp+248h+TokenHandle]; this
0x18006b33f  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18006b344  nop
0x18006b345  xor     edx, edx
0x18006b347  lea     rcx, [rsp+248h+var_208]
0x18006b34c  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18006b351  nop
0x18006b352  lea     rcx, [rsp+248h+var_200]; this
0x18006b357  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b35c  nop
0x18006b35d  lea     rcx, [rsp+248h+var_198]; this
0x18006b365  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b36a  mov     eax, ebx
0x18006b36c  jmp     loc_18006B96A
0x18006b371  mov     [rsp+248h+string], r15
0x18006b376  lea     r8, [rsp+248h+string]; HSTRING *
0x18006b37b  mov     rdx, r14; struct Windows::Security::Credentials::IWebAccountProvider *
0x18006b37e  mov     rcx, rdi; this
0x18006b381  call    ?GetPluginPFN@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@PEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::GetPluginPFN(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18006b386  mov     ebx, eax
0x18006b388  test    eax, eax
0x18006b38a  jns     short loc_18006B3F1
0x18006b38c  mov     rcx, [rsp+248h]; this
0x18006b394  mov     r9d, eax; char *
0x18006b397  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b39e  mov     edx, 440h; void *
0x18006b3a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b3a8  nop
0x18006b3a9  mov     rcx, [rsp+248h+string]; string
0x18006b3ae  test    rcx, rcx
0x18006b3b1  jz      short loc_18006B3BA
0x18006b3b3  call    cs:__imp_WindowsDeleteString
0x18006b3b9  nop
0x18006b3ba  lea     rcx, [rsp+248h+TokenHandle]; this
0x18006b3bf  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18006b3c4  nop
0x18006b3c5  xor     edx, edx
0x18006b3c7  lea     rcx, [rsp+248h+var_208]
0x18006b3cc  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18006b3d1  nop
0x18006b3d2  lea     rcx, [rsp+248h+var_200]; this
0x18006b3d7  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b3dc  nop
0x18006b3dd  lea     rcx, [rsp+248h+var_198]; this
0x18006b3e5  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b3ea  mov     eax, ebx
0x18006b3ec  jmp     loc_18006B96A
0x18006b3f1  mov     rcx, rdi; this
0x18006b3f4  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x18006b3f9  mov     r12b, al
0x18006b3fc  test    al, al
0x18006b3fe  jz      short loc_18006B423
0x18006b400  xor     edx, edx; bool
0x18006b402  mov     rcx, rdi; this
0x18006b405  call    ?GetCallerPackageFamilyName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAPEAUHSTRING__@@_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(bool)
0x18006b40a  mov     rcx, rax; string
0x18006b40d  mov     rbx, [rsp+248h+string]
0x18006b412  mov     rdx, rbx; HSTRING
0x18006b415  call    ?ComparePfns@@YA_NPEAUHSTRING__@@0@Z; ComparePfns(HSTRING__ *,HSTRING__ *)
0x18006b41a  test    al, al
0x18006b41c  jz      short loc_18006B428
0x18006b41e  mov     r15b, 1
0x18006b421  jmp     short loc_18006B428
0x18006b423  mov     rbx, [rsp+248h+string]
0x18006b428  call    ?IsProviderEnumerationCheckDisabled@@YA_NXZ; IsProviderEnumerationCheckDisabled(void)
0x18006b42d  test    al, al
0x18006b42f  jnz     loc_18006B6B1
0x18006b435  mov     [rsp+248h+var_210], 0
0x18006b43e  mov     rax, [r14]
0x18006b441  mov     rsi, [rax]
0x18006b444  lea     rcx, [rsp+248h+var_210]
0x18006b449  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006b44e  lea     r8, [rsp+248h+var_210]
0x18006b453  lea     rdx, _GUID_26af3d4c_8b79_408c_ae0f_df1aadbe137f
0x18006b45a  mov     rcx, r14
0x18006b45d  mov     rax, rsi
0x18006b460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b465  mov     esi, eax
0x18006b467  test    eax, eax
0x18006b469  jns     short loc_18006B4D9
0x18006b46b  mov     rcx, [rsp+248h]; this
0x18006b473  mov     r9d, eax; char *
0x18006b476  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b47d  mov     edx, 449h; void *
0x18006b482  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b487  nop
0x18006b488  lea     rcx, [rsp+248h+var_210]
0x18006b48d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006b492  nop
0x18006b493  test    rbx, rbx
0x18006b496  jz      short loc_18006B4A2
0x18006b498  mov     rcx, rbx; string
0x18006b49b  call    cs:__imp_WindowsDeleteString
0x18006b4a1  nop
0x18006b4a2  lea     rcx, [rsp+248h+TokenHandle]; this
0x18006b4a7  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18006b4ac  nop
0x18006b4ad  xor     edx, edx
0x18006b4af  lea     rcx, [rsp+248h+var_208]
0x18006b4b4  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18006b4b9  nop
0x18006b4ba  lea     rcx, [rsp+248h+var_200]; this
0x18006b4bf  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b4c4  nop
0x18006b4c5  lea     rcx, [rsp+248h+var_198]; this
0x18006b4cd  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b4d2  mov     eax, esi
0x18006b4d4  jmp     loc_18006B96A
0x18006b4d9  mov     [rsp+248h+var_218], 0
0x18006b4de  mov     rcx, [rsp+248h+var_210]
0x18006b4e3  mov     rax, [rcx]
0x18006b4e6  lea     rdx, [rsp+248h+var_218]
0x18006b4eb  mov     rax, [rax+30h]
0x18006b4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4f4  mov     esi, eax
0x18006b4f6  test    eax, eax
0x18006b4f8  jns     short loc_18006B568
0x18006b4fa  mov     rcx, [rsp+248h]; this
0x18006b502  mov     r9d, eax; char *
0x18006b505  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18006b50c  mov     edx, 44Ch; void *
0x18006b511  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006b516  nop
0x18006b517  lea     rcx, [rsp+248h+var_210]
0x18006b51c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006b521  nop
0x18006b522  test    rbx, rbx
0x18006b525  jz      short loc_18006B531
0x18006b527  mov     rcx, rbx; string
0x18006b52a  call    cs:__imp_WindowsDeleteString
0x18006b530  nop
0x18006b531  lea     rcx, [rsp+248h+TokenHandle]; this
0x18006b536  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18006b53b  nop
0x18006b53c  xor     edx, edx
0x18006b53e  lea     rcx, [rsp+248h+var_208]
0x18006b543  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18006b548  nop
0x18006b549  lea     rcx, [rsp+248h+var_200]; this
0x18006b54e  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18006b553  nop
0x18006b554  lea     rcx, [rsp+248h+var_198]; this
0x18006b55c  call    ??1TokenBrokerInternalSetWebAccountEnumerableState@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalSetWebAccountEnumerableState::~TokenBrokerInternalSetWebAccountEnumerableState(void)
0x18006b561  mov     eax, esi
0x18006b563  jmp     loc_18006B96A
0x18006b568  cmp     [rsp+248h+var_218], 0
0x18006b56d  jnz     loc_18006B62A
0x18006b573  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x18006b578  mov     rdi, rax
  ... truncated ...
```
