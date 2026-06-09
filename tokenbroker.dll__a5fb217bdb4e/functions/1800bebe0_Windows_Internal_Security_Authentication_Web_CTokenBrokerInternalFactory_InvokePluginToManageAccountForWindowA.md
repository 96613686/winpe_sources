# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountForWindowAsync(uint,Windows::Security::Credentials::IWebAccount *,Windows::Foundation::IAsyncAction * *)

- ea: `0x1800bebe0`
- end: `0x1800bf160`
- name: `?InvokePluginToManageAccountForWindowAsync@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJIPEAUIWebAccount@Credentials@46@PEAPEAUIAsyncAction@Foundation@6@@Z`
- size: `1408`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, unsigned int, struct Windows::Security::Credentials::IWebAccount *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `25`
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
- `0x18008e690`
- `0x1800b6948`
- `0x1800b7698`
- `0x1800b950c`
- `0x1800ba470`
- `0x1800bebe0`
- `0x1800c4068`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800beeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800beeed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bef62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf0fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bef62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf0fe`

## string_xrefs

- `0x1800bec80`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800becc6`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bed0b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bed6b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bedd3`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bee42`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bef3b`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bf044`: `onecore\ds\security\tokenbroker\broker\lib\manager.cpp`
- `0x1800bec56`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountForWindowAsync`
- `0x1800bec10`: `TokenBrokerInternalInvokePluginToManageAccountForWindow`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountForWindowAsync(
        unsigned __int64 this,
        int a2,
        struct Windows::Security::Credentials::IWebAccount *a3,
        struct Windows::Foundation::IAsyncAction **a4)
{
  struct IUnknown *v8; // rsi
  __int64 v9; // rcx
  __int64 v11; // rdx
  Windows::Internal::Security::Authentication::Web::CallerContext *v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int (__fastcall *v16)(struct Windows::Security::Credentials::IWebAccount *, __int64 *); // rbx
  const struct _tlgProvider_t *v17; // rbx
  int v18; // r9d
  __int64 v19; // rax
  __int64 v20; // r8
  int v21; // ebx
  int v22; // [rsp+20h] [rbp-388h]
  int v23; // [rsp+20h] [rbp-388h]
  int v24; // [rsp+30h] [rbp-378h] BYREF
  __int64 v25; // [rsp+38h] [rbp-370h] BYREF
  int v26[2]; // [rsp+40h] [rbp-368h] BYREF
  HSTRING string; // [rsp+48h] [rbp-360h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-358h] BYREF
  __int64 v29; // [rsp+58h] [rbp-350h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v30; // [rsp+60h] [rbp-348h] BYREF
  std::_Ref_count_base *v31; // [rsp+68h] [rbp-340h]
  void *TokenHandle; // [rsp+70h] [rbp-338h] BYREF
  char v33; // [rsp+78h] [rbp-330h]
  int v34; // [rsp+80h] [rbp-328h] BYREF
  __int64 v35; // [rsp+84h] [rbp-324h]
  void *v36[2]; // [rsp+90h] [rbp-318h] BYREF
  _QWORD v37[34]; // [rsp+A0h] [rbp-308h] BYREF
  __int64 v38; // [rsp+1B0h] [rbp-1F8h]
  _BYTE v39[384]; // [rsp+1F0h] [rbp-1B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+0h]

  v24 = a2;
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v37,
    "TokenBrokerInternalInvokePluginToManageAccountForWindow");
  v37[0] = &TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::`vftable';
  TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::StartActivity((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
  v8 = (struct IUnknown *)(this & -(__int64)(this != 48));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v9,
    (__int64)v28,
    v8,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::InvokePluginToManageAccountForWindowAsync",
    0);
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8BA,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v22);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8BB,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v22);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8BC,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070057LL,
      v22);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
    return 2147942487LL;
  }
  v11 = v29;
  v29 = 0;
  std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(
    &v30,
    v11);
  v12 = v30;
  if ( !v30 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8BF,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x8007000ELL,
      v22);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v30 )
  {
    v13 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v30, v8, 0, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C2,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v13,
        v22);
      if ( v31 )
        std::_Ref_count_base::_Decref(v31);
