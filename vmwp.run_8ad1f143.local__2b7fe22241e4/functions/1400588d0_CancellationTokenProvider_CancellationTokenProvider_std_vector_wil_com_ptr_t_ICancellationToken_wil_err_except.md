# CancellationTokenProvider::CancellationTokenProvider(std::vector<wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>>> const &)

- ea: `0x1400588d0`
- end: `0x140058a5c`
- name: `??0CancellationTokenProvider@@QEAA@AEBV?$vector@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@Z`
- size: `396`
- prototype: `__int64 __fastcall(std::_Mutex_base *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401bc3d0`

## callees

- `0x14002873c`
- `0x1400587f8`
- `0x1400588d0`
- `0x140058a64`
- `0x140058ab8`
- `0x140058b0c`
- `0x1400598a0`
- `0x140059968`
- `0x14005b648`
- `0x14006af58`
- `0x140132960`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1400589e9`
- `msvcp_win!_Mtx_unlock` at `0x1400589e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400589b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400589b6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140058985`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140058985`

## string_xrefs

- `0x140058a1a`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x140058a32`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x140058a4a`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`

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
    ThreadpoolWait = CreateThreadpoolWait(lambda_e4ffa3337851658bfdbd92f22338e347_::_lambda_invoker_cdecl_, this, 0);
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
0x1400588d0  mov     [rsp-28h+arg_10], rbx
0x1400588d5  push    rbp
0x1400588d6  push    rsi
0x1400588d7  push    rdi
0x1400588d8  push    r14
0x1400588da  push    r15
0x1400588dc  mov     rbp, rsp
0x1400588df  sub     rsp, 60h
0x1400588e3  mov     rax, cs:__security_cookie
0x1400588ea  xor     rax, rsp
0x1400588ed  mov     [rbp+var_10], rax
0x1400588f1  mov     rbx, rdx
0x1400588f4  mov     rdi, rcx
0x1400588f7  mov     qword ptr [rbp+var_40], rcx
0x1400588fb  call    ??0CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::CancellationTokenProvider(void)
0x140058900  nop
0x140058901  mov     [rbp+var_30], rdi
0x140058905  mov     rcx, rdi; this
0x140058908  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14005890d  nop
0x14005890e  mov     rsi, [rbx]
0x140058911  mov     r15, [rbx+8]
0x140058915  jmp     loc_1400589DD
0x14005891a  mov     r14, [rsi]
0x14005891d  test    r14, r14
0x140058920  setz    al
0x140058923  mov     rcx, [rbp+28h]; this
0x140058927  test    al, al
0x140058929  jnz     loc_140058A44
0x14005892f  xorps   xmm0, xmm0
0x140058932  movdqu  xmmword ptr [rbp+h], xmm0
0x140058937  mov     [rbp+var_18], 0
0x14005893f  mov     rax, [r14]
0x140058942  mov     rbx, [rax+18h]
0x140058946  xor     edx, edx
0x140058948  lea     rcx, [rbp+h+8]
0x14005894c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140058951  lea     rdx, [rbp+h+8]
0x140058955  mov     rcx, r14
0x140058958  mov     rax, rbx
0x14005895b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140058960  mov     rcx, [rbp+28h]; this
0x140058964  test    eax, eax
0x140058966  js      loc_140058A2F
0x14005896c  mov     rdx, rsi
0x14005896f  lea     rcx, [rbp+var_18]
0x140058973  call    ??4?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(wil::com_ptr_t<ICancellationToken,wil::err_exception_policy> const &)
0x140058978  xor     r8d, r8d; pcbe
0x14005897b  mov     rdx, rdi; pv
0x14005897e  lea     rcx, _lambda_e4ffa3337851658bfdbd92f22338e347____lambda_invoker_cdecl_; pfnwa
0x140058985  call    cs:__imp_CreateThreadpoolWait
0x14005898c  nop     dword ptr [rax+rax+00h]
0x140058991  mov     rdx, rax
0x140058994  lea     rcx, [rbp+h]
0x140058998  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x14005899d  mov     rcx, [rbp+h]; pwa
0x1400589a1  test    rcx, rcx
0x1400589a4  setz    al
0x1400589a7  mov     r9, [rbp+28h]; char *
0x1400589ab  test    al, al
0x1400589ad  jnz     short loc_140058A1A
0x1400589af  xor     r8d, r8d; pftTimeout
0x1400589b2  mov     rdx, [rbp+h+8]; h
0x1400589b6  call    cs:__imp_SetThreadpoolWait
0x1400589bd  nop     dword ptr [rax+rax+00h]
0x1400589c2  lea     rcx, [rdi+60h]
0x1400589c6  lea     rdx, [rbp+h]
0x1400589ca  call    ?push_back@?$vector@UTrackedDetails@CancellationTokenProvider@@V?$allocator@UTrackedDetails@CancellationTokenProvider@@@std@@@std@@QEAAX$$QEAUTrackedDetails@CancellationTokenProvider@@@Z; std::vector<CancellationTokenProvider::TrackedDetails>::push_back(CancellationTokenProvider::TrackedDetails &&)
0x1400589cf  nop
0x1400589d0  lea     rcx, [rbp+h]; this
0x1400589d4  call    ??1TrackedDetails@CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::TrackedDetails::~TrackedDetails(void)
0x1400589d9  add     rsi, 8
0x1400589dd  cmp     rsi, r15
0x1400589e0  jnz     loc_14005891A
0x1400589e6  mov     rcx, rdi; _Mtx_t
0x1400589e9  call    cs:__imp__Mtx_unlock
0x1400589f0  nop     dword ptr [rax+rax+00h]
0x1400589f5  nop
0x1400589f6  mov     rax, rdi
0x1400589f9  mov     rcx, [rbp+var_10]
0x1400589fd  xor     rcx, rsp; StackCookie
0x140058a00  call    __security_check_cookie
0x140058a05  mov     rbx, [rsp+60h+arg_10]
0x140058a0d  add     rsp, 60h
0x140058a11  pop     r15
0x140058a13  pop     r14
0x140058a15  pop     rdi
0x140058a16  pop     rsi
0x140058a17  pop     rbp
0x140058a18  retn
0x140058a1a  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140058a21  mov     edx, 9Ch; void *
0x140058a26  mov     rcx, r9; this
0x140058a29  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140058a2f  mov     r9d, eax; char *
0x140058a32  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140058a39  mov     edx, 94h; void *
0x140058a3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140058a44  mov     r9d, 80004003h; char *
0x140058a4a  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140058a51  mov     edx, 91h; void *
0x140058a56  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
