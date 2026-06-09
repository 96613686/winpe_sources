# Windows::Internal::CloudRequestor::TokenBrokerHandler::GetTokenAsync(winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>)

- ea: `0x1800438d0`
- end: `0x180043a97`
- name: `?GetTokenAsync@TokenBrokerHandler@CloudRequestor@Internal@Windows@@UEAA?AU?$IAsyncOperation@Uhstring@winrt@@@Foundation@4winrt@@UIWebAccount@Credentials@Security@47@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@Z`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002810`
- `0x180002840`
- `0x180003384`
- `0x18000ed24`
- `0x180043000`
- `0x1800438d0`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800439d1`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800439d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Windows::Internal::CloudRequestor::TokenBrokerHandler::GetTokenAsync(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        _QWORD *a4)
{
  _QWORD *v8; // rax
  char *v9; // rdi
  __int64 v10; // rax
  char *v11; // rbx
  volatile signed __int32 *v12; // rbx

  v8 = operator new(0x370u);
  v9 = (char *)(v8 + 14);
  v8[105] = a1;
  v10 = *a3;
  *a3 = 0;
  *((_QWORD *)v9 + 92) = v10;
  *((_QWORD *)v9 + 93) = 0;
  *((_QWORD *)v9 + 94) = 0;
  *((_QWORD *)v9 + 93) = *a4;
  *((_QWORD *)v9 + 94) = a4[1];
  *a4 = 0;
  a4[1] = 0;
  *(_QWORD *)v9 = Windows::Internal::CloudRequestor::TokenBrokerHandler::GetTokenAsync__ResumeCoro_1;
  *((_DWORD *)v9 + 2) = 65538;
  v11 = v9 - 112;
  memset_0(v9 - 112, 0, 0x70u);
  *((_QWORD *)v11 + 2) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>>::`vftable';
  *((_QWORD *)v11 + 3) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *((_QWORD *)v11 + 1) = 1;
  *((_QWORD *)v11 + 4) = 0;
  *((_QWORD *)v11 + 5) = 0;
  v11[48] = 0;
  *(_QWORD *)v11 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,void>::`vftable';
  *((_QWORD *)v11 + 7) = 0;
  *((_QWORD *)v11 + 8) = 0;
  __ExceptionPtrCreate(v9 - 56);
  *((_QWORD *)v11 + 9) = 0;
  *((_QWORD *)v11 + 10) = 0;
  *((_QWORD *)v11 + 11) = 0;
  *((_DWORD *)v11 + 24) = 0;
  v11[100] = 0;
  *(_QWORD *)v11 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type::`vftable';
  *((_QWORD *)v11 + 13) = 0;
  *a2 = v9 - 96;
  if ( v9 != (char *)96 )
    (*(void (__fastcall **)(char *))(*((_QWORD *)v11 + 2) + 8LL))(v11 + 16);
  v9[720] = 0;
  Windows::Internal::CloudRequestor::TokenBrokerHandler::GetTokenAsync__ResumeCoro_1(v9);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  v12 = (volatile signed __int32 *)a4[1];
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800438d0  mov     rax, rsp
0x1800438d3  mov     [rax+8], rbx
0x1800438d7  mov     [rax+20h], r9
0x1800438db  mov     [rax+18h], r8
0x1800438df  mov     [rax+10h], rdx
0x1800438e3  push    rbp
0x1800438e4  push    rsi
0x1800438e5  push    rdi
0x1800438e6  push    r12
0x1800438e8  push    r13
0x1800438ea  push    r14
0x1800438ec  push    r15
0x1800438ee  sub     rsp, 40h
0x1800438f2  mov     rax, cs:__security_cookie
0x1800438f9  xor     rax, rsp
0x1800438fc  mov     [rsp+78h+var_40], rax
0x180043901  mov     r14, r9
0x180043904  mov     rsi, r8
0x180043907  mov     r15, rdx
0x18004390a  mov     rbx, rcx
0x18004390d  mov     r13d, 2D0h
0x180043913  lea     rcx, [r13+0A0h]; Size
0x18004391a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004391f  mov     [rsp+78h+var_58], rax
0x180043924  mov     r8d, 70h ; 'p'; Size
0x18004392a  lea     rdi, [r8+rax]
0x18004392e  mov     [rsp+78h+var_58], rdi
0x180043933  mov     [rdi+r13+8], rbx
0x180043938  mov     rax, [rsi]
0x18004393b  xor     r12d, r12d
0x18004393e  mov     [rsi], r12
0x180043941  mov     [rdi+r13+10h], rax
0x180043946  mov     [rdi+r13+18h], r12
0x18004394b  mov     [rdi+r13+20h], r12
0x180043950  mov     rax, [r14]
0x180043953  mov     [rdi+r13+18h], rax
0x180043958  mov     rax, [r14+8]
0x18004395c  mov     [rdi+r13+20h], rax
0x180043961  mov     [r14], r12
0x180043964  mov     [r14+8], r12
0x180043968  lea     rax, Windows__Internal__CloudRequestor__TokenBrokerHandler__GetTokenAsync$_ResumeCoro$1
0x18004396f  mov     [rdi], rax
0x180043972  mov     dword ptr [rdi+8], 10002h
0x180043979  lea     rbx, [rdi-70h]
0x18004397d  xor     edx, edx; Val
0x18004397f  mov     rcx, rbx; void *
0x180043982  call    memset_0
0x180043987  lea     rbp, [rbx+10h]
0x18004398b  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>>::`vftable'
0x180043992  mov     [rbp+0], rax
0x180043996  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18004399d  mov     [rbp+8], rax
0x1800439a1  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800439a8  mov     qword ptr [rbx+8], 1
0x1800439b0  mov     [rbx+20h], r12
0x1800439b4  mov     [rbx+28h], r12
0x1800439b8  mov     [rbx+30h], r12b
0x1800439bc  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,void>::`vftable'
0x1800439c3  mov     [rbx], rax
0x1800439c6  lea     rcx, [rbx+38h]
0x1800439ca  mov     [rcx], r12
0x1800439cd  mov     [rcx+8], r12
0x1800439d1  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800439d7  mov     [rbx+48h], r12
0x1800439db  mov     [rbx+50h], r12
0x1800439df  mov     [rbx+58h], r12
0x1800439e3  xor     eax, eax
0x1800439e5  mov     [rbx+60h], eax
0x1800439e8  mov     [rbx+64h], r12b
0x1800439ec  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type::`vftable'
0x1800439f3  mov     [rbx], rax
0x1800439f6  mov     [rbx+68h], r12
0x1800439fa  mov     [r15], rbp
0x1800439fd  test    rbp, rbp
0x180043a00  jz      short loc_180043A13
0x180043a02  mov     rax, [rbp+0]
0x180043a06  mov     rcx, rbp
0x180043a09  mov     rax, [rax+8]
0x180043a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a12  nop
0x180043a13  xor     eax, eax
0x180043a15  mov     [rdi+r13], al
0x180043a19  mov     rcx, rdi
0x180043a1c  call    Windows__Internal__CloudRequestor__TokenBrokerHandler__GetTokenAsync$_ResumeCoro$1
0x180043a21  nop
0x180043a22  cmp     [rsi], r12
0x180043a25  jz      short loc_180043A30
0x180043a27  mov     rcx, rsi
0x180043a2a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180043a2f  nop
0x180043a30  mov     rbx, [r14+8]
0x180043a34  test    rbx, rbx
0x180043a37  jz      short loc_180043A6F
0x180043a39  or      edi, 0FFFFFFFFh
0x180043a3c  mov     eax, edi
0x180043a3e  lock xadd [rbx+8], eax
0x180043a43  add     eax, edi
0x180043a45  jnz     short loc_180043A6F
0x180043a47  mov     rax, [rbx]
0x180043a4a  mov     rcx, rbx
0x180043a4d  mov     rax, [rax]
0x180043a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a55  mov     eax, edi
0x180043a57  lock xadd [rbx+0Ch], eax
0x180043a5c  add     eax, edi
0x180043a5e  jnz     short loc_180043A6F
0x180043a60  mov     rax, [rbx]
0x180043a63  mov     rcx, rbx
0x180043a66  mov     rax, [rax+8]
0x180043a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043a6f  mov     rax, r15
0x180043a72  mov     rcx, [rsp+78h+var_40]
0x180043a77  xor     rcx, rsp; StackCookie
0x180043a7a  call    __security_check_cookie
0x180043a7f  mov     rbx, [rsp+78h+arg_0]
0x180043a87  add     rsp, 40h
0x180043a8b  pop     r15
0x180043a8d  pop     r14
0x180043a8f  pop     r13
0x180043a91  pop     r12
0x180043a93  pop     rdi
0x180043a94  pop     rsi
0x180043a95  pop     rbp
0x180043a96  retn
```
