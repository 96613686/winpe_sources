# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountAsync(Windows::Security::Credentials::IWebAccountProvider *,Windows::Foundation::IAsyncAction * *)

- ea: `0x1800bd970`
- end: `0x1800bdeec`
- name: `?InvokePluginToAddAccountAsync@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUIAsyncAction@Foundation@6@@Z`
- size: `1404`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, struct Windows::Security::Credentials::IWebAccountProvider *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `27`
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
- `0x180040980`
- `0x1800455a4`
- `0x180056174`
- `0x18005f394`
- `0x18008169c`
- `0x18008e690`
- `0x1800b6818`
- `0x1800b7514`
- `0x1800b94c8`
- `0x1800ba3ec`
- `0x1800bd970`
- `0x1800c3ea0`
- `0x1800e5718`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bdc10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bdc10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdc7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdd0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bde16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bde85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdc7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bdd0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bde16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bde85`

## string_xrefs

- `0x1800bda08`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bda4e`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bdab2`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bdb1a`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bdb8d`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bdc5e`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bdcf0`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bdde1`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bd9de`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountAsync`
- `0x1800bd99b`: `TokenBrokerInternalInvokePluginToAddAccount`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountAsync(
        unsigned __int64 this,
        struct Windows::Security::Credentials::IWebAccountProvider *a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  struct IUnknown *v6; // rsi
  __int64 v7; // rcx
  __int64 v9; // rdx
  Windows::Internal::Security::Authentication::Web::CallerContext *v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  const struct _tlgProvider_t *v14; // rbx
  int v15; // r9d
  HWND *v16; // rdx
  HWND *v17; // r8
  int ClientWindowHandle; // eax
  int v19; // ebx
  __int64 v20; // rax
  __int64 v21; // r8
  int v22; // [rsp+20h] [rbp-378h]
  int v23; // [rsp+20h] [rbp-378h]
  HSTRING string; // [rsp+30h] [rbp-368h] BYREF
  int v25[2]; // [rsp+38h] [rbp-360h] BYREF
  Windows::Internal::Security::Authentication::Web::CallerContext *v26; // [rsp+40h] [rbp-358h] BYREF
  std::_Ref_count_base *v27; // [rsp+48h] [rbp-350h]
  _BYTE v28[8]; // [rsp+50h] [rbp-348h] BYREF
  __int64 v29; // [rsp+58h] [rbp-340h]
  struct IUnknown v30; // [rsp+60h] [rbp-338h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-330h] BYREF
  char v32; // [rsp+70h] [rbp-328h]
  int v33; // [rsp+78h] [rbp-320h] BYREF
  __int64 v34; // [rsp+7Ch] [rbp-31Ch]
  void *v35[3]; // [rsp+88h] [rbp-310h] BYREF
  _QWORD v36[34]; // [rsp+A0h] [rbp-2F8h] BYREF
  __int64 v37; // [rsp+1B0h] [rbp-1E8h]
  _BYTE v38[384]; // [rsp+1F0h] [rbp-1A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+398h] [rbp+0h]

  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v36,
    "TokenBrokerInternalInvokePluginToAddAccount");
  v36[0] = &TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::`vftable';
  TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::StartActivity((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
  v6 = (struct IUnknown *)(this & -(__int64)(this != 40));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v7,
    (__int64)v28,
    v6,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToAddAccountAsync",
    0);
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x357,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v22);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x358,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v22);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
    return 2147942487LL;
  }
  v9 = v29;
  v29 = 0;
  std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
    &v26,
    v9);
  v10 = v26;
  if ( !v26 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35B,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v22);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v26 )
  {
    v11 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
            v26,
            (struct IUnknown *)(this & -(__int64)(this != 40)),
            0,
            0);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v11,
        v22);
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
LABEL_13:
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
      TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
      return v12;
    }
    v10 = v26;
  }
  TokenHandle = 0;
  v32 = 0;
  v13 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
          &TokenHandle,
          *((_QWORD *)v10 + 2));
  v12 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x362,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v13,
      v22);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    goto LABEL_13;
  }
  string = 0;
  if ( !(*(unsigned int (__fastcall **)(struct Windows::Security::Credentials::IWebAccountProvider *, HSTRING *))(*(_QWORD *)a2 + 48LL))(
          a2,
          &string) )
  {
    v14 = TbLogProvider::Provider();
    if ( *(_DWORD *)v14 > 5u )
    {
      *(_QWORD *)v25 = WindowsGetStringRawBuffer(string, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v14,
        (unsigned int)byte_18014B6AB,
        v37 + 8,
        v15,
        (__int64)v25);
    }
  }
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(v26) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070005LL,
      v22);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
    return 2147942405LL;
  }
  v30.lpVtbl = 0;
  if ( (int)CallerIdentity::GetCoreWindowHandleForCurrentThread((CallerIdentity *)&v30, v16) < 0 )
  {
    ClientWindowHandle = Windows::Internal::Security::Authentication::TokenBroker::GetClientWindowHandle(
                           (Windows::Internal::Security::Authentication::TokenBroker *)v6,
                           &v30,
                           v17);
    v19 = ClientWindowHandle;
    if ( ClientWindowHandle < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x374,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)ClientWindowHandle,
        v22);
      if ( string )
        WindowsDeleteString(string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      if ( v27 )
        std::_Ref_count_base::_Decref(v27);
LABEL_34:
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
      TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
      return (unsigned int)v19;
    }
  }
  *(_QWORD *)v25 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v25);
  Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(v35);
  v20 = lambda_0fb36ac665e45584ed4f2d7fa0a335e2_::_lambda_0fb36ac665e45584ed4f2d7fa0a335e2__0(
          (unsigned int)v38,
          (unsigned int)v35,
          (unsigned int)v36,
          (unsigned int)&v30,
          (__int64)v25,
          (__int64)&v26);
  v33 = 3;
  v34 = 128;
  v19 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__Windows::Internal::Security::Authentication::Web::AddAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_0fb36ac665e45584ed4f2d7fa0a335e2___(
          &v33,
          a3,
          v21,
          v20);
  lambda_0fb36ac665e45584ed4f2d7fa0a335e2_::__lambda_0fb36ac665e45584ed4f2d7fa0a335e2_((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v38);
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v19,
      v23);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    goto LABEL_34;
  }
  wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v36);
  Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v35);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v25);
  if ( string )
    WindowsDeleteString(string);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
  TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount((TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount *)v36);
  return 0;
}

```

