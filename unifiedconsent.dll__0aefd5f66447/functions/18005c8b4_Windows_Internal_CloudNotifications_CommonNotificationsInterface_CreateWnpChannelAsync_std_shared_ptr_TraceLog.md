# Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateWnpChannelAsync(std::shared_ptr<TraceLoggingCorrelationVector>)

- ea: `0x18005c8b4`
- end: `0x18005ca2e`
- name: `?CreateWnpChannelAsync@CommonNotificationsInterface@CloudNotifications@Internal@Windows@@AEAA?AU?$IAsyncOperation@Uhstring@winrt@@@Foundation@4winrt@@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@Z`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180059840`

## callees

- `0x180002840`
- `0x180003384`
- `0x18005ba20`
- `0x18005c8b4`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005c98d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18005c98d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateWnpChannelAsync(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rdi
  _QWORD *v8; // rbx
  volatile signed __int32 *v9; // rbx

  v6 = operator new(0x2D0u);
  v7 = (__int64)(v6 + 14);
  v6[87] = a1;
  v6[88] = 0;
  v6[89] = 0;
  v6[88] = *a3;
  v6[89] = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v6[14] = Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateWnpChannelAsync__ResumeCoro_1;
  *((_DWORD *)v6 + 30) = 65538;
  v8 = v6;
  memset_0(v6, 0, 0x70u);
  v8[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>>::`vftable';
  v8[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v8[1] = 1;
  v8[4] = 0;
  v8[5] = 0;
  *((_BYTE *)v8 + 48) = 0;
  *v8 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,void>::`vftable';
  v8[7] = 0;
  v8[8] = 0;
  __ExceptionPtrCreate(v8 + 7);
  v8[9] = 0;
  v8[10] = 0;
  v8[11] = 0;
  *((_DWORD *)v8 + 24) = 0;
  *((_BYTE *)v8 + 100) = 0;
  *v8 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type::`vftable';
  v8[13] = 0;
  *a2 = v8 + 2;
  if ( v8 != (_QWORD *)-16LL )
    (*(void (__fastcall **)(_QWORD *))(v8[2] + 8LL))(v8 + 2);
  *(_BYTE *)(v7 + 576) = 0;
  Windows::Internal::CloudNotifications::CommonNotificationsInterface::CreateWnpChannelAsync__ResumeCoro_1(v7);
  v9 = (volatile signed __int32 *)a3[1];
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18005c8b4  mov     [rsp+arg_10], r8
0x18005c8b9  mov     [rsp+arg_8], rdx
0x18005c8be  push    rbx
0x18005c8bf  push    rbp
0x18005c8c0  push    rsi
0x18005c8c1  push    rdi
0x18005c8c2  push    r12
0x18005c8c4  push    r14
0x18005c8c6  push    r15
0x18005c8c8  sub     rsp, 30h
0x18005c8cc  mov     rsi, r8
0x18005c8cf  mov     r14, rdx
0x18005c8d2  mov     rbx, rcx
0x18005c8d5  mov     r12d, 240h
0x18005c8db  lea     rcx, [r12+90h]; Size
0x18005c8e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c8e8  mov     [rsp+68h+arg_0], rax
0x18005c8ed  mov     r8d, 70h ; 'p'; Size
0x18005c8f3  lea     rdi, [r8+rax]
0x18005c8f7  mov     [rsp+68h+arg_0], rdi
0x18005c8fc  mov     [rdi+r12+8], rbx
0x18005c901  xor     ebp, ebp
0x18005c903  mov     [rdi+r12+10h], rbp
0x18005c908  mov     [rdi+r12+18h], rbp
0x18005c90d  mov     rax, [rsi]
0x18005c910  mov     [rdi+r12+10h], rax
0x18005c915  mov     rax, [rsi+8]
0x18005c919  mov     [rdi+r12+18h], rax
0x18005c91e  mov     [rsi], rbp
0x18005c921  mov     [rsi+8], rbp
0x18005c925  lea     rax, Windows__Internal__CloudNotifications__CommonNotificationsInterface__CreateWnpChannelAsync$_ResumeCoro$1
0x18005c92c  mov     [rdi], rax
0x18005c92f  mov     dword ptr [rdi+8], 10002h
0x18005c936  lea     rbx, [rdi-70h]
0x18005c93a  xor     edx, edx; Val
0x18005c93c  mov     rcx, rbx; void *
0x18005c93f  call    memset_0
0x18005c944  lea     r15, [rbx+10h]
0x18005c948  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>>::`vftable'
0x18005c94f  mov     [r15], rax
0x18005c952  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18005c959  mov     [r15+8], rax
0x18005c95d  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005c964  mov     qword ptr [rbx+8], 1
0x18005c96c  mov     [rbx+20h], rbp
0x18005c970  mov     [rbx+28h], rbp
0x18005c974  mov     [rbx+30h], bpl
0x18005c978  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,void>::`vftable'
0x18005c97f  mov     [rbx], rax
0x18005c982  lea     rcx, [rbx+38h]
0x18005c986  mov     [rcx], rbp
0x18005c989  mov     [rcx+8], rbp
0x18005c98d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18005c993  mov     [rbx+48h], rbp
0x18005c997  mov     [rbx+50h], rbp
0x18005c99b  mov     [rbx+58h], rbp
0x18005c99f  xor     eax, eax
0x18005c9a1  mov     [rbx+60h], eax
0x18005c9a4  mov     [rbx+64h], bpl
0x18005c9a8  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type::`vftable'
0x18005c9af  mov     [rbx], rax
0x18005c9b2  mov     [rbx+68h], rbp
0x18005c9b6  mov     [r14], r15
0x18005c9b9  test    r15, r15
0x18005c9bc  jz      short loc_18005C9CE
0x18005c9be  mov     rax, [r15]
0x18005c9c1  mov     rcx, r15
0x18005c9c4  mov     rax, [rax+8]
0x18005c9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c9cd  nop
0x18005c9ce  xor     eax, eax
0x18005c9d0  mov     [rdi+r12], al
0x18005c9d4  mov     rcx, rdi
0x18005c9d7  call    Windows__Internal__CloudNotifications__CommonNotificationsInterface__CreateWnpChannelAsync$_ResumeCoro$1
0x18005c9dc  nop
0x18005c9dd  mov     rbx, [rsi+8]
0x18005c9e1  test    rbx, rbx
0x18005c9e4  jz      short loc_18005CA1C
0x18005c9e6  or      edi, 0FFFFFFFFh
0x18005c9e9  mov     eax, edi
0x18005c9eb  lock xadd [rbx+8], eax
0x18005c9f0  add     eax, edi
0x18005c9f2  jnz     short loc_18005CA1C
0x18005c9f4  mov     rax, [rbx]
0x18005c9f7  mov     rcx, rbx
0x18005c9fa  mov     rax, [rax]
0x18005c9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca02  mov     eax, edi
0x18005ca04  lock xadd [rbx+0Ch], eax
0x18005ca09  add     eax, edi
0x18005ca0b  jnz     short loc_18005CA1C
0x18005ca0d  mov     rax, [rbx]
0x18005ca10  mov     rcx, rbx
0x18005ca13  mov     rax, [rax+8]
0x18005ca17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ca1c  mov     rax, r14
0x18005ca1f  add     rsp, 30h
0x18005ca23  pop     r15
0x18005ca25  pop     r14
0x18005ca27  pop     r12
0x18005ca29  pop     rdi
0x18005ca2a  pop     rsi
0x18005ca2b  pop     rbp
0x18005ca2c  pop     rbx
0x18005ca2d  retn
```
