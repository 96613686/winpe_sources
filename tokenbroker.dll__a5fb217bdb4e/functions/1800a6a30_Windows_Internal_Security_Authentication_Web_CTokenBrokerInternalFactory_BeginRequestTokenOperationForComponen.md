# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::BeginRequestTokenOperationForComponentUI(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,IInspectable * *)

- ea: `0x1800a6a30`
- end: `0x1800a72e6`
- name: `?BeginRequestTokenOperationForComponentUI@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebTokenRequest@Core@2346@PEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@6@PEAPEAUIInspectable@@@Z`
- size: `2230`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000189c`
- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x18001e00c`
- `0x18001e700`
- `0x180020620`
- `0x180020c60`
- `0x180021750`
- `0x1800231c0`
- `0x180023a80`
- `0x18002ea84`
- `0x18002fbf0`
- `0x180031270`
- `0x1800455a4`
- `0x18004a75c`
- `0x18004d844`
- `0x18004dd84`
- `0x18004f560`
- `0x1800512b0`
- `0x180052120`
- `0x180063ff0`
- `0x18008e690`
- `0x1800a5604`
- `0x1800a6a30`
- `0x1800abfec`
- `0x1800b022c`
- `0x1800b33f0`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6efb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6ed5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a6efb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a711c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a71f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a726d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a7028`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a711c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a71f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a726d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800a6ede`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800a6ede`

## string_xrefs

- `0x1800a6ad1`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6b17`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6b82`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6be3`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6c5c`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6cc8`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6d43`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6dc3`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6e42`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6f88`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a700c`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a70f2`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a71cc`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800a6aa7`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::BeginRequestTokenOperationForComponentUI`
- `0x1800a6a61`: `TokenBrokerInternalBeginRequestTokenOperationForComponentUI`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::BeginRequestTokenOperationForComponentUI(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct IInspectable **a4)
{
  struct IUnknown *v8; // rdi
  __int64 v9; // rcx
  __int64 (__fastcall *v11)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // ebx
  HSTRING v18; // rbx
  int v19; // eax
  unsigned int v20; // edi
  int v21; // eax
  unsigned int v22; // edi
  int v23; // eax
  unsigned int v24; // edi
  const struct _tlgProvider_t *v25; // rax
  unsigned int v26; // edx
  int v27; // edi
  const WCHAR *StringRawBuffer; // rax
  HSTRING CallerPackageFamilyName; // rax
  int v30; // r9d
  int PluginPFN; // eax
  unsigned int v32; // edi
  HSTRING v33; // rdi
  Windows::Internal::Security::Authentication::TokenBroker *v34; // rax
  int TokenBindingContext; // eax
  unsigned int v36; // esi
  unsigned __int64 v37; // rdx
  int v38; // eax
  unsigned int v39; // ebx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rdx
  unsigned __int64 *v42; // [rsp+20h] [rbp-278h]
  int v43; // [rsp+20h] [rbp-278h]
  struct Windows::Security::Credentials::IWebAccountProvider *v44; // [rsp+40h] [rbp-258h] BYREF
  __int64 v45; // [rsp+48h] [rbp-250h] BYREF
  HSTRING v46; // [rsp+50h] [rbp-248h] BYREF
  HSTRING string; // [rsp+58h] [rbp-240h] BYREF
  Windows::Internal::Security::Authentication::TokenBroker *v48; // [rsp+60h] [rbp-238h] BYREF
  _BYTE v49[16]; // [rsp+68h] [rbp-230h] BYREF
  void *TokenHandle; // [rsp+78h] [rbp-220h] BYREF
  char v51; // [rsp+80h] [rbp-218h]
  unsigned __int64 v52; // [rsp+88h] [rbp-210h] BYREF
  __int64 v53; // [rsp+90h] [rbp-208h] BYREF
  LPWSTR FileNameW; // [rsp+98h] [rbp-200h] BYREF
  unsigned __int64 v55; // [rsp+A0h] [rbp-1F8h] BYREF
  char v56; // [rsp+A8h] [rbp-1F0h]
  _QWORD v57[6]; // [rsp+B0h] [rbp-1E8h] BYREF
  _QWORD v58[34]; // [rsp+E0h] [rbp-1B8h] BYREF
  __int64 v59; // [rsp+1F0h] [rbp-A8h]
  HSTRING v60; // [rsp+230h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v58,
    "TokenBrokerInternalBeginRequestTokenOperationForComponentUI");
  v58[0] = &TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::`vftable';
  TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::StartActivity((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
  v8 = (struct IUnknown *)(a1 & -(__int64)(a1 != 72));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v9,
    (__int64)v49,
    v8,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::BeginRequestTokenOperationForComponentUI",
    0);
  if ( a2 )
  {
    if ( a4 )
    {
      *a4 = 0;
      v44 = 0;
      v11 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(*(_QWORD *)a2 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
      v12 = v11(a2, &v44);
      v13 = v12;
      if ( v12 >= 0 )
      {
        v45 = 0;
        v14 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>(
                &v44,
                &v45);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v52 = 0;
          v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v45 + 48LL))(v45, &v52);
          v17 = v16;
          if ( v16 >= 0 )
          {
            wil::make_unique_nothrow<Windows::Internal::Security::Authentication::Web::CallerContext,>(&v46);
            v18 = v46;
            if ( v46 )
            {
              v19 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
                      (Windows::Internal::Security::Authentication::Web::CallerContext *)v46,
                      v8,
                      v52,
                      1);
              v20 = v19;
              if ( v19 >= 0 )
              {
                TokenHandle = 0;
                v51 = 0;
                v21 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
                        &TokenHandle,
                        *((_QWORD *)v18 + 2));
                v22 = v21;
                if ( v21 >= 0 )
                {
                  v23 = Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(
                          (Windows::Internal::Security::Authentication::Web::CallerContext *)v18,
                          ::string);
                  v24 = v23;
                  if ( v23 >= 0 )
                  {
                    v25 = TbLogProvider::Provider();
                    v27 = (int)v25;
                    if ( *(_DWORD *)v25 > 5u )
                    {
                      v53 = *((_QWORD *)v18 + 1);
                      LODWORD(string) = Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v18);
                      StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v18 + 7), 0);
                      FileNameW = PathFindFileNameW(StringRawBuffer);
                      CallerPackageFamilyName = Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(
                                                  (Windows::Internal::Security::Authentication::Web::CallerContext *)v18,
                                                  0);
                      v55 = (unsigned __int64)WindowsGetStringRawBuffer(CallerPackageFamilyName, 0);
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                        v27,
                        (unsigned int)&word_180148E66,
                        v59 + 8,
                        v30,
                        (__int64)&v55,
                        (__int64)&FileNameW,
                        (__int64)&string,
                        (__int64)&v53);
                    }
                    Windows::Internal::Security::Authentication::Web::PrimeTokenBrokerOnFirstInvocation(
                      (Windows::Internal::Security::Authentication::Web *)*((unsigned int *)v18 + 6),
                      v26);
                    if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v18)
                      && (unsigned int)Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType((int (__fastcall ***)(_QWORD, GUID *, __int64 *))v44) == 4 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x88F,
                        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                        (const char *)0x80070005LL,
                        (int)v42);
                      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
                      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                        &v46,
                        0);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                      TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                      return 2147942405LL;
                    }
                    else
                    {
                      string = 0;
                      PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(
                                    v44,
                                    &string);
                      v32 = PluginPFN;
                      if ( PluginPFN >= 0 )
                      {
                        v48 = 0;
                        v55 = (unsigned __int64)&v48;
                        v56 = 1;
                        v33 = string;
                        if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v18) )
                          v34 = (Windows::Internal::Security::Authentication::TokenBroker *)Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(
                                                                                              (Windows::Internal::Security::Authentication::Web::CallerContext *)v18,
                                                                                              0);
                        else
                          v34 = *(Windows::Internal::Security::Authentication::TokenBroker **)Windows::Internal::StringReference::StringReference(
                                                                                                &v60,
                                                                                                L"NO_APPLICATION");
                        TokenBindingContext = Windows::Internal::Security::Authentication::TokenBroker::CreateTokenBindingContext(
                                                v34,
                                                v33,
                                                v18,
                                                (struct Windows::Internal::Security::Authentication::Web::CallerContext *)&v48,
                                                v42);
                        v36 = TokenBindingContext;
                        if ( TokenBindingContext >= 0 )
                        {
                          v57[4] = 0;
                          v57[0] = a2;
                          v57[1] = a3;
                          v46 = 0;
                          v57[2] = v18;
                          v57[3] = v48;
                          v48 = 0;
                          v38 = LaunchProvider(
                                  (struct Windows::Internal::Security::Authentication::Web::RequestTokenOperationParams *)v57,
                                  a4);
                          v39 = v38;
                          if ( v38 >= 0 )
                          {
                            wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v58);
                            if ( v48 )
                              Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(
                                v48,
                                v41);
                            if ( v33 )
                              WindowsDeleteString(v33);
                            Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
                            wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                              &v46,
                              0);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                            Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                            TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                            return 0;
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x8B1,
                              (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                              (const char *)(unsigned int)v38,
                              v43);
                            if ( v48 )
                              Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(
                                v48,
                                v40);
                            if ( v33 )
                              WindowsDeleteString(v33);
                            Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
                            wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                              &v46,
                              0);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                            Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                            TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                            return v39;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x8A5,
                            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                            (const char *)(unsigned int)TokenBindingContext,
                            v43);
                          if ( v48 )
                            Windows::Internal::Security::Authentication::TokenBroker::FreeTokenBindingContext(v48, v37);
                          if ( v33 )
                            WindowsDeleteString(v33);
                          Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
                          wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                            &v46,
                            0);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                          TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                          return v36;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x896,
                          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                          (const char *)(unsigned int)PluginPFN,
                          (int)v42);
                        if ( string )
                          WindowsDeleteString(string);
                        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
                        wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                          &v46,
                          0);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                        TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                        return v32;
                      }
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x87D,
                      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                      (const char *)(unsigned int)v23,
                      (int)v42);
                    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
                    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                      &v46,
                      0);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                    TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                    return v24;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x87B,
                    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                    (const char *)(unsigned int)v21,
                    (int)v42);
                  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
                  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                    &v46,
                    0);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                  TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                  return v22;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x878,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                  (const char *)(unsigned int)v19,
                  (int)v42);
                wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                  &v46,
                  0);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
                Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
                TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
                return v20;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x877,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
                (const char *)0x8007000ELL,
                (int)v42);
              wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
                &v46,
                0);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
              Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
              TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
              return 2147942414LL;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x874,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
              (const char *)(unsigned int)v16,
              (int)v42);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
            TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
            return v17;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x871,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
            (const char *)(unsigned int)v14,
            (int)v42);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
          Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
          TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
          return v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x86E,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
          (const char *)(unsigned int)v12,
          (int)v42);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
        Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
        TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x869,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)0x80004003LL,
        (int)v42);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
      TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x868,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)0x80070057LL,
      (int)v42);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v49);
    TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI((TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI *)v58);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800a6a30  push    rbx
