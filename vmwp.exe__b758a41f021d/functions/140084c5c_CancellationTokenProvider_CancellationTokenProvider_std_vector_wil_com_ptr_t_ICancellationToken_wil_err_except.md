# CancellationTokenProvider::CancellationTokenProvider(std::vector<wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>>> const &)

- ea: `0x140084c5c`
- end: `0x140084de8`
- name: `??0CancellationTokenProvider@@QEAA@AEBV?$vector@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(std::_Mutex_base *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401ab4b0`

## callees

- `0x140028cac`
- `0x140078628`
- `0x140083990`
- `0x140084870`
- `0x140084ad4`
- `0x140084b6c`
- `0x140084bc0`
- `0x140084c14`
- `0x140084c5c`
- `0x1400859d8`
- `0x14011ea40`
- `0x1402cb010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x140084d75`
- `msvcp_win!_Mtx_unlock` at `0x140084d75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140084d42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140084d42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140084d11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140084d11`

## string_xrefs

- `0x140084da6`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x140084dbe`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x140084dd6`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CancellationTokenProvider *__fastcall CancellationTokenProvider::CancellationTokenProvider(
        CancellationTokenProvider *this,
        __int64 **a2)
{
  __int64 *v4; // rsi
  __int64 *v5; // r15
  __int64 v6; // r14
  __int64 (__fastcall *v7)(__int64, HANDLE *); // rbx
  int v8; // eax
  PTP_WAIT ThreadpoolWait; // rax
  int v11; // [rsp+20h] [rbp-40h]
  HANDLE h[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v11 = (int)this;
  CancellationTokenProvider::CancellationTokenProvider(this);
  std::_Mutex_base::lock(this);
  v4 = *a2;
  v5 = a2[1];
  while ( v4 != v5 )
  {
    v6 = *v4;
    if ( !*v4 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
        (const char *)0x80004003LL,
        v11);
    *(_OWORD *)h = 0;
    v13 = 0;
    v7 = *(__int64 (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v6 + 24LL);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &h[1],
      0);
    v8 = v7(v6, &h[1]);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x94,
        (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
        (const char *)(unsigned int)v8,
        v11);
    wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(&v13, v4);
    ThreadpoolWait = CreateThreadpoolWait(
                       (PTP_WAIT_CALLBACK)lambda_e4ffa3337851658bfdbd92f22338e347_::_lambda_invoker_cdecl_,
                       this,
                       0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
      h,
      ThreadpoolWait);
    if ( !h[0] )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
        (const char *)retaddr);
    SetThreadpoolWait((PTP_WAIT)h[0], h[1], 0);
    std::vector<CancellationTokenProvider::TrackedDetails>::push_back((char *)this + 96, h);
    CancellationTokenProvider::TrackedDetails::~TrackedDetails((CancellationTokenProvider::TrackedDetails *)h);
    ++v4;
  }
  _Mtx_unlock(this);
  return this;
}

