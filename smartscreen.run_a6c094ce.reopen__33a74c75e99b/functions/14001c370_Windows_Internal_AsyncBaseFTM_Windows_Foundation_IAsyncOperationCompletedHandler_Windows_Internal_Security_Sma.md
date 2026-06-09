# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x14001c370`
- end: `0x14001c4e1`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001c310`

## callees

- `0x1400061cc`
- `0x140007ba0`
- `0x14000e724`
- `0x14000e84c`
- `0x14000fa34`
- `0x14001b91c`
- `0x14001b9c8`
- `0x14001c370`
- `0x14001ea40`
- `0x14001ebcc`
- `0x14001f264`
- `0x14001f82c`
- `0x140026c20`
- `0x140030bfc`
- `0x140034918`
- `0x14006a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  unsigned int v6; // eax
  struct IRpcOptions *v8; // [rsp+20h] [rbp-40h] BYREF
  __int64 v9; // [rsp+28h] [rbp-38h] BYREF
  unsigned int v10; // [rsp+30h] [rbp-30h] BYREF
  struct IUnknown *v11; // [rsp+38h] [rbp-28h] BYREF
  IUnknown *v12; // [rsp+40h] [rbp-20h] BYREF
  LPSTREAM ppstm[2]; // [rsp+48h] [rbp-18h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && v3 + _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
    v12 = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>(
                &v9,
                &v12) >= 0 )
    {
      v10 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v10, *(_DWORD *)(a1 + 56), -2);
      v11 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v11) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v8 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v8);
        RpcOptionsHelper::GetRpcOptions(v11, v5, &v8);
        BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(
          ppstm,
          (__int64)v8,
          v12,
          (__int64)v11);
        v6 = ((__int64 (__fastcall *)(struct IUnknown *, IUnknown *, _QWORD))v11->lpVtbl[1].QueryInterface)(
               v11,
               v12,
               v10);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v6,
               v11,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>(ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v8);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v12);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x14001c370  mov     [rsp-8+arg_8], rbx
0x14001c375  mov     [rsp-8+arg_10], rdi
0x14001c37a  push    rbp
0x14001c37b  mov     rbp, rsp
0x14001c37e  sub     rsp, 60h
0x14001c382  mov     rax, cs:__security_cookie
0x14001c389  xor     rax, rsp
0x14001c38c  mov     [rbp+var_8], rax
0x14001c390  mov     rbx, rcx
0x14001c393  xor     edi, edi
0x14001c395  lea     edx, [rdi+1]
0x14001c398  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14001c39d  cmp     [rbx+88h], edi
0x14001c3a3  jle     loc_14001C4C0
0x14001c3a9  mov     eax, edx
0x14001c3ab  lock xadd [rbx+10h], eax
0x14001c3b0  add     eax, edx
0x14001c3b2  cmp     eax, edx
0x14001c3b4  jnz     loc_14001C4C0
0x14001c3ba  mov     [rbp+var_38], rbx
0x14001c3be  lea     rcx, [rbp+var_38]
0x14001c3c2  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x14001c3c7  nop
0x14001c3c8  mov     [rbp+var_20], rdi
0x14001c3cc  mov     rcx, rbx
0x14001c3cf  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x14001c3d4  lea     rdx, [rbp+var_20]
0x14001c3d8  lea     rcx, [rbp+var_38]
0x14001c3dc  call    ??$As@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>>>)
0x14001c3e1  test    eax, eax
0x14001c3e3  js      loc_14001C4AD
0x14001c3e9  mov     [rbp+var_30], 0FFFFFFFEh
0x14001c3f0  mov     ecx, [rbx+38h]
0x14001c3f3  mov     eax, [rbp+var_30]
0x14001c3f6  lock cmpxchg [rbp+var_30], ecx
0x14001c3fb  mov     [rbp+var_28], rdi
0x14001c3ff  lea     rcx, [rbp+var_28]
0x14001c403  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c408  lea     rcx, [rbx+78h]
0x14001c40c  lea     r8, [rbp+var_28]
0x14001c410  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::CopyLocal(_GUID const &,void * *)
0x14001c415  test    eax, eax
0x14001c417  js      loc_14001C4A3
0x14001c41d  mov     rcx, rbx
0x14001c420  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x14001c425  mov     [rbp+var_40], rdi
0x14001c429  lea     rcx, [rbp+var_40]
0x14001c42d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c432  lea     r8, [rbp+var_40]; struct IRpcOptions **
0x14001c436  mov     rcx, [rbp+var_28]; struct IUnknown *
0x14001c43a  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x14001c43f  mov     r9, [rbp+var_28]
0x14001c443  mov     r8, [rbp+var_20]
0x14001c447  mov     rdx, [rbp+var_40]
0x14001c44b  lea     rcx, [rbp+ppstm]; ppstm
0x14001c44f  call    ?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@56@@Z; BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *> *)
0x14001c454  nop
0x14001c455  mov     rcx, [rbp+var_28]
0x14001c459  mov     rax, [rcx]
0x14001c45c  mov     r8d, [rbp+var_30]
0x14001c460  mov     rdx, [rbp+var_20]
0x14001c464  mov     rax, [rax+18h]
0x14001c468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c46d  mov     r8, [rbx+80h]
0x14001c474  mov     rdx, [rbp+var_28]
0x14001c478  mov     ecx, eax
0x14001c47a  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x14001c47f  mov     edi, eax
0x14001c481  mov     rcx, rbx
0x14001c484  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x14001c489  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x14001c48e  nop
0x14001c48f  lea     rcx, [rbp+ppstm]
0x14001c493  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>(void)
0x14001c498  nop
0x14001c499  lea     rcx, [rbp+var_40]
0x14001c49d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c4a2  nop
0x14001c4a3  lea     rcx, [rbp+var_28]
0x14001c4a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c4ac  nop
0x14001c4ad  lea     rcx, [rbp+var_20]
0x14001c4b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c4b6  nop
0x14001c4b7  lea     rcx, [rbp+var_38]
0x14001c4bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c4c0  mov     eax, edi
0x14001c4c2  mov     rcx, [rbp+var_8]
0x14001c4c6  xor     rcx, rsp; StackCookie
0x14001c4c9  call    __security_check_cookie
0x14001c4ce  lea     r11, [rsp+60h+var_s0]
0x14001c4d3  mov     rbx, [r11+18h]
0x14001c4d7  mov     rdi, [r11+20h]
0x14001c4db  mov     rsp, r11
0x14001c4de  pop     rbp
0x14001c4df  retn
```
