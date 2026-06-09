# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ClearDefaultSignInAccountRegistryIfNeeded(HSTRING__ *,HSTRING__ *)

- ea: `0x1800ccf00`
- end: `0x1800cd4ac`
- name: `?ClearDefaultSignInAccountRegistryIfNeeded@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJPEAUHSTRING__@@0@Z`
- size: `1452`
- prototype: `int(Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory *__hidden this, HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000bd40`
- `0x18000bd70`
- `0x18001e700`
- `0x180020620`
- `0x180020c60`
- `0x180021750`
- `0x1800231c0`
- `0x180023a80`
- `0x18002ea84`
- `0x18003d940`
- `0x18003ffa0`
- `0x180043370`
- `0x18004fdbc`
- `0x18006eda8`
- `0x18008e690`
- `0x18009942c`
- `0x1800cc9b8`
- `0x1800ccf00`
- `0x1800cf4f0`
- `0x1800dad10`
- `0x1800e38ec`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd2b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd2c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd172`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd2b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800cd2c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd1fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd3a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd3b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd43e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd1fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd399`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd3a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd3b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd43e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800cd44d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ccf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ccfd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ccf88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x1800ccfd6`

## string_xrefs

- `0x1800ccfa2`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800ccff0`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800cd049`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800cd0ae`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800cd119`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800cd1e1`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800cd278`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800cd37f`: `onecore\ds\security\tokenbroker\broker\lib\tokenbrokerdefaultaccount.cpp`
- `0x1800ccf70`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ClearDefaultSignInAccountRegistryIfNeeded`
- `0x1800ccf34`: `TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ClearDefaultSignInAccountRegistryIfNeeded(
        unsigned __int64 this,
        HSTRING a2,
        HSTRING a3)
{
  struct IUnknown *v5; // rbx
  __int64 v6; // rcx
  __int64 *v8; // rsi
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  struct _GUID *v14; // r9
  unsigned int v15; // ebx
  int DefaultSignInAccountInfoFromTokenBrokerReg; // eax
  HSTRING v17; // rdi
  HSTRING v18; // rbx
  HSTRING v19; // r14
  struct Windows::Internal::Security::Authentication::Web::CallerContext *v20; // rdx
  __int64 v21; // r8
  struct _GUID *v22; // r9
  int v23; // eax
  unsigned int v24; // esi
  HSTRING *p_string1; // [rsp+20h] [rbp-208h]
  __int64 *v26; // [rsp+30h] [rbp-1F8h] BYREF
  HSTRING string1; // [rsp+38h] [rbp-1F0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-1E8h] BYREF
  HSTRING v29; // [rsp+48h] [rbp-1E0h] BYREF
  _BYTE v30[8]; // [rsp+50h] [rbp-1D8h] BYREF
  Windows::Internal::Security::Authentication::Web::CallerContext *v31; // [rsp+58h] [rbp-1D0h]
  void *TokenHandle; // [rsp+60h] [rbp-1C8h] BYREF
  char v33; // [rsp+68h] [rbp-1C0h]
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp-1B8h]
  HSTRING v35[5]; // [rsp+78h] [rbp-1B0h] BYREF
  _QWORD v36[42]; // [rsp+A0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v5 = (struct IUnknown *)(this & -(__int64)(this != 56));
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v36,
    "TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded");
  v36[0] = &TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::`vftable';
  TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::StartActivity(
    (TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36,
    v5,
    a2);
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v6,
    (__int64)v30,
    v5,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::ClearDefaultSignInAccountRegistryIfNeeded",
    0);
  if ( WindowsIsStringEmpty(a2) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
      (const char *)0x80070057LL,
      (int)p_string1);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
    return 2147942487LL;
  }
  if ( WindowsIsStringEmpty(a3) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
      (const char *)0x80070057LL,
      (int)p_string1);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
    return 2147942487LL;
  }
  v8 = (__int64 *)v31;
  v31 = 0;
  v26 = v8;
  if ( !v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
      (const char *)0x8007000ELL,
      (int)p_string1);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v26,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v8 )
  {
    v9 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(
           (Windows::Internal::Security::Authentication::Web::CallerContext *)v8,
           v5,
           0,
           0);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1ED,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
        (const char *)(unsigned int)v9,
        (int)p_string1);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        &v26,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
      TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
      return v10;
    }
  }
  TokenHandle = 0;
  v33 = 0;
  v11 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&TokenHandle, v8[2]);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
      (const char *)(unsigned int)v11,
      (int)p_string1);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v26,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
    return v12;
  }
  if ( (unsigned int)dword_180175000 > 4 )
  {
    string = (HSTRING)WindowsGetStringRawBuffer(a3, 0);
    string1 = (HSTRING)WindowsGetStringRawBuffer(a2, 0);
    p_string1 = &string1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      &dword_180175000,
      byte_18014F593,
      0);
  }
  string = 0;
  v13 = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::ConvertPluginPFNToPluginId(
          (struct Windows::Internal::Security::Authentication::Web::CallerContext *)v8,
          a2,
          &string);
  v15 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x201,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
      (const char *)(unsigned int)v13,
      (int)p_string1);
    if ( string )
      WindowsDeleteString(string);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v26,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
    return v15;
  }
  *(_OWORD *)v35 = 0;
  string1 = 0;
  v29 = 0;
  DefaultSignInAccountInfoFromTokenBrokerReg = Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountInfoFromTokenBrokerReg(
                                                 (Windows::Internal::Security::Authentication::Web *)&string1,
                                                 &v29,
                                                 v35,
                                                 v14);
  if ( DefaultSignInAccountInfoFromTokenBrokerReg < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
      (const char *)(unsigned int)DefaultSignInAccountInfoFromTokenBrokerReg,
      (int)p_string1);
    v17 = string;
    v18 = string1;
    v19 = v29;
    goto LABEL_37;
  }
  if ( (unsigned int)dword_180175000 <= 4 )
  {
    v18 = string1;
    v19 = v29;
  }
  else
  {
    v19 = v29;
    StringRawBuffer = WindowsGetStringRawBuffer(v29, 0);
    v18 = string1;
    v35[0] = (HSTRING)WindowsGetStringRawBuffer(string1, 0);
    p_string1 = v35;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      &dword_180175000,
      byte_18014F53B,
      0);
  }
  v17 = string;
  if ( !CompareProviderIds(v18, string)
    || (v35[0] = a3,
        (unsigned int)Windows::Internal::StringReference::CompareOrdinal(
                        (Windows::Internal::StringReference *)v35,
                        (const struct Windows::Internal::String *)&v29)) )
  {
    if ( (unsigned int)dword_180175000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180175000,
        byte_18014F4BB,
        0,
        0);
    goto LABEL_37;
  }
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      &dword_18014F4FC,
      0,
      0);
  LOBYTE(v20) = 1;
  v23 = Windows::Internal::Security::Authentication::Web::ClearDefaultSignInAccountInfoInTokenBrokerReg(
          (Windows::Internal::Security::Authentication::Web *)v8,
          v20,
          v21,
          v22);
  v24 = v23;
  if ( v23 >= 0 )
  {
LABEL_37:
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v36);
    if ( v19 )
      WindowsDeleteString(v19);
    if ( v18 )
      WindowsDeleteString(v18);
    if ( v17 )
      WindowsDeleteString(v17);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      &v26,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x222,
    (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tokenbrokerdefaultaccount.cpp",
    (const char *)(unsigned int)v23,
    (int)p_string1);
  if ( v19 )
    WindowsDeleteString(v19);
  if ( v18 )
    WindowsDeleteString(v18);
  if ( v17 )
    WindowsDeleteString(v17);
  Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
  wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
    &v26,
    0);
  Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
  TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded((TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded *)v36);
  return v24;
}

```

