# Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudAsync(winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount)

- ea: `0x180062db0`
- end: `0x1800630a9`
- name: `?GetHomeCloudAsync@HomeCloudHandler@CloudNotifications@Internal@Windows@@UEAA?AU?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@4winrt@@Uhstring@7@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@std@@UIWebAccount@Credentials@Security@47@@Z`
- size: `761`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002810`
- `0x180002840`
- `0x180003384`
- `0x1800034f7`
- `0x1800035ab`
- `0x18000ed24`
- `0x180061d10`
- `0x180062db0`
- `0x18007d010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180062f19`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180062f19`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800630a2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800630a2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudAsync(
        __int64 a1,
        _QWORD *a2,
        volatile signed __int32 **a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 *a7)
{
  _QWORD *v11; // rax
  __int64 v12; // rdi
  volatile signed __int32 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rbx
  volatile signed __int32 *v16; // rbx
  int v17; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v19; // rbx
  volatile signed __int32 *v20; // rbx
  volatile signed __int32 *v21; // rbx

  v11 = operator new(0x470u);
  v12 = (__int64)(v11 + 14);
  v11[133] = a1;
  v13 = *a3;
  *a3 = 0;
  *(_QWORD *)(v12 + 960) = v13;
  *(_QWORD *)(v12 + 968) = 0;
  *(_QWORD *)(v12 + 976) = 0;
  *(_QWORD *)(v12 + 968) = *a4;
  *(_QWORD *)(v12 + 976) = a4[1];
  *a4 = 0;
  a4[1] = 0;
  *(_QWORD *)(v12 + 984) = 0;
  *(_QWORD *)(v12 + 992) = 0;
  *(_QWORD *)(v12 + 984) = *a5;
  *(_QWORD *)(v12 + 992) = a5[1];
  *a5 = 0;
  a5[1] = 0;
  *(_QWORD *)(v12 + 1000) = 0;
  *(_QWORD *)(v12 + 1008) = 0;
  *(_QWORD *)(v12 + 1000) = *a6;
  *(_QWORD *)(v12 + 1008) = a6[1];
  *a6 = 0;
  a6[1] = 0;
  v14 = *a7;
  *a7 = 0;
  *(_QWORD *)(v12 + 1016) = v14;
  *(_QWORD *)v12 = Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudAsync__ResumeCoro_1;
  *(_DWORD *)(v12 + 8) = 65538;
  v15 = v12 - 112;
  memset_0((void *)(v12 - 112), 0, 0x70u);
  *(_QWORD *)(v15 + 16) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>>::`vftable';
  *(_QWORD *)(v15 + 24) = &winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)(v15 + 8) = 1;
  *(_QWORD *)(v15 + 32) = 0;
  *(_QWORD *)(v15 + 40) = 0;
  *(_BYTE *)(v15 + 48) = 0;
  *(_QWORD *)v15 = &winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,void>::`vftable';
  *(_QWORD *)(v15 + 56) = 0;
  *(_QWORD *)(v15 + 64) = 0;
  __ExceptionPtrCreate((void *)(v12 - 112 + 56));
  *(_QWORD *)(v15 + 72) = 0;
  *(_QWORD *)(v15 + 80) = 0;
  *(_QWORD *)(v15 + 88) = 0;
  *(_DWORD *)(v15 + 96) = 0;
  *(_BYTE *)(v15 + 100) = 0;
  *(_QWORD *)v15 = &std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type::`vftable';
  *(_QWORD *)(v15 + 104) = 0;
  *a2 = v12 - 112 + 16;
  if ( v12 != 96 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v15 + 16) + 8LL))(v15 + 16);
  *(_BYTE *)(v12 + 944) = 0;
  Windows::Internal::CloudNotifications::HomeCloudHandler::GetHomeCloudAsync__ResumeCoro_1(v12);
  v16 = *a3;
  if ( *a3 )
  {
    v17 = _InterlockedDecrement(v16 + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v16);
    }
    *a3 = 0;
  }
  v19 = (volatile signed __int32 *)a4[1];
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  v20 = (volatile signed __int32 *)a5[1];
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = (volatile signed __int32 *)a6[1];
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  if ( *a7 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a7);
  return a2;
}

```

## disassembly

```asm
0x180062db0  mov     rax, rsp
0x180062db3  mov     [rax+8], rbx
0x180062db7  mov     [rax+20h], r9
0x180062dbb  mov     [rax+18h], r8
0x180062dbf  mov     [rax+10h], rdx
0x180062dc3  push    rbp
0x180062dc4  push    rsi
0x180062dc5  push    rdi
0x180062dc6  push    r12
0x180062dc8  push    r13
0x180062dca  push    r14
0x180062dcc  push    r15
0x180062dce  sub     rsp, 40h
0x180062dd2  mov     rax, cs:__security_cookie
0x180062dd9  xor     rax, rsp
0x180062ddc  mov     [rsp+78h+var_40], rax
0x180062de1  mov     r14, r9
0x180062de4  mov     rsi, r8
0x180062de7  mov     r15, rdx
0x180062dea  mov     rbx, rcx
0x180062ded  mov     ebp, 3B0h
0x180062df2  lea     rcx, [rbp+0C0h]; Size
0x180062df9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180062dfe  mov     [rsp+78h+var_58], rax
0x180062e03  mov     r8d, 70h ; 'p'; Size
0x180062e09  lea     rdi, [r8+rax]
0x180062e0d  mov     [rsp+78h+var_58], rdi
0x180062e12  mov     [rdi+rbp+8], rbx
0x180062e17  mov     rax, [rsi]
0x180062e1a  xor     edx, edx; Val
0x180062e1c  mov     [rsi], rdx
0x180062e1f  mov     [rdi+rbp+10h], rax
0x180062e24  mov     [rdi+rbp+18h], rdx
0x180062e29  mov     [rdi+rbp+20h], rdx
0x180062e2e  mov     rax, [r14]
0x180062e31  mov     [rdi+rbp+18h], rax
0x180062e36  mov     rax, [r14+8]
0x180062e3a  mov     [rdi+rbp+20h], rax
0x180062e3f  mov     [r14], rdx
0x180062e42  mov     [r14+8], rdx
0x180062e46  mov     [rdi+rbp+28h], rdx
0x180062e4b  mov     [rdi+rbp+30h], rdx
0x180062e50  mov     r13, [rsp+78h+arg_20]
0x180062e58  mov     rax, [r13+0]
0x180062e5c  mov     [rdi+rbp+28h], rax
0x180062e61  mov     rax, [r13+8]
0x180062e65  mov     [rdi+rbp+30h], rax
0x180062e6a  mov     [r13+0], rdx
0x180062e6e  mov     [r13+8], rdx
0x180062e72  mov     [rdi+rbp+38h], rdx
0x180062e77  mov     [rdi+rbp+40h], rdx
0x180062e7c  mov     rcx, [rsp+78h+arg_28]
0x180062e84  mov     rax, [rcx]
0x180062e87  mov     [rdi+rbp+38h], rax
0x180062e8c  mov     rax, [rcx+8]
0x180062e90  mov     [rdi+rbp+40h], rax
0x180062e95  mov     [rcx], rdx
0x180062e98  mov     [rcx+8], rdx
0x180062e9c  mov     r12, [rsp+78h+arg_30]
0x180062ea4  mov     rax, [r12]
0x180062ea8  mov     [r12], rdx
0x180062eac  mov     [rdi+rbp+48h], rax
0x180062eb1  lea     rax, Windows__Internal__CloudNotifications__HomeCloudHandler__GetHomeCloudAsync$_ResumeCoro$1
0x180062eb8  mov     [rdi], rax
0x180062ebb  mov     dword ptr [rdi+8], 10002h
0x180062ec2  lea     rbx, [rdi-70h]
0x180062ec6  mov     rcx, rbx; void *
0x180062ec9  call    memset_0
0x180062ece  lea     rbp, [rbx+10h]
0x180062ed2  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@PEAVHomeCloudHandler@CloudNotifications@Internal@3@Uhstring@4@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@std@@UIWebAccount@Credentials@Security@34@@experimental@std@@U?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>>::`vftable'
0x180062ed9  mov     [rbp+0], rax
0x180062edd  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@PEAVHomeCloudHandler@CloudNotifications@Internal@3@Uhstring@4@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@std@@UIWebAccount@Credentials@Security@34@@experimental@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x180062ee4  mov     [rbp+8], rax
0x180062ee8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180062eef  mov     qword ptr [rbx+8], 1
0x180062ef7  xor     edx, edx
0x180062ef9  mov     [rbx+20h], rdx
0x180062efd  mov     [rbx+28h], rdx
0x180062f01  mov     [rbx+30h], dl
0x180062f04  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@PEAVHomeCloudHandler@CloudNotifications@Internal@3@Uhstring@4@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@std@@UIWebAccount@Credentials@Security@34@@experimental@std@@U?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,void>::`vftable'
0x180062f0b  mov     [rbx], rax
0x180062f0e  lea     rcx, [rbx+38h]
0x180062f12  mov     [rcx], rdx
0x180062f15  mov     [rcx+8], rdx
0x180062f19  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180062f1f  xor     ecx, ecx
0x180062f21  mov     [rbx+48h], rcx
0x180062f25  mov     [rbx+50h], rcx
0x180062f29  mov     [rbx+58h], rcx
0x180062f2d  xor     eax, eax
0x180062f2f  mov     [rbx+60h], eax
0x180062f32  mov     [rbx+64h], cl
0x180062f35  lea     rax, ??_7promise_type@?$coroutine_traits@U?$IAsyncOperation@UUri@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@PEAVHomeCloudHandler@CloudNotifications@Internal@3@Uhstring@4@V?$shared_ptr@UServiceInfo@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIServiceConfiguration@CloudRequestor@Internal@Windows@@@std@@V?$shared_ptr@VIHttpClient@CloudRequestor@Internal@Windows@@@std@@UIWebAccount@Credentials@Security@34@@experimental@std@@6B@; const std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Uri>,Windows::Internal::CloudNotifications::HomeCloudHandler *,winrt::hstring,std::shared_ptr<Windows::Internal::CloudRequestor::ServiceInfo>,std::shared_ptr<Windows::Internal::CloudRequestor::IServiceConfiguration>,std::shared_ptr<Windows::Internal::CloudRequestor::IHttpClient>,winrt::Windows::Security::Credentials::IWebAccount>::promise_type::`vftable'
0x180062f3c  mov     [rbx], rax
0x180062f3f  mov     [rbx+68h], rcx
0x180062f43  mov     [r15], rbp
0x180062f46  test    rbp, rbp
0x180062f49  jz      short loc_180062F5C
0x180062f4b  mov     rax, [rbp+0]
0x180062f4f  mov     rcx, rbp
0x180062f52  mov     rax, [rax+8]
0x180062f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f5b  nop
0x180062f5c  xor     eax, eax
0x180062f5e  mov     ecx, 3B0h
0x180062f63  mov     [rdi+rcx], al
0x180062f66  mov     rcx, rdi
0x180062f69  call    Windows__Internal__CloudNotifications__HomeCloudHandler__GetHomeCloudAsync$_ResumeCoro$1
0x180062f6e  nop
0x180062f6f  mov     rbx, [rsi]
0x180062f72  or      edi, 0FFFFFFFFh
0x180062f75  test    rbx, rbx
0x180062f78  jz      short loc_180062FA4
0x180062f7a  mov     eax, edi
0x180062f7c  lock xadd [rbx+18h], eax
0x180062f81  sub     eax, 1
0x180062f84  jnz     loc_18006309A
0x180062f8a  nop
0x180062f8b  call    WINRT_IMPL_GetProcessHeap
0x180062f90  mov     rcx, rax; hHeap
0x180062f93  mov     r8, rbx; lpMem
0x180062f96  xor     edx, edx; dwFlags
0x180062f98  call    WINRT_IMPL_HeapFree
0x180062f9d  mov     qword ptr [rsi], 0
0x180062fa4  mov     rbx, [r14+8]
0x180062fa8  test    rbx, rbx
0x180062fab  jz      short loc_180062FE1
0x180062fad  mov     eax, edi
0x180062faf  lock xadd [rbx+8], eax
0x180062fb4  add     eax, edi
0x180062fb6  jnz     short loc_180062FE1
0x180062fb8  mov     rax, [rbx]
0x180062fbb  mov     rcx, rbx
0x180062fbe  mov     rax, [rax]
0x180062fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062fc6  mov     eax, edi
0x180062fc8  lock xadd [rbx+0Ch], eax
0x180062fcd  add     eax, edi
0x180062fcf  jnz     short loc_180062FE1
0x180062fd1  mov     rax, [rbx]
0x180062fd4  mov     rcx, rbx
0x180062fd7  mov     rax, [rax+8]
0x180062fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062fe0  nop
0x180062fe1  mov     rbx, [r13+8]
0x180062fe5  test    rbx, rbx
0x180062fe8  jz      short loc_18006301E
0x180062fea  mov     eax, edi
0x180062fec  lock xadd [rbx+8], eax
0x180062ff1  add     eax, edi
0x180062ff3  jnz     short loc_18006301E
0x180062ff5  mov     rax, [rbx]
0x180062ff8  mov     rcx, rbx
0x180062ffb  mov     rax, [rax]
0x180062ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063003  mov     eax, edi
0x180063005  lock xadd [rbx+0Ch], eax
0x18006300a  add     eax, edi
0x18006300c  jnz     short loc_18006301E
0x18006300e  mov     rax, [rbx]
0x180063011  mov     rcx, rbx
0x180063014  mov     rax, [rax+8]
0x180063018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006301d  nop
0x18006301e  mov     rbx, [rsp+78h+arg_28]
0x180063026  mov     rbx, [rbx+8]
0x18006302a  test    rbx, rbx
0x18006302d  jz      short loc_180063063
0x18006302f  mov     eax, edi
0x180063031  lock xadd [rbx+8], eax
0x180063036  add     eax, edi
0x180063038  jnz     short loc_180063063
0x18006303a  mov     rax, [rbx]
0x18006303d  mov     rcx, rbx
0x180063040  mov     rax, [rax]
0x180063043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063048  mov     eax, edi
0x18006304a  lock xadd [rbx+0Ch], eax
0x18006304f  add     eax, edi
0x180063051  jnz     short loc_180063063
0x180063053  mov     rax, [rbx]
0x180063056  mov     rcx, rbx
0x180063059  mov     rax, [rax+8]
0x18006305d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063062  nop
0x180063063  cmp     qword ptr [r12], 0
0x180063068  jz      short loc_180063072
0x18006306a  mov     rcx, r12
0x18006306d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180063072  mov     rax, r15
0x180063075  mov     rcx, [rsp+78h+var_40]
0x18006307a  xor     rcx, rsp; StackCookie
0x18006307d  call    __security_check_cookie
0x180063082  mov     rbx, [rsp+78h+arg_0]
0x18006308a  add     rsp, 40h
0x18006308e  pop     r15
0x180063090  pop     r14
0x180063092  pop     r13
0x180063094  pop     r12
0x180063096  pop     rdi
0x180063097  pop     rsi
0x180063098  pop     rbp
0x180063099  retn
0x18006309a  test    eax, eax
0x18006309c  jns     loc_180062F9D
0x1800630a2  call    cs:__imp_abort
```
