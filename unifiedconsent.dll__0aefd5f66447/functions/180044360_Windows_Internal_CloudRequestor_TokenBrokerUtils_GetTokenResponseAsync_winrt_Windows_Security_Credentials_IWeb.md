# Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync(winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring)

- ea: `0x180044360`
- end: `0x180044536`
- name: `?GetTokenResponseAsync@TokenBrokerUtils@CloudRequestor@Internal@Windows@@UEAA?AU?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@4winrt@@UIWebAccount@Credentials@Security@47@Uhstring@7@1@Z`
- size: `470`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002840`
- `0x180003384`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000ed24`
- `0x180043aa0`
- `0x180044360`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044452`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180044452`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044524`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004452f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180044524`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004452f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        volatile signed __int32 **a4,
        volatile signed __int32 **a5)
{
  _QWORD *v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rax
  volatile signed __int32 *v12; // rax
  volatile signed __int32 *v13; // rax
  __int64 v14; // rbx
  volatile signed __int32 *v15; // rbx
  int v16; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v18; // rbx
  int v19; // edi
  HANDLE v20; // rax

  v9 = operator new(0x2C0u);
  v10 = (__int64)(v9 + 14);
  v9[83] = a1;
  v11 = *a3;
  *a3 = 0;
  *(_QWORD *)(v10 + 560) = v11;
  v12 = *a4;
  *a4 = 0;
  *(_QWORD *)(v10 + 568) = v12;
  v13 = *a5;
  *a5 = 0;
  *(_QWORD *)(v10 + 576) = v13;
  *(_QWORD *)v10 = Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync__ResumeCoro_1;
  *(_DWORD *)(v10 + 8) = 65538;
  v14 = v10 - 112;
  memset_0((void *)(v10 - 112), 0, 0x70u);
  *(_QWORD *)(v14 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>>::`vftable';
  *(_QWORD *)(v14 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(v14 + 8) = 1;
  *(_QWORD *)(v14 + 32) = 0;
  *(_QWORD *)(v14 + 40) = 0;
  *(_BYTE *)(v14 + 48) = 0;
  *(_QWORD *)v14 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,void>::`vftable';
  *(_QWORD *)(v14 + 56) = 0;
  *(_QWORD *)(v14 + 64) = 0;
  __ExceptionPtrCreate((void *)(v10 - 112 + 56));
  *(_QWORD *)(v14 + 72) = 0;
  *(_QWORD *)(v14 + 80) = 0;
  *(_QWORD *)(v14 + 88) = 0;
  *(_DWORD *)(v14 + 96) = 0;
  *(_BYTE *)(v14 + 100) = 0;
  *(_QWORD *)v14 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type::`vftable';
  *(_QWORD *)(v14 + 104) = 0;
  *a2 = v10 - 112 + 16;
  if ( v10 != 96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v14 + 16) + 8LL))(v14 + 16);
  *(_BYTE *)(v10 + 544) = 0;
  Windows::Internal::CloudRequestor::TokenBrokerUtils::GetTokenResponseAsync__ResumeCoro_1(v10);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  v15 = *a4;
  if ( *a4 )
  {
    v16 = _InterlockedDecrement(v15 + 6);
    if ( v16 )
    {
      if ( v16 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v15);
    }
    *a4 = 0;
  }
  v18 = *a5;
  if ( *a5 )
  {
    v19 = _InterlockedDecrement(v18 + 6);
    if ( v19 )
    {
      if ( v19 < 0 )
        abort();
    }
    else
    {
      v20 = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(v20, 0, (LPVOID)v18);
    }
    *a5 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180044360  mov     [rsp+arg_18], r9
0x180044365  mov     [rsp+arg_10], r8
0x18004436a  mov     [rsp+arg_8], rdx
0x18004436f  push    rbx
0x180044370  push    rbp
0x180044371  push    rsi
0x180044372  push    rdi
0x180044373  push    r12
0x180044375  push    r13
0x180044377  push    r14
0x180044379  push    r15
0x18004437b  sub     rsp, 38h
0x18004437f  mov     rsi, r9
0x180044382  mov     r14, r8
0x180044385  mov     r12, rdx
0x180044388  mov     rbx, rcx
0x18004438b  mov     r15d, 220h
0x180044391  lea     rcx, [r15+0A0h]; Size
0x180044398  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004439d  mov     [rsp+78h+arg_0], rax
0x1800443a5  mov     r8d, 70h ; 'p'; Size
0x1800443ab  lea     rdi, [r8+rax]
0x1800443af  mov     [rsp+78h+arg_0], rdi
0x1800443b7  mov     [rdi+r15+8], rbx
0x1800443bc  mov     rax, [r14]
0x1800443bf  xor     r13d, r13d
0x1800443c2  mov     [r14], r13
0x1800443c5  mov     [rdi+r15+10h], rax
0x1800443ca  mov     rax, [rsi]
0x1800443cd  mov     [rsi], r13
0x1800443d0  mov     [rdi+r15+18h], rax
0x1800443d5  mov     rbp, [rsp+78h+arg_20]
0x1800443dd  mov     rax, [rbp+0]
0x1800443e1  mov     [rbp+0], r13
0x1800443e5  mov     [rdi+r15+20h], rax
0x1800443ea  lea     rax, Windows__Internal__CloudRequestor__TokenBrokerUtils__GetTokenResponseAsync$_ResumeCoro$1
0x1800443f1  mov     [rdi], rax
0x1800443f4  mov     dword ptr [rdi+8], 10002h
0x1800443fb  lea     rbx, [rdi-70h]
0x1800443ff  xor     edx, edx; Val
0x180044401  mov     rcx, rbx; void *
0x180044404  call    memset_0
0x180044409  lea     r15, [rbx+10h]
0x18004440d  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@Uhstring@4@Uhstring@4@@experimental@std@@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>>::`vftable'
0x180044414  mov     [r15], rax
0x180044417  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@Uhstring@4@Uhstring@4@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18004441e  mov     [r15+8], rax
0x180044422  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180044429  mov     qword ptr [rbx+8], 1
0x180044431  mov     [rbx+20h], r13
0x180044435  mov     [rbx+28h], r13
0x180044439  mov     [rbx+30h], r13b
0x18004443d  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@Uhstring@4@Uhstring@4@@experimental@std@@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,void>::`vftable'
0x180044444  mov     [rbx], rax
0x180044447  lea     rcx, [rbx+38h]
0x18004444b  mov     [rcx], r13
0x18004444e  mov     [rcx+8], r13
0x180044452  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180044458  mov     [rbx+48h], r13
0x18004445c  mov     [rbx+50h], r13
0x180044460  mov     [rbx+58h], r13
0x180044464  xor     eax, eax
0x180044466  mov     [rbx+60h], eax
0x180044469  mov     [rbx+64h], r13b
0x18004446d  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UWebTokenRequestResult@Core@Web@Authentication@Security@Windows@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerUtils@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@Uhstring@4@Uhstring@4@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authentication::Web::Core::WebTokenRequestResult>,Windows::Internal::CloudRequestor::TokenBrokerUtils *,winrt::Windows::Security::Credentials::IWebAccount,winrt::hstring,winrt::hstring>::promise_type::`vftable'
0x180044474  mov     [rbx], rax
0x180044477  mov     [rbx+68h], r13
0x18004447b  mov     [r12], r15
0x18004447f  test    r15, r15
0x180044482  jz      short loc_180044494
0x180044484  mov     rax, [r15]
0x180044487  mov     rcx, r15
0x18004448a  mov     rax, [rax+8]
0x18004448e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044493  nop
0x180044494  xor     eax, eax
0x180044496  mov     ecx, 220h
0x18004449b  mov     [rdi+rcx], al
0x18004449e  mov     rcx, rdi
0x1800444a1  call    Windows__Internal__CloudRequestor__TokenBrokerUtils__GetTokenResponseAsync$_ResumeCoro$1
0x1800444a6  nop
0x1800444a7  cmp     [r14], r13
0x1800444aa  jz      short loc_1800444B5
0x1800444ac  mov     rcx, r14
0x1800444af  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800444b4  nop
0x1800444b5  mov     rbx, [rsi]
0x1800444b8  or      edi, 0FFFFFFFFh
0x1800444bb  test    rbx, rbx
0x1800444be  jz      short loc_1800444E2
0x1800444c0  mov     eax, edi
0x1800444c2  lock xadd [rbx+18h], eax
0x1800444c7  sub     eax, 1
0x1800444ca  jnz     short loc_180044520
0x1800444cc  nop
0x1800444cd  call    WINRT_IMPL_GetProcessHeap
0x1800444d2  mov     rcx, rax; hHeap
0x1800444d5  mov     r8, rbx; lpMem
0x1800444d8  xor     edx, edx; dwFlags
0x1800444da  call    WINRT_IMPL_HeapFree
0x1800444df  mov     [rsi], r13
0x1800444e2  mov     rbx, [rbp+0]
0x1800444e6  test    rbx, rbx
0x1800444e9  jz      short loc_18004450C
0x1800444eb  lock xadd [rbx+18h], edi
0x1800444f0  sub     edi, 1
0x1800444f3  jnz     short loc_18004452B
0x1800444f5  nop
0x1800444f6  call    WINRT_IMPL_GetProcessHeap
0x1800444fb  mov     rcx, rax; hHeap
0x1800444fe  mov     r8, rbx; lpMem
0x180044501  xor     edx, edx; dwFlags
0x180044503  call    WINRT_IMPL_HeapFree
0x180044508  mov     [rbp+0], r13
0x18004450c  mov     rax, r12
0x18004450f  add     rsp, 38h
0x180044513  pop     r15
0x180044515  pop     r14
0x180044517  pop     r13
0x180044519  pop     r12
0x18004451b  pop     rdi
0x18004451c  pop     rsi
0x18004451d  pop     rbp
0x18004451e  pop     rbx
0x18004451f  retn
0x180044520  test    eax, eax
0x180044522  jns     short loc_1800444DF
0x180044524  call    cs:__imp_abort
0x18004452b  test    edi, edi
0x18004452d  jns     short loc_180044508
0x18004452f  call    cs:__imp_abort
```