## disassembly

```asm
0x1800ccf00  push    rbx
0x1800ccf02  push    rsi
0x1800ccf03  push    rdi
0x1800ccf04  push    r14
0x1800ccf06  push    r15
0x1800ccf08  sub     rsp, 200h
0x1800ccf0f  mov     rax, cs:__security_cookie
0x1800ccf16  xor     rax, rsp
0x1800ccf19  mov     [rsp+228h+var_38], rax
0x1800ccf21  mov     r15, r8
0x1800ccf24  mov     rdi, rdx
0x1800ccf27  lea     rax, [rcx-38h]
0x1800ccf2b  neg     rax
0x1800ccf2e  sbb     rbx, rbx
0x1800ccf31  and     rbx, rcx
0x1800ccf34  lea     rdx, aTokenbrokerint_24; "TokenBrokerInternalClearDefaultSignInAc"...
0x1800ccf3b  lea     rcx, [rsp+228h+var_188]
0x1800ccf43  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800ccf48  lea     rax, ??_7TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::`vftable'
0x1800ccf4f  mov     [rsp+228h+var_188], rax
0x1800ccf57  mov     r8, rdi; HSTRING
0x1800ccf5a  mov     rdx, rbx; struct IUnknown *
0x1800ccf5d  lea     rcx, [rsp+228h+var_188]; this
0x1800ccf65  call    ?StartActivity@TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAAXPEAUIUnknown@@PEAUHSTRING__@@@Z; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::StartActivity(IUnknown *,HSTRING__ *)
0x1800ccf6a  nop
0x1800ccf6b  mov     byte ptr [rsp+228h+var_208], 0; int
0x1800ccf70  lea     r9, aWindowsInterna_47; "Windows::Internal::Security::Authentica"...
0x1800ccf77  mov     r8, rbx
0x1800ccf7a  lea     rdx, [rsp+228h+var_1D8]
0x1800ccf7f  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800ccf84  nop
0x1800ccf85  mov     rcx, rdi; string
0x1800ccf88  call    cs:__imp_WindowsIsStringEmpty
0x1800ccf8e  test    eax, eax
0x1800ccf90  jz      short loc_1800CCFD3
0x1800ccf92  mov     rcx, [rsp+228h]; this
0x1800ccf9a  mov     ebx, 80070057h
0x1800ccf9f  mov     r9d, ebx; char *
0x1800ccfa2  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ccfa9  mov     edx, 1E6h; void *
0x1800ccfae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ccfb3  nop
0x1800ccfb4  lea     rcx, [rsp+228h+var_1D8]; this
0x1800ccfb9  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800ccfbe  nop
0x1800ccfbf  lea     rcx, [rsp+228h+var_188]; this
0x1800ccfc7  call    ??1TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded(void)
0x1800ccfcc  mov     eax, ebx
0x1800ccfce  jmp     loc_1800CD48C
0x1800ccfd3  mov     rcx, r15; string
0x1800ccfd6  call    cs:__imp_WindowsIsStringEmpty
0x1800ccfdc  test    eax, eax
0x1800ccfde  jz      short loc_1800CD021
0x1800ccfe0  mov     rcx, [rsp+228h]; this
0x1800ccfe8  mov     ebx, 80070057h
0x1800ccfed  mov     r9d, ebx; char *
0x1800ccff0  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800ccff7  mov     edx, 1E7h; void *
0x1800ccffc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd001  nop
0x1800cd002  lea     rcx, [rsp+228h+var_1D8]; this
0x1800cd007  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800cd00c  nop
0x1800cd00d  lea     rcx, [rsp+228h+var_188]; this
0x1800cd015  call    ??1TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded(void)
0x1800cd01a  mov     eax, ebx
0x1800cd01c  jmp     loc_1800CD48C
0x1800cd021  mov     rsi, [rsp+228h+var_1D0]
0x1800cd026  mov     [rsp+228h+var_1D0], 0
0x1800cd02f  mov     [rsp+228h+var_1F8], rsi
0x1800cd034  test    rsi, rsi
0x1800cd037  jnz     short loc_1800CD087
0x1800cd039  mov     rcx, [rsp+228h]; this
0x1800cd041  mov     ebx, 8007000Eh
0x1800cd046  mov     r9d, ebx; char *
0x1800cd049  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cd050  mov     edx, 1EAh; void *
0x1800cd055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd05a  nop
0x1800cd05b  xor     edx, edx
0x1800cd05d  lea     rcx, [rsp+228h+var_1F8]
0x1800cd062  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800cd067  nop
0x1800cd068  lea     rcx, [rsp+228h+var_1D8]; this
0x1800cd06d  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800cd072  nop
0x1800cd073  lea     rcx, [rsp+228h+var_188]; this
0x1800cd07b  call    ??1TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded(void)
0x1800cd080  mov     eax, ebx
0x1800cd082  jmp     loc_1800CD48C
0x1800cd087  cmp     byte ptr [rsi], 0
0x1800cd08a  jnz     short loc_1800CD0EC
0x1800cd08c  xor     r9d, r9d; bool
0x1800cd08f  xor     r8d, r8d; unsigned __int64
0x1800cd092  mov     rdx, rbx; struct IUnknown *
0x1800cd095  mov     rcx, rsi; this
0x1800cd098  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x1800cd09d  mov     ebx, eax
0x1800cd09f  test    eax, eax
0x1800cd0a1  jns     short loc_1800CD0EC
0x1800cd0a3  mov     rcx, [rsp+228h]; this
0x1800cd0ab  mov     r9d, eax; char *
0x1800cd0ae  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cd0b5  mov     edx, 1EDh; void *
0x1800cd0ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd0bf  nop
0x1800cd0c0  xor     edx, edx
0x1800cd0c2  lea     rcx, [rsp+228h+var_1F8]
0x1800cd0c7  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800cd0cc  nop
0x1800cd0cd  lea     rcx, [rsp+228h+var_1D8]; this
0x1800cd0d2  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800cd0d7  nop
0x1800cd0d8  lea     rcx, [rsp+228h+var_188]; this
0x1800cd0e0  call    ??1TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded(void)
0x1800cd0e5  mov     eax, ebx
0x1800cd0e7  jmp     loc_1800CD48C
0x1800cd0ec  mov     [rsp+228h+TokenHandle], 0
0x1800cd0f5  mov     [rsp+228h+var_1C0], 0
0x1800cd0fa  mov     rdx, [rsi+10h]; unsigned __int64
0x1800cd0fe  lea     rcx, [rsp+228h+TokenHandle]; TokenHandle
0x1800cd103  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x1800cd108  mov     ebx, eax
0x1800cd10a  test    eax, eax
0x1800cd10c  jns     short loc_1800CD162
0x1800cd10e  mov     rcx, [rsp+228h]; this
0x1800cd116  mov     r9d, eax; char *
0x1800cd119  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cd120  mov     edx, 1F1h; void *
0x1800cd125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd12a  nop
0x1800cd12b  lea     rcx, [rsp+228h+TokenHandle]; this
0x1800cd130  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800cd135  nop
0x1800cd136  xor     edx, edx
0x1800cd138  lea     rcx, [rsp+228h+var_1F8]
0x1800cd13d  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800cd142  nop
0x1800cd143  lea     rcx, [rsp+228h+var_1D8]; this
0x1800cd148  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800cd14d  nop
0x1800cd14e  lea     rcx, [rsp+228h+var_188]; this
0x1800cd156  call    ??1TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded(void)
0x1800cd15b  mov     eax, ebx
0x1800cd15d  jmp     loc_1800CD48C
0x1800cd162  mov     eax, cs:dword_180175000
0x1800cd168  cmp     eax, 4
0x1800cd16b  jbe     short loc_1800CD1B7
0x1800cd16d  xor     edx, edx; length
0x1800cd16f  mov     rcx, r15; string
0x1800cd172  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd178  mov     [rsp+228h+string], rax
0x1800cd17d  xor     edx, edx; length
0x1800cd17f  mov     rcx, rdi; string
0x1800cd182  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd188  mov     [rsp+228h+string1], rax
0x1800cd18d  lea     rax, [rsp+228h+string]
0x1800cd192  mov     [rsp+228h+var_200], rax
0x1800cd197  lea     rax, [rsp+228h+string1]
0x1800cd19c  mov     qword ptr [rsp+228h+var_208], rax; int
0x1800cd1a1  xor     r8d, r8d
0x1800cd1a4  lea     rdx, byte_18014F593
0x1800cd1ab  lea     rcx, dword_180175000
0x1800cd1b2  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800cd1b7  mov     [rsp+228h+string], 0
0x1800cd1c0  lea     r8, [rsp+228h+string]; HSTRING *
0x1800cd1c5  mov     rdx, rdi; HSTRING
0x1800cd1c8  mov     rcx, rsi; this
0x1800cd1cb  call    ?ConvertPluginPFNToPluginId@PluginRegistrationInternal@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAVCallerContext@Web@3456@QEAUHSTRING__@@PEAPEAU9@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistrationInternal::ConvertPluginPFNToPluginId(Windows::Internal::Security::Authentication::Web::CallerContext *,HSTRING__ * const,HSTRING__ * *)
0x1800cd1d0  mov     ebx, eax
0x1800cd1d2  test    eax, eax
0x1800cd1d4  jns     short loc_1800CD23B
0x1800cd1d6  mov     rcx, [rsp+228h]; this
0x1800cd1de  mov     r9d, eax; char *
0x1800cd1e1  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cd1e8  mov     edx, 201h; void *
0x1800cd1ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd1f2  nop
0x1800cd1f3  mov     rcx, [rsp+228h+string]; string
0x1800cd1f8  test    rcx, rcx
0x1800cd1fb  jz      short loc_1800CD204
0x1800cd1fd  call    cs:__imp_WindowsDeleteString
0x1800cd203  nop
0x1800cd204  lea     rcx, [rsp+228h+TokenHandle]; this
0x1800cd209  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800cd20e  nop
0x1800cd20f  xor     edx, edx
0x1800cd211  lea     rcx, [rsp+228h+var_1F8]
0x1800cd216  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800cd21b  nop
0x1800cd21c  lea     rcx, [rsp+228h+var_1D8]; this
0x1800cd221  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800cd226  nop
0x1800cd227  lea     rcx, [rsp+228h+var_188]; this
0x1800cd22f  call    ??1TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded(void)
0x1800cd234  mov     eax, ebx
0x1800cd236  jmp     loc_1800CD48C
0x1800cd23b  xorps   xmm0, xmm0
0x1800cd23e  movups  xmmword ptr [rsp+228h+var_1B0], xmm0
0x1800cd243  mov     [rsp+228h+string1], 0
0x1800cd24c  mov     [rsp+228h+var_1E0], 0
0x1800cd255  lea     r8, [rsp+228h+var_1B0]; HSTRING *
0x1800cd25a  lea     rdx, [rsp+228h+var_1E0]; HSTRING *
0x1800cd25f  lea     rcx, [rsp+228h+string1]; this
0x1800cd264  call    ?GetDefaultSignInAccountInfoFromTokenBrokerReg@Web@Authentication@Security@Internal@Windows@@YAJPEAPEAUHSTRING__@@0PEAU_GUID@@@Z; Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountInfoFromTokenBrokerReg(HSTRING__ * *,HSTRING__ * *,_GUID *)
0x1800cd269  mov     rcx, [rsp+228h]; this
0x1800cd271  test    eax, eax
0x1800cd273  jns     short loc_1800CD29D
0x1800cd275  mov     r9d, eax; char *
0x1800cd278  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cd27f  mov     edx, 20Dh; void *
0x1800cd284  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800cd289  mov     rdi, [rsp+228h+string]
0x1800cd28e  mov     rbx, [rsp+228h+string1]
0x1800cd293  mov     r14, [rsp+228h+var_1E0]
0x1800cd298  jmp     loc_1800CD419
0x1800cd29d  mov     eax, cs:dword_180175000
0x1800cd2a3  cmp     eax, 4
0x1800cd2a6  jbe     short loc_1800CD2FE
0x1800cd2a8  xor     edx, edx; length
0x1800cd2aa  mov     r14, [rsp+228h+var_1E0]
0x1800cd2af  mov     rcx, r14; string
0x1800cd2b2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd2b8  mov     [rsp+228h+var_1B8], rax
0x1800cd2bd  xor     edx, edx; length
0x1800cd2bf  mov     rbx, [rsp+228h+string1]
0x1800cd2c4  mov     rcx, rbx; string
0x1800cd2c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800cd2cd  mov     [rsp+228h+var_1B0], rax
0x1800cd2d2  lea     rax, [rsp+228h+var_1B8]
0x1800cd2d7  mov     [rsp+228h+var_200], rax
0x1800cd2dc  lea     rax, [rsp+228h+var_1B0]
0x1800cd2e1  mov     qword ptr [rsp+228h+var_208], rax
0x1800cd2e6  xor     r8d, r8d
0x1800cd2e9  lea     rdx, byte_18014F53B
0x1800cd2f0  lea     rcx, dword_180175000
0x1800cd2f7  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800cd2fc  jmp     short loc_1800CD308
0x1800cd2fe  mov     rbx, [rsp+228h+string1]
0x1800cd303  mov     r14, [rsp+228h+var_1E0]
0x1800cd308  mov     rdi, [rsp+228h+string]
0x1800cd30d  mov     rdx, rdi; string2
0x1800cd310  mov     rcx, rbx; string1
0x1800cd313  call    ?CompareProviderIds@@YA_NPEAUHSTRING__@@0@Z; CompareProviderIds(HSTRING__ *,HSTRING__ *)
0x1800cd318  test    al, al
0x1800cd31a  jz      loc_1800CD3F5
0x1800cd320  mov     [rsp+228h+var_1B0], r15
0x1800cd325  lea     rdx, [rsp+228h+var_1E0]; struct Windows::Internal::String *
0x1800cd32a  lea     rcx, [rsp+228h+var_1B0]; this
0x1800cd32f  call    ?CompareOrdinal@StringReference@Internal@Windows@@QEBAHAEBVString@23@@Z; Windows::Internal::StringReference::CompareOrdinal(Windows::Internal::String const &)
0x1800cd334  test    eax, eax
0x1800cd336  jnz     loc_1800CD3F5
0x1800cd33c  mov     eax, cs:dword_180175000
0x1800cd342  cmp     eax, 4
0x1800cd345  jbe     short loc_1800CD360
0x1800cd347  xor     r9d, r9d
0x1800cd34a  xor     r8d, r8d
0x1800cd34d  lea     rdx, dword_18014F4FC
0x1800cd354  lea     rcx, dword_180175000
0x1800cd35b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800cd360  mov     dl, 1; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x1800cd362  mov     rcx, rsi; this
0x1800cd365  call    ?ClearDefaultSignInAccountInfoInTokenBrokerReg@Web@Authentication@Security@Internal@Windows@@YAJPEAVCallerContext@12345@_N@Z; Windows::Internal::Security::Authentication::Web::ClearDefaultSignInAccountInfoInTokenBrokerReg(Windows::Internal::Security::Authentication::Web::CallerContext *,bool)
0x1800cd36a  mov     esi, eax
0x1800cd36c  test    eax, eax
0x1800cd36e  jns     loc_1800CD419
0x1800cd374  mov     rcx, [rsp+228h]; this
0x1800cd37c  mov     r9d, eax; char *
0x1800cd37f  lea     r8, aOnecoreDsSecur_41; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800cd386  mov     edx, 222h; void *
0x1800cd38b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cd390  nop
0x1800cd391  test    r14, r14
0x1800cd394  jz      short loc_1800CD3A0
0x1800cd396  mov     rcx, r14; string
0x1800cd399  call    cs:__imp_WindowsDeleteString
0x1800cd39f  nop
0x1800cd3a0  test    rbx, rbx
0x1800cd3a3  jz      short loc_1800CD3AF
0x1800cd3a5  mov     rcx, rbx; string
0x1800cd3a8  call    cs:__imp_WindowsDeleteString
0x1800cd3ae  nop
0x1800cd3af  test    rdi, rdi
0x1800cd3b2  jz      short loc_1800CD3BE
0x1800cd3b4  mov     rcx, rdi; string
0x1800cd3b7  call    cs:__imp_WindowsDeleteString
0x1800cd3bd  nop
0x1800cd3be  lea     rcx, [rsp+228h+TokenHandle]; this
0x1800cd3c3  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1800cd3c8  nop
0x1800cd3c9  xor     edx, edx
0x1800cd3cb  lea     rcx, [rsp+228h+var_1F8]
0x1800cd3d0  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x1800cd3d5  nop
0x1800cd3d6  lea     rcx, [rsp+228h+var_1D8]; this
0x1800cd3db  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800cd3e0  nop
0x1800cd3e1  lea     rcx, [rsp+228h+var_188]; this
0x1800cd3e9  call    ??1TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded::~TokenBrokerInternalClearDefaultSignInAccountRegistryIfNeeded(void)
0x1800cd3ee  mov     eax, esi
  ... truncated ...
```
