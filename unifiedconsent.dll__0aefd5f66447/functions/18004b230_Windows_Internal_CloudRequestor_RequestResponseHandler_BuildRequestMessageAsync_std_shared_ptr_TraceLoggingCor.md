# Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync(std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>)

- ea: `0x18004b230`
- end: `0x18004b53c`
- name: `?BuildRequestMessageAsync@RequestResponseHandler@CloudRequestor@Internal@Windows@@UEAA?AU?$IAsyncOperation@UHttpRequestMessage@Http@Web@Windows@winrt@@@Foundation@4winrt@@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@9@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@9@UIWebAccount@Credentials@Security@47@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@9@@Z`
- size: `780`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002810`
- `0x180002840`
- `0x180003384`
- `0x18000ed24`
- `0x180049ec0`
- `0x18004b230`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004b3b0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18004b3b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 *a6,
        _QWORD *a7)
{
  _QWORD *v11; // rax
  _QWORD *v12; // rdi
  __int64 v13; // rax
  _QWORD *v14; // rbx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx

  v11 = operator new(0x6D0u);
  v12 = v11 + 14;
  v11[207] = a1;
  v11[208] = 0;
  v11[209] = 0;
  v11[208] = *a3;
  v11[209] = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v11[210] = 0;
  v11[211] = 0;
  v11[210] = *a4;
  v11[211] = a4[1];
  *a4 = 0;
  a4[1] = 0;
  v11[212] = 0;
  v11[213] = 0;
  v11[212] = *a5;
  v11[213] = a5[1];
  *a5 = 0;
  a5[1] = 0;
  v13 = *a6;
  *a6 = 0;
  v12[200] = v13;
  v12[201] = 0;
  v12[202] = 0;
  v12[201] = *a7;
  v12[202] = a7[1];
  *a7 = 0;
  a7[1] = 0;
  *v12 = Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync__ResumeCoro_1;
  *((_DWORD *)v12 + 2) = 65538;
  v14 = v12 - 14;
  memset_0(v12 - 14, 0, 0x70u);
  v14[2] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>>::`vftable';
  v14[3] = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  v14[1] = 1;
  v14[4] = 0;
  v14[5] = 0;
  *((_BYTE *)v14 + 48) = 0;
  *v14 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,void>::`vftable';
  v14[7] = 0;
  v14[8] = 0;
  __ExceptionPtrCreate(v12 - 7);
  v14[9] = 0;
  v14[10] = 0;
  v14[11] = 0;
  *((_DWORD *)v14 + 24) = 0;
  *((_BYTE *)v14 + 100) = 0;
  *v14 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type::`vftable';
  v14[13] = 0;
  *a2 = v12 - 12;
  if ( v12 != (_QWORD *)96 )
    (*(void (__fastcall **)(_QWORD *))(v14[2] + 8LL))(v14 + 2);
  *((_BYTE *)v12 + 1536) = 0;
  Windows::Internal::CloudRequestor::RequestResponseHandler::BuildRequestMessageAsync__ResumeCoro_1(v12);
  v15 = (volatile signed __int32 *)a3[1];
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = (volatile signed __int32 *)a4[1];
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v17 = (volatile signed __int32 *)a5[1];
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  if ( *a6 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a6);
  v18 = (volatile signed __int32 *)a7[1];
  if ( v18 )
  {
    if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18004b230  mov     rax, rsp
0x18004b233  mov     [rax+8], rbx
0x18004b237  mov     [rax+20h], r9
0x18004b23b  mov     [rax+18h], r8
0x18004b23f  mov     [rax+10h], rdx
0x18004b243  push    rbp
0x18004b244  push    rsi
0x18004b245  push    rdi
0x18004b246  push    r12
0x18004b248  push    r13
0x18004b24a  push    r14
0x18004b24c  push    r15
0x18004b24e  sub     rsp, 40h
0x18004b252  mov     rax, cs:__security_cookie
0x18004b259  xor     rax, rsp
0x18004b25c  mov     [rsp+78h+var_40], rax
0x18004b261  mov     rsi, r9
0x18004b264  mov     r14, r8
0x18004b267  mov     r15, rdx
0x18004b26a  mov     rbx, rcx
0x18004b26d  mov     ebp, 600h
0x18004b272  lea     rcx, [rbp+0D0h]; Size
0x18004b279  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004b27e  mov     [rsp+78h+var_58], rax
0x18004b283  mov     r8d, 70h ; 'p'; Size
0x18004b289  lea     rdi, [r8+rax]
0x18004b28d  mov     [rsp+78h+var_58], rdi
0x18004b292  mov     [rdi+rbp+8], rbx
0x18004b297  xor     edx, edx; Val
0x18004b299  mov     [rdi+rbp+10h], rdx
0x18004b29e  mov     [rdi+rbp+18h], rdx
0x18004b2a3  mov     rax, [r14]
0x18004b2a6  mov     [rdi+rbp+10h], rax
0x18004b2ab  mov     rax, [r14+8]
0x18004b2af  mov     [rdi+rbp+18h], rax
0x18004b2b4  mov     [r14], rdx
0x18004b2b7  mov     [r14+8], rdx
0x18004b2bb  mov     [rdi+rbp+20h], rdx
0x18004b2c0  mov     [rdi+rbp+28h], rdx
0x18004b2c5  mov     rax, [rsi]
0x18004b2c8  mov     [rdi+rbp+20h], rax
0x18004b2cd  mov     rax, [rsi+8]
0x18004b2d1  mov     [rdi+rbp+28h], rax
0x18004b2d6  mov     [rsi], rdx
0x18004b2d9  mov     [rsi+8], rdx
0x18004b2dd  mov     [rdi+rbp+30h], rdx
0x18004b2e2  mov     [rdi+rbp+38h], rdx
0x18004b2e7  mov     r13, [rsp+78h+arg_20]
0x18004b2ef  mov     rax, [r13+0]
0x18004b2f3  mov     [rdi+rbp+30h], rax
0x18004b2f8  mov     rax, [r13+8]
0x18004b2fc  mov     [rdi+rbp+38h], rax
0x18004b301  mov     [r13+0], rdx
0x18004b305  mov     [r13+8], rdx
0x18004b309  mov     r12, [rsp+78h+arg_28]
0x18004b311  mov     rax, [r12]
0x18004b315  mov     [r12], rdx
0x18004b319  mov     [rdi+rbp+40h], rax
0x18004b31e  mov     [rdi+rbp+48h], rdx
0x18004b323  mov     [rdi+rbp+50h], rdx
0x18004b328  mov     rcx, [rsp+78h+arg_30]
0x18004b330  mov     rax, [rcx]
0x18004b333  mov     [rdi+rbp+48h], rax
0x18004b338  mov     rax, [rcx+8]
0x18004b33c  mov     [rdi+rbp+50h], rax
0x18004b341  mov     [rcx], rdx
0x18004b344  mov     [rcx+8], rdx
0x18004b348  lea     rax, Windows__Internal__CloudRequestor__RequestResponseHandler__BuildRequestMessageAsync$_ResumeCoro$1
0x18004b34f  mov     [rdi], rax
0x18004b352  mov     dword ptr [rdi+8], 10002h
0x18004b359  lea     rbx, [rdi-70h]
0x18004b35d  mov     rcx, rbx; void *
0x18004b360  call    memset_0
0x18004b365  lea     rbp, [rbx+10h]
0x18004b369  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UHttpRequestMessage@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@PEAVRequestResponseHandler@CloudRequestor@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@9@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@9@UIWebAccount@Credentials@Security@34@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@9@@experimental@std@@U?$IAsyncOperation@UHttpRequestMessage@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>>::`vftable'
0x18004b370  mov     [rbp+0], rax
0x18004b374  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UHttpRequestMessage@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@PEAVRequestResponseHandler@CloudRequestor@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@9@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@9@UIWebAccount@Credentials@Security@34@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@9@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18004b37b  mov     [rbp+8], rax
0x18004b37f  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18004b386  mov     qword ptr [rbx+8], 1
0x18004b38e  xor     edx, edx
0x18004b390  mov     [rbx+20h], rdx
0x18004b394  mov     [rbx+28h], rdx
0x18004b398  mov     [rbx+30h], dl
0x18004b39b  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UHttpRequestMessage@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@PEAVRequestResponseHandler@CloudRequestor@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@9@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@9@UIWebAccount@Credentials@Security@34@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@9@@experimental@std@@U?$IAsyncOperation@UHttpRequestMessage@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,void>::`vftable'
0x18004b3a2  mov     [rbx], rax
0x18004b3a5  lea     rcx, [rbx+38h]
0x18004b3a9  mov     [rcx], rdx
0x18004b3ac  mov     [rcx+8], rdx
0x18004b3b0  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18004b3b6  xor     ecx, ecx
0x18004b3b8  mov     [rbx+48h], rcx
0x18004b3bc  mov     [rbx+50h], rcx
0x18004b3c0  mov     [rbx+58h], rcx
0x18004b3c4  xor     eax, eax
0x18004b3c6  mov     [rbx+60h], eax
0x18004b3c9  mov     [rbx+64h], cl
0x18004b3cc  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UHttpRequestMessage@Http@Web@Windows@winrt@@@Foundation@Windows@winrt@@PEAVRequestResponseHandler@CloudRequestor@Internal@3@V?$shared_ptr@VTraceLoggingCorrelationVector@@@std@@V?$shared_ptr@URequestItem@CloudRequestor@Internal@Windows@@@9@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@9@UIWebAccount@Credentials@Security@34@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@9@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Web::Http::HttpRequestMessage>,Windows::Internal::CloudRequestor::RequestResponseHandler *,std::shared_ptr<TraceLoggingCorrelationVector>,std::shared_ptr<Windows::Internal::CloudRequestor::RequestItem>,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>>::promise_type::`vftable'
0x18004b3d3  mov     [rbx], rax
0x18004b3d6  mov     [rbx+68h], rcx
0x18004b3da  mov     [r15], rbp
0x18004b3dd  test    rbp, rbp
0x18004b3e0  jz      short loc_18004B3F3
0x18004b3e2  mov     rax, [rbp+0]
0x18004b3e6  mov     rcx, rbp
0x18004b3e9  mov     rax, [rax+8]
0x18004b3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b3f2  nop
0x18004b3f3  xor     eax, eax
0x18004b3f5  mov     ecx, 600h
0x18004b3fa  mov     [rdi+rcx], al
0x18004b3fd  mov     rcx, rdi
0x18004b400  call    Windows__Internal__CloudRequestor__RequestResponseHandler__BuildRequestMessageAsync$_ResumeCoro$1
0x18004b405  nop
0x18004b406  mov     rbx, [r14+8]
0x18004b40a  or      edi, 0FFFFFFFFh
0x18004b40d  test    rbx, rbx
0x18004b410  jz      short loc_18004B446
0x18004b412  mov     eax, edi
0x18004b414  lock xadd [rbx+8], eax
0x18004b419  add     eax, edi
0x18004b41b  jnz     short loc_18004B446
0x18004b41d  mov     rax, [rbx]
0x18004b420  mov     rcx, rbx
0x18004b423  mov     rax, [rax]
0x18004b426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b42b  mov     eax, edi
0x18004b42d  lock xadd [rbx+0Ch], eax
0x18004b432  add     eax, edi
0x18004b434  jnz     short loc_18004B446
0x18004b436  mov     rax, [rbx]
0x18004b439  mov     rcx, rbx
0x18004b43c  mov     rax, [rax+8]
0x18004b440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b445  nop
0x18004b446  mov     rbx, [rsi+8]
0x18004b44a  test    rbx, rbx
0x18004b44d  jz      short loc_18004B483
0x18004b44f  mov     eax, edi
0x18004b451  lock xadd [rbx+8], eax
0x18004b456  add     eax, edi
0x18004b458  jnz     short loc_18004B483
0x18004b45a  mov     rax, [rbx]
0x18004b45d  mov     rcx, rbx
0x18004b460  mov     rax, [rax]
0x18004b463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b468  mov     eax, edi
0x18004b46a  lock xadd [rbx+0Ch], eax
0x18004b46f  add     eax, edi
0x18004b471  jnz     short loc_18004B483
0x18004b473  mov     rax, [rbx]
0x18004b476  mov     rcx, rbx
0x18004b479  mov     rax, [rax+8]
0x18004b47d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b482  nop
0x18004b483  mov     rbx, [r13+8]
0x18004b487  test    rbx, rbx
0x18004b48a  jz      short loc_18004B4C0
0x18004b48c  mov     eax, edi
0x18004b48e  lock xadd [rbx+8], eax
0x18004b493  add     eax, edi
0x18004b495  jnz     short loc_18004B4C0
0x18004b497  mov     rax, [rbx]
0x18004b49a  mov     rcx, rbx
0x18004b49d  mov     rax, [rax]
0x18004b4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4a5  mov     eax, edi
0x18004b4a7  lock xadd [rbx+0Ch], eax
0x18004b4ac  add     eax, edi
0x18004b4ae  jnz     short loc_18004B4C0
0x18004b4b0  mov     rax, [rbx]
0x18004b4b3  mov     rcx, rbx
0x18004b4b6  mov     rax, [rax+8]
0x18004b4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4bf  nop
0x18004b4c0  cmp     qword ptr [r12], 0
0x18004b4c5  jz      short loc_18004B4D0
0x18004b4c7  mov     rcx, r12
0x18004b4ca  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18004b4cf  nop
0x18004b4d0  mov     rbx, [rsp+78h+arg_30]
0x18004b4d8  mov     rbx, [rbx+8]
0x18004b4dc  test    rbx, rbx
0x18004b4df  jz      short loc_18004B514
0x18004b4e1  mov     eax, edi
0x18004b4e3  lock xadd [rbx+8], eax
0x18004b4e8  add     eax, edi
0x18004b4ea  jnz     short loc_18004B514
0x18004b4ec  mov     rax, [rbx]
0x18004b4ef  mov     rcx, rbx
0x18004b4f2  mov     rax, [rax]
0x18004b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b4fa  mov     eax, edi
0x18004b4fc  lock xadd [rbx+0Ch], eax
0x18004b501  add     eax, edi
0x18004b503  jnz     short loc_18004B514
0x18004b505  mov     rax, [rbx]
0x18004b508  mov     rcx, rbx
0x18004b50b  mov     rax, [rax+8]
0x18004b50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b514  mov     rax, r15
0x18004b517  mov     rcx, [rsp+78h+var_40]
0x18004b51c  xor     rcx, rsp; StackCookie
0x18004b51f  call    __security_check_cookie
0x18004b524  mov     rbx, [rsp+78h+arg_0]
0x18004b52c  add     rsp, 40h
0x18004b530  pop     r15
0x18004b532  pop     r14
0x18004b534  pop     r13
0x18004b536  pop     r12
0x18004b538  pop     rdi
0x18004b539  pop     rsi
0x18004b53a  pop     rbp
0x18004b53b  retn
```
