# CancellationTokenProvider::CancellationTokenProvider(wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>)

- ea: `0x14005b1c8`
- end: `0x14005b360`
- name: `??0CancellationTokenProvider@@QEAA@V?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(std::_Mutex_base *this, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005b368`

## callees

- `0x14002873c`
- `0x1400587f8`
- `0x140058a64`
- `0x140058ab8`
- `0x1400598a0`
- `0x140059940`
- `0x140059968`
- `0x14005b1c8`
- `0x14006af58`
- `0x140132960`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x14005b322`
- `msvcp_win!_Mtx_unlock` at `0x14005b322`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14005b2fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14005b2fb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14005b2d8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x14005b2d8`

## string_xrefs

- `0x14005b253`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`
- `0x14005b2ad`: `onecore\vm\common\cancellation\cancellationtokenprovider.cpp`

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
  ThreadpoolWait = CreateThreadpoolWait(lambda_e4ffa3337851658bfdbd92f22338e347_::_lambda_invoker_cdecl_, this, 0);
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
0x14005b1c8  mov     [rsp-28h+arg_10], rbx
0x14005b1cd  mov     [rsp-28h+arg_18], rsi
0x14005b1d2  push    rbp
0x14005b1d3  push    rdi
0x14005b1d4  push    r12
0x14005b1d6  push    r14
0x14005b1d8  push    r15
0x14005b1da  mov     rbp, rsp
0x14005b1dd  sub     rsp, 60h
0x14005b1e1  mov     rax, cs:__security_cookie
0x14005b1e8  xor     rax, rsp
0x14005b1eb  mov     [rbp+var_8], rax
0x14005b1ef  mov     r14, rdx
0x14005b1f2  mov     rsi, rcx
0x14005b1f5  mov     qword ptr [rbp+var_40], rcx
0x14005b1f9  mov     [rbp+var_30], rdx
0x14005b1fd  xor     r12d, r12d
0x14005b200  mov     [rcx], r12
0x14005b203  xorps   xmm0, xmm0
0x14005b206  movups  xmmword ptr [rcx+18h], xmm0
0x14005b20a  movups  xmmword ptr [rcx+28h], xmm0
0x14005b20e  movups  xmmword ptr [rcx+38h], xmm0
0x14005b212  mov     [rcx+48h], r12
0x14005b216  mov     [rcx+8], r12
0x14005b21a  mov     [rcx+10h], r12
0x14005b21e  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x14005b225  mov     dword ptr [rcx], 2
0x14005b22b  mov     [rcx+4Ch], r12d
0x14005b22f  mov     [rcx+58h], r12b
0x14005b233  mov     [rcx+60h], r12
0x14005b237  mov     [rcx+68h], r12
0x14005b23b  mov     [rcx+70h], r12
0x14005b23f  cmp     [rdx], r12
0x14005b242  setz    al
0x14005b245  mov     rcx, [rbp+28h]; this
0x14005b249  test    al, al
0x14005b24b  jz      short loc_14005B265
0x14005b24d  mov     r9d, 80004003h; char *
0x14005b253  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x14005b25a  lea     edx, [r12+6Ah]; void *
0x14005b25f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005b265  mov     [rbp+var_28], rsi
0x14005b269  mov     rcx, rsi; this
0x14005b26c  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x14005b271  nop
0x14005b272  xorps   xmm0, xmm0
0x14005b275  movdqu  xmmword ptr [rbp+pwa], xmm0
0x14005b27a  mov     [rbp+var_10], r12
0x14005b27e  mov     rdi, [r14]
0x14005b281  mov     rax, [rdi]
0x14005b284  mov     rbx, [rax+18h]
0x14005b288  xor     edx, edx
0x14005b28a  lea     rcx, [rbp+pwa+8]
0x14005b28e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x14005b293  lea     rdx, [rbp+pwa+8]
0x14005b297  mov     rcx, rdi
0x14005b29a  mov     rax, rbx
0x14005b29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b2a2  mov     rcx, [rbp+28h]; this
0x14005b2a6  test    eax, eax
0x14005b2a8  jns     short loc_14005B2BF
0x14005b2aa  mov     r9d, eax; char *
0x14005b2ad  lea     r8, aOnecoreVmCommo_96; "onecore\\vm\\common\\cancellation\\canc"...
0x14005b2b4  mov     edx, 6Fh ; 'o'; void *
0x14005b2b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14005b2bf  mov     rdx, r14
0x14005b2c2  lea     rcx, [rbp+var_10]
0x14005b2c6  call    ??4?$com_ptr_t@UICancellationToken@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<ICancellationToken,wil::err_exception_policy>::operator=(wil::com_ptr_t<ICancellationToken,wil::err_exception_policy> const &)
0x14005b2cb  xor     r8d, r8d; pcbe
0x14005b2ce  mov     rdx, rsi; pv
0x14005b2d1  lea     rcx, _lambda_e4ffa3337851658bfdbd92f22338e347____lambda_invoker_cdecl_; pfnwa
0x14005b2d8  call    cs:__imp_CreateThreadpoolWait
0x14005b2df  nop     dword ptr [rax+rax+00h]
0x14005b2e4  mov     rdx, rax
0x14005b2e7  lea     rcx, [rbp+pwa]
0x14005b2eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x14005b2f0  xor     r8d, r8d; pftTimeout
0x14005b2f3  mov     rdx, [rbp+pwa+8]; h
0x14005b2f7  mov     rcx, [rbp+pwa]; pwa
0x14005b2fb  call    cs:__imp_SetThreadpoolWait
0x14005b302  nop     dword ptr [rax+rax+00h]
0x14005b307  lea     rdx, [rbp+pwa]
0x14005b30b  lea     rcx, [rsi+60h]
0x14005b30f  call    ?push_back@?$vector@UTrackedDetails@CancellationTokenProvider@@V?$allocator@UTrackedDetails@CancellationTokenProvider@@@std@@@std@@QEAAX$$QEAUTrackedDetails@CancellationTokenProvider@@@Z; std::vector<CancellationTokenProvider::TrackedDetails>::push_back(CancellationTokenProvider::TrackedDetails &&)
0x14005b314  nop
0x14005b315  lea     rcx, [rbp+pwa]; this
0x14005b319  call    ??1TrackedDetails@CancellationTokenProvider@@QEAA@XZ; CancellationTokenProvider::TrackedDetails::~TrackedDetails(void)
0x14005b31e  nop
0x14005b31f  mov     rcx, rsi; _Mtx_t
0x14005b322  call    cs:__imp__Mtx_unlock
0x14005b329  nop     dword ptr [rax+rax+00h]
0x14005b32e  nop
0x14005b32f  mov     rcx, r14; void *
0x14005b332  call    ??1?$HvsComPtr@UIXmlReader@@@@QEAA@XZ; HvsComPtr<IXmlReader>::~HvsComPtr<IXmlReader>(void)
0x14005b337  mov     rax, rsi
0x14005b33a  mov     rcx, [rbp+var_8]
0x14005b33e  xor     rcx, rsp; StackCookie
0x14005b341  call    __security_check_cookie
0x14005b346  lea     r11, [rsp+60h+var_s0]
0x14005b34b  mov     rbx, [r11+40h]
0x14005b34f  mov     rsi, [r11+48h]
0x14005b353  mov     rsp, r11
0x14005b356  pop     r15
0x14005b358  pop     r14
0x14005b35a  pop     r12
0x14005b35c  pop     rdi
0x14005b35d  pop     rbp
0x14005b35e  retn
```
