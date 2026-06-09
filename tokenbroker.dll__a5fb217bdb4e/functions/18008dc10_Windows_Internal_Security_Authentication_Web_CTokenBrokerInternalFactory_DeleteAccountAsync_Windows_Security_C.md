# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::DeleteAccountAsync(Windows::Security::Credentials::IWebAccount *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18008dc10`
- end: `0x18008e252`
- name: `?DeleteAccountAsync@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebAccount@Credentials@46@PEAPEAUIAsyncAction@Foundation@6@@Z`
- size: `1602`
- prototype: `__int64 __fastcall(unsigned __int64 this, struct Windows::Security::Credentials::IWebAccount *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x18000bd70`
- `0x180010a70`
- `0x18001e700`
- `0x180020c60`
- `0x180021750`
- `0x180023a80`
- `0x180024000`
- `0x180024118`
- `0x18002ea84`
- `0x18002fbf0`
- `0x1800372d0`
- `0x180056174`
- `0x180057440`
- `0x18005f394`
- `0x18008dc10`
- `0x18008e258`
- `0x18008e690`
- `0x1800b68e0`
- `0x1800b7f68`
- `0x1800b96b0`
- `0x1800c3c40`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008df7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dfc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e04e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e1e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008df7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008dfc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e04e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e166`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e1e0`

## string_xrefs

- `0x18008dca8`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008dcee`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008dd46`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008ddaa`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008de14`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008de87`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008df0e`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008dfac`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008e032`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008e131`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x18008dc7e`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::DeleteAccountAsync`
- `0x18008dc3b`: `TokenBrokerInternalDeleteAccount`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::DeleteAccountAsync(
        unsigned __int64 this,
        struct Windows::Security::Credentials::IWebAccount *a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  struct IUnknown *v6; // rdi
  __int64 v7; // rcx
  unsigned __int64 *v8; // r8
  int UserContextFromWebAccount; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  Windows::Internal::Security::Authentication::Web::CallerContext *v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  __int64 (__fastcall *v17)(struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  int v18; // eax
  int v19; // ebx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // rax
  __int64 v24; // r8
  int v25; // [rsp+20h] [rbp-378h]
  int v26; // [rsp+20h] [rbp-378h]
  __int64 v27; // [rsp+30h] [rbp-368h] BYREF
  HSTRING string; // [rsp+38h] [rbp-360h] BYREF
  _BYTE v29[8]; // [rsp+40h] [rbp-358h] BYREF
  __int64 v30; // [rsp+48h] [rbp-350h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v31; // [rsp+50h] [rbp-348h] BYREF
  std::_Ref_count_base *v32; // [rsp+58h] [rbp-340h]
  struct Windows::Security::Credentials::IWebAccount *v33; // [rsp+60h] [rbp-338h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-330h] BYREF
  char v35; // [rsp+70h] [rbp-328h]
  unsigned __int64 v36; // [rsp+78h] [rbp-320h] BYREF
  int v37; // [rsp+80h] [rbp-318h] BYREF
  __int64 v38; // [rsp+84h] [rbp-314h]
  void *v39[2]; // [rsp+90h] [rbp-308h] BYREF
  _QWORD v40[42]; // [rsp+A0h] [rbp-2F8h] BYREF
  _BYTE v41[384]; // [rsp+1F0h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v40,
    "TokenBrokerInternalDeleteAccount");
  v40[0] = &TbLogProvider::TokenBrokerInternalDeleteAccount::`vftable';
  TbLogProvider::TokenBrokerInternalDeleteAccount::StartActivity((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
  v6 = (struct IUnknown *)(this & -(__int64)(this != 40));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v7,
    (__int64)v29,
    v6,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::DeleteAccountAsync",
    0);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31C,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
    return 2147942487LL;
  }
  v36 = 0;
  UserContextFromWebAccount = Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromWebAccount(
                                a2,
                                (struct Windows::Security::Credentials::IWebAccount *)&v36,
                                v8);
  v11 = UserContextFromWebAccount;
  if ( UserContextFromWebAccount < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)UserContextFromWebAccount,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
    return v11;
  }
  v12 = v30;
  v30 = 0;
  std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
    &v31,
    v12);
  v13 = v31;
  if ( !v31 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x322,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v25);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v31 )
  {
    v14 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v31, v6, v36, 0);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x325,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v14,
        v25);
      if ( v32 )
        std::_Ref_count_base::_Decref(v32);
