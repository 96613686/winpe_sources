# LaunchProvider(Windows::Internal::Security::Authentication::Web::RequestTokenOperationParams *,IInspectable * *)

- ea: `0x1800abfec`
- end: `0x1800ac650`
- name: `?LaunchProvider@@YAJPEAURequestTokenOperationParams@Web@Authentication@Security@Internal@Windows@@PEAPEAUIInspectable@@@Z`
- size: `1636`
- prototype: `__int64 __fastcall(struct Windows::Internal::Security::Authentication::Web::RequestTokenOperationParams *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a6a30`

## callees

- `0x180001008`
- `0x180007350`
- `0x18000bd40`
- `0x18000d250`
- `0x180024544`
- `0x1800277c4`
- `0x18002fbf0`
- `0x180031220`
- `0x18004a4fc`
- `0x18004f560`
- `0x18004fdbc`
- `0x1800512b0`
- `0x180063fc4`
- `0x180063ff0`
- `0x18008e690`
- `0x1800a2c64`
- `0x1800a2e44`
- `0x1800a3864`
- `0x1800a4a4c`
- `0x1800a53d0`
- `0x1800a55a8`
- `0x1800abfec`
- `0x1800b296c`
- `0x1800ef38c`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac36f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac37e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac38f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac36f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac37e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac38f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ac3af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac2c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac5ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac5ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac2c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac2e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac486`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac5d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac5ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ac5ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ac39e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ac39e`

## string_xrefs