LABEL_15:
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
      TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
      return v14;
    }
    v12 = v30;
  }
  TokenHandle = 0;
  v33 = 0;
  v15 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(
          &TokenHandle,
          *((_QWORD *)v12 + 2));
  v14 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C6,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)(unsigned int)v15,
      v22);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    goto LABEL_15;
  }
  string = 0;
  v25 = 0;
  v16 = *(unsigned int (__fastcall **)(struct Windows::Security::Credentials::IWebAccount *, __int64 *))(*(_QWORD *)a3 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  if ( !v16(a3, &v25) && !(*(unsigned int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v25 + 48LL))(v25, &string) )
  {
    v17 = TbLogProvider::Provider();
    if ( *(_DWORD *)v17 > 5u )
    {
      *(_QWORD *)v26 = WindowsGetStringRawBuffer(string, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v17,
        (unsigned int)&word_18014E42E,
        v38 + 8,
        v18,
        (__int64)v26);
    }
  }
  if ( Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(v30) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8D5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
      (const char *)0x80070005LL,
      v22);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
    TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
    return 2147942405LL;
  }
  else
  {
    *(_QWORD *)v26 = a3;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v26);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(v36);
    v19 = lambda_3a9123f536a141223e3dc303f2a7bc00_::_lambda_3a9123f536a141223e3dc303f2a7bc00__0(
            (unsigned int)v39,
            (unsigned int)v36,
            (unsigned int)v37,
            (unsigned int)&v24,
            (__int64)v26,
            (__int64)&v30);
    v34 = 3;
    v35 = 128;
    v21 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__Windows::Internal::Security::Authentication::Web::ManageAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_3a9123f536a141223e3dc303f2a7bc00___(
            &v34,
            a4,
            v20,
            v19);
    lambda_3a9123f536a141223e3dc303f2a7bc00_::__lambda_3a9123f536a141223e3dc303f2a7bc00_((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v39);
    if ( v21 >= 0 )
    {
      wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v37);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      if ( string )
        WindowsDeleteString(string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      if ( v31 )
        std::_Ref_count_base::_Decref(v31);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
      TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8ED,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\manager.cpp",
        (const char *)(unsigned int)v21,
        v23);
      Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v26);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      if ( string )
        WindowsDeleteString(string);
      Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
      if ( v31 )
        std::_Ref_count_base::_Decref(v31);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v28);
      TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow((TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow *)v37);
      return (unsigned int)v21;
    }
  }
}

