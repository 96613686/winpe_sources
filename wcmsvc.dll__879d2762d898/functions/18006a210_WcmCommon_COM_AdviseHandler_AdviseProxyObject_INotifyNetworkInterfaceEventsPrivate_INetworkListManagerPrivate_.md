# WcmCommon::COM::AdviseHandler::AdviseProxyObject<INotifyNetworkInterfaceEventsPrivate,INetworkListManagerPrivate,INotifyNetworkListManagerEventsPrivate>(Microsoft::WRL::ComPtr<INetworkListManagerPrivate>,INotifyNetworkListManagerEventsPrivate *)

- ea: `0x18006a210`
- end: `0x18006a3e3`
- name: `??$AdviseProxyObject@UINotifyNetworkInterfaceEventsPrivate@@UINetworkListManagerPrivate@@UINotifyNetworkListManagerEventsPrivate@@@AdviseHandler@COM@WcmCommon@@QEAAXV?$ComPtr@UINetworkListManagerPrivate@@@WRL@Microsoft@@PEAUINotifyNetworkListManagerEventsPrivate@@@Z`
- size: `467`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006a1b0`

## callees

- `0x18001c11c`
- `0x18006a210`
- `0x18006a3f8`
- `0x18006a448`
- `0x18006a474`
- `0x18006a4cc`
- `0x180084f50`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a2a9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a333`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a2a9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18006a333`

## string_xrefs

- `0x18006a268`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a2ba`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a2f2`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a344`: `onecore\private\net\inc\wcm\wcm_com.h`
- `0x18006a378`: `onecore\private\net\inc\wcm\wcm_com.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WcmCommon::COM::AdviseHandler::AdviseProxyObject<INotifyNetworkInterfaceEventsPrivate,INetworkListManagerPrivate,INotifyNetworkListManagerEventsPrivate>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v6; // eax
  HRESULT v7; // eax
  int v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  IUnknown *v11; // rcx
  DWORD dwAuthnLevel; // [rsp+20h] [rbp-50h]
  DWORD dwAuthnLevela; // [rsp+20h] [rbp-50h]
  DWORD dwAuthnLevelb; // [rsp+20h] [rbp-50h]
  IUnknown *pProxy; // [rsp+48h] [rbp-28h] BYREF
  IUnknown *v17; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v17 = 0;
  v18 = 0;
  pProxy = 0;
  v6 = Microsoft::WRL::ComPtr<INetworkListManagerPrivate>::As<IConnectionPointContainer>(a2, &pProxy);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v6,
      dwAuthnLevel);
  v7 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v7,
      dwAuthnLevela);
  v8 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl[1].AddRef)(
         pProxy,
         &GUID_2abc0864_9677_42e5_882a_d415c556c284,
         &v17);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v8,
      dwAuthnLevela);
  v9 = CoSetProxyBlanket(v17, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v9,
      dwAuthnLevelb);
  v10 = ((__int64 (__fastcall *)(IUnknown *, __int64, int *))v17->lpVtbl[1].Release)(v17, a3, &v18);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_com.h",
      (const char *)(unsigned int)v10,
      dwAuthnLevelb);
  std::vector<WcmCommon::COM::AdviseHandler::AdviseInstance>::emplace_back<WcmCommon::COM::AdviseHandler::AdviseInstance>(
    a1,
    &v17);
  v11 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v11->lpVtbl->Release)(v11);
  }
  WcmCommon::COM::AdviseHandler::AdviseInstance::~AdviseInstance((WcmCommon::COM::AdviseHandler::AdviseInstance *)&v17);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
}

```

## disassembly

