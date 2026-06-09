# Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetApplicationTokenBindingPublicKeyId(unsigned __int64,Windows::Security::Authentication::Web::TokenBindingKeyType,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IUriRuntimeClass *,Windows::Security::Authentication::Web::TokenBindingKeyType *,Windows::Storage::Streams::IBuffer * *)

- ea: `0x180033800`
- end: `0x180033d66`
- name: `?GetApplicationTokenBindingPublicKeyId@CTokenBrokerInternalFactory@Web@Authentication@Security@Internal@Windows@@UEAAJ_KW4TokenBindingKeyType@2346@PEAUIUriRuntimeClass@Foundation@6@2PEAW472346@PEAPEAUIBuffer@Streams@Storage@6@@Z`
- size: `1382`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000bd40`
- `0x18000bd70`
- `0x18001e700`
- `0x180020620`
- `0x18002071c`
- `0x180020c60`
- `0x180021750`
- `0x1800228a8`
- `0x180023090`
- `0x1800231c0`
- `0x180023a80`
- `0x180024000`
- `0x18002ea84`
- `0x18002fbf0`
- `0x1800332f8`
- `0x180033800`
- `0x180033d6c`
- `0x180033e04`
- `0x180033f50`
- `0x180033f7c`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033b05`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033bc5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033ce8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033b05`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033bc5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180033ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033cd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033c7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180033cd3`

## string_xrefs

- `0x1800338bb`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033901`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033947`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x18003399a`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x1800339f5`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033a5a`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033ae5`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033b94`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033c65`: `onecore\ds\security\tokenbroker\broker\lib\tbtokenbinding.cpp`
- `0x180033891`: `Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetApplicationTokenBindingPublicKeyId`
- `0x18003384e`: `TokenBrokerInternalGetApplicationTokenBindingPublicKeyId`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetApplicationTokenBindingPublicKeyId(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        struct Windows::Internal::Security::Authentication::Web::CallerContext *a4,
        Windows::Internal::Security::Authentication::TokenBroker *a5,
        HSTRING a6,
        __int64 a7)
{
  struct IUnknown *v11; // rdi
  __int64 v12; // rcx
  __int64 *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  int v17; // eax
  HSTRING *v18; // r8
  unsigned int v19; // edi
  struct Windows::Foundation::IUriRuntimeClass *v20; // r8
  int TokenBindingAllowed; // eax
  HSTRING v22; // rbx
  int TokenBindingPublicKeyId; // eax
  unsigned int v24; // edi
  int v25; // [rsp+20h] [rbp-1F8h]
  int v26[2]; // [rsp+20h] [rbp-1F8h]
  Windows::Internal::Security::Authentication::Web::CallerContext *v27[2]; // [rsp+40h] [rbp-1D8h] BYREF
  HANDLE Token; // [rsp+50h] [rbp-1C8h] BYREF
  char v29; // [rsp+58h] [rbp-1C0h]
  _BYTE v30[8]; // [rsp+60h] [rbp-1B8h] BYREF
  _BYTE v31[8]; // [rsp+68h] [rbp-1B0h] BYREF
  HSTRING string[2]; // [rsp+70h] [rbp-1A8h] BYREF
  _QWORD v33[42]; // [rsp+80h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  string[1] = a6;
  wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "TokenBrokerInternalGetApplicationTokenBindingPublicKeyId");
  v33[0] = &TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable';
  TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::StartActivity((TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId *)v33);
  v11 = (struct IUnknown *)(a1 & -(__int64)(a1 != 40));
  Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(
    v12,
    (__int64)v30,
    v11,
    "Windows::Internal::Security::Authentication::Web::CTokenBrokerInternalFactory::GetApplicationTokenBindingPublicKeyId",
    0);
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x368,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId((TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId *)v33);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x369,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId((TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId *)v33);
    return 2147942487LL;
  }
  if ( !a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36A,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId((TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId *)v33);
    return 2147942487LL;
  }
  if ( a3 && a3 - 1 >= 2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x373,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)0x80070057LL,
      v25);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId((TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId *)v33);
    return 2147942487LL;
  }
  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v27, v31);
  v14 = (__int64 *)v27[0];
  if ( !v27[0] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x377,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)0x8007000ELL,
      v25);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      v27,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId((TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId *)v33);
    return 2147942414LL;
  }
  if ( !*(_BYTE *)v27[0] )
  {
    v15 = Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(v27[0], v11, 0, 0);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37A,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
        (const char *)(unsigned int)v15,
        v25);
      wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
        v27,
        0);
      Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
      v33[0] = &TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable';
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
      wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v33);
      return v16;
    }
  }
  Token = 0;
  v29 = 0;
  v17 = Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&Token, v14[1]);
  v19 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)v17,
      v25);
    if ( v29 )
      SetThreadToken(0, Token);
