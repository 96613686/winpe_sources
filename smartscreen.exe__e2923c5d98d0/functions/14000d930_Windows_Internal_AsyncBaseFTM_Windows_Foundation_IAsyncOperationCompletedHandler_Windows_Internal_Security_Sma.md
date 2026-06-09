# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x14000d930`
- end: `0x14000db1f`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001ba20`

## callees

- `0x140005e4c`
- `0x1400077d0`
- `0x14000d930`
- `0x14000df68`
- `0x14000dff0`
- `0x14000e118`
- `0x14001aae8`
- `0x14001ab60`
- `0x14001aba0`
- `0x14001adf0`
- `0x14001d934`
- `0x140025aa0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14000da8e`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14000da8e`

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
0x14000d930  push    rbp
0x14000d932  push    rbx
0x14000d933  push    rsi
0x14000d934  push    rdi
0x14000d935  mov     rbp, rsp
0x14000d938  sub     rsp, 78h
0x14000d93c  mov     rax, cs:__security_cookie
0x14000d943  xor     rax, rsp
0x14000d946  mov     [rbp+var_10], rax
0x14000d94a  mov     rdi, rcx
0x14000d94d  xor     esi, esi
0x14000d94f  lea     edx, [rsi+1]
0x14000d952  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14000d957  cmp     [rdi+88h], esi
0x14000d95d  jle     loc_14000DB08
0x14000d963  mov     eax, edx
0x14000d965  lock xadd [rdi+10h], eax
0x14000d96a  add     eax, edx
0x14000d96c  cmp     eax, edx
0x14000d96e  jnz     loc_14000DB08
0x14000d974  mov     [rbp+var_40], rdi
0x14000d978  mov     rax, [rdi]
0x14000d97b  mov     rcx, rdi
0x14000d97e  mov     rax, [rax+8]
0x14000d982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d987  nop
0x14000d988  mov     [rbp+var_28], rsi
0x14000d98c  mov     rcx, rdi
0x14000d98f  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x14000d994  nop
0x14000d995  mov     rax, [rdi]
0x14000d998  mov     rbx, [rax]
0x14000d99b  lea     rcx, [rbp+var_28]
0x14000d99f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000d9a4  lea     r8, [rbp+var_28]
0x14000d9a8  lea     rdx, _GUID_f84b2c99_2f3d_5877_bf78_4f40f6bd25c0
0x14000d9af  mov     rcx, rdi
0x14000d9b2  mov     rax, rbx
0x14000d9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9ba  nop
0x14000d9bb  test    eax, eax
0x14000d9bd  js      loc_14000DADA
0x14000d9c3  mov     [rbp+var_38], 0FFFFFFFEh
0x14000d9ca  mov     ecx, [rdi+38h]
0x14000d9cd  mov     eax, [rbp+var_38]
0x14000d9d0  lock cmpxchg [rbp+var_38], ecx
0x14000d9d5  mov     [rbp+var_30], rsi
0x14000d9d9  lea     rcx, [rbp+var_30]
0x14000d9dd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000d9e2  lea     rcx, [rdi+78h]
0x14000d9e6  lea     r8, [rbp+var_30]
0x14000d9ea  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>>::CopyLocal(_GUID const &,void * *)
0x14000d9ef  test    eax, eax
0x14000d9f1  js      loc_14000DABC
0x14000d9f7  mov     rcx, rdi
0x14000d9fa  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x14000d9ff  mov     [rbp+var_48], rsi
0x14000da03  lea     rcx, [rbp+var_48]
0x14000da07  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000da0c  lea     r8, [rbp+var_48]; struct IRpcOptions **
0x14000da10  mov     rcx, [rbp+var_30]; struct IUnknown *
0x14000da14  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x14000da19  mov     r9, [rbp+var_30]
0x14000da1d  mov     r8, [rbp+var_28]
0x14000da21  mov     rdx, [rbp+var_48]
0x14000da25  lea     rcx, [rbp+pStm]; ppstm
0x14000da29  call    ?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@56@@Z; BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *> *)
0x14000da2e  nop
0x14000da2f  mov     rcx, [rbp+var_30]
0x14000da33  mov     rax, [rcx]
0x14000da36  mov     r8d, [rbp+var_38]
0x14000da3a  mov     rdx, [rbp+var_28]
0x14000da3e  mov     rax, [rax+18h]
0x14000da42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da47  mov     r8, [rdi+80h]
0x14000da4e  mov     rdx, [rbp+var_30]
0x14000da52  mov     ecx, eax
0x14000da54  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x14000da59  mov     esi, eax
0x14000da5b  mov     rcx, rdi
0x14000da5e  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x14000da63  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x14000da68  nop
0x14000da69  cmp     [rbp+var_18], 0
0x14000da6d  jl      short loc_14000DA94
0x14000da6f  mov     r10, [rbp+pStm]
0x14000da73  xor     edx, edx
0x14000da75  mov     rcx, [r10]
0x14000da78  mov     rax, [rcx+28h]
0x14000da7c  xor     r9d, r9d
0x14000da7f  xor     r8d, r8d
0x14000da82  mov     rcx, r10
0x14000da85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da8a  mov     rcx, [rbp+pStm]; pStm
0x14000da8e  call    cs:__imp_CoReleaseMarshalData
0x14000da94  lea     rcx, [rbp+pStm]
0x14000da98  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000da9d  nop
0x14000da9e  mov     rcx, [rbp+var_48]
0x14000daa2  test    rcx, rcx
0x14000daa5  jz      short loc_14000DABC
0x14000daa7  mov     [rbp+var_48], 0
0x14000daaf  mov     rax, [rcx]
0x14000dab2  mov     rax, [rax+10h]
0x14000dab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dabb  nop
0x14000dabc  mov     rcx, [rbp+var_30]
0x14000dac0  test    rcx, rcx
0x14000dac3  jz      short loc_14000DADA
0x14000dac5  mov     [rbp+var_30], 0
0x14000dacd  mov     rax, [rcx]
0x14000dad0  mov     rax, [rax+10h]
0x14000dad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dad9  nop
0x14000dada  mov     rcx, [rbp+var_28]
0x14000dade  test    rcx, rcx
0x14000dae1  jz      short loc_14000DAF8
0x14000dae3  mov     [rbp+var_28], 0
0x14000daeb  mov     rax, [rcx]
0x14000daee  mov     rax, [rax+10h]
0x14000daf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000daf7  nop
0x14000daf8  mov     rax, [rdi]
0x14000dafb  mov     rcx, rdi
0x14000dafe  mov     rax, [rax+10h]
0x14000db02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000db07  nop
0x14000db08  mov     eax, esi
0x14000db0a  mov     rcx, [rbp+var_10]
0x14000db0e  xor     rcx, rsp; StackCookie
0x14000db11  call    __security_check_cookie
0x14000db16  add     rsp, 78h
0x14000db1a  pop     rdi
0x14000db1b  pop     rsi
0x14000db1c  pop     rbx
0x14000db1d  pop     rbp
0x14000db1e  retn
```