0x1800a6a32  push    rsi
0x1800a6a33  push    rdi
0x1800a6a34  push    r12
0x1800a6a36  push    r13
0x1800a6a38  push    r14
0x1800a6a3a  push    r15
0x1800a6a3c  sub     rsp, 260h
0x1800a6a43  mov     rax, cs:__security_cookie
0x1800a6a4a  xor     rax, rsp
0x1800a6a4d  mov     [rsp+298h+var_48], rax
0x1800a6a55  mov     r15, r9
0x1800a6a58  mov     r12, r8
0x1800a6a5b  mov     r14, rdx
0x1800a6a5e  mov     rbx, rcx
0x1800a6a61  lea     rdx, aTokenbrokerint_9; "TokenBrokerInternalBeginRequestTokenOpe"...
0x1800a6a68  lea     rcx, [rsp+298h+var_1B8]
0x1800a6a70  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800a6a75  lea     rax, ??_7TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::`vftable'
0x1800a6a7c  mov     [rsp+298h+var_1B8], rax
0x1800a6a84  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6a8c  call    ?StartActivity@TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::StartActivity(void)
0x1800a6a91  nop
0x1800a6a92  lea     rax, [rbx-48h]
0x1800a6a96  neg     rax
0x1800a6a99  sbb     rdi, rdi
0x1800a6a9c  and     rdi, rbx
0x1800a6a9f  xor     r13d, r13d
0x1800a6aa2  mov     byte ptr [rsp+298h+var_278], r13b; int
0x1800a6aa7  lea     r9, aWindowsInterna_34; "Windows::Internal::Security::Authentica"...
0x1800a6aae  mov     r8, rdi
0x1800a6ab1  lea     rdx, [rsp+298h+var_230]
0x1800a6ab6  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800a6abb  nop
0x1800a6abc  test    r14, r14
0x1800a6abf  jnz     short loc_1800A6B02
0x1800a6ac1  mov     rcx, [rsp+298h]; this
0x1800a6ac9  mov     ebx, 80070057h
0x1800a6ace  mov     r9d, ebx; char *
0x1800a6ad1  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6ad8  mov     edx, 868h; void *
0x1800a6add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6ae2  nop
0x1800a6ae3  lea     rcx, [rsp+298h+var_230]; this
0x1800a6ae8  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6aed  nop
0x1800a6aee  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6af6  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6afb  mov     eax, ebx
0x1800a6afd  jmp     loc_1800A72C2
0x1800a6b02  test    r15, r15
0x1800a6b05  jnz     short loc_1800A6B48
0x1800a6b07  mov     rcx, [rsp+298h]; this
0x1800a6b0f  mov     ebx, 80004003h
0x1800a6b14  mov     r9d, ebx; char *
0x1800a6b17  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6b1e  mov     edx, 869h; void *
0x1800a6b23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6b28  nop
0x1800a6b29  lea     rcx, [rsp+298h+var_230]; this
0x1800a6b2e  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6b33  nop
0x1800a6b34  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6b3c  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6b41  mov     eax, ebx
0x1800a6b43  jmp     loc_1800A72C2
0x1800a6b48  mov     [r15], r13
0x1800a6b4b  mov     [rsp+298h+var_258], r13
0x1800a6b50  mov     rax, [r14]
0x1800a6b53  mov     rbx, [rax+30h]
0x1800a6b57  lea     rcx, [rsp+298h+var_258]
0x1800a6b5c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6b61  lea     rdx, [rsp+298h+var_258]
0x1800a6b66  mov     rcx, r14
0x1800a6b69  mov     rax, rbx
0x1800a6b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6b71  mov     ebx, eax
0x1800a6b73  test    eax, eax
0x1800a6b75  jns     short loc_1800A6BBE
0x1800a6b77  mov     rcx, [rsp+298h]; this
0x1800a6b7f  mov     r9d, eax; char *
0x1800a6b82  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6b89  mov     edx, 86Eh; void *
0x1800a6b8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6b93  nop
0x1800a6b94  lea     rcx, [rsp+298h+var_258]
0x1800a6b99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6b9e  nop
0x1800a6b9f  lea     rcx, [rsp+298h+var_230]; this
0x1800a6ba4  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6ba9  nop
0x1800a6baa  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6bb2  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6bb7  mov     eax, ebx
0x1800a6bb9  jmp     loc_1800A72C2
0x1800a6bbe  mov     [rsp+298h+var_250], r13
0x1800a6bc3  lea     rdx, [rsp+298h+var_250]
0x1800a6bc8  lea     rcx, [rsp+298h+var_258]
0x1800a6bcd  call    ??$As@UIWebAccountProviderUserContext@Credentials@Security@Internal@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProviderUserContext@Credentials@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>>)
0x1800a6bd2  mov     ebx, eax
0x1800a6bd4  test    eax, eax
0x1800a6bd6  jns     short loc_1800A6C2A
0x1800a6bd8  mov     rcx, [rsp+298h]; this
0x1800a6be0  mov     r9d, eax; char *
0x1800a6be3  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6bea  mov     edx, 871h; void *
0x1800a6bef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6bf4  nop
0x1800a6bf5  lea     rcx, [rsp+298h+var_250]
0x1800a6bfa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6bff  nop
0x1800a6c00  lea     rcx, [rsp+298h+var_258]
0x1800a6c05  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6c0a  nop
0x1800a6c0b  lea     rcx, [rsp+298h+var_230]; this
0x1800a6c10  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6c15  nop
0x1800a6c16  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6c1e  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6c23  mov     eax, ebx
0x1800a6c25  jmp     loc_1800A72C2
0x1800a6c2a  mov     [rsp+298h+var_210], r13
0x1800a6c32  mov     rcx, [rsp+298h+var_250]
0x1800a6c37  mov     rax, [rcx]
0x1800a6c3a  lea     rdx, [rsp+298h+var_210]
0x1800a6c42  mov     rax, [rax+30h]
0x1800a6c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c4b  mov     ebx, eax
0x1800a6c4d  test    eax, eax
0x1800a6c4f  jns     short loc_1800A6CA3
0x1800a6c51  mov     rcx, [rsp+298h]; this
0x1800a6c59  mov     r9d, eax; char *
0x1800a6c5c  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6c63  mov     edx, 874h; void *
0x1800a6c68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c6d  nop
0x1800a6c6e  lea     rcx, [rsp+298h+var_250]
0x1800a6c73  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6c78  nop
0x1800a6c79  lea     rcx, [rsp+298h+var_258]
0x1800a6c7e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6c83  nop
0x1800a6c84  lea     rcx, [rsp+298h+var_230]; this
0x1800a6c89  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6c8e  nop
0x1800a6c8f  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6c97  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6c9c  mov     eax, ebx
0x1800a6c9e  jmp     loc_1800A72C2
0x1800a6ca3  lea     rcx, [rsp+298h+var_248]
0x1800a6ca8  call    ??$make_unique_nothrow@VCallerContext@Web@Authentication@Security@Internal@Windows@@$$V@wil@@YA?AV?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@XZ; wil::make_unique_nothrow<Windows::Internal::Security::Authentication::Web::CallerContext,>(void)
0x1800a6cad  nop
0x1800a6cae  mov     rbx, [rsp+298h+var_248]
0x1800a6cb3  test    rbx, rbx
0x1800a6cb6  jnz     short loc_1800A6D1C
0x1800a6cb8  mov     rcx, [rsp+298h]; this
0x1800a6cc0  mov     ebx, 8007000Eh
0x1800a6cc5  mov     r9d, ebx; char *
0x1800a6cc8  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6ccf  mov     edx, 877h; void *
0x1800a6cd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6cd9  nop
0x1800a6cda  xor     edx, edx
0x1800a6cdc  lea     rcx, [rsp+298h+var_248]
0x1800a6ce1  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800a6ce6  nop
0x1800a6ce7  lea     rcx, [rsp+298h+var_250]
0x1800a6cec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6cf1  nop
0x1800a6cf2  lea     rcx, [rsp+298h+var_258]
0x1800a6cf7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6cfc  nop
0x1800a6cfd  lea     rcx, [rsp+298h+var_230]; this
0x1800a6d02  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6d07  nop
0x1800a6d08  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6d10  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6d15  mov     eax, ebx
0x1800a6d17  jmp     loc_1800A72C2
0x1800a6d1c  mov     r9b, 1; bool
0x1800a6d1f  mov     r8, [rsp+298h+var_210]; unsigned __int64
0x1800a6d27  mov     rdx, rdi; struct IUnknown *
0x1800a6d2a  mov     rcx, rbx; this
0x1800a6d2d  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800a6d32  mov     edi, eax
0x1800a6d34  test    eax, eax
0x1800a6d36  jns     short loc_1800A6D97
0x1800a6d38  mov     rcx, [rsp+298h]; this
0x1800a6d40  mov     r9d, eax; char *
0x1800a6d43  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6d4a  mov     edx, 878h; void *
0x1800a6d4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6d54  nop
0x1800a6d55  xor     edx, edx
0x1800a6d57  lea     rcx, [rsp+298h+var_248]
0x1800a6d5c  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800a6d61  nop
0x1800a6d62  lea     rcx, [rsp+298h+var_250]
0x1800a6d67  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6d6c  nop
0x1800a6d6d  lea     rcx, [rsp+298h+var_258]
0x1800a6d72  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6d77  nop
0x1800a6d78  lea     rcx, [rsp+298h+var_230]; this
0x1800a6d7d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6d82  nop
0x1800a6d83  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6d8b  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6d90  mov     eax, edi
0x1800a6d92  jmp     loc_1800A72C2
0x1800a6d97  mov     [rsp+298h+TokenHandle], r13
0x1800a6d9c  mov     [rsp+298h+var_218], r13b
0x1800a6da4  mov     rdx, [rbx+10h]; unsigned __int64
0x1800a6da8  lea     rcx, [rsp+298h+TokenHandle]; TokenHandle
0x1800a6dad  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800a6db2  mov     edi, eax
0x1800a6db4  test    eax, eax
0x1800a6db6  jns     short loc_1800A6E22
0x1800a6db8  mov     rcx, [rsp+298h]; this
0x1800a6dc0  mov     r9d, eax; char *
0x1800a6dc3  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6dca  mov     edx, 87Bh; void *
0x1800a6dcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6dd4  nop
0x1800a6dd5  lea     rcx, [rsp+298h+TokenHandle]; this
0x1800a6dda  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800a6ddf  nop
0x1800a6de0  xor     edx, edx
0x1800a6de2  lea     rcx, [rsp+298h+var_248]
0x1800a6de7  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800a6dec  nop
0x1800a6ded  lea     rcx, [rsp+298h+var_250]
0x1800a6df2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6df7  nop
0x1800a6df8  lea     rcx, [rsp+298h+var_258]
0x1800a6dfd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6e02  nop
0x1800a6e03  lea     rcx, [rsp+298h+var_230]; this
0x1800a6e08  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6e0d  nop
0x1800a6e0e  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6e16  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6e1b  mov     eax, edi
0x1800a6e1d  jmp     loc_1800A72C2
0x1800a6e22  mov     rdx, cs:string; HSTRING
0x1800a6e29  mov     rcx, rbx; this
0x1800a6e2c  call    ?VerifyCapability@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAJPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::Web::CallerContext::VerifyCapability(HSTRING__ *)
0x1800a6e31  mov     edi, eax
0x1800a6e33  test    eax, eax
0x1800a6e35  jns     short loc_1800A6EA1
0x1800a6e37  mov     rcx, [rsp+298h]; this
0x1800a6e3f  mov     r9d, eax; char *
0x1800a6e42  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800a6e49  mov     edx, 87Dh; void *
0x1800a6e4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6e53  nop
0x1800a6e54  lea     rcx, [rsp+298h+TokenHandle]; this
0x1800a6e59  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800a6e5e  nop
0x1800a6e5f  xor     edx, edx
0x1800a6e61  lea     rcx, [rsp+298h+var_248]
0x1800a6e66  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800a6e6b  nop
0x1800a6e6c  lea     rcx, [rsp+298h+var_250]
0x1800a6e71  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6e76  nop
0x1800a6e77  lea     rcx, [rsp+298h+var_258]
0x1800a6e7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a6e81  nop
0x1800a6e82  lea     rcx, [rsp+298h+var_230]; this
0x1800a6e87  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800a6e8c  nop
0x1800a6e8d  lea     rcx, [rsp+298h+var_1B8]; this
0x1800a6e95  call    ??1TokenBrokerInternalBeginRequestTokenOperationForComponentUI@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalBeginRequestTokenOperationForComponentUI::~TokenBrokerInternalBeginRequestTokenOperationForComponentUI(void)
0x1800a6e9a  mov     eax, edi
0x1800a6e9c  jmp     loc_1800A72C2
0x1800a6ea1  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800a6ea6  mov     rdi, rax
0x1800a6ea9  mov     ecx, [rax]
0x1800a6eab  cmp     ecx, 5
0x1800a6eae  jbe     loc_1800A6F55
0x1800a6eb4  mov     rcx, [rbx+8]
0x1800a6eb8  mov     [rsp+298h+var_208], rcx
0x1800a6ec0  mov     rcx, rbx; this
0x1800a6ec3  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800a6ec8  movzx   ecx, al
0x1800a6ecb  mov     dword ptr [rsp+298h+string], ecx
0x1800a6ecf  xor     edx, edx; length
0x1800a6ed1  mov     rcx, [rbx+38h]; string
0x1800a6ed5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a6edb  mov     rcx, rax; pszPath
0x1800a6ede  call    cs:__imp_PathFindFileNameW
0x1800a6ee4  mov     [rsp+298h+var_200], rax
0x1800a6eec  xor     edx, edx; bool
0x1800a6eee  mov     rcx, rbx; this
0x1800a6ef1  call    ?GetCallerPackageFamilyName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAPEAUHSTRING__@@_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(bool)
0x1800a6ef6  mov     rcx, rax; string
0x1800a6ef9  xor     edx, edx; length
0x1800a6efb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a6f01  mov     [rsp+298h+var_1F8], rax
  ... truncated ...
```