```asm
0x18006a210  mov     [rsp-18h+arg_18], rbx
0x18006a215  push    rbp
0x18006a216  push    rsi
0x18006a217  push    rdi
0x18006a218  mov     rbp, rsp
0x18006a21b  sub     rsp, 70h
0x18006a21f  mov     rax, cs:__security_cookie
0x18006a226  xor     rax, rsp
0x18006a229  mov     [rbp+var_10], rax
0x18006a22d  mov     rsi, r8
0x18006a230  mov     rbx, rdx
0x18006a233  mov     rdi, rcx
0x18006a236  mov     [rbp+var_30], rdx
0x18006a23a  mov     [rbp+var_20], 0
0x18006a242  mov     [rbp+var_18], 0
0x18006a249  mov     [rbp+pProxy], 0
0x18006a251  lea     rdx, [rbp+pProxy]
0x18006a255  mov     rcx, rbx
0x18006a258  call    ??$As@UIConnectionPointContainer@@@?$ComPtr@UINetworkListManagerPrivate@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIConnectionPointContainer@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<INetworkListManagerPrivate>::As<IConnectionPointContainer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IConnectionPointContainer>>)
0x18006a25d  mov     rcx, [rbp+18h]; this
0x18006a261  test    eax, eax
0x18006a263  jns     short loc_18006A27A
0x18006a265  mov     r9d, eax; char *
0x18006a268  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a26f  mov     edx, 0F8h; void *
0x18006a274  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a27a  mov     [rsp+70h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18006a282  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x18006a28b  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x18006a293  mov     [rsp+70h+dwAuthnLevel], 0; int
0x18006a29b  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18006a29f  xor     r8d, r8d; dwAuthzSvc
0x18006a2a2  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18006a2a5  mov     rcx, [rbp+pProxy]; pProxy
0x18006a2a9  call    cs:__imp_CoSetProxyBlanket
0x18006a2af  mov     rcx, [rbp+18h]; this
0x18006a2b3  test    eax, eax
0x18006a2b5  jns     short loc_18006A2CC
0x18006a2b7  mov     r9d, eax; char *
0x18006a2ba  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a2c1  mov     edx, 101h; void *
0x18006a2c6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a2cc  mov     rcx, [rbp+pProxy]
0x18006a2d0  mov     rax, [rcx]
0x18006a2d3  lea     r8, [rbp+var_20]
0x18006a2d7  lea     rdx, _GUID_2abc0864_9677_42e5_882a_d415c556c284
0x18006a2de  mov     rax, [rax+20h]
0x18006a2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a2e7  mov     rcx, [rbp+18h]; this
0x18006a2eb  test    eax, eax
0x18006a2ed  jns     short loc_18006A304
0x18006a2ef  mov     r9d, eax; char *
0x18006a2f2  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a2f9  mov     edx, 103h; void *
0x18006a2fe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a304  mov     [rsp+70h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18006a30c  mov     [rsp+70h+pAuthInfo], 0; pAuthInfo
0x18006a315  mov     [rsp+70h+dwImpLevel], 3; dwImpLevel
0x18006a31d  mov     [rsp+70h+dwAuthnLevel], 0; int
0x18006a325  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18006a329  xor     r8d, r8d; dwAuthzSvc
0x18006a32c  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18006a32f  mov     rcx, [rbp+var_20]; pProxy
0x18006a333  call    cs:__imp_CoSetProxyBlanket
0x18006a339  mov     rcx, [rbp+18h]; this
0x18006a33d  test    eax, eax
0x18006a33f  jns     short loc_18006A356
0x18006a341  mov     r9d, eax; char *
0x18006a344  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a34b  mov     edx, 10Ch; void *
0x18006a350  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a356  mov     rcx, [rbp+var_20]
0x18006a35a  mov     rax, [rcx]
0x18006a35d  lea     r8, [rbp+var_18]
0x18006a361  mov     rdx, rsi
0x18006a364  mov     rax, [rax+28h]
0x18006a368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a36d  mov     rcx, [rbp+18h]; this
0x18006a371  test    eax, eax
0x18006a373  jns     short loc_18006A38A
0x18006a375  mov     r9d, eax; char *
0x18006a378  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_co"...
0x18006a37f  mov     edx, 10Eh; void *
0x18006a384  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006a38a  lea     rdx, [rbp+var_20]
0x18006a38e  mov     rcx, rdi
0x18006a391  call    ??$emplace_back@UAdviseInstance@AdviseHandler@COM@WcmCommon@@@?$vector@UAdviseInstance@AdviseHandler@COM@WcmCommon@@V?$allocator@UAdviseInstance@AdviseHandler@COM@WcmCommon@@@std@@@std@@QEAAAEAUAdviseInstance@AdviseHandler@COM@WcmCommon@@$$QEAU2345@@Z; std::vector<WcmCommon::COM::AdviseHandler::AdviseInstance>::emplace_back<WcmCommon::COM::AdviseHandler::AdviseInstance>(WcmCommon::COM::AdviseHandler::AdviseInstance &&)
0x18006a396  nop
0x18006a397  mov     rcx, [rbp+pProxy]
0x18006a39b  test    rcx, rcx
0x18006a39e  jz      short loc_18006A3B5
0x18006a3a0  mov     [rbp+pProxy], 0
0x18006a3a8  mov     rax, [rcx]
0x18006a3ab  mov     rax, [rax+10h]
0x18006a3af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a3b4  nop
0x18006a3b5  lea     rcx, [rbp+var_20]; this
0x18006a3b9  call    ??1AdviseInstance@AdviseHandler@COM@WcmCommon@@QEAA@XZ; WcmCommon::COM::AdviseHandler::AdviseInstance::~AdviseInstance(void)
0x18006a3be  nop
0x18006a3bf  mov     rcx, rbx
0x18006a3c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006a3c7  mov     rcx, [rbp+var_10]
0x18006a3cb  xor     rcx, rsp; StackCookie
0x18006a3ce  call    __security_check_cookie
0x18006a3d3  mov     rbx, [rsp+70h+arg_18]
0x18006a3db  add     rsp, 70h
0x18006a3df  pop     rdi
0x18006a3e0  pop     rsi
0x18006a3e1  pop     rbp
0x18006a3e2  retn
```