LABEL_15:
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
      TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
      return v15;
    }
    v13 = v31;
  }
  TokenHandle = 0;
  v35 = 0;
  v16 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
          &TokenHandle,
          *((_QWORD *)v13 + 2));
  v15 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x329,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v16,
      v25);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    goto LABEL_15;
  }
  v27 = 0;
  v17 = *(__int64 (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v18 = v17(a2, &v27);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v18,
      v25);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
LABEL_42:
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
    return (unsigned int)v19;
  }
  string = 0;
  v20 = v27;
  v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v27 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v22 = v21(v20, &string);
  v19 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v22,
      v25);
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    goto LABEL_42;
  }
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(v31) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x331,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070005LL,
      v25);
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
    return 2147942405LL;
  }
  else
  {
    v33 = a2;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v33);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(v39);
    v23 = lambda_b97ff56844d4ec83de67894a2ecc0a7c_::_lambda_b97ff56844d4ec83de67894a2ecc0a7c__0(
            (unsigned int)v41,
            (unsigned int)v39,
            (unsigned int)v40,
            (unsigned int)&v33,
            (__int64)&v31);
    v37 = 3;
    v38 = 128;
    v19 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__Windows::Internal::Security::Authentication::Web::DeleteAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_b97ff56844d4ec83de67894a2ecc0a7c___(
            &v37,
            a3,
            v24,
            v23);
    lambda_b97ff56844d4ec83de67894a2ecc0a7c_::__lambda_b97ff56844d4ec83de67894a2ecc0a7c_((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v41);
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x348,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v19,
        v26);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v39);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      if ( string )
        WindowsDeleteString(string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      if ( v32 )
        std::_Ref_count_base::_Decref(v32);
      goto LABEL_42;
    }
    wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v40);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    if ( string )
      WindowsDeleteString(string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v29);
    TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount((TbLogProvider::TokenBrokerInternalDeleteAccount *)v40);
    return 0;
  }
}