```

## disassembly

```asm
0x140084c5c  mov     [rsp-28h+arg_10], rbx
0x140084c61  push    rbp
0x140084c62  push    rsi
0x140084c63  push    rdi
0x140084c64  push    r14
0x140084c66  push    r15
0x140084c68  mov     rbp, rsp
0x140084c6b  sub     rsp, 60h
0x140084c6f  mov     rax, cs:__security_cookie
0x140084c76  xor     rax, rsp
0x140084c79  mov     [rbp+var_10], rax
0x140084c7d  mov     rbx, rdx
0x140084c80  mov     rdi, rcx
0x140084c83  mov     qword ptr [rbp+var_40], rcx
0x140084c87  call    ??0CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::CancellationTokenProvider(void)
0x140084c8c  nop
0x140084c8d  mov     [rbp+var_30], rdi
0x140084c91  mov     rcx, rdi; this
0x140084c94  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140084c99  nop
0x140084c9a  mov     rsi, [rbx]
0x140084c9d  mov     r15, [rbx+8]
0x140084ca1  jmp     loc_140084D69
0x140084ca6  mov     r14, [rsi]
0x140084ca9  test    r14, r14
0x140084cac  setz    al
0x140084caf  mov     rcx, [rbp+28h]; this
0x140084cb3  test    al, al
0x140084cb5  jnz     loc_140084DD0
0x140084cbb  xorps   xmm0, xmm0
0x140084cbe  movdqu  xmmword ptr [rbp+h], xmm0
0x140084cc3  mov     [rbp+var_18], 0
0x140084ccb  mov     rax, [r14]
0x140084cce  mov     rbx, [rax+18h]
0x140084cd2  xor     edx, edx
0x140084cd4  lea     rcx, [rbp+h+8]
0x140084cd8  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140084cdd  lea     rdx, [rbp+h+8]
0x140084ce1  mov     rcx, r14
0x140084ce4  mov     rax, rbx
0x140084ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140084cec  mov     rcx, [rbp+28h]; this
0x140084cf0  test    eax, eax
0x140084cf2  js      loc_140084DBB
0x140084cf8  mov     rdx, rsi
0x140084cfb  lea     rcx, [rbp+var_18]
0x140084cff  call    ??4?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(wil::com_ptr_t<ICancellationToken,wil::err_exception_policy> const &)
0x140084d04  xor     r8d, r8d; pcbe
0x140084d07  mov     rdx, rdi; pv
0x140084d0a  lea     rcx, _lambda_e4ffa3337851658bfdbd92f22338e347____lambda_invoker_cdecl_; pfnwa
0x140084d11  call    cs:__imp_CreateThreadpoolWait
0x140084d18  nop     dword ptr [rax+rax+00h]
0x140084d1d  mov     rdx, rax
0x140084d20  lea     rcx, [rbp+h]
0x140084d24  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x140084d29  mov     rcx, [rbp+h]; pwa
0x140084d2d  test    rcx, rcx
0x140084d30  setz    al
0x140084d33  mov     r9, [rbp+28h]; char *
0x140084d37  test    al, al
0x140084d39  jnz     short loc_140084DA6
0x140084d3b  xor     r8d, r8d; pftTimeout
0x140084d3e  mov     rdx, [rbp+h+8]; h
0x140084d42  call    cs:__imp_SetThreadpoolWait
0x140084d49  nop     dword ptr [rax+rax+00h]
0x140084d4e  lea     rcx, [rdi+60h]
0x140084d52  lea     rdx, [rbp+h]
0x140084d56  call    ?push_back@?$vector@UTrackedDetails@CancellationTokenProvider@@V?$allocator@UTrackedDetails@CancellationTokenProvider@@@std@@@std@@QEAAX$$QEAUTrackedDetails@CancellationTokenProvider@@@Z; std::vector<CancellationTokenProvider::TrackedDetails>::push_back(CancellationTokenProvider::TrackedDetails &&)
0x140084d5b  nop
0x140084d5c  lea     rcx, [rbp+h]; this
0x140084d60  call    ??1TrackedDetails@CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::TrackedDetails::~TrackedDetails(void)
0x140084d65  add     rsi, 8
0x140084d69  cmp     rsi, r15
0x140084d6c  jnz     loc_140084CA6
0x140084d72  mov     rcx, rdi; _Mtx_t
0x140084d75  call    cs:__imp__Mtx_unlock
0x140084d7c  nop     dword ptr [rax+rax+00h]
0x140084d81  nop
0x140084d82  mov     rax, rdi
0x140084d85  mov     rcx, [rbp+var_10]
0x140084d89  xor     rcx, rsp; StackCookie
0x140084d8c  call    __security_check_cookie
0x140084d91  mov     rbx, [rsp+60h+arg_10]
0x140084d99  add     rsp, 60h
0x140084d9d  pop     r15
0x140084d9f  pop     r14
0x140084da1  pop     rdi
0x140084da2  pop     rsi
0x140084da3  pop     rbp
0x140084da4  retn
0x140084da6  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140084dad  mov     edx, 9Ch; void *
0x140084db2  mov     rcx, r9; this
0x140084db5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140084dbb  mov     r9d, eax; char *
0x140084dbe  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140084dc5  mov     edx, 94h; void *
0x140084dca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140084dd0  mov     r9d, 80004003h; char *
0x140084dd6  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140084ddd  mov     edx, 91h; void *
0x140084de2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