- `0x1800ac070`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800ac0bd`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800ac104`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800ac19d`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800ac29e`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800ac455`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800ac4fb`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`
- `0x1800ac53c`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerinternal.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall LaunchProvider(
        struct Windows::Internal::Security::Authentication::Web::RequestTokenOperationParams *a1,
        struct IInspectable **a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **); // rbx
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  int AccountsWithContext; // eax
  __int64 v11; // rdx
  unsigned int CallingAppName; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rdx
  PCWSTR v16; // rsi
  int v17; // eax
  __int64 v18; // rdx
  HSTRING v19; // rcx
  HSTRING v20; // rbx
  HSTRING CallerPackageFamilyName; // rax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  bool IsCallerAppContainer; // di
  HSTRING v26; // rax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  struct IInspectable *v30; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  int v35[2]; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING v37; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v40; // [rsp+70h] [rbp-90h] BYREF
  HSTRING v41; // [rsp+78h] [rbp-88h] BYREF
  const WCHAR *v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  int v45; // [rsp+98h] [rbp-68h] BYREF
  struct IInspectable *v46; // [rsp+A0h] [rbp-60h] BYREF
  IUnknown *ppOldObject; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR v48; // [rsp+B0h] [rbp-50h] BYREF
  PCWSTR v49; // [rsp+B8h] [rbp-48h] BYREF
  int v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-38h] BYREF
  PCWSTR StringRawBuffer; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v53[48]; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v34 = 0;
  *a2 = 0;
  LaunchProvider_::_2_::ActLogger_TokenBrokerOperationAction::ActLogger_TokenBrokerOperationAction(v53, &v34);
  v40 = 0;
  v4 = *(_QWORD *)a1;
  v5 = *(__int64 (__fastcall **)(__int64, struct Windows::Security::Credentials::IWebAccountProvider **))(**(_QWORD **)a1 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  v6 = v5(v4, &v40);
  v7 = v6;
  v34 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F9,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v6,
      v32);
    goto LABEL_60;
  }
  *(_QWORD *)v35 = 0;
  v8 = *((_QWORD *)a1 + 1);
  if ( !v8 )
    goto LABEL_15;
  v45 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 56LL))(v8, &v45);
  v7 = v9;
  v34 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7FF,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v9,
      v32);
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
    goto LABEL_60;
  }
  if ( v45 )
  {
    ppOldObject = 0;
    AccountsWithContext = Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext::SwitchToNull(&ppOldObject);
    v7 = AccountsWithContext;
    v34 = AccountsWithContext;
    if ( AccountsWithContext < 0 )
    {
      v11 = 2056;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)AccountsWithContext,
        v32);
      Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext::~ScopedSwitchContext((Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext *)&ppOldObject);
      goto LABEL_6;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
    CallingAppName = (unsigned int)Windows::Internal::Security::Authentication::Web::CallerContext::GetCallingAppName(*((Windows::Internal::Security::Authentication::Web::CallerContext **)a1 + 2));
    AccountsWithContext = Windows::Internal::Security::Authentication::TokenBroker::ReFindAccountsWithContext(
                            *((_QWORD *)a1 + 1),
                            (_DWORD)v40,
                            2,
                            CallingAppName,
                            (__int64)v35);
    v7 = AccountsWithContext;
    v34 = AccountsWithContext;
    if ( AccountsWithContext < 0 )
    {
      v11 = 2063;
      goto LABEL_10;
    }
    Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext::~ScopedSwitchContext((Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext *)&ppOldObject);
  }
  if ( !*(_QWORD *)v35 )
  {
LABEL_15:
    v43 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    v14 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
            v13,
            &v43);
    v7 = v14;
    v34 = v14;
    if ( v14 < 0 )
    {
      v15 = 2070;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
        (const char *)(unsigned int)v14,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
      goto LABEL_6;
    }
    v14 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>::As<Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *>>(
            &v43,
            v35);
    v7 = v14;
    v34 = v14;
    if ( v14 < 0 )
    {
      v15 = 2071;
      goto LABEL_17;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  }
  v37 = 0;
  (*(void (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)v40 + 48LL))(
    v40,
    &v37);
  v41 = 0;
  v16 = L"NULL";
  Windows::Internal::String::Initialize((Windows::Internal::String *)&v41, L"NULL", 4u);
  Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(v40, &v41);
  v39 = 0;
  string = 0;
  if ( (int)Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(
              &v40,
              &v39) < 0
    || (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 56LL))(v39, &string) < 0 )
  {
    Windows::Internal::String::Initialize((Windows::Internal::String *)&string, L"NULL", 4u);
  }
  v38 = 0;
  v17 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>(
          &v40,
          &v38);
  v7 = v17;
  v34 = v17;
  if ( v17 < 0 )
  {
    v18 = 2092;
    goto LABEL_26;
  }
  v51 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v38 + 48LL))(v38, &v51);
  v7 = v17;
  v34 = v17;
  if ( v17 < 0 )
  {
    v18 = 2095;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v17,
      v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v19 = v41;
    if ( !v41 )
      goto LABEL_30;
    goto LABEL_29;
  }
  v20 = v41;
  if ( (unsigned int)dword_180175000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180175000, 0x400000000000LL) )
  {
    CallerPackageFamilyName = Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(
                                *((Windows::Internal::Security::Authentication::Web::CallerContext **)a1 + 2),
                                0);
    StringRawBuffer = WindowsGetStringRawBuffer(CallerPackageFamilyName, 0);
    v48 = WindowsGetStringRawBuffer(v20, 0);
    v49 = WindowsGetStringRawBuffer(string, 0);
    if ( !WindowsIsStringEmpty(v37) )
      v16 = WindowsGetStringRawBuffer(v37, 0);
    *(_QWORD *)v50 = v16;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      v22,
      (unsigned int)byte_1801490C5,
      v23,
      v24,
      (__int64)v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&StringRawBuffer);
  }
  *a2 = 0;
  v42 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  IsCallerAppContainer = Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(*((Windows::Internal::Security::Authentication::Web::CallerContext **)a1 + 2));
  v26 = Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(
          *((Windows::Internal::Security::Authentication::Web::CallerContext **)a1 + 2),
          0);
  LOBYTE(v32) = IsCallerAppContainer;
  v27 = Windows::Internal::Security::Authentication::TokenBroker::ConstructWebProviderTokenRequest(
          *(_QWORD *)a1,
          *(_QWORD *)v35,
          v26);
  v7 = v27;
  v34 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x847,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v27,
      v32);
LABEL_41:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    if ( !v20 )
      goto LABEL_30;
    v19 = v20;
LABEL_29:
    WindowsDeleteString(v19);
LABEL_30:
    if ( v37 )
      WindowsDeleteString(v37);
    goto LABEL_6;
  }
  v44 = 0;
  *(_QWORD *)v50 = 0;
  v49 = 0;
  v48 = v42;
  LODWORD(v41) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  v28 = Windows::Internal::ComTaskPool::MakeAndInitializeOnSharedSTAThread<Windows::Security::Authentication::Web::Provider::CWebAccountProviderActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,enum Windows::Security::Authentication::Web::Provider::WebAccountProviderOperationKind,Windows::Security::Authentication::Web::Provider::IWebProviderTokenRequest *,std::nullptr_t,std::nullptr_t>(
          (unsigned int)&v44,
          (unsigned int)&v41,
          (unsigned int)&v48,
          (unsigned int)&v49,
          (__int64)v50);
  v7 = v28;
  v34 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x850,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v28,
      v33);
LABEL_47:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
    goto LABEL_41;
  }
  v46 = 0;
  v29 = Microsoft::WRL::ComPtr<Windows::ApplicationModel::Activation::IActivatedEventArgs>::As<Windows::ApplicationModel::Activation::IWebAccountProviderActivatedEventArgs>(
          &v44,
          &v46);
  v7 = v29;
  v34 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x853,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerinternal.cpp",
      (const char *)(unsigned int)v29,
      v33);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    goto LABEL_47;
  }
  if ( (unsigned int)dword_180175000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180175000, 0x200000000000LL) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &byte_180149137,
      0,
      0);
  v30 = v46;
  v46 = 0;
  *a2 = v30;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  if ( string )
    WindowsDeleteString(string);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  if ( v20 )
    WindowsDeleteString(v20);
  if ( v37 )
    WindowsDeleteString(v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
  v7 = 0;
LABEL_60:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  LaunchProvider_::_2_::ActLogger_TokenBrokerOperationAction::_ActLogger_TokenBrokerOperationAction(v53);
  return v7;
}

```

