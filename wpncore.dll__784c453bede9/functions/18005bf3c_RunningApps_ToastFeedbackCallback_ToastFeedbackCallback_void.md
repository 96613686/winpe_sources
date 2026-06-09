# RunningApps::ToastFeedbackCallback::~ToastFeedbackCallback(void)

- ea: `0x18005bf3c`
- end: `0x18005c088`
- name: `??1ToastFeedbackCallback@RunningApps@@QEAA@XZ`
- size: `332`
- prototype: `void __fastcall(RunningApps::ToastFeedbackCallback *__hidden this)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800517b4`
- `0x18005bbe0`
- `0x18005be64`
- `0x18005be9c`
- `0x18010cb28`

## callees

- `0x180004e38`
- `0x1800117c0`
- `0x18002949c`
- `0x18004c9e4`
- `0x18004ca20`
- `0x18005bf3c`
- `0x1800d4944`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bf50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005bf50`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18005bfd5`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18005c00b`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18005bfd5`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18005c00b`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18005bf6e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18005bf6e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005bfa1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005bfa1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005bfea`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005c020`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005bfea`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18005c020`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RunningApps::ToastFeedbackCallback::~ToastFeedbackCallback(RunningApps::ToastFeedbackCallback *this)
{
  void *v2; // rdx
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rsi
  char v7; // bl
  char v8; // di
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // r8
  DWORD Parameter; // [rsp+40h] [rbp-40h] BYREF
  char v13; // [rsp+44h] [rbp-3Ch]
  HRESULT v14; // [rsp+48h] [rbp-38h]
  void *phNewTimer; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v16[40]; // [rsp+58h] [rbp-28h] BYREF

  Parameter = GetCurrentThreadId();
  v13 = 0;
  phNewTimer = 0;
  v14 = CoEnableCallCancellation(0);
  if ( v14 >= 0 )
    CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x3E8u, 0x3E8u, 0);
  v3 = *(_QWORD *)this;
  *(_QWORD *)this = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = v13;
  if ( v14 >= 0 )
  {
    v14 = -2147467259;
    CoDisableCallCancellation(0);
    v2 = phNewTimer;
    if ( phNewTimer )
    {
      DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      phNewTimer = 0;
    }
  }
  if ( v4 && WpncoreTelemetry::IsEnabled(v3, (unsigned __int64)v2) )
  {
    v6 = wil::details::static_lazy<WpncoreTelemetry>::get(
           v5,
           _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_);
    v7 = *((_BYTE *)this + 8);
    v8 = *((_BYTE *)this + 9);
    v9 = std::wstring::wstring(v16, (char *)this + 16);
    LOBYTE(v10) = v7;
    LOBYTE(v11) = v8;
    WpncoreTelemetry::ToastFeedbackCallbackCleaningTimedOut_(v6, v9, v11, v10);
  }
  if ( v14 >= 0 )
  {
    v14 = -2147467259;
    CoDisableCallCancellation(0);
    if ( phNewTimer )
      DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>((char *)this + 16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(this);
}

```

## disassembly