LABEL_18:
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      v27,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    v33[0] = &TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable';
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v33);
    return v19;
  }
  string[0] = 0;
  Windows::Internal::Security::Authentication::TokenBroker::GetApplicationPfnForLookup(
    a5,
    (struct Windows::Foundation::IUriRuntimeClass *)string,
    v18);
  TokenBindingAllowed = Windows::Internal::Security::Authentication::TokenBroker::VerifyQueryTokenBindingAllowed(
                          (Windows::Internal::Security::Authentication::TokenBroker *)v14,
                          a4,
                          v20);
  v19 = TokenBindingAllowed;
  if ( TokenBindingAllowed < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x387,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)TokenBindingAllowed,
      v25);
    if ( string[0] )
      WindowsDeleteString(string[0]);
    if ( v29 )
      SetThreadToken(0, Token);
    goto LABEL_18;
  }
  Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer((Windows::Internal::Security::Authentication::Web::CallerContext *)v14);
  *(_QWORD *)v26 = v14[9];
  v22 = string[0];
  TokenBindingPublicKeyId = Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyId(
                              a2,
                              a3,
                              a4,
                              string[0]);
  v24 = TokenBindingPublicKeyId;
  if ( TokenBindingPublicKeyId >= 0 )
  {
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v33);
    if ( v22 )
      WindowsDeleteString(v22);
    if ( v29 )
      SetThreadToken(0, Token);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      v27,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    v33[0] = &TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable';
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
    wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v33);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x393,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\tbtokenbinding.cpp",
      (const char *)(unsigned int)TokenBindingPublicKeyId,
      v26[0]);
    if ( v22 )
      WindowsDeleteString(v22);
    Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&Token);
    wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(
      v27,
      0);
    Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope((Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope *)v30);
    TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId((TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId *)v33);
    return v24;
  }
}

