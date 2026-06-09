# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x14000e050`
- end: `0x14000e246`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001cb00`

## callees

- `0x1400061cc`
- `0x140007ba0`
- `0x14000e050`
- `0x14000e69c`
- `0x14000e724`
- `0x14000e84c`
- `0x14001b91c`
- `0x14001b984`
- `0x14001b9c8`
- `0x14001bad4`
- `0x14001ea40`
- `0x140026c20`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14000e1ae`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14000e1ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        _QWORD **a1)
{
  unsigned int v2; // esi
  unsigned int v3; // edx
  int (__fastcall *v4)(_QWORD **, GUID *, IUnknown **); // rbx
  __int64 v5; // rdx
  bool v6; // dl
  unsigned int v7; // eax
  struct IRpcOptions *v8; // rcx
  struct IUnknown *v9; // rcx
  IUnknown *v10; // rcx
  struct IRpcOptions *v12[2]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v13; // [rsp+40h] [rbp-38h] BYREF
  struct IUnknown *v14; // [rsp+48h] [rbp-30h] BYREF
  IUnknown *v15; // [rsp+50h] [rbp-28h] BYREF
  LPSTREAM pStm; // [rsp+58h] [rbp-20h] BYREF
  int v17; // [rsp+60h] [rbp-18h]

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *((int *)a1 + 34) > 0 && v3 + _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, v3) == v3 )
  {
    v12[1] = (struct IRpcOptions *)a1;
    ((void (__fastcall *)(_QWORD **))(*a1)[1])(a1);
    v15 = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete((__int64)a1);
    v4 = (int (__fastcall *)(_QWORD **, GUID *, IUnknown **))**a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v15);
    if ( v4(a1, &GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0, &v15) >= 0 )
    {
      v13 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v13, *((_DWORD *)a1 + 14), -2);
      v14 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v14);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>>::CopyLocal(
                  a1 + 15,
                  v5,
                  &v14) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v12[0] = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)v12);
        RpcOptionsHelper::GetRpcOptions(v14, v6, v12);
        BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(
          &pStm,
          (__int64)v12[0],
          v15,
          (__int64)v14);
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, IUnknown *, _QWORD))v14->lpVtbl[1].QueryInterface)(
               v14,
               v15,
               v13);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v7,
               v14,
               a1[16]);
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        if ( v17 >= 0 )
        {
          (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)pStm + 40LL))(pStm, 0, 0, 0);
          CoReleaseMarshalData(pStm);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&pStm);
        v8 = v12[0];
        if ( v12[0] )
        {
          v12[0] = 0;
          ((void (__fastcall *)(struct IRpcOptions *))v8->lpVtbl->Release)(v8);
        }
      }
      v9 = v14;
      if ( v14 )
      {
        v14 = 0;
        ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->Release)(v9);
      }
    }
    v10 = v15;
    if ( v15 )
    {
      v15 = 0;
      ((void (__fastcall *)(IUnknown *))v10->lpVtbl->Release)(v10);
    }
    ((void (__fastcall *)(_QWORD **))(*a1)[2])(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x14000e050  push    rbp
0x14000e052  push    rbx
0x14000e053  push    rsi
0x14000e054  push    rdi
0x14000e055  mov     rbp, rsp
0x14000e058  sub     rsp, 78h
0x14000e05c  mov     rax, cs:__security_cookie
0x14000e063  xor     rax, rsp
0x14000e066  mov     [rbp+var_10], rax
0x14000e06a  mov     rdi, rcx
0x14000e06d  xor     esi, esi
0x14000e06f  lea     edx, [rsi+1]
0x14000e072  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14000e077  cmp     [rdi+88h], esi
0x14000e07d  jle     loc_14000E22E
0x14000e083  mov     eax, edx
0x14000e085  lock xadd [rdi+10h], eax
0x14000e08a  add     eax, edx
0x14000e08c  cmp     eax, edx
0x14000e08e  jnz     loc_14000E22E
0x14000e094  mov     [rbp+var_40], rdi
0x14000e098  mov     rax, [rdi]
0x14000e09b  mov     rcx, rdi
0x14000e09e  mov     rax, [rax+8]
0x14000e0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0a7  nop
0x14000e0a8  mov     [rbp+var_28], rsi
0x14000e0ac  mov     rcx, rdi
0x14000e0af  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x14000e0b4  nop
0x14000e0b5  mov     rax, [rdi]
0x14000e0b8  mov     rbx, [rax]
0x14000e0bb  lea     rcx, [rbp+var_28]
0x14000e0bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e0c4  lea     r8, [rbp+var_28]
0x14000e0c8  lea     rdx, _GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0
0x14000e0cf  mov     rcx, rdi
0x14000e0d2  mov     rax, rbx
0x14000e0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e0da  nop
0x14000e0db  test    eax, eax
0x14000e0dd  js      loc_14000E200
0x14000e0e3  mov     [rbp+var_38], 0FFFFFFFEh
0x14000e0ea  mov     ecx, [rdi+38h]
0x14000e0ed  mov     eax, [rbp+var_38]
0x14000e0f0  lock cmpxchg [rbp+var_38], ecx
0x14000e0f5  mov     [rbp+var_30], rsi
0x14000e0f9  lea     rcx, [rbp+var_30]
0x14000e0fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e102  lea     rcx, [rdi+78h]
0x14000e106  lea     r8, [rbp+var_30]
0x14000e10a  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>>::CopyLocal(_GUID const &,void * *)
0x14000e10f  test    eax, eax
0x14000e111  js      loc_14000E1E2
0x14000e117  mov     rcx, rdi
0x14000e11a  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x14000e11f  mov     [rbp+var_48], rsi
0x14000e123  lea     rcx, [rbp+var_48]
0x14000e127  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e12c  lea     r8, [rbp+var_48]; struct IRpcOptions **
0x14000e130  mov     rcx, [rbp+var_30]; struct IUnknown *
0x14000e134  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x14000e139  mov     r9, [rbp+var_30]
0x14000e13d  mov     r8, [rbp+var_28]
0x14000e141  mov     rdx, [rbp+var_48]
0x14000e145  lea     rcx, [rbp+pStm]; ppstm
0x14000e149  call    ?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@56@@Z; BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *> *)
0x14000e14e  nop
0x14000e14f  mov     rcx, [rbp+var_30]
0x14000e153  mov     rax, [rcx]
0x14000e156  mov     r8d, [rbp+var_38]
0x14000e15a  mov     rdx, [rbp+var_28]
0x14000e15e  mov     rax, [rax+18h]
0x14000e162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e167  mov     r8, [rdi+80h]
0x14000e16e  mov     rdx, [rbp+var_30]
0x14000e172  mov     ecx, eax
0x14000e174  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x14000e179  mov     esi, eax
0x14000e17b  mov     rcx, rdi
0x14000e17e  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x14000e183  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x14000e188  nop
0x14000e189  cmp     [rbp+var_18], 0
0x14000e18d  jl      short loc_14000E1BA
0x14000e18f  mov     r10, [rbp+pStm]
0x14000e193  xor     edx, edx
0x14000e195  mov     rcx, [r10]
0x14000e198  mov     rax, [rcx+28h]
0x14000e19c  xor     r9d, r9d
0x14000e19f  xor     r8d, r8d
0x14000e1a2  mov     rcx, r10
0x14000e1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1aa  mov     rcx, [rbp+pStm]; pStm
0x14000e1ae  call    cs:__imp_CoReleaseMarshalData
0x14000e1b5  nop     dword ptr [rax+rax+00h]
0x14000e1ba  lea     rcx, [rbp+pStm]
0x14000e1be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000e1c3  nop
0x14000e1c4  mov     rcx, [rbp+var_48]
0x14000e1c8  test    rcx, rcx
0x14000e1cb  jz      short loc_14000E1E2
0x14000e1cd  mov     [rbp+var_48], 0
0x14000e1d5  mov     rax, [rcx]
0x14000e1d8  mov     rax, [rax+10h]
0x14000e1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1e1  nop
0x14000e1e2  mov     rcx, [rbp+var_30]
0x14000e1e6  test    rcx, rcx
0x14000e1e9  jz      short loc_14000E200
0x14000e1eb  mov     [rbp+var_30], 0
0x14000e1f3  mov     rax, [rcx]
0x14000e1f6  mov     rax, [rax+10h]
0x14000e1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1ff  nop
0x14000e200  mov     rcx, [rbp+var_28]
0x14000e204  test    rcx, rcx
0x14000e207  jz      short loc_14000E21E
0x14000e209  mov     [rbp+var_28], 0
0x14000e211  mov     rax, [rcx]
0x14000e214  mov     rax, [rax+10h]
0x14000e218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e21d  nop
0x14000e21e  mov     rax, [rdi]
0x14000e221  mov     rcx, rdi
0x14000e224  mov     rax, [rax+10h]
0x14000e228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e22d  nop
0x14000e22e  mov     eax, esi
0x14000e230  mov     rcx, [rbp+var_10]
0x14000e234  xor     rcx, rsp; StackCookie
0x14000e237  call    __security_check_cookie
0x14000e23c  add     rsp, 78h
0x14000e240  pop     rdi
0x14000e241  pop     rsi
0x14000e242  pop     rbx
0x14000e243  pop     rbp
0x14000e244  retn
```