```asm
0x18005bf3c  push    rbp
0x18005bf3e  push    rbx
0x18005bf3f  push    rsi
0x18005bf40  push    rdi
0x18005bf41  push    r14
0x18005bf43  mov     rbp, rsp
0x18005bf46  sub     rsp, 80h
0x18005bf4d  mov     r14, rcx
0x18005bf50  call    cs:__imp_GetCurrentThreadId
0x18005bf56  mov     [rbp+Parameter], eax
0x18005bf59  mov     [rbp+var_3C], 0
0x18005bf5d  mov     [rbp+var_38], 80004005h
0x18005bf64  mov     [rbp+phNewTimer], 0
0x18005bf6c  xor     ecx, ecx; pReserved
0x18005bf6e  call    cs:__imp_CoEnableCallCancellation
0x18005bf74  mov     [rbp+var_38], eax
0x18005bf77  test    eax, eax
0x18005bf79  js      short loc_18005BFA7
0x18005bf7b  mov     [rsp+80h+Flags], 0; Flags
0x18005bf83  mov     eax, 3E8h
0x18005bf88  mov     [rsp+80h+Period], eax; Period
0x18005bf8c  mov     [rsp+80h+DueTime], eax; DueTime
0x18005bf90  lea     r9, [rbp+Parameter]; Parameter
0x18005bf94  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18005bf9b  xor     edx, edx; TimerQueue
0x18005bf9d  lea     rcx, [rbp+phNewTimer]; phNewTimer
0x18005bfa1  call    cs:__imp_CreateTimerQueueTimer
0x18005bfa7  mov     rcx, [r14]
0x18005bfaa  mov     qword ptr [r14], 0
0x18005bfb1  test    rcx, rcx
0x18005bfb4  jz      short loc_18005BFC3
0x18005bfb6  mov     rax, [rcx]
0x18005bfb9  mov     rax, [rax+10h]
0x18005bfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bfc2  nop
0x18005bfc3  mov     bl, [rbp+var_3C]
0x18005bfc6  cmp     [rbp+var_38], 0
0x18005bfca  jl      short loc_18005BFF8
0x18005bfcc  mov     [rbp+var_38], 80004005h
0x18005bfd3  xor     ecx, ecx; pReserved
0x18005bfd5  call    cs:__imp_CoDisableCallCancellation
0x18005bfdb  mov     rdx, [rbp+phNewTimer]; Timer
0x18005bfdf  test    rdx, rdx
0x18005bfe2  jz      short loc_18005BFF8
0x18005bfe4  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18005bfe8  xor     ecx, ecx; TimerQueue
0x18005bfea  call    cs:__imp_DeleteTimerQueueTimer
0x18005bff0  mov     [rbp+phNewTimer], 0
0x18005bff8  test    bl, bl
0x18005bffa  jnz     short loc_18005C044
0x18005bffc  cmp     [rbp+var_38], 0
0x18005c000  jl      short loc_18005C026
0x18005c002  mov     [rbp+var_38], 80004005h
0x18005c009  xor     ecx, ecx; pReserved
0x18005c00b  call    cs:__imp_CoDisableCallCancellation
0x18005c011  mov     rdx, [rbp+phNewTimer]; Timer
0x18005c015  test    rdx, rdx
0x18005c018  jz      short loc_18005C026
0x18005c01a  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18005c01e  xor     ecx, ecx; TimerQueue
0x18005c020  call    cs:__imp_DeleteTimerQueueTimer
0x18005c026  lea     rcx, [r14+10h]; void *
0x18005c02a  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x18005c02f  mov     rcx, r14
0x18005c032  add     rsp, 80h
0x18005c039  pop     r14
0x18005c03b  pop     rdi
0x18005c03c  pop     rsi
0x18005c03d  pop     rbx
0x18005c03e  pop     rbp
0x18005c03f  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005c044  call    ?IsEnabled@WpncoreTelemetry@@SA_NE_K@Z; WpncoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x18005c049  test    al, al
0x18005c04b  jz      short loc_18005C083
0x18005c04d  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c91d295e9756ec26c89460bbd269b90b_@@CA@XZ; _lambda_c91d295e9756ec26c89460bbd269b90b_::_lambda_invoker_cdecl_(void)
0x18005c054  call    ?get@?$static_lazy@VWpncoreTelemetry@@@details@wil@@QEAAPEAVWpncoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<WpncoreTelemetry>::get(void (*)(void))
0x18005c059  mov     rsi, rax
0x18005c05c  mov     bl, [r14+8]
0x18005c060  mov     dil, [r14+9]
0x18005c064  lea     rdx, [r14+10h]
0x18005c068  lea     rcx, [rbp+var_28]
0x18005c06c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005c071  mov     r9b, bl
0x18005c074  mov     r8b, dil
0x18005c077  mov     rdx, rax
0x18005c07a  mov     rcx, rsi
0x18005c07d  call    ?ToastFeedbackCallbackCleaningTimedOut_@WpncoreTelemetry@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N1@Z; WpncoreTelemetry::ToastFeedbackCallbackCleaningTimedOut_(std::wstring,bool,bool)
0x18005c082  nop
0x18005c083  jmp     loc_18005BFFC
```
