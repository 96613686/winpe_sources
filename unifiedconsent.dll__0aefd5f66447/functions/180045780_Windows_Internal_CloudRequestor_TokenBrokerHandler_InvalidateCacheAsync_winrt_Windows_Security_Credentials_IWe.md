# Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync(winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>)

- ea: `0x180045780`
- end: `0x180045947`
- name: `?InvalidateCacheAsync@TokenBrokerHandler@CloudRequestor@Internal@Windows@@UEAA?AU?$IAsyncOperation@Uhresult@winrt@@@Foundation@4winrt@@UIWebAccount@Credentials@Security@47@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@Z`
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
- `0x1800446f0`
- `0x180045780`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180045881`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180045881`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync(
        __int64 a1,
        _QWORD *a2,
        __int64 *a3,
        _QWORD *a4)
{
  _QWORD *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rbx
  volatile signed __int32 *v12; // rbx

  v8 = operator new(0x380u);
  v9 = (__int64)(v8 + 14);
  v8[107] = a1;
  v10 = *a3;
  *a3 = 0;
  *(_QWORD *)(v9 + 752) = v10;
  *(_QWORD *)(v9 + 760) = 0;
  *(_QWORD *)(v9 + 768) = 0;
  *(_QWORD *)(v9 + 760) = *a4;
  *(_QWORD *)(v9 + 768) = a4[1];
  *a4 = 0;
  a4[1] = 0;
  *(_QWORD *)v9 = Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync__ResumeCoro_1;
  *(_DWORD *)(v9 + 8) = 65538;
  v11 = v9 - 112;
  memset_0((void *)(v9 - 112), 0, 0x70u);
  *(_QWORD *)(v11 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>>::`vftable';
  *(_QWORD *)(v11 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(v11 + 8) = 1;
  *(_QWORD *)(v11 + 32) = 0;
  *(_QWORD *)(v11 + 40) = 0;
  *(_BYTE *)(v11 + 48) = 0;
  *(_QWORD *)v11 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,void>::`vftable';
  *(_QWORD *)(v11 + 56) = 0;
  *(_QWORD *)(v11 + 64) = 0;
  __ExceptionPtrCreate((void *)(v9 - 112 + 56));
  *(_QWORD *)(v11 + 72) = 0;
  *(_QWORD *)(v11 + 80) = 0;
  *(_QWORD *)(v11 + 88) = 0;
  *(_DWORD *)(v11 + 96) = 0;
  *(_BYTE *)(v11 + 100) = 0;
  *(_QWORD *)v11 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type::`vftable';
  *(_DWORD *)(v11 + 104) = 0;
  *a2 = v9 - 112 + 16;
  if ( v9 != 96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 16) + 8LL))(v11 + 16);
  *(_BYTE *)(v9 + 736) = 0;
  Windows::Internal::CloudRequestor::TokenBrokerHandler::InvalidateCacheAsync__ResumeCoro_1(v9);
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
0x180045780  mov     rax, rsp
0x180045783  mov     [rax+8], rbx
0x180045787  mov     [rax+20h], r9
0x18004578b  mov     [rax+18h], r8
0x18004578f  mov     [rax+10h], rdx
0x180045793  push    rbp
0x180045794  push    rsi
0x180045795  push    rdi
0x180045796  push    r12
0x180045798  push    r13
0x18004579a  push    r14
0x18004579c  push    r15
0x18004579e  sub     rsp, 40h
0x1800457a2  mov     rax, cs:__security_cookie
0x1800457a9  xor     rax, rsp
0x1800457ac  mov     [rsp+78h+var_40], rax
0x1800457b1  mov     r14, r9
0x1800457b4  mov     rsi, r8
0x1800457b7  mov     r15, rdx
0x1800457ba  mov     rbx, rcx
0x1800457bd  mov     r13d, 2E0h
0x1800457c3  lea     rcx, [r13+0A0h]; Size
0x1800457ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800457cf  mov     [rsp+78h+var_58], rax
0x1800457d4  mov     r8d, 70h ; 'p'; Size
0x1800457da  lea     rdi, [r8+rax]
0x1800457de  mov     [rsp+78h+var_58], rdi
0x1800457e3  mov     [rdi+r13+8], rbx
0x1800457e8  mov     rax, [rsi]
0x1800457eb  xor     r12d, r12d
0x1800457ee  mov     [rsi], r12
0x1800457f1  mov     [rdi+r13+10h], rax
0x1800457f6  mov     [rdi+r13+18h], r12
0x1800457fb  mov     [rdi+r13+20h], r12
0x180045800  mov     rax, [r14]
0x180045803  mov     [rdi+r13+18h], rax
0x180045808  mov     rax, [r14+8]
0x18004580c  mov     [rdi+r13+20h], rax
0x180045811  mov     [r14], r12
0x180045814  mov     [r14+8], r12
0x180045818  lea     rax, Windows__Internal__CloudRequestor__TokenBrokerHandler__InvalidateCacheAsync$_ResumeCoro$1
0x18004581f  mov     [rdi], rax
0x180045822  mov     dword ptr [rdi+8], 10002h
0x180045829  lea     rbx, [rdi-70h]
0x18004582d  xor     edx, edx; Val
0x18004582f  mov     rcx, rbx; void *
0x180045832  call    memset_0
0x180045837  lea     rbp, [rbx+10h]
0x18004583b  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhresult@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@U?$IAsyncOperation@Uhresult@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>>::`vftable'
0x180045842  mov     [rbp+0], rax
0x180045846  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhresult@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18004584d  mov     [rbp+8], rax
0x180045851  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180045858  mov     qword ptr [rbx+8], 1
0x180045860  mov     [rbx+20h], r12
0x180045864  mov     [rbx+28h], r12
0x180045868  mov     [rbx+30h], r12b
0x18004586c  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@Uhresult@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@U?$IAsyncOperation@Uhresult@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,void>::`vftable'
0x180045873  mov     [rbx], rax
0x180045876  lea     rcx, [rbx+38h]
0x18004587a  mov     [rcx], r12
0x18004587d  mov     [rcx+8], r12
0x180045881  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180045887  mov     [rbx+48h], r12
0x18004588b  mov     [rbx+50h], r12
0x18004588f  mov     [rbx+58h], r12
0x180045893  xor     eax, eax
0x180045895  mov     [rbx+60h], eax
0x180045898  mov     [rbx+64h], r12b
0x18004589c  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@Uhresult@winrt@@@Foundation@Windows@winrt@@PEAVTokenBrokerHandler@CloudRequestor@Internal@3@UIWebAccount@Credentials@Security@34@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::hresult>,Windows::Internal::CloudRequestor::TokenBrokerHandler *,winrt::Windows::Security::Credentials::IWebAccount,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>>::promise_type::`vftable'
0x1800458a3  mov     [rbx], rax
0x1800458a6  mov     [rbx+68h], r12d
0x1800458aa  mov     [r15], rbp
0x1800458ad  test    rbp, rbp
0x1800458b0  jz      short loc_1800458C3
0x1800458b2  mov     rax, [rbp+0]
0x1800458b6  mov     rcx, rbp
0x1800458b9  mov     rax, [rax+8]
0x1800458bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458c2  nop
0x1800458c3  xor     eax, eax
0x1800458c5  mov     [rdi+r13], al
0x1800458c9  mov     rcx, rdi
0x1800458cc  call    Windows__Internal__CloudRequestor__TokenBrokerHandler__InvalidateCacheAsync$_ResumeCoro$1
0x1800458d1  nop
0x1800458d2  cmp     [rsi], r12
0x1800458d5  jz      short loc_1800458E0
0x1800458d7  mov     rcx, rsi
0x1800458da  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800458df  nop
0x1800458e0  mov     rbx, [r14+8]
0x1800458e4  test    rbx, rbx
0x1800458e7  jz      short loc_18004591F
0x1800458e9  or      edi, 0FFFFFFFFh
0x1800458ec  mov     eax, edi
0x1800458ee  lock xadd [rbx+8], eax
0x1800458f3  add     eax, edi
0x1800458f5  jnz     short loc_18004591F
0x1800458f7  mov     rax, [rbx]
0x1800458fa  mov     rcx, rbx
0x1800458fd  mov     rax, [rax]
0x180045900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045905  mov     eax, edi
0x180045907  lock xadd [rbx+0Ch], eax
0x18004590c  add     eax, edi
0x18004590e  jnz     short loc_18004591F
0x180045910  mov     rax, [rbx]
0x180045913  mov     rcx, rbx
0x180045916  mov     rax, [rax+8]
0x18004591a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004591f  mov     rax, r15
0x180045922  mov     rcx, [rsp+78h+var_40]
0x180045927  xor     rcx, rsp; StackCookie
0x18004592a  call    __security_check_cookie
0x18004592f  mov     rbx, [rsp+78h+arg_0]
0x180045937  add     rsp, 40h
0x18004593b  pop     r15
0x18004593d  pop     r14
0x18004593f  pop     r13
0x180045941  pop     r12
0x180045943  pop     rdi
0x180045944  pop     rsi
0x180045945  pop     rbp
0x180045946  retn
```