```

## disassembly

```asm
0x18008dc10  mov     [rsp+arg_18], rbx
0x18008dc15  push    rsi
0x18008dc16  push    rdi
0x18008dc17  push    r14
0x18008dc19  sub     rsp, 380h
0x18008dc20  mov     rax, cs:__security_cookie
0x18008dc27  xor     rax, rsp
0x18008dc2a  mov     [rsp+398h+var_28], rax
0x18008dc32  mov     r14, r8
0x18008dc35  mov     rsi, rdx
0x18008dc38  mov     rbx, rcx
0x18008dc3b  lea     rdx, aTokenbrokerint_36; "TokenBrokerInternalDeleteAccount"
0x18008dc42  lea     rcx, [rsp+398h+var_2F8]
0x18008dc4a  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18008dc4f  lea     rax, ??_7TokenBrokerInternalDeleteAccount@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalDeleteAccount::`vftable'
0x18008dc56  mov     [rsp+398h+var_2F8], rax
0x18008dc5e  lea     rcx, [rsp+398h+var_2F8]; this
0x18008dc66  call    ?StartActivity@TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalDeleteAccount::StartActivity(void)
0x18008dc6b  nop
0x18008dc6c  lea     rax, [rbx-28h]
0x18008dc70  neg     rax
0x18008dc73  sbb     rdi, rdi
0x18008dc76  and     rdi, rbx
0x18008dc79  mov     byte ptr [rsp+398h+var_378], 0; int
0x18008dc7e  lea     r9, aWindowsInterna_26; "Windows::Internal::Security::Authentica"...
0x18008dc85  mov     r8, rdi
0x18008dc88  lea     rdx, [rsp+398h+var_358]
0x18008dc8d  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x18008dc92  nop
0x18008dc93  test    r14, r14
0x18008dc96  jnz     short loc_18008DCD9
0x18008dc98  mov     rcx, [rsp+398h]; this
0x18008dca0  mov     ebx, 80070057h
0x18008dca5  mov     r9d, ebx; char *
0x18008dca8  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008dcaf  mov     edx, 31Bh; void *
0x18008dcb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dcb9  nop
0x18008dcba  lea     rcx, [rsp+398h+var_358]; this
0x18008dcbf  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008dcc4  nop
0x18008dcc5  lea     rcx, [rsp+398h+var_2F8]; this
0x18008dccd  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008dcd2  mov     eax, ebx
0x18008dcd4  jmp     loc_18008E22D
0x18008dcd9  test    rsi, rsi
0x18008dcdc  jnz     short loc_18008DD1F
0x18008dcde  mov     rcx, [rsp+398h]; this
0x18008dce6  mov     ebx, 80070057h
0x18008dceb  mov     r9d, ebx; char *
0x18008dcee  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008dcf5  mov     edx, 31Ch; void *
0x18008dcfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dcff  nop
0x18008dd00  lea     rcx, [rsp+398h+var_358]; this
0x18008dd05  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008dd0a  nop
0x18008dd0b  lea     rcx, [rsp+398h+var_2F8]; this
0x18008dd13  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008dd18  mov     eax, ebx
0x18008dd1a  jmp     loc_18008E22D
0x18008dd1f  mov     [rsp+398h+var_320], 0
0x18008dd28  lea     rdx, [rsp+398h+var_320]; struct Windows::Security::Credentials::IWebAccount *
0x18008dd2d  mov     rcx, rsi; this
0x18008dd30  call    ?GetUserContextFromWebAccount@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIWebAccount@Credentials@35@AEA_K@Z; Windows::Internal::Security::Authentication::TokenBroker::GetUserContextFromWebAccount(Windows::Security::Credentials::IWebAccount *,unsigned __int64 &)
0x18008dd35  mov     ebx, eax
0x18008dd37  test    eax, eax
0x18008dd39  jns     short loc_18008DD77
0x18008dd3b  mov     rcx, [rsp+398h]; this
0x18008dd43  mov     r9d, eax; char *
0x18008dd46  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008dd4d  mov     edx, 31Fh; void *
0x18008dd52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dd57  nop
0x18008dd58  lea     rcx, [rsp+398h+var_358]; this
0x18008dd5d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008dd62  nop
0x18008dd63  lea     rcx, [rsp+398h+var_2F8]; this
0x18008dd6b  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008dd70  mov     eax, ebx
0x18008dd72  jmp     loc_18008E22D
0x18008dd77  mov     rdx, [rsp+398h+var_350]
0x18008dd7c  mov     [rsp+398h+var_350], 0
0x18008dd85  lea     rcx, [rsp+398h+var_348]
0x18008dd8a  call    ??$?0VCallerContext@Web@Authentication@Security@Internal@Windows@@$0A@@?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@PEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x18008dd8f  nop
0x18008dd90  mov     rax, [rsp+398h+var_348]
0x18008dd95  test    rax, rax
0x18008dd98  jnz     short loc_18008DDEB
0x18008dd9a  mov     rcx, [rsp+398h]; this
0x18008dda2  mov     ebx, 8007000Eh
0x18008dda7  mov     r9d, ebx; char *
0x18008ddaa  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008ddb1  mov     edx, 322h; void *
0x18008ddb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ddbb  nop
0x18008ddbc  mov     rcx, [rsp+398h+var_340]; this
0x18008ddc1  test    rcx, rcx
0x18008ddc4  jz      short loc_18008DDCC
0x18008ddc6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008ddcb  nop
0x18008ddcc  lea     rcx, [rsp+398h+var_358]; this
0x18008ddd1  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008ddd6  nop
0x18008ddd7  lea     rcx, [rsp+398h+var_2F8]; this
0x18008dddf  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008dde4  mov     eax, ebx
0x18008dde6  jmp     loc_18008E22D
0x18008ddeb  cmp     byte ptr [rax], 0
0x18008ddee  jnz     short loc_18008DE5A
0x18008ddf0  xor     r9d, r9d; bool
0x18008ddf3  mov     r8, [rsp+398h+var_320]; unsigned __int64
0x18008ddf8  mov     rdx, rdi; struct IUnknown *
0x18008ddfb  mov     rcx, rax; this
0x18008ddfe  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x18008de03  mov     ebx, eax
0x18008de05  test    eax, eax
0x18008de07  jns     short loc_18008DE55
0x18008de09  mov     rcx, [rsp+398h]; this
0x18008de11  mov     r9d, eax; char *
0x18008de14  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008de1b  mov     edx, 325h; void *
0x18008de20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008de25  nop
0x18008de26  mov     rcx, [rsp+398h+var_340]; this
0x18008de2b  test    rcx, rcx
0x18008de2e  jz      short loc_18008DE36
0x18008de30  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008de35  nop
0x18008de36  lea     rcx, [rsp+398h+var_358]; this
0x18008de3b  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008de40  nop
0x18008de41  lea     rcx, [rsp+398h+var_2F8]; this
0x18008de49  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008de4e  mov     eax, ebx
0x18008de50  jmp     loc_18008E22D
0x18008de55  mov     rax, [rsp+398h+var_348]
0x18008de5a  mov     [rsp+398h+TokenHandle], 0
0x18008de63  mov     [rsp+398h+var_328], 0
0x18008de68  mov     rdx, [rax+10h]; unsigned __int64
0x18008de6c  lea     rcx, [rsp+398h+TokenHandle]; TokenHandle
0x18008de71  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x18008de76  mov     ebx, eax
0x18008de78  test    eax, eax
0x18008de7a  jns     short loc_18008DED3
0x18008de7c  mov     rcx, [rsp+398h]; this
0x18008de84  mov     r9d, eax; char *
0x18008de87  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008de8e  mov     edx, 329h; void *
0x18008de93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008de98  nop
0x18008de99  lea     rcx, [rsp+398h+TokenHandle]; this
0x18008de9e  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18008dea3  nop
0x18008dea4  mov     rcx, [rsp+398h+var_340]; this
0x18008dea9  test    rcx, rcx
0x18008deac  jz      short loc_18008DEB4
0x18008deae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008deb3  nop
0x18008deb4  lea     rcx, [rsp+398h+var_358]; this
0x18008deb9  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008debe  nop
0x18008debf  lea     rcx, [rsp+398h+var_2F8]; this
0x18008dec7  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008decc  mov     eax, ebx
0x18008dece  jmp     loc_18008E22D
0x18008ded3  mov     [rsp+398h+var_368], 0
0x18008dedc  mov     rax, [rsi]
0x18008dedf  mov     rbx, [rax+30h]
0x18008dee3  lea     rcx, [rsp+398h+var_368]
0x18008dee8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008deed  lea     rdx, [rsp+398h+var_368]
0x18008def2  mov     rcx, rsi
0x18008def5  mov     rax, rbx
0x18008def8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008defd  mov     ebx, eax
0x18008deff  test    eax, eax
0x18008df01  jns     short loc_18008DF65
0x18008df03  mov     rcx, [rsp+398h]; this
0x18008df0b  mov     r9d, eax; char *
0x18008df0e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008df15  mov     edx, 32Dh; void *
0x18008df1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008df1f  nop
0x18008df20  lea     rcx, [rsp+398h+var_368]
0x18008df25  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008df2a  nop
0x18008df2b  lea     rcx, [rsp+398h+TokenHandle]; this
0x18008df30  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18008df35  nop
0x18008df36  mov     rcx, [rsp+398h+var_340]; this
0x18008df3b  test    rcx, rcx
0x18008df3e  jz      short loc_18008DF46
0x18008df40  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008df45  nop
0x18008df46  lea     rcx, [rsp+398h+var_358]; this
0x18008df4b  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008df50  nop
0x18008df51  lea     rcx, [rsp+398h+var_2F8]; this
0x18008df59  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008df5e  mov     eax, ebx
0x18008df60  jmp     loc_18008E22D
0x18008df65  mov     [rsp+398h+string], 0
0x18008df6e  mov     rdi, [rsp+398h+var_368]
0x18008df73  mov     rax, [rdi]
0x18008df76  mov     rbx, [rax+30h]
0x18008df7a  xor     ecx, ecx; string
0x18008df7c  call    cs:__imp_WindowsDeleteString
0x18008df82  mov     [rsp+398h+string], 0
0x18008df8b  lea     rdx, [rsp+398h+string]
0x18008df90  mov     rcx, rdi
0x18008df93  mov     rax, rbx
0x18008df96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008df9b  mov     ebx, eax
0x18008df9d  test    eax, eax
0x18008df9f  jns     short loc_18008E014
0x18008dfa1  mov     rcx, [rsp+398h]; this
0x18008dfa9  mov     r9d, eax; char *
0x18008dfac  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008dfb3  mov     edx, 32Fh; void *
0x18008dfb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dfbd  nop
0x18008dfbe  mov     rcx, [rsp+398h+string]; string
0x18008dfc3  test    rcx, rcx
0x18008dfc6  jz      short loc_18008DFCF
0x18008dfc8  call    cs:__imp_WindowsDeleteString
0x18008dfce  nop
0x18008dfcf  lea     rcx, [rsp+398h+var_368]
0x18008dfd4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008dfd9  nop
0x18008dfda  lea     rcx, [rsp+398h+TokenHandle]; this
0x18008dfdf  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18008dfe4  nop
0x18008dfe5  mov     rcx, [rsp+398h+var_340]; this
0x18008dfea  test    rcx, rcx
0x18008dfed  jz      short loc_18008DFF5
0x18008dfef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008dff4  nop
0x18008dff5  lea     rcx, [rsp+398h+var_358]; this
0x18008dffa  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008dfff  nop
0x18008e000  lea     rcx, [rsp+398h+var_2F8]; this
0x18008e008  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008e00d  mov     eax, ebx
0x18008e00f  jmp     loc_18008E22D
0x18008e014  mov     rcx, [rsp+398h+var_348]; this
0x18008e019  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x18008e01e  test    al, al
0x18008e020  jz      short loc_18008E09A
0x18008e022  mov     rcx, [rsp+398h]; this
0x18008e02a  mov     ebx, 80070005h
0x18008e02f  mov     r9d, ebx; char *
0x18008e032  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18008e039  mov     edx, 331h; void *
0x18008e03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e043  nop
0x18008e044  mov     rcx, [rsp+398h+string]; string
0x18008e049  test    rcx, rcx
0x18008e04c  jz      short loc_18008E055
0x18008e04e  call    cs:__imp_WindowsDeleteString
0x18008e054  nop
0x18008e055  lea     rcx, [rsp+398h+var_368]
0x18008e05a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18008e05f  nop
0x18008e060  lea     rcx, [rsp+398h+TokenHandle]; this
0x18008e065  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x18008e06a  nop
0x18008e06b  mov     rcx, [rsp+398h+var_340]; this
0x18008e070  test    rcx, rcx
0x18008e073  jz      short loc_18008E07B
0x18008e075  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18008e07a  nop
0x18008e07b  lea     rcx, [rsp+398h+var_358]; this
0x18008e080  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18008e085  nop
0x18008e086  lea     rcx, [rsp+398h+var_2F8]; this
0x18008e08e  call    ??1TokenBrokerInternalDeleteAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalDeleteAccount::~TokenBrokerInternalDeleteAccount(void)
0x18008e093  mov     eax, ebx
0x18008e095  jmp     loc_18008E22D
0x18008e09a  mov     [rsp+398h+var_338], rsi
0x18008e09f  lea     rcx, [rsp+398h+var_338]
0x18008e0a4  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18008e0a9  nop
0x18008e0aa  lea     rcx, [rsp+398h+var_308]; TokenHandle
0x18008e0b2  call    ??0AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(void)
0x18008e0b7  nop
0x18008e0b8  lea     rax, [rsp+398h+var_348]
0x18008e0bd  mov     qword ptr [rsp+398h+var_378], rax; int
0x18008e0c2  lea     r9, [rsp+398h+var_338]
0x18008e0c7  lea     r8, [rsp+398h+var_2F8]
0x18008e0cf  lea     rdx, [rsp+398h+var_308]
0x18008e0d7  lea     rcx, [rsp+398h+var_1A8]
0x18008e0df  call    _lambda_b97ff56844d4ec83de67894a2ecc0a7c____lambda_b97ff56844d4ec83de67894a2ecc0a7c__0
0x18008e0e4  nop
0x18008e0e5  mov     [rsp+398h+var_318], 3
0x18008e0f0  mov     [rsp+398h+var_314], 80h
0x18008e0fc  mov     r9, rax
0x18008e0ff  mov     rdx, r14
0x18008e102  lea     rcx, [rsp+398h+var_318]
0x18008e10a  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__Windows__Internal__Security__Authentication__Web__DeleteAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_b97ff56844d4ec83de67894a2ecc0a7c___
  ... truncated ...
```