## disassembly

```asm
0x1800abfec  mov     [rsp-8+arg_10], rbx
0x1800abff1  push    rbp
0x1800abff2  push    rsi
0x1800abff3  push    rdi
0x1800abff4  push    r12
0x1800abff6  push    r13
0x1800abff8  push    r14
0x1800abffa  push    r15
0x1800abffc  lea     rbp, [rsp-10h]
0x1800ac001  sub     rsp, 110h
0x1800ac008  mov     rax, cs:__security_cookie
0x1800ac00f  xor     rax, rsp
0x1800ac012  mov     [rbp+40h+var_38], rax
0x1800ac016  mov     r12, rdx
0x1800ac019  mov     r15, rcx
0x1800ac01c  xor     r13d, r13d
0x1800ac01f  mov     [rsp+140h+var_100], r13d
0x1800ac024  mov     [rdx], r13
0x1800ac027  lea     rdx, [rsp+140h+var_100]
0x1800ac02c  lea     rcx, [rbp+40h+var_68]
0x1800ac030  call    _LaunchProvider____2___ActLogger_TokenBrokerOperationAction__ActLogger_TokenBrokerOperationAction
0x1800ac035  nop
0x1800ac036  mov     [rsp+140h+var_D0], r13
0x1800ac03b  mov     rdi, [r15]
0x1800ac03e  mov     rax, [rdi]
0x1800ac041  mov     rbx, [rax+30h]
0x1800ac045  lea     rcx, [rsp+140h+var_D0]
0x1800ac04a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac04f  lea     rdx, [rsp+140h+var_D0]
0x1800ac054  mov     rcx, rdi
0x1800ac057  mov     rax, rbx
0x1800ac05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac05f  mov     edi, eax
0x1800ac061  mov     [rsp+140h+var_100], eax
0x1800ac065  test    eax, eax
0x1800ac067  jns     short loc_1800AC086
0x1800ac069  mov     rcx, [rbp+48h]; this
0x1800ac06d  mov     r9d, eax; char *
0x1800ac070  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ac077  mov     edx, 7F9h; void *
0x1800ac07c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac081  jmp     loc_1800AC613
0x1800ac086  mov     qword ptr [rsp+140h+var_F8], r13
0x1800ac08b  mov     rcx, [r15+8]
0x1800ac08f  test    rcx, rcx
0x1800ac092  jz      loc_1800AC178
0x1800ac098  mov     [rbp+40h+var_A8], r13d
0x1800ac09c  mov     rax, [rcx]
0x1800ac09f  lea     rdx, [rbp+40h+var_A8]
0x1800ac0a3  mov     rax, [rax+38h]
0x1800ac0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac0ac  mov     edi, eax
0x1800ac0ae  mov     [rsp+140h+var_100], eax
0x1800ac0b2  test    eax, eax
0x1800ac0b4  jns     short loc_1800AC0DE
0x1800ac0b6  mov     rcx, [rbp+48h]; this
0x1800ac0ba  mov     r9d, eax; char *
0x1800ac0bd  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ac0c4  mov     edx, 7FFh; void *
0x1800ac0c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac0ce  nop
0x1800ac0cf  lea     rcx, [rsp+140h+var_F8]
0x1800ac0d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac0d9  jmp     loc_1800AC613
0x1800ac0de  cmp     [rbp+40h+var_A8], r13d
0x1800ac0e2  jbe     loc_1800AC171
0x1800ac0e8  mov     [rbp+40h+ppOldObject], r13
0x1800ac0ec  lea     rcx, [rbp+40h+ppOldObject]; ppOldObject
0x1800ac0f0  call    ?SwitchToNull@ScopedSwitchContext@TokenBroker@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext::SwitchToNull(void)
0x1800ac0f5  mov     edi, eax
0x1800ac0f7  mov     [rsp+140h+var_100], eax
0x1800ac0fb  test    eax, eax
0x1800ac0fd  jns     short loc_1800AC123
0x1800ac0ff  mov     edx, 808h; void *
0x1800ac104  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ac10b  mov     r9d, eax; char *
0x1800ac10e  mov     rcx, [rbp+48h]; this
0x1800ac112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac117  nop
0x1800ac118  lea     rcx, [rbp+40h+ppOldObject]; this
0x1800ac11c  call    ??1ScopedSwitchContext@TokenBroker@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext::~ScopedSwitchContext(void)
0x1800ac121  jmp     short loc_1800AC0CF
0x1800ac123  lea     rcx, [rsp+140h+var_F8]
0x1800ac128  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac12d  mov     rcx, [r15+10h]; this
0x1800ac131  call    ?GetCallingAppName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAPEAUHSTRING__@@XZ; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallingAppName(void)
0x1800ac136  lea     rcx, [rsp+140h+var_F8]
0x1800ac13b  mov     qword ptr [rsp+140h+var_120], rcx; int
0x1800ac140  mov     r9, rax
0x1800ac143  mov     r8d, 2
0x1800ac149  mov     rdx, [rsp+140h+var_D0]
0x1800ac14e  mov     rcx, [r15+8]
0x1800ac152  call    ?ReFindAccountsWithContext@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAUIWebAccountProvider@Credentials@35@W4AccountLookupContext@12345@PEAUHSTRING__@@PEAPEAU?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@785@@Z; Windows::Internal::Security::Authentication::TokenBroker::ReFindAccountsWithContext(Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Internal::Security::Authentication::TokenBroker::AccountLookupContext,HSTRING__ *,Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *> * *)
0x1800ac157  mov     edi, eax
0x1800ac159  mov     [rsp+140h+var_100], eax
0x1800ac15d  test    eax, eax
0x1800ac15f  jns     short loc_1800AC168
0x1800ac161  mov     edx, 80Fh
0x1800ac166  jmp     short loc_1800AC104
0x1800ac168  lea     rcx, [rbp+40h+ppOldObject]; this
0x1800ac16c  call    ??1ScopedSwitchContext@TokenBroker@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::TokenBroker::ScopedSwitchContext::~ScopedSwitchContext(void)
0x1800ac171  cmp     qword ptr [rsp+140h+var_F8], r13
0x1800ac176  jnz     short loc_1800AC1E6
0x1800ac178  mov     [rbp+40h+var_B8], r13
0x1800ac17c  lea     rcx, [rbp+40h+var_B8]
0x1800ac180  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac185  lea     rdx, [rbp+40h+var_B8]
0x1800ac189  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0> * *)
0x1800ac18e  mov     edi, eax
0x1800ac190  mov     [rsp+140h+var_100], eax
0x1800ac194  test    eax, eax
0x1800ac196  jns     short loc_1800AC1BE
0x1800ac198  mov     edx, 816h; void *
0x1800ac19d  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ac1a4  mov     r9d, eax; char *
0x1800ac1a7  mov     rcx, [rbp+48h]; this
0x1800ac1ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac1b0  lea     rcx, [rbp+40h+var_B8]
0x1800ac1b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac1b9  jmp     loc_1800AC0CF
0x1800ac1be  lea     rdx, [rsp+140h+var_F8]
0x1800ac1c3  lea     rcx, [rbp+40h+var_B8]
0x1800ac1c7  call    ??$As@U?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@?$ComPtr@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>::As<Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *>>>)
0x1800ac1cc  mov     edi, eax
0x1800ac1ce  mov     [rsp+140h+var_100], eax
0x1800ac1d2  test    eax, eax
0x1800ac1d4  jns     short loc_1800AC1DD
0x1800ac1d6  mov     edx, 817h
0x1800ac1db  jmp     short loc_1800AC19D
0x1800ac1dd  lea     rcx, [rbp+40h+var_B8]
0x1800ac1e1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac1e6  mov     [rsp+140h+var_E8], r13
0x1800ac1eb  mov     rcx, [rsp+140h+var_D0]
0x1800ac1f0  mov     rax, [rcx]
0x1800ac1f3  lea     rdx, [rsp+140h+var_E8]
0x1800ac1f8  mov     rax, [rax+30h]
0x1800ac1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac201  mov     [rsp+140h+var_C8], r13
0x1800ac206  mov     ebx, 4
0x1800ac20b  mov     r8d, ebx; unsigned int
0x1800ac20e  lea     rsi, aNull_1; "NULL"
0x1800ac215  mov     rdx, rsi; unsigned __int16 *
0x1800ac218  lea     rcx, [rsp+140h+var_C8]; this
0x1800ac21d  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x1800ac222  lea     rdx, [rsp+140h+var_C8]; HSTRING *
0x1800ac227  mov     rcx, [rsp+140h+var_D0]; struct Windows::Security::Credentials::IWebAccountProvider *
0x1800ac22c  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x1800ac231  mov     [rsp+140h+var_D8], r13
0x1800ac236  mov     [rsp+140h+string], r13
0x1800ac23b  lea     rdx, [rsp+140h+var_D8]
0x1800ac240  lea     rcx, [rsp+140h+var_D0]
0x1800ac245  call    ??$As@UIWebAccountProvider2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProvider2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Security::Credentials::IWebAccountProvider2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider2>>)
0x1800ac24a  test    eax, eax
0x1800ac24c  js      short loc_1800AC268
0x1800ac24e  mov     rcx, [rsp+140h+var_D8]
0x1800ac253  mov     rax, [rcx]
0x1800ac256  lea     rdx, [rsp+140h+string]
0x1800ac25b  mov     rax, [rax+38h]
0x1800ac25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac264  test    eax, eax
0x1800ac266  jns     short loc_1800AC278
0x1800ac268  mov     r8d, ebx; unsigned int
0x1800ac26b  mov     rdx, rsi; unsigned __int16 *
0x1800ac26e  lea     rcx, [rsp+140h+string]; this
0x1800ac273  call    ?Initialize@String@Internal@Windows@@QEAAJPEBGI@Z; Windows::Internal::String::Initialize(ushort const *,uint)
0x1800ac278  mov     [rsp+140h+var_E0], r13
0x1800ac27d  lea     rdx, [rsp+140h+var_E0]
0x1800ac282  lea     rcx, [rsp+140h+var_D0]
0x1800ac287  call    ??$As@UIWebAccountProviderUserContext@Credentials@Security@Internal@Windows@@@?$ComPtr@UIWebAccountProvider@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountProviderUserContext@Credentials@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccountProvider>::As<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountProviderUserContext>>)
0x1800ac28c  mov     edi, eax
0x1800ac28e  mov     [rsp+140h+var_100], eax
0x1800ac292  test    eax, eax
0x1800ac294  jns     short loc_1800AC300
0x1800ac296  mov     edx, 82Ch; void *
0x1800ac29b  mov     r9d, eax; char *
0x1800ac29e  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ac2a5  mov     rcx, [rbp+48h]; this
0x1800ac2a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac2ae  nop
0x1800ac2af  lea     rcx, [rsp+140h+var_E0]
0x1800ac2b4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac2b9  nop
0x1800ac2ba  mov     rcx, [rsp+140h+string]; string
0x1800ac2bf  test    rcx, rcx
0x1800ac2c2  jz      short loc_1800AC2CB
0x1800ac2c4  call    cs:__imp_WindowsDeleteString
0x1800ac2ca  nop
0x1800ac2cb  lea     rcx, [rsp+140h+var_D8]
0x1800ac2d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac2d5  nop
0x1800ac2d6  mov     rcx, [rsp+140h+var_C8]; string
0x1800ac2db  test    rcx, rcx
0x1800ac2de  jz      short loc_1800AC2E7
0x1800ac2e0  call    cs:__imp_WindowsDeleteString
0x1800ac2e6  nop
0x1800ac2e7  mov     rcx, [rsp+140h+var_E8]; string
0x1800ac2ec  test    rcx, rcx
0x1800ac2ef  jz      loc_1800AC0CF
0x1800ac2f5  call    cs:__imp_WindowsDeleteString
0x1800ac2fb  jmp     loc_1800AC0CF
0x1800ac300  mov     [rbp+40h+var_78], r13
0x1800ac304  mov     rcx, [rsp+140h+var_E0]
0x1800ac309  mov     rax, [rcx]
0x1800ac30c  lea     rdx, [rbp+40h+var_78]
0x1800ac310  mov     rax, [rax+30h]
0x1800ac314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac319  mov     edi, eax
0x1800ac31b  mov     [rsp+140h+var_100], eax
0x1800ac31f  test    eax, eax
0x1800ac321  jns     short loc_1800AC32D
0x1800ac323  mov     edx, 82Fh
0x1800ac328  jmp     loc_1800AC29B
0x1800ac32d  mov     eax, cs:dword_180175000
0x1800ac333  mov     rbx, [rsp+140h+var_C8]
0x1800ac338  cmp     eax, 5
0x1800ac33b  jbe     loc_1800AC3EC
0x1800ac341  mov     rdx, 400000000000h
0x1800ac34b  lea     rcx, dword_180175000
0x1800ac352  call    _tlgKeywordOn
0x1800ac357  test    al, al
0x1800ac359  jz      loc_1800AC3EC
0x1800ac35f  xor     edx, edx; bool
0x1800ac361  mov     rcx, [r15+10h]; this
0x1800ac365  call    ?GetCallerPackageFamilyName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAPEAUHSTRING__@@_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(bool)
0x1800ac36a  mov     rcx, rax; string
0x1800ac36d  xor     edx, edx; length
0x1800ac36f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ac375  mov     [rbp+40h+var_70], rax
0x1800ac379  xor     edx, edx; length
0x1800ac37b  mov     rcx, rbx; string
0x1800ac37e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ac384  mov     [rbp+40h+var_90], rax
0x1800ac388  xor     edx, edx; length
0x1800ac38a  mov     rcx, [rsp+140h+string]; string
0x1800ac38f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ac395  mov     [rbp+40h+var_88], rax
0x1800ac399  mov     rcx, [rsp+140h+var_E8]; string
0x1800ac39e  call    cs:__imp_WindowsIsStringEmpty
0x1800ac3a4  test    eax, eax
0x1800ac3a6  jnz     short loc_1800AC3B8
0x1800ac3a8  xor     edx, edx; length
0x1800ac3aa  mov     rcx, [rsp+140h+var_E8]; string
0x1800ac3af  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ac3b5  mov     rsi, rax
0x1800ac3b8  mov     qword ptr [rbp+40h+var_80], rsi
0x1800ac3bc  lea     rax, [rbp+40h+var_70]
0x1800ac3c0  mov     [rsp+140h+var_108], rax
0x1800ac3c5  lea     rax, [rbp+40h+var_90]
0x1800ac3c9  mov     [rsp+140h+var_110], rax
0x1800ac3ce  lea     rax, [rbp+40h+var_88]
0x1800ac3d2  mov     [rsp+140h+var_118], rax
0x1800ac3d7  lea     rax, [rbp+40h+var_80]
0x1800ac3db  mov     qword ptr [rsp+140h+var_120], rax
0x1800ac3e0  lea     rdx, byte_1801490C5
0x1800ac3e7  call    ??$Write@U?$_tlgWrapSz@G@@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800ac3ec  mov     [r12], r13
0x1800ac3f0  mov     [rbp+40h+var_C0], r13
0x1800ac3f4  lea     rcx, [rbp+40h+var_C0]
0x1800ac3f8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac3fd  mov     rcx, [r15+10h]; this
0x1800ac401  mov     rsi, [rcx+38h]
0x1800ac405  mov     r14, [r15+18h]
0x1800ac409  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800ac40e  mov     dil, al
0x1800ac411  xor     edx, edx; bool
0x1800ac413  mov     rcx, [r15+10h]; this
0x1800ac417  call    ?GetCallerPackageFamilyName@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBAPEAUHSTRING__@@_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::GetCallerPackageFamilyName(bool)
0x1800ac41c  lea     rcx, [rbp+40h+var_C0]
0x1800ac420  mov     [rsp+140h+var_108], rcx
0x1800ac425  mov     [rsp+140h+var_110], rsi
0x1800ac42a  mov     [rsp+140h+var_118], r14
0x1800ac42f  mov     byte ptr [rsp+140h+var_120], dil; int
0x1800ac434  mov     r8, rax
0x1800ac437  mov     rdx, qword ptr [rsp+140h+var_F8]
0x1800ac43c  mov     rcx, [r15]
0x1800ac43f  call    ?ConstructWebProviderTokenRequest@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebTokenRequest@Core@Web@235@PEAU?$IVector@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@PEAUHSTRING__@@_N3_K2PEAPEAUIWebProviderTokenRequest@Provider@8235@@Z; Windows::Internal::Security::Authentication::TokenBroker::ConstructWebProviderTokenRequest(Windows::Security::Authentication::Web::Core::IWebTokenRequest *,Windows::Foundation::Collections::IVector<Windows::Security::Credentials::WebAccount *> *,HSTRING__ *,bool,bool,unsigned __int64,HSTRING__ *,Windows::Security::Authentication::Web::Provider::IWebProviderTokenRequest * *)
0x1800ac444  mov     edi, eax
0x1800ac446  mov     [rsp+140h+var_100], eax
0x1800ac44a  test    eax, eax
0x1800ac44c  jns     short loc_1800AC4A9
0x1800ac44e  mov     rcx, [rbp+48h]; this
0x1800ac452  mov     r9d, eax; char *
0x1800ac455  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ac45c  mov     edx, 847h; void *
0x1800ac461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac466  nop
0x1800ac467  lea     rcx, [rbp+40h+var_C0]
0x1800ac46b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac470  nop
0x1800ac471  lea     rcx, [rsp+140h+var_E0]
0x1800ac476  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac47b  nop
0x1800ac47c  mov     rcx, [rsp+140h+string]; string
0x1800ac481  test    rcx, rcx
0x1800ac484  jz      short loc_1800AC48D
0x1800ac486  call    cs:__imp_WindowsDeleteString
0x1800ac48c  nop
0x1800ac48d  lea     rcx, [rsp+140h+var_D8]
0x1800ac492  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ac497  nop
  ... truncated ...
```