```

## disassembly

```asm
0x1800bebe0  push    rbx
0x1800bebe2  push    rsi
0x1800bebe3  push    rdi
0x1800bebe4  push    r14
0x1800bebe6  push    r15
0x1800bebe8  sub     rsp, 380h
0x1800bebef  mov     rax, cs:__security_cookie
0x1800bebf6  xor     rax, rsp
0x1800bebf9  mov     [rsp+3A8h+var_38], rax
0x1800bec01  mov     r15, r9
0x1800bec04  mov     rdi, r8
0x1800bec07  mov     ebx, edx
0x1800bec09  mov     r14, rcx
0x1800bec0c  mov     [rsp+3A8h+var_378], edx
0x1800bec10  lea     rdx, aTokenbrokerint_15; "TokenBrokerInternalInvokePluginToManage"...
0x1800bec17  lea     rcx, [rsp+3A8h+var_308]
0x1800bec1f  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800bec24  lea     rax, ??_7TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::`vftable'
0x1800bec2b  mov     [rsp+3A8h+var_308], rax
0x1800bec33  lea     rcx, [rsp+3A8h+var_308]; this
0x1800bec3b  call    ?StartActivity@TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::StartActivity(void)
0x1800bec40  nop
0x1800bec41  lea     rax, [r14-30h]
0x1800bec45  neg     rax
0x1800bec48  sbb     rsi, rsi
0x1800bec4b  and     rsi, r14
0x1800bec4e  xor     r14d, r14d
0x1800bec51  mov     byte ptr [rsp+3A8h+var_388], r14b; int
0x1800bec56  lea     r9, aWindowsInterna_74; "Windows::Internal::Security::Authentica"...
0x1800bec5d  mov     r8, rsi
0x1800bec60  lea     rdx, [rsp+3A8h+var_358]
0x1800bec65  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800bec6a  nop
0x1800bec6b  test    r15, r15
0x1800bec6e  jnz     short loc_1800BECB1
0x1800bec70  mov     rcx, [rsp+3A8h]; this
0x1800bec78  mov     ebx, 80070057h
0x1800bec7d  mov     r9d, ebx; char *
0x1800bec80  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bec87  mov     edx, 8BAh; void *
0x1800bec8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bec91  nop
0x1800bec92  lea     rcx, [rsp+3A8h+var_358]; this
0x1800bec97  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bec9c  nop
0x1800bec9d  lea     rcx, [rsp+3A8h+var_308]; this
0x1800beca5  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800becaa  mov     eax, ebx
0x1800becac  jmp     loc_1800BF140
0x1800becb1  test    rdi, rdi
0x1800becb4  jnz     short loc_1800BECF7
0x1800becb6  mov     rcx, [rsp+3A8h]; this
0x1800becbe  mov     ebx, 80070057h
0x1800becc3  mov     r9d, ebx; char *
0x1800becc6  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800beccd  mov     edx, 8BBh; void *
0x1800becd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800becd7  nop
0x1800becd8  lea     rcx, [rsp+3A8h+var_358]; this
0x1800becdd  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bece2  nop
0x1800bece3  lea     rcx, [rsp+3A8h+var_308]; this
0x1800beceb  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800becf0  mov     eax, ebx
0x1800becf2  jmp     loc_1800BF140
0x1800becf7  test    ebx, ebx
0x1800becf9  jnz     short loc_1800BED3C
0x1800becfb  mov     rcx, [rsp+3A8h]; this
0x1800bed03  mov     ebx, 80070057h
0x1800bed08  mov     r9d, ebx; char *
0x1800bed0b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bed12  mov     edx, 8BCh; void *
0x1800bed17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bed1c  nop
0x1800bed1d  lea     rcx, [rsp+3A8h+var_358]; this
0x1800bed22  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bed27  nop
0x1800bed28  lea     rcx, [rsp+3A8h+var_308]; this
0x1800bed30  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800bed35  mov     eax, ebx
0x1800bed37  jmp     loc_1800BF140
0x1800bed3c  mov     rdx, [rsp+3A8h+var_350]
0x1800bed41  mov     [rsp+3A8h+var_350], r14
0x1800bed46  lea     rcx, [rsp+3A8h+var_348]
0x1800bed4b  call    ??$?0VCallerContext@Web@Authentication@Security@Internal@Windows@@$0A@@?$shared_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@@std@@QEAA@PEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; std::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>::shared_ptr<Windows::Internal::Security::Authentication::Web::CallerContext>(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800bed50  nop
0x1800bed51  mov     rax, [rsp+3A8h+var_348]
0x1800bed56  test    rax, rax
0x1800bed59  jnz     short loc_1800BEDAC
0x1800bed5b  mov     rcx, [rsp+3A8h]; this
0x1800bed63  mov     ebx, 8007000Eh
0x1800bed68  mov     r9d, ebx; char *
0x1800bed6b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bed72  mov     edx, 8BFh; void *
0x1800bed77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bed7c  nop
0x1800bed7d  mov     rcx, [rsp+3A8h+var_340]; this
0x1800bed82  test    rcx, rcx
0x1800bed85  jz      short loc_1800BED8D
0x1800bed87  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bed8c  nop
0x1800bed8d  lea     rcx, [rsp+3A8h+var_358]; this
0x1800bed92  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bed97  nop
0x1800bed98  lea     rcx, [rsp+3A8h+var_308]; this
0x1800beda0  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800beda5  mov     eax, ebx
0x1800beda7  jmp     loc_1800BF140
0x1800bedac  cmp     [rax], r14b
0x1800bedaf  jnz     short loc_1800BEE19
0x1800bedb1  xor     r9d, r9d; bool
0x1800bedb4  xor     r8d, r8d; unsigned __int64
0x1800bedb7  mov     rdx, rsi; struct IUnknown *
0x1800bedba  mov     rcx, rax; this
0x1800bedbd  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800bedc2  mov     ebx, eax
0x1800bedc4  test    eax, eax
0x1800bedc6  jns     short loc_1800BEE14
0x1800bedc8  mov     rcx, [rsp+3A8h]; this
0x1800bedd0  mov     r9d, eax; char *
0x1800bedd3  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bedda  mov     edx, 8C2h; void *
0x1800beddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bede4  nop
0x1800bede5  mov     rcx, [rsp+3A8h+var_340]; this
0x1800bedea  test    rcx, rcx
0x1800beded  jz      short loc_1800BEDF5
0x1800bedef  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bedf4  nop
0x1800bedf5  lea     rcx, [rsp+3A8h+var_358]; this
0x1800bedfa  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bedff  nop
0x1800bee00  lea     rcx, [rsp+3A8h+var_308]; this
0x1800bee08  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800bee0d  mov     eax, ebx
0x1800bee0f  jmp     loc_1800BF140
0x1800bee14  mov     rax, [rsp+3A8h+var_348]
0x1800bee19  mov     [rsp+3A8h+TokenHandle], r14
0x1800bee1e  mov     [rsp+3A8h+var_330], r14b
0x1800bee23  mov     rdx, [rax+10h]; unsigned __int64
0x1800bee27  lea     rcx, [rsp+3A8h+TokenHandle]; TokenHandle
0x1800bee2c  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800bee31  mov     ebx, eax
0x1800bee33  test    eax, eax
0x1800bee35  jns     short loc_1800BEE8E
0x1800bee37  mov     rcx, [rsp+3A8h]; this
0x1800bee3f  mov     r9d, eax; char *
0x1800bee42  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bee49  mov     edx, 8C6h; void *
0x1800bee4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bee53  nop
0x1800bee54  lea     rcx, [rsp+3A8h+TokenHandle]; this
0x1800bee59  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800bee5e  nop
0x1800bee5f  mov     rcx, [rsp+3A8h+var_340]; this
0x1800bee64  test    rcx, rcx
0x1800bee67  jz      short loc_1800BEE6F
0x1800bee69  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bee6e  nop
0x1800bee6f  lea     rcx, [rsp+3A8h+var_358]; this
0x1800bee74  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bee79  nop
0x1800bee7a  lea     rcx, [rsp+3A8h+var_308]; this
0x1800bee82  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800bee87  mov     eax, ebx
0x1800bee89  jmp     loc_1800BF140
0x1800bee8e  mov     [rsp+3A8h+string], r14
0x1800bee93  mov     [rsp+3A8h+var_370], r14
0x1800bee98  mov     rax, [rdi]
0x1800bee9b  mov     rbx, [rax+30h]
0x1800bee9f  lea     rcx, [rsp+3A8h+var_370]
0x1800beea4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800beea9  lea     rdx, [rsp+3A8h+var_370]
0x1800beeae  mov     rcx, rdi
0x1800beeb1  mov     rax, rbx
0x1800beeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beeb9  test    eax, eax
0x1800beebb  jnz     short loc_1800BEF1D
0x1800beebd  mov     rcx, [rsp+3A8h+var_370]
0x1800beec2  mov     rax, [rcx]
0x1800beec5  lea     rdx, [rsp+3A8h+string]
0x1800beeca  mov     rax, [rax+30h]
0x1800beece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beed3  test    eax, eax
0x1800beed5  jnz     short loc_1800BEF1D
0x1800beed7  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x1800beedc  mov     rbx, rax
0x1800beedf  mov     ecx, [rax]
0x1800beee1  cmp     ecx, 5
0x1800beee4  jbe     short loc_1800BEF1D
0x1800beee6  xor     edx, edx; length
0x1800beee8  mov     rcx, [rsp+3A8h+string]; string
0x1800beeed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800beef3  mov     qword ptr [rsp+3A8h+var_368], rax
0x1800beef8  mov     r8, [rsp+3A8h+var_1F8]
0x1800bef00  add     r8, 8
0x1800bef04  lea     rax, [rsp+3A8h+var_368]
0x1800bef09  mov     qword ptr [rsp+3A8h+var_388], rax; int
0x1800bef0e  lea     rdx, word_18014E42E
0x1800bef15  mov     rcx, rbx
0x1800bef18  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800bef1d  mov     rcx, [rsp+3A8h+var_348]; this
0x1800bef22  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x1800bef27  test    al, al
0x1800bef29  jz      short loc_1800BEFA3
0x1800bef2b  mov     rcx, [rsp+3A8h]; this
0x1800bef33  mov     ebx, 80070005h
0x1800bef38  mov     r9d, ebx; char *
0x1800bef3b  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bef42  mov     edx, 8D5h; void *
0x1800bef47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bef4c  nop
0x1800bef4d  lea     rcx, [rsp+3A8h+var_370]
0x1800bef52  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bef57  nop
0x1800bef58  mov     rcx, [rsp+3A8h+string]; string
0x1800bef5d  test    rcx, rcx
0x1800bef60  jz      short loc_1800BEF69
0x1800bef62  call    cs:__imp_WindowsDeleteString
0x1800bef68  nop
0x1800bef69  lea     rcx, [rsp+3A8h+TokenHandle]; this
0x1800bef6e  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800bef73  nop
0x1800bef74  mov     rcx, [rsp+3A8h+var_340]; this
0x1800bef79  test    rcx, rcx
0x1800bef7c  jz      short loc_1800BEF84
0x1800bef7e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bef83  nop
0x1800bef84  lea     rcx, [rsp+3A8h+var_358]; this
0x1800bef89  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bef8e  nop
0x1800bef8f  lea     rcx, [rsp+3A8h+var_308]; this
0x1800bef97  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800bef9c  mov     eax, ebx
0x1800bef9e  jmp     loc_1800BF140
0x1800befa3  mov     qword ptr [rsp+3A8h+var_368], rdi
0x1800befa8  lea     rcx, [rsp+3A8h+var_368]
0x1800befad  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800befb2  nop
0x1800befb3  lea     rcx, [rsp+3A8h+var_318]; TokenHandle
0x1800befbb  call    ??0AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::AsyncImpersonator(void)
0x1800befc0  nop
0x1800befc1  lea     rax, [rsp+3A8h+var_348]
0x1800befc6  mov     [rsp+3A8h+var_380], rax
0x1800befcb  lea     rax, [rsp+3A8h+var_368]
0x1800befd0  mov     qword ptr [rsp+3A8h+var_388], rax; int
0x1800befd5  lea     r9, [rsp+3A8h+var_378]
0x1800befda  lea     r8, [rsp+3A8h+var_308]
0x1800befe2  lea     rdx, [rsp+3A8h+var_318]
0x1800befea  lea     rcx, [rsp+3A8h+var_1B8]
0x1800beff2  call    _lambda_3a9123f536a141223e3dc303f2a7bc00____lambda_3a9123f536a141223e3dc303f2a7bc00__0
0x1800beff7  nop
0x1800beff8  mov     [rsp+3A8h+var_328], 3
0x1800bf003  mov     [rsp+3A8h+var_324], 80h
0x1800bf00f  mov     r9, rax
0x1800bf012  mov     rdx, r15
0x1800bf015  lea     rcx, [rsp+3A8h+var_328]
0x1800bf01d  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__Windows__Internal__Security__Authentication__Web__ManageAccountAsyncActionName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_3a9123f536a141223e3dc303f2a7bc00___
0x1800bf022  mov     ebx, eax
0x1800bf024  lea     rcx, [rsp+3A8h+var_1B8]; this
0x1800bf02c  call    _lambda_3a9123f536a141223e3dc303f2a7bc00_____lambda_3a9123f536a141223e3dc303f2a7bc00_
0x1800bf031  test    ebx, ebx
0x1800bf033  jns     loc_1800BF0C2
0x1800bf039  mov     rcx, [rsp+3A8h]; this
0x1800bf041  mov     r9d, ebx; char *
0x1800bf044  lea     r8, aOnecoreDsSecur_30; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800bf04b  mov     edx, 8EDh; void *
0x1800bf050  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf055  nop
0x1800bf056  lea     rcx, [rsp+3A8h+var_318]; this
0x1800bf05e  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800bf063  nop
0x1800bf064  lea     rcx, [rsp+3A8h+var_368]
0x1800bf069  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf06e  nop
0x1800bf06f  lea     rcx, [rsp+3A8h+var_370]
0x1800bf074  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800bf079  nop
0x1800bf07a  mov     rcx, [rsp+3A8h+string]; string
0x1800bf07f  test    rcx, rcx
0x1800bf082  jz      short loc_1800BF08B
0x1800bf084  call    cs:__imp_WindowsDeleteString
0x1800bf08a  nop
0x1800bf08b  lea     rcx, [rsp+3A8h+TokenHandle]; this
0x1800bf090  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800bf095  nop
0x1800bf096  mov     rcx, [rsp+3A8h+var_340]; this
0x1800bf09b  test    rcx, rcx
0x1800bf09e  jz      short loc_1800BF0A6
0x1800bf0a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bf0a5  nop
0x1800bf0a6  lea     rcx, [rsp+3A8h+var_358]; this
0x1800bf0ab  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800bf0b0  nop
0x1800bf0b1  lea     rcx, [rsp+3A8h+var_308]; this
0x1800bf0b9  call    ??1TokenBrokerInternalInvokePluginToManageAccountForWindow@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalInvokePluginToManageAccountForWindow::~TokenBrokerInternalInvokePluginToManageAccountForWindow(void)
0x1800bf0be  mov     eax, ebx
0x1800bf0c0  jmp     short loc_1800BF140
0x1800bf0c2  lea     rcx, [rsp+3A8h+var_308]
0x1800bf0ca  call    ?IgnoreCurrentThread@?$ActivityBase@VWamClientLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WamClientLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
  ... truncated ...
```
