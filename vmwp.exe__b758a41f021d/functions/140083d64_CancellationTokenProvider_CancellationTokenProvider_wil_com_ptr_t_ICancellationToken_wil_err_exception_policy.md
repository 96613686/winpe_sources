# CancellationTokenProvider::CancellationTokenProvider(wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>)

- ea: `0x140083d64`
- end: `0x140083efc`
- name: `??0CancellationTokenProvider@@QEAA@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(std::_Mutex_base *this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400836b0`

## callees

- `0x140028cac`
- `0x1400703b0`
- `0x140078628`
- `0x140083d64`
- `0x140084870`
- `0x140084ad4`
- `0x140084b6c`
- `0x140084bc0`
- `0x140084c14`
- `0x14011ea40`
- `0x1402cb010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x140083ebe`
- `msvcp_win!_Mtx_unlock` at `0x140083ebe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140083e97`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140083e97`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140083e74`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140083e74`

## string_xrefs

- `0x140083def`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x140083e49`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CancellationTokenProvider *__fastcall CancellationTokenProvider::CancellationTokenProvider(
        CancellationTokenProvider *this,
        __int64 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, PTP_WAIT *); // rbx
  int v6; // eax
  PTP_WAIT ThreadpoolWait; // rax
  int v9; // [rsp+20h] [rbp-40h]
  PTP_WAIT pwa[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v9 = (int)this;
  *(_QWORD *)this = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 18) = -1;
  *(_DWORD *)this = 2;
  *((_DWORD *)this + 19) = 0;
  *((_BYTE *)this + 88) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  if ( !*a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
      (const char *)0x80004003LL,
      (int)this);
  std::_Mutex_base::lock(this);
  *(_OWORD *)pwa = 0;
  v11 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, PTP_WAIT *))(*(_QWORD *)*a2 + 24LL);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &pwa[1],
    0);
  v6 = v5(v4, &pwa[1]);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6F,
      (unsigned int)"onecore\\vm\\common\\cancellation\\cancellationtokenprovider.cpp",
      (const char *)(unsigned int)v6,
      v9);
  wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(&v11, a2);
  ThreadpoolWait = CreateThreadpoolWait(
                     (PTP_WAIT_CALLBACK)lambda_e4ffa3337851658bfdbd92f22338e347_::_lambda_invoker_cdecl_,
                     this,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    pwa,
    ThreadpoolWait);
  SetThreadpoolWait(pwa[0], pwa[1], 0);
  std::vector<CancellationTokenProvider::TrackedDetails>::push_back((char *)this + 96, pwa);
  CancellationTokenProvider::TrackedDetails::~TrackedDetails((CancellationTokenProvider::TrackedDetails *)pwa);
  _Mtx_unlock(this);
  HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(a2);
  return this;
}