```

## disassembly

```asm
0x180033800  push    rbx
0x180033802  push    rsi
0x180033803  push    rdi
0x180033804  push    r12
0x180033806  push    r13
0x180033808  push    r14
0x18003380a  push    r15
0x18003380c  sub     rsp, 1E0h
0x180033813  mov     rax, cs:__security_cookie
0x18003381a  xor     rax, rsp
0x18003381d  mov     [rsp+218h+var_48], rax
0x180033825  mov     rsi, r9
0x180033828  mov     r14d, r8d
0x18003382b  mov     r13, rdx
0x18003382e  mov     rbx, rcx
0x180033831  mov     r15, [rsp+218h+arg_20]
0x180033839  mov     rax, [rsp+218h+arg_28]
0x180033841  mov     [rsp+218h+var_1A0], rax
0x180033846  mov     r12, [rsp+218h+arg_30]
0x18003384e  lea     rdx, aTokenbrokerint; "TokenBrokerInternalGetApplicationTokenB"...
0x180033855  lea     rcx, [rsp+218h+var_198]
0x18003385d  call    ??0?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180033862  lea     rax, ??_7TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable'
0x180033869  mov     [rsp+218h+var_198], rax
0x180033871  lea     rcx, [rsp+218h+var_198]; this
0x180033879  call    ?StartActivity@TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@QEAAXXZ; TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::StartActivity(void)
0x18003387e  nop
0x18003387f  lea     rax, [rbx-28h]
0x180033883  neg     rax
0x180033886  sbb     rdi, rdi
0x180033889  and     rdi, rbx
0x18003388c  mov     byte ptr [rsp+218h+var_1F8], 0; int
0x180033891  lea     r9, aWindowsInterna_91; "Windows::Internal::Security::Authentica"...
0x180033898  mov     r8, rdi
0x18003389b  lea     rdx, [rsp+218h+var_1B8]
0x1800338a0  call    ?ProfileCaller@CWamCallerProfiler@Web@Authentication@Security@Internal@Windows@@QEAA?AVCWamProfilerThreadScope@23456@PEAUIUnknown@@PEBD_N@Z; Windows::Internal::Security::Authentication::Web::CWamCallerProfiler::ProfileCaller(IUnknown *,char const *,bool)
0x1800338a5  nop
0x1800338a6  test    rsi, rsi
0x1800338a9  jnz     short loc_1800338EC
0x1800338ab  mov     rcx, [rsp+218h]; this
0x1800338b3  mov     ebx, 80070057h
0x1800338b8  mov     r9d, ebx; char *
0x1800338bb  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800338c2  mov     edx, 368h; void *
0x1800338c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800338cc  nop
0x1800338cd  lea     rcx, [rsp+218h+var_1B8]; this
0x1800338d2  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800338d7  nop
0x1800338d8  lea     rcx, [rsp+218h+var_198]; this
0x1800338e0  call    ??1TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId(void)
0x1800338e5  mov     eax, ebx
0x1800338e7  jmp     loc_180033D42
0x1800338ec  test    r15, r15
0x1800338ef  jnz     short loc_180033932
0x1800338f1  mov     rcx, [rsp+218h]; this
0x1800338f9  mov     ebx, 80070057h
0x1800338fe  mov     r9d, ebx; char *
0x180033901  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033908  mov     edx, 369h; void *
0x18003390d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033912  nop
0x180033913  lea     rcx, [rsp+218h+var_1B8]; this
0x180033918  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x18003391d  nop
0x18003391e  lea     rcx, [rsp+218h+var_198]; this
0x180033926  call    ??1TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId(void)
0x18003392b  mov     eax, ebx
0x18003392d  jmp     loc_180033D42
0x180033932  test    r12, r12
0x180033935  jnz     short loc_180033978
0x180033937  mov     rcx, [rsp+218h]; this
0x18003393f  mov     ebx, 80070057h
0x180033944  mov     r9d, ebx; char *
0x180033947  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18003394e  mov     edx, 36Ah; void *
0x180033953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033958  nop
0x180033959  lea     rcx, [rsp+218h+var_1B8]; this
0x18003395e  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180033963  nop
0x180033964  lea     rcx, [rsp+218h+var_198]; this
0x18003396c  call    ??1TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId(void)
0x180033971  mov     eax, ebx
0x180033973  jmp     loc_180033D42
0x180033978  mov     ecx, r14d
0x18003397b  test    r14d, r14d
0x18003397e  jz      short loc_1800339CB
0x180033980  sub     ecx, 1
0x180033983  jz      short loc_1800339CB
0x180033985  cmp     ecx, 1
0x180033988  jz      short loc_1800339CB
0x18003398a  mov     rcx, [rsp+218h]; this
0x180033992  mov     ebx, 80070057h
0x180033997  mov     r9d, ebx; char *
0x18003399a  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800339a1  mov     edx, 373h; void *
0x1800339a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800339ab  nop
0x1800339ac  lea     rcx, [rsp+218h+var_1B8]; this
0x1800339b1  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x1800339b6  nop
0x1800339b7  lea     rcx, [rsp+218h+var_198]; this
0x1800339bf  call    ??1TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId(void)
0x1800339c4  mov     eax, ebx
0x1800339c6  jmp     loc_180033D42
0x1800339cb  lea     rdx, [rsp+218h+var_1B0]
0x1800339d0  lea     rcx, [rsp+218h+var_1D8]
0x1800339d5  call    ??0?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x1800339da  nop
0x1800339db  mov     rbx, [rsp+218h+var_1D8]
0x1800339e0  test    rbx, rbx
0x1800339e3  jnz     short loc_180033A33
0x1800339e5  mov     rcx, [rsp+218h]; this
0x1800339ed  mov     ebx, 8007000Eh
0x1800339f2  mov     r9d, ebx; char *
0x1800339f5  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x1800339fc  mov     edx, 377h; void *
0x180033a01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a06  nop
0x180033a07  xor     edx, edx
0x180033a09  lea     rcx, [rsp+218h+var_1D8]
0x180033a0e  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180033a13  nop
0x180033a14  lea     rcx, [rsp+218h+var_1B8]; this
0x180033a19  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180033a1e  nop
0x180033a1f  lea     rcx, [rsp+218h+var_198]; this
0x180033a27  call    ??1TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId(void)
0x180033a2c  mov     eax, ebx
0x180033a2e  jmp     loc_180033D42
0x180033a33  cmp     byte ptr [rbx], 0
0x180033a36  jnz     short loc_180033AB4
0x180033a38  xor     r9d, r9d; bool
0x180033a3b  xor     r8d, r8d; unsigned __int64
0x180033a3e  mov     rdx, rdi; struct IUnknown *
0x180033a41  mov     rcx, rbx; this
0x180033a44  call    ?Initialize@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJPEAUIUnknown@@_K_N@Z; Windows::Internal::Security::Authentication::Web::CallerContext::Initialize(IUnknown *,unsigned __int64,bool)
0x180033a49  mov     edi, eax
0x180033a4b  test    eax, eax
0x180033a4d  jns     short loc_180033AB4
0x180033a4f  mov     rcx, [rsp+218h]; this
0x180033a57  mov     r9d, eax; char *
0x180033a5a  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033a61  mov     edx, 37Ah; void *
0x180033a66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033a6b  nop
0x180033a6c  xor     edx, edx
0x180033a6e  lea     rcx, [rsp+218h+var_1D8]
0x180033a73  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180033a78  nop
0x180033a79  lea     rcx, [rsp+218h+var_1B8]; this
0x180033a7e  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180033a83  nop
0x180033a84  lea     rax, ??_7TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable'
0x180033a8b  mov     [rsp+218h+var_198], rax
0x180033a93  lea     rcx, [rsp+218h+var_198]
0x180033a9b  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180033aa0  lea     rcx, [rsp+218h+var_198]
0x180033aa8  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180033aad  mov     eax, edi
0x180033aaf  jmp     loc_180033D42
0x180033ab4  mov     [rsp+218h+Token], 0
0x180033abd  mov     [rsp+218h+var_1C0], 0
0x180033ac2  mov     rdx, [rbx+8]; unsigned __int64
0x180033ac6  lea     rcx, [rsp+218h+Token]; TokenHandle
0x180033acb  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJ_K@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(unsigned __int64)
0x180033ad0  mov     edi, eax
0x180033ad2  test    eax, eax
0x180033ad4  jns     loc_180033B5E
0x180033ada  mov     rcx, [rsp+218h]; this
0x180033ae2  mov     r9d, eax; char *
0x180033ae5  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033aec  mov     edx, 37Eh; void *
0x180033af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033af6  nop
0x180033af7  cmp     [rsp+218h+var_1C0], 0
0x180033afc  jz      short loc_180033B0B
0x180033afe  mov     rdx, [rsp+218h+Token]; Token
0x180033b03  xor     ecx, ecx; Thread
0x180033b05  call    cs:__imp_SetThreadToken
0x180033b0b  lea     rcx, [rsp+218h+Token]; this
0x180033b10  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180033b15  nop
0x180033b16  xor     edx, edx
0x180033b18  lea     rcx, [rsp+218h+var_1D8]
0x180033b1d  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180033b22  nop
0x180033b23  lea     rcx, [rsp+218h+var_1B8]; this
0x180033b28  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180033b2d  nop
0x180033b2e  lea     rax, ??_7TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable'
0x180033b35  mov     [rsp+218h+var_198], rax
0x180033b3d  lea     rcx, [rsp+218h+var_198]
0x180033b45  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180033b4a  lea     rcx, [rsp+218h+var_198]
0x180033b52  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180033b57  mov     eax, edi
0x180033b59  jmp     loc_180033D42
0x180033b5e  mov     [rsp+218h+string], 0
0x180033b67  lea     rdx, [rsp+218h+string]; struct Windows::Foundation::IUriRuntimeClass *
0x180033b6c  mov     rcx, r15; this
0x180033b6f  call    ?GetApplicationPfnForLookup@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUriRuntimeClass@Foundation@5@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetApplicationPfnForLookup(Windows::Foundation::IUriRuntimeClass *,HSTRING__ * *)
0x180033b74  mov     rdx, rsi; struct Windows::Internal::Security::Authentication::Web::CallerContext *
0x180033b77  mov     rcx, rbx; this
0x180033b7a  call    ?VerifyQueryTokenBindingAllowed@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAVCallerContext@Web@2345@PEAUIUriRuntimeClass@Foundation@5@@Z; Windows::Internal::Security::Authentication::TokenBroker::VerifyQueryTokenBindingAllowed(Windows::Internal::Security::Authentication::Web::CallerContext *,Windows::Foundation::IUriRuntimeClass *)
0x180033b7f  mov     edi, eax
0x180033b81  test    eax, eax
0x180033b83  jns     loc_180033C1E
0x180033b89  mov     rcx, [rsp+218h]; this
0x180033b91  mov     r9d, eax; char *
0x180033b94  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033b9b  mov     edx, 387h; void *
0x180033ba0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ba5  nop
0x180033ba6  mov     rcx, [rsp+218h+string]; string
0x180033bab  test    rcx, rcx
0x180033bae  jz      short loc_180033BB7
0x180033bb0  call    cs:__imp_WindowsDeleteString
0x180033bb6  nop
0x180033bb7  cmp     [rsp+218h+var_1C0], 0
0x180033bbc  jz      short loc_180033BCB
0x180033bbe  mov     rdx, [rsp+218h+Token]; Token
0x180033bc3  xor     ecx, ecx; Thread
0x180033bc5  call    cs:__imp_SetThreadToken
0x180033bcb  lea     rcx, [rsp+218h+Token]; this
0x180033bd0  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180033bd5  nop
0x180033bd6  xor     edx, edx
0x180033bd8  lea     rcx, [rsp+218h+var_1D8]
0x180033bdd  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180033be2  nop
0x180033be3  lea     rcx, [rsp+218h+var_1B8]; this
0x180033be8  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180033bed  nop
0x180033bee  lea     rax, ??_7TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@6B@; const TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::`vftable'
0x180033bf5  mov     [rsp+218h+var_198], rax
0x180033bfd  lea     rcx, [rsp+218h+var_198]
0x180033c05  call    ?Destroy@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180033c0a  lea     rcx, [rsp+218h+var_198]
0x180033c12  call    ??1?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180033c17  mov     eax, edi
0x180033c19  jmp     loc_180033D42
0x180033c1e  mov     rcx, rbx; this
0x180033c21  call    ?IsCallerAppContainer@CallerContext@Web@Authentication@Security@Internal@Windows@@QEBA_NXZ; Windows::Internal::Security::Authentication::Web::CallerContext::IsCallerAppContainer(void)
0x180033c26  mov     [rsp+218h+var_1E8], r12
0x180033c2b  mov     rax, [rsp+218h+var_1A0]
0x180033c30  mov     [rsp+218h+var_1F0], rax
0x180033c35  mov     rax, [rbx+48h]
0x180033c39  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x180033c3e  mov     rbx, [rsp+218h+string]
0x180033c43  mov     r9, rbx
0x180033c46  mov     r8, rsi
0x180033c49  mov     edx, r14d
0x180033c4c  mov     rcx, r13
0x180033c4f  call    ?GetTokenBindingPublicKeyId@TokenBroker@Authentication@Security@Internal@Windows@@YAJ_KW4TokenBindingKeyType@Web@235@PEAUIUriRuntimeClass@Foundation@5@PEAUHSTRING__@@3PEAW467235@PEAPEAUIBuffer@Streams@Storage@5@@Z; Windows::Internal::Security::Authentication::TokenBroker::GetTokenBindingPublicKeyId(unsigned __int64,Windows::Security::Authentication::Web::TokenBindingKeyType,Windows::Foundation::IUriRuntimeClass *,HSTRING__ *,HSTRING__ *,Windows::Security::Authentication::Web::TokenBindingKeyType *,Windows::Storage::Streams::IBuffer * *)
0x180033c54  mov     edi, eax
0x180033c56  test    eax, eax
0x180033c58  jns     short loc_180033CBD
0x180033c5a  mov     rcx, [rsp+218h]; this
0x180033c62  mov     r9d, eax; char *
0x180033c65  lea     r8, aOnecoreDsSecur_46; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180033c6c  mov     edx, 393h; void *
0x180033c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033c76  nop
0x180033c77  test    rbx, rbx
0x180033c7a  jz      short loc_180033C86
0x180033c7c  mov     rcx, rbx; string
0x180033c7f  call    cs:__imp_WindowsDeleteString
0x180033c85  nop
0x180033c86  lea     rcx, [rsp+218h+Token]; this
0x180033c8b  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x180033c90  nop
0x180033c91  xor     edx, edx
0x180033c93  lea     rcx, [rsp+218h+var_1D8]
0x180033c98  call    ?reset@?$unique_ptr@VCallerContext@Web@Authentication@Security@Internal@Windows@@U?$default_delete@VCallerContext@Web@Authentication@Security@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVCallerContext@Web@Authentication@Security@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::Security::Authentication::Web::CallerContext,wistd::default_delete<Windows::Internal::Security::Authentication::Web::CallerContext>>::reset(Windows::Internal::Security::Authentication::Web::CallerContext *)
0x180033c9d  nop
0x180033c9e  lea     rcx, [rsp+218h+var_1B8]; this
0x180033ca3  call    ??1CWamProfilerThreadScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::CWamProfilerThreadScope::~CWamProfilerThreadScope(void)
0x180033ca8  nop
0x180033ca9  lea     rcx, [rsp+218h+var_198]; this
0x180033cb1  call    ??1TokenBrokerInternalGetApplicationTokenBindingPublicKeyId@TbLogProvider@@QEAA@XZ; TbLogProvider::TokenBrokerInternalGetApplicationTokenBindingPublicKeyId::~TokenBrokerInternalGetApplicationTokenBindingPublicKeyId(void)
0x180033cb6  mov     eax, edi
0x180033cb8  jmp     loc_180033D42
0x180033cbd  lea     rcx, [rsp+218h+var_198]
0x180033cc5  call    ?Stop@?$ActivityBase@VTbLogProvider@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<TbLogProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180033cca  nop
0x180033ccb  test    rbx, rbx
0x180033cce  jz      short loc_180033CDA
0x180033cd0  mov     rcx, rbx; string
0x180033cd3  call    cs:__imp_WindowsDeleteString
0x180033cd9  nop
0x180033cda  cmp     [rsp+218h+var_1C0], 0
0x180033cdf  jz      short loc_180033CEE
0x180033ce1  mov     rdx, [rsp+218h+Token]; Token
0x180033ce6  xor     ecx, ecx; Thread
0x180033ce8  call    cs:__imp_SetThreadToken
0x180033cee  lea     rcx, [rsp+218h+Token]; this
0x180033cf3  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x180033cf8  nop
  ... truncated ...
```