## disassembly

```asm
0x1800bd970  mov     [rsp+arg_18], rbx
0x1800bd975  push    rsi
0x1800bd976  push    rdi
0x1800bd977  push    r14
0x1800bd979  sub     rsp, 380h
0x1800bd980  mov     rax, cs:__security_cookie
0x1800bd987  xor     rax, rsp
0x1800bd98a  mov     [rsp+398h+var_28], rax
0x1800bd992  mov     r14, r8
0x1800bd995  mov     rdi, rdx
0x1800bd998  mov     rbx, rcx
0x1800bd99b  lea     rdx, aTokenbrokerint_7; "TokenBrokerInternalInvokePluginToAddAcc"...
0x1800bd9a2  lea     rcx, [rsp+398h+var_2F8]
0x1800bd9aa  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800bd9af  lea     rax, ??_7TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::`vftable'
0x1800bd9b6  mov     [rsp+398h+var_2F8], rax
0x1800bd9be  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bd9c6  call    ?StartActivity@TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::StartActivity(void)
0x1800bd9cb  nop
0x1800bd9cc  lea     rax, [rbx-28h]
0x1800bd9d0  neg     rax
0x1800bd9d3  sbb     rsi, rsi
0x1800bd9d6  and     rsi, rbx
0x1800bd9d9  mov     byte ptr [rsp+398h+var_378], 0; int
0x1800bd9de  lea     r9, aWindowsInterna_65; "Windows::Internal::Security::Authentica"...
0x1800bd9e5  mov     r8, rsi
0x1800bd9e8  lea     rdx, [rsp+398h+var_348]
0x1800bd9ed  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800bd9f2  nop
0x1800bd9f3  test    r14, r14
0x1800bd9f6  jnz     short loc_1800BDA39
0x1800bd9f8  mov     rcx, [rsp+398h]; this
0x1800bda00  mov     ebx, 80070057h
0x1800bda05  mov     r9d, ebx; char *
0x1800bda08  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bda0f  mov     edx, 357h; void *
0x1800bda14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bda19  nop
0x1800bda1a  lea     rcx, [rsp+398h+var_348]; this
0x1800bda1f  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bda24  nop
0x1800bda25  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bda2d  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bda32  mov     eax, ebx
0x1800bda34  jmp     loc_1800BDEC7
0x1800bda39  test    rdi, rdi
0x1800bda3c  jnz     short loc_1800BDA7F
0x1800bda3e  mov     rcx, [rsp+398h]; this
0x1800bda46  mov     ebx, 80070057h
0x1800bda4b  mov     r9d, ebx; char *
0x1800bda4e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bda55  mov     edx, 358h; void *
0x1800bda5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bda5f  nop
0x1800bda60  lea     rcx, [rsp+398h+var_348]; this
0x1800bda65  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bda6a  nop
0x1800bda6b  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bda73  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bda78  mov     eax, ebx
0x1800bda7a  jmp     loc_1800BDEC7
0x1800bda7f  mov     rdx, [rsp+398h+var_340]
0x1800bda84  mov     [rsp+398h+var_340], 0
0x1800bda8d  lea     rcx, [rsp+398h+var_358]
0x1800bda92  call    ??$?0VCallerContext@Web@Authentication@Security@Internal@Windows@@$0A@@?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@PEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800bda97  nop
0x1800bda98  mov     rax, [rsp+398h+var_358]
0x1800bda9d  test    rax, rax
0x1800bdaa0  jnz     short loc_1800BDAF3
0x1800bdaa2  mov     rcx, [rsp+398h]; this
0x1800bdaaa  mov     ebx, 8007000Eh
0x1800bdaaf  mov     r9d, ebx; char *
0x1800bdab2  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bdab9  mov     edx, 35Bh; void *
0x1800bdabe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdac3  nop
0x1800bdac4  mov     rcx, [rsp+398h+var_350]; this
0x1800bdac9  test    rcx, rcx
0x1800bdacc  jz      short loc_1800BDAD4
0x1800bdace  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdad3  nop
0x1800bdad4  lea     rcx, [rsp+398h+var_348]; this
0x1800bdad9  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bdade  nop
0x1800bdadf  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bdae7  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bdaec  mov     eax, ebx
0x1800bdaee  jmp     loc_1800BDEC7
0x1800bdaf3  cmp     byte ptr [rax], 0
0x1800bdaf6  jnz     short loc_1800BDB60
0x1800bdaf8  xor     r9d, r9d; bool
0x1800bdafb  xor     r8d, r8d; unsigned __int64
0x1800bdafe  mov     rdx, rsi; struct IUnknown *
0x1800bdb01  mov     rcx, rax; this
0x1800bdb04  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800bdb09  mov     ebx, eax
0x1800bdb0b  test    eax, eax
0x1800bdb0d  jns     short loc_1800BDB5B
0x1800bdb0f  mov     rcx, [rsp+398h]; this
0x1800bdb17  mov     r9d, eax; char *
0x1800bdb1a  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bdb21  mov     edx, 35Eh; void *
0x1800bdb26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdb2b  nop
0x1800bdb2c  mov     rcx, [rsp+398h+var_350]; this
0x1800bdb31  test    rcx, rcx
0x1800bdb34  jz      short loc_1800BDB3C
0x1800bdb36  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdb3b  nop
0x1800bdb3c  lea     rcx, [rsp+398h+var_348]; this
0x1800bdb41  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bdb46  nop
0x1800bdb47  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bdb4f  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bdb54  mov     eax, ebx
0x1800bdb56  jmp     loc_1800BDEC7
0x1800bdb5b  mov     rax, [rsp+398h+var_358]
0x1800bdb60  mov     [rsp+398h+TokenHandle], 0
0x1800bdb69  mov     [rsp+398h+var_328], 0
0x1800bdb6e  mov     rdx, [rax+10h]; unsigned __int64
0x1800bdb72  lea     rcx, [rsp+398h+TokenHandle]; TokenHandle
0x1800bdb77  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800bdb7c  mov     ebx, eax
0x1800bdb7e  test    eax, eax
0x1800bdb80  jns     short loc_1800BDBD9
0x1800bdb82  mov     rcx, [rsp+398h]; this
0x1800bdb8a  mov     r9d, eax; char *
0x1800bdb8d  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bdb94  mov     edx, 362h; void *
0x1800bdb99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdb9e  nop
0x1800bdb9f  lea     rcx, [rsp+398h+TokenHandle]; this
0x1800bdba4  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800bdba9  nop
0x1800bdbaa  mov     rcx, [rsp+398h+var_350]; this
0x1800bdbaf  test    rcx, rcx
0x1800bdbb2  jz      short loc_1800BDBBA
0x1800bdbb4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdbb9  nop
0x1800bdbba  lea     rcx, [rsp+398h+var_348]; this
0x1800bdbbf  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bdbc4  nop
0x1800bdbc5  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bdbcd  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bdbd2  mov     eax, ebx
0x1800bdbd4  jmp     loc_1800BDEC7
0x1800bdbd9  mov     [rsp+398h+string], 0
0x1800bdbe2  mov     rax, [rdi]
0x1800bdbe5  lea     rdx, [rsp+398h+string]
0x1800bdbea  mov     rcx, rdi
0x1800bdbed  mov     rax, [rax+30h]
0x1800bdbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdbf6  test    eax, eax
0x1800bdbf8  jnz     short loc_1800BDC40
0x1800bdbfa  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800bdbff  mov     rbx, rax
0x1800bdc02  mov     ecx, [rax]
0x1800bdc04  cmp     ecx, 5
0x1800bdc07  jbe     short loc_1800BDC40
0x1800bdc09  xor     edx, edx; length
0x1800bdc0b  mov     rcx, [rsp+398h+string]; string
0x1800bdc10  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bdc16  mov     qword ptr [rsp+398h+var_360], rax
0x1800bdc1b  mov     r8, [rsp+398h+var_1E8]
0x1800bdc23  add     r8, 8
0x1800bdc27  lea     rax, [rsp+398h+var_360]
0x1800bdc2c  mov     qword ptr [rsp+398h+var_378], rax; int
0x1800bdc31  lea     rdx, byte_18014B6AB
0x1800bdc38  mov     rcx, rbx
0x1800bdc3b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800bdc40  mov     rcx, [rsp+398h+var_358]; this
0x1800bdc45  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800bdc4a  test    al, al
0x1800bdc4c  jz      short loc_1800BDCBB
0x1800bdc4e  mov     rcx, [rsp+398h]; this
0x1800bdc56  mov     ebx, 80070005h
0x1800bdc5b  mov     r9d, ebx; char *
0x1800bdc5e  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bdc65  mov     edx, 36Eh; void *
0x1800bdc6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdc6f  nop
0x1800bdc70  mov     rcx, [rsp+398h+string]; string
0x1800bdc75  test    rcx, rcx
0x1800bdc78  jz      short loc_1800BDC81
0x1800bdc7a  call    cs:__imp_WindowsDeleteString
0x1800bdc80  nop
0x1800bdc81  lea     rcx, [rsp+398h+TokenHandle]; this
0x1800bdc86  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800bdc8b  nop
0x1800bdc8c  mov     rcx, [rsp+398h+var_350]; this
0x1800bdc91  test    rcx, rcx
0x1800bdc94  jz      short loc_1800BDC9C
0x1800bdc96  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdc9b  nop
0x1800bdc9c  lea     rcx, [rsp+398h+var_348]; this
0x1800bdca1  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bdca6  nop
0x1800bdca7  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bdcaf  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bdcb4  mov     eax, ebx
0x1800bdcb6  jmp     loc_1800BDEC7
0x1800bdcbb  mov     [rsp+398h+var_338.lpVtbl], 0
0x1800bdcc4  lea     rcx, [rsp+398h+var_338]; this
0x1800bdcc9  call    ?GetCoreWindowHandleForCurrentThread@CallerIdentity@@YAJPEAPEAUHWND__@@@Z; CallerIdentity::GetCoreWindowHandleForCurrentThread(HWND__ * *)
0x1800bdcce  test    eax, eax
0x1800bdcd0  jns     short loc_1800BDD4D
0x1800bdcd2  lea     rdx, [rsp+398h+var_338]; struct IUnknown *
0x1800bdcd7  mov     rcx, rsi; this
0x1800bdcda  call    ?GetClientWindowHandle@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHWND__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetClientWindowHandle(IUnknown *,HWND__ * *)
0x1800bdcdf  mov     ebx, eax
0x1800bdce1  test    eax, eax
0x1800bdce3  jns     short loc_1800BDD4D
0x1800bdce5  mov     rcx, [rsp+398h]; this
0x1800bdced  mov     r9d, eax; char *
0x1800bdcf0  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bdcf7  mov     edx, 374h; void *
0x1800bdcfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdd01  nop
0x1800bdd02  mov     rcx, [rsp+398h+string]; string
0x1800bdd07  test    rcx, rcx
0x1800bdd0a  jz      short loc_1800BDD13
0x1800bdd0c  call    cs:__imp_WindowsDeleteString
0x1800bdd12  nop
0x1800bdd13  lea     rcx, [rsp+398h+TokenHandle]; this
0x1800bdd18  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800bdd1d  nop
0x1800bdd1e  mov     rcx, [rsp+398h+var_350]; this
0x1800bdd23  test    rcx, rcx
0x1800bdd26  jz      short loc_1800BDD2E
0x1800bdd28  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdd2d  nop
0x1800bdd2e  lea     rcx, [rsp+398h+var_348]; this
0x1800bdd33  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bdd38  nop
0x1800bdd39  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bdd41  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bdd46  mov     eax, ebx
0x1800bdd48  jmp     loc_1800BDEC7
0x1800bdd4d  mov     qword ptr [rsp+398h+var_360], rdi
0x1800bdd52  lea     rcx, [rsp+398h+var_360]
0x1800bdd57  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800bdd5c  nop
0x1800bdd5d  lea     rcx, [rsp+398h+var_310]; TokenHandle
0x1800bdd65  call    ??0AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(void)
0x1800bdd6a  nop
0x1800bdd6b  lea     rax, [rsp+398h+var_358]
0x1800bdd70  mov     [rsp+398h+var_370], rax
0x1800bdd75  lea     rax, [rsp+398h+var_360]
0x1800bdd7a  mov     qword ptr [rsp+398h+var_378], rax; int
0x1800bdd7f  lea     r9, [rsp+398h+var_338]
0x1800bdd84  lea     r8, [rsp+398h+var_2F8]
0x1800bdd8c  lea     rdx, [rsp+398h+var_310]
0x1800bdd94  lea     rcx, [rsp+398h+var_1A8]
0x1800bdd9c  call    _lambda_0fb36ac665e45584ed4f2d7fa0a335e2____lambda_0fb36ac665e45584ed4f2d7fa0a335e2__0
0x1800bdda1  nop
0x1800bdda2  mov     [rsp+398h+var_320], 3
0x1800bddaa  mov     [rsp+398h+var_31C], 80h
0x1800bddb3  mov     r9, rax
0x1800bddb6  mov     rdx, r14
0x1800bddb9  lea     rcx, [rsp+398h+var_320]
0x1800bddbe  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__Windows__Internal__Security__Authentication__Web__AddAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_0fb36ac665e45584ed4f2d7fa0a335e2___
0x1800bddc3  mov     ebx, eax
0x1800bddc5  lea     rcx, [rsp+398h+var_1A8]; this
0x1800bddcd  call    _lambda_0fb36ac665e45584ed4f2d7fa0a335e2_____lambda_0fb36ac665e45584ed4f2d7fa0a335e2_
0x1800bddd2  test    ebx, ebx
0x1800bddd4  jns     short loc_1800BDE54
0x1800bddd6  mov     rcx, [rsp+398h]; this
0x1800bddde  mov     r9d, ebx; char *
0x1800bdde1  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bdde8  mov     edx, 38Eh; void *
0x1800bdded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bddf2  nop
0x1800bddf3  lea     rcx, [rsp+398h+var_310]; this
0x1800bddfb  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800bde00  nop
0x1800bde01  lea     rcx, [rsp+398h+var_360]
0x1800bde06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bde0b  nop
0x1800bde0c  mov     rcx, [rsp+398h+string]; string
0x1800bde11  test    rcx, rcx
0x1800bde14  jz      short loc_1800BDE1D
0x1800bde16  call    cs:__imp_WindowsDeleteString
0x1800bde1c  nop
0x1800bde1d  lea     rcx, [rsp+398h+TokenHandle]; this
0x1800bde22  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800bde27  nop
0x1800bde28  mov     rcx, [rsp+398h+var_350]; this
0x1800bde2d  test    rcx, rcx
0x1800bde30  jz      short loc_1800BDE38
0x1800bde32  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bde37  nop
0x1800bde38  lea     rcx, [rsp+398h+var_348]; this
0x1800bde3d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bde42  nop
0x1800bde43  lea     rcx, [rsp+398h+var_2F8]; this
0x1800bde4b  call    ??1TokenBrokerInternalInvokePluginToAddAccount@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToAddAccount::~TokenBrokerInternalInvokePluginToAddAccount(void)
0x1800bde50  mov     eax, ebx
0x1800bde52  jmp     short loc_1800BDEC7
0x1800bde54  lea     rcx, [rsp+398h+var_2F8]
0x1800bde5c  call    ?IgnoreCurrentThread@?$ActivityBase@VWamClientLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
  ... truncated ...
```
