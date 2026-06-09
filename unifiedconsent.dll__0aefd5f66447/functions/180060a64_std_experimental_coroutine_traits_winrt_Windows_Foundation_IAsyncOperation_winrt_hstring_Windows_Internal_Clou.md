# std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type::promise_type(void)

- ea: `0x180060a64`
- end: `0x180060b04`
- name: `??0promise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVHomeCloudHandler@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@9@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@9@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@9@UIWebAccount@Credentials@Security@34@@experimental@std@@QEAA@XZ`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180064854`
- `0x18006670c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180060ac3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180060ac3`

## pseudocode

```c
__int64 __fastcall std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::HomeCloudHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type::promise_type(
        __int64 a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  *(_QWORD *)(a1 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>>::`vftable';
  *(_QWORD *)(a1 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(a1 + 8) = 1;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 48) = 0;
  *(_QWORD *)a1 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,void>::`vftable';
  v2 = (_QWORD *)(a1 + 56);
  *v2 = 0;
  v2[1] = 0;
  __ExceptionPtrCreate(v2);
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  *(_BYTE *)(a1 + 100) = 0;
  *(_QWORD *)a1 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type::`vftable';
  result = a1;
  *(_QWORD *)(a1 + 104) = 0;
  return result;
}

```

## disassembly

```asm
0x180060a64  push    rbx
0x180060a66  sub     rsp, 20h
0x180060a6a  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>>::`vftable'
0x180060a71  mov     rbx, rcx
0x180060a74  mov     [rcx+10h], rax
0x180060a78  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180060a7f  mov     [rcx+18h], rax
0x180060a83  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180060a8a  mov     qword ptr [rcx+8], 1
0x180060a92  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,void>::`vftable'
0x180060a99  mov     qword ptr [rcx+20h], 0
0x180060aa1  mov     qword ptr [rcx+28h], 0
0x180060aa9  mov     byte ptr [rcx+30h], 0
0x180060aad  mov     [rcx], rax
0x180060ab0  add     rcx, 38h ; '8'
0x180060ab4  mov     qword ptr [rcx], 0
0x180060abb  mov     qword ptr [rcx+8], 0
0x180060ac3  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180060ac9  xor     eax, eax
0x180060acb  mov     qword ptr [rbx+48h], 0
0x180060ad3  mov     qword ptr [rbx+50h], 0
0x180060adb  mov     qword ptr [rbx+58h], 0
0x180060ae3  mov     [rbx+60h], eax
0x180060ae6  mov     [rbx+64h], al
0x180060ae9  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@Uhstring@winrt@@@Foundation@Windows@winrt@@PEAVCommonNotificationsInterface@CloudNotifications@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hstring>,Windows::Internal::CloudNotifications::CommonNotificationsInterface *,std::shared_ptr<TraceLoggingCorrelationVector>>::promise_type::`vftable'
0x180060af0  mov     [rbx], rax
0x180060af3  mov     rax, rbx
0x180060af6  mov     qword ptr [rbx+68h], 0
0x180060afe  add     rsp, 20h
0x180060b02  pop     rbx
0x180060b03  retn
```