```

## disassembly

```asm
0x140083d64  mov     [rsp-28h+arg_10], rbx
0x140083d69  mov     [rsp-28h+arg_18], rsi
0x140083d6e  push    rbp
0x140083d6f  push    rdi
0x140083d70  push    r12
0x140083d72  push    r14
0x140083d74  push    r15
0x140083d76  mov     rbp, rsp
0x140083d79  sub     rsp, 60h
0x140083d7d  mov     rax, cs:__security_cookie
0x140083d84  xor     rax, rsp
0x140083d87  mov     [rbp+var_8], rax
0x140083d8b  mov     r14, rdx
0x140083d8e  mov     rsi, rcx
0x140083d91  mov     qword ptr [rbp+var_40], rcx
0x140083d95  mov     [rbp+var_30], rdx
0x140083d99  xor     r12d, r12d
0x140083d9c  mov     [rcx], r12
0x140083d9f  xorps   xmm0, xmm0
0x140083da2  movups  xmmword ptr [rcx+18h], xmm0
0x140083da6  movups  xmmword ptr [rcx+28h], xmm0
0x140083daa  movups  xmmword ptr [rcx+38h], xmm0
0x140083dae  mov     [rcx+48h], r12
0x140083db2  mov     [rcx+8], r12
0x140083db6  mov     [rcx+10h], r12
0x140083dba  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x140083dc1  mov     dword ptr [rcx], 2
0x140083dc7  mov     [rcx+4Ch], r12d
0x140083dcb  mov     [rcx+58h], r12b
0x140083dcf  mov     [rcx+60h], r12
0x140083dd3  mov     [rcx+68h], r12
0x140083dd7  mov     [rcx+70h], r12
0x140083ddb  cmp     [rdx], r12
0x140083dde  setz    al
0x140083de1  mov     rcx, [rbp+28h]; this
0x140083de5  test    al, al
0x140083de7  jz      short loc_140083E01
0x140083de9  mov     r9d, 80004003h; char *
0x140083def  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140083df6  lea     edx, [r12+6Ah]; void *
0x140083dfb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083e01  mov     [rbp+var_28], rsi
0x140083e05  mov     rcx, rsi; this
0x140083e08  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x140083e0d  nop
0x140083e0e  xorps   xmm0, xmm0
0x140083e11  movdqu  xmmword ptr [rbp+pwa], xmm0
0x140083e16  mov     [rbp+var_10], r12
0x140083e1a  mov     rdi, [r14]
0x140083e1d  mov     rax, [rdi]
0x140083e20  mov     rbx, [rax+18h]
0x140083e24  xor     edx, edx
0x140083e26  lea     rcx, [rbp+pwa+8]
0x140083e2a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140083e2f  lea     rdx, [rbp+pwa+8]
0x140083e33  mov     rcx, rdi
0x140083e36  mov     rax, rbx
0x140083e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140083e3e  mov     rcx, [rbp+28h]; this
0x140083e42  test    eax, eax
0x140083e44  jns     short loc_140083E5B
0x140083e46  mov     r9d, eax; char *
0x140083e49  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x140083e50  mov     edx, 6Fh ; 'o'; void *
0x140083e55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140083e5b  mov     rdx, r14
0x140083e5e  lea     rcx, [rbp+var_10]
0x140083e62  call    ??4?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(wil::com_ptr_t<ICancellationToken,wil::err_exception_policy> const &)
0x140083e67  xor     r8d, r8d; pcbe
0x140083e6a  mov     rdx, rsi; pv
0x140083e6d  lea     rcx, _lambda_e4ffa3337851658bfdbd92f22338e347____lambda_invoker_cdecl_; pfnwa
0x140083e74  call    cs:__imp_CreateThreadpoolWait
0x140083e7b  nop     dword ptr [rax+rax+00h]
0x140083e80  mov     rdx, rax
0x140083e83  lea     rcx, [rbp+pwa]
0x140083e87  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x140083e8c  xor     r8d, r8d; pftTimeout
0x140083e8f  mov     rdx, [rbp+pwa+8]; h
0x140083e93  mov     rcx, [rbp+pwa]; pwa
0x140083e97  call    cs:__imp_SetThreadpoolWait
0x140083e9e  nop     dword ptr [rax+rax+00h]
0x140083ea3  lea     rdx, [rbp+pwa]
0x140083ea7  lea     rcx, [rsi+60h]
0x140083eab  call    ?push_back@?$vector@UTrackedDetails@CancellationTokenProvider@@V?$allocator@UTrackedDetails@CancellationTokenProvider@@@std@@@std@@QEAAX$$QEAUTrackedDetails@CancellationTokenProvider@@@Z; std::vector<CancellationTokenProvider::TrackedDetails>::push_back(CancellationTokenProvider::TrackedDetails &&)
0x140083eb0  nop
0x140083eb1  lea     rcx, [rbp+pwa]; this
0x140083eb5  call    ??1TrackedDetails@CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::TrackedDetails::~TrackedDetails(void)
0x140083eba  nop
0x140083ebb  mov     rcx, rsi; _Mtx_t
0x140083ebe  call    cs:__imp__Mtx_unlock
0x140083ec5  nop     dword ptr [rax+rax+00h]
0x140083eca  nop
0x140083ecb  mov     rcx, r14; void *
0x140083ece  call    ??1?$HvsComPtr@UIXmlReader@@@@QEAA@XZ; HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(void)
0x140083ed3  mov     rax, rsi
0x140083ed6  mov     rcx, [rbp+var_8]
0x140083eda  xor     rcx, rsp; StackCookie
0x140083edd  call    __security_check_cookie
0x140083ee2  lea     r11, [rsp+60h+var_s0]
0x140083ee7  mov     rbx, [r11+40h]
0x140083eeb  mov     rsi, [r11+48h]
0x140083eef  mov     rsp, r11
0x140083ef2  pop     r15
0x140083ef4  pop     r14
0x140083ef6  pop     r12
0x140083ef8  pop     rdi
0x140083ef9  pop     rbp
0x140083efa  retn
```
