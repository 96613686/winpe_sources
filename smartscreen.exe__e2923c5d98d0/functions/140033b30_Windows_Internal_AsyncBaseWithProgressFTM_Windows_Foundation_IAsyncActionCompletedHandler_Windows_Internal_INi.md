# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x140033b30`
- end: `0x140033cc9`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `409`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140034f00`

## callees

- `0x140005e4c`
- `0x14000d81c`
- `0x14000dff0`
- `0x14001d934`
- `0x14001dbbc`
- `0x14001e178`
- `0x140025aa0`
- `0x14002f9c0`
- `0x14002faec`
- `0x140033b30`
- `0x140035174`
- `0x1400352c0`
- `0x140068010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(
        __int64 a1,
        unsigned int a2)
{
  unsigned int v4; // edi
  bool v5; // dl
  unsigned int v6; // eax
  struct IRpcOptions *v8; // [rsp+40h] [rbp-9h] BYREF
  __int64 v9; // [rsp+48h] [rbp-1h] BYREF
  GUID v10; // [rsp+50h] [rbp+7h] BYREF
  struct IUnknown *v11; // [rsp+60h] [rbp+17h] BYREF
  IUnknown *v12; // [rsp+68h] [rbp+1Fh] BYREF
  LPSTREAM ppstm[2]; // [rsp+70h] [rbp+27h] BYREF

  v4 = 0;
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
  v12 = 0;
  if ( (unsigned __int8)Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(a1)
    && (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<IUnknown>(&v9, &v12) >= 0 )
  {
    v11 = 0;
    if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal<Windows::Internal::INilDelegate>(
                a1 + 144,
                &v11) >= 0 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v10 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 72LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          &v10,
          a1,
          1);
      }
      v8 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v8);
      RpcOptionsHelper::GetRpcOptions(v11, v5, &v8);
      BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(
        ppstm,
        (__int64)v8,
        v12,
        (__int64)v11);
      v6 = ((__int64 (__fastcall *)(struct IUnknown *, IUnknown *, _QWORD))v11->lpVtbl[1].QueryInterface)(v11, v12, a2);
      v4 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
             v6,
             v11,
             *(_QWORD *)(a1 + 152));
      if ( Microsoft::WRL::gCausality )
        (*(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::gCausality + 80LL))(
          Microsoft::WRL::gCausality,
          1,
          2,
          1);
      AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>(ppstm);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v8);
    }
    Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(a1);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v11);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)&v12);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
  return v4;
}

```

## disassembly

```asm
0x140033b30  mov     [rsp-8+arg_10], rbx
0x140033b35  push    rbp
0x140033b36  push    rsi
0x140033b37  push    rdi
0x140033b38  lea     rbp, [rsp-47h]
0x140033b3d  sub     rsp, 90h
0x140033b44  mov     rax, cs:__security_cookie
0x140033b4b  xor     rax, rsp
0x140033b4e  mov     [rbp+57h+var_20], rax
0x140033b52  mov     esi, edx
0x140033b54  mov     rbx, rcx
0x140033b57  xor     edi, edi
0x140033b59  mov     [rbp+57h+var_58], rcx
0x140033b5d  lea     rcx, [rbp+57h+var_58]
0x140033b61  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x140033b66  nop
0x140033b67  mov     [rbp+57h+var_38], rdi
0x140033b6b  mov     rcx, rbx
0x140033b6e  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x140033b73  test    al, al
0x140033b75  jz      loc_140033C95
0x140033b7b  lea     rdx, [rbp+57h+var_38]
0x140033b7f  lea     rcx, [rbp+57h+var_58]
0x140033b83  call    ??$As@UIUnknown@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x140033b88  test    eax, eax
0x140033b8a  js      loc_140033C95
0x140033b90  mov     [rbp+57h+var_40], rdi
0x140033b94  lea     rcx, [rbx+90h]
0x140033b9b  lea     rdx, [rbp+57h+var_40]
0x140033b9f  call    ??$CopyLocal@UINilDelegate@Internal@Windows@@@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UINilDelegate@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal<Windows::Internal::INilDelegate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::INilDelegate>>)
0x140033ba4  test    eax, eax
0x140033ba6  js      loc_140033C82
0x140033bac  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140033bb3  test    rcx, rcx
0x140033bb6  jz      short loc_140033BE8
0x140033bb8  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140033bbf  movdqu  [rbp+57h+var_50], xmm0
0x140033bc4  mov     rax, [rcx]
0x140033bc7  mov     [rsp+0A0h+var_78], 1
0x140033bcf  mov     [rsp+0A0h+var_80], rbx
0x140033bd4  lea     r9, [rbp+57h+var_50]
0x140033bd8  lea     edx, [rdi+1]
0x140033bdb  lea     r8d, [rdi+2]
0x140033bdf  mov     rax, [rax+48h]
0x140033be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033be8  mov     [rbp+57h+var_60], 0
0x140033bf0  lea     rcx, [rbp+57h+var_60]
0x140033bf4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033bf9  lea     r8, [rbp+57h+var_60]; struct IRpcOptions **
0x140033bfd  mov     rcx, [rbp+57h+var_40]; struct IUnknown *
0x140033c01  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x140033c06  mov     r9, [rbp+57h+var_40]
0x140033c0a  mov     r8, [rbp+57h+var_38]
0x140033c0e  mov     rdx, [rbp+57h+var_60]
0x140033c12  lea     rcx, [rbp+57h+ppstm]; ppstm
0x140033c16  call    ?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@56@@Z; BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *> *)
0x140033c1b  nop
0x140033c1c  mov     rcx, [rbp+57h+var_40]
0x140033c20  mov     rax, [rcx]
0x140033c23  mov     r8d, esi
0x140033c26  mov     rdx, [rbp+57h+var_38]
0x140033c2a  mov     rax, [rax+18h]
0x140033c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033c33  mov     r8, [rbx+98h]
0x140033c3a  mov     rdx, [rbp+57h+var_40]
0x140033c3e  mov     ecx, eax
0x140033c40  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x140033c45  mov     edi, eax
0x140033c47  mov     r10, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140033c4e  test    r10, r10
0x140033c51  jz      short loc_140033C6F
0x140033c53  mov     rcx, [r10]
0x140033c56  mov     rax, [rcx+50h]
0x140033c5a  mov     edx, 1
0x140033c5f  mov     r9d, edx
0x140033c62  lea     r8d, [rdx+1]
0x140033c66  mov     rcx, r10
0x140033c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033c6e  nop
0x140033c6f  lea     rcx, [rbp+57h+ppstm]
0x140033c73  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>(void)
0x140033c78  nop
0x140033c79  lea     rcx, [rbp+57h+var_60]
0x140033c7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033c82  mov     rcx, rbx
0x140033c85  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x140033c8a  nop
0x140033c8b  lea     rcx, [rbp+57h+var_40]
0x140033c8f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033c94  nop
0x140033c95  lea     rcx, [rbp+57h+var_38]
0x140033c99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033c9e  nop
0x140033c9f  lea     rcx, [rbp+57h+var_58]
0x140033ca3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033ca8  mov     eax, edi
0x140033caa  mov     rcx, [rbp+57h+var_20]
0x140033cae  xor     rcx, rsp; StackCookie
0x140033cb1  call    __security_check_cookie
0x140033cb6  mov     rbx, [rsp+0A0h+arg_10]
0x140033cbe  add     rsp, 90h
0x140033cc5  pop     rdi
0x140033cc6  pop     rsi
0x140033cc7  pop     rbp
0x140033cc8  retn
```
