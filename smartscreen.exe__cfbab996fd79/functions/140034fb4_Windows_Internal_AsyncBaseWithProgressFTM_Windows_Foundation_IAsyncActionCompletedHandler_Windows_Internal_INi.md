# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireProgress(int)

- ea: `0x140034fb4`
- end: `0x14003514e`
- name: `?FireProgress@?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@QEAAJH@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140036410`

## callees

- `0x1400061cc`
- `0x14000df14`
- `0x14000e724`
- `0x14001ea40`
- `0x14001ebcc`
- `0x14001f264`
- `0x140026c20`
- `0x140030c9c`
- `0x140030dc8`
- `0x140034fb4`
- `0x1400366a8`
- `0x140036808`
- `0x14006a010`

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
0x140034fb4  mov     [rsp-8+arg_10], rbx
0x140034fb9  push    rbp
0x140034fba  push    rsi
0x140034fbb  push    rdi
0x140034fbc  lea     rbp, [rsp-47h]
0x140034fc1  sub     rsp, 90h
0x140034fc8  mov     rax, cs:__security_cookie
0x140034fcf  xor     rax, rsp
0x140034fd2  mov     [rbp+57h+var_20], rax
0x140034fd6  mov     esi, edx
0x140034fd8  mov     rbx, rcx
0x140034fdb  xor     edi, edi
0x140034fdd  mov     [rbp+57h+var_58], rcx
0x140034fe1  lea     rcx, [rbp+57h+var_58]
0x140034fe5  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x140034fea  nop
0x140034feb  mov     [rbp+57h+var_38], rdi
0x140034fef  mov     rcx, rbx
0x140034ff2  call    ?TryLockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAA_NXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryLockProgressDelegate(void)
0x140034ff7  test    al, al
0x140034ff9  jz      loc_140035119
0x140034fff  lea     rdx, [rbp+57h+var_38]
0x140035003  lea     rcx, [rbp+57h+var_58]
0x140035007  call    ??$As@UIUnknown@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<IUnknown>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUnknown>>)
0x14003500c  test    eax, eax
0x14003500e  js      loc_140035119
0x140035014  mov     [rbp+57h+var_40], rdi
0x140035018  lea     rcx, [rbx+90h]
0x14003501f  lea     rdx, [rbp+57h+var_40]
0x140035023  call    ??$CopyLocal@UINilDelegate@Internal@Windows@@@?$GitPtrSupportsAgile@UINilDelegate@Internal@Windows@@@Internal@Windows@@QEAAJV?$ComPtrRef@V?$ComPtr@UINilDelegate@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Internal::INilDelegate>::CopyLocal<Windows::Internal::INilDelegate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::INilDelegate>>)
0x140035028  test    eax, eax
0x14003502a  js      loc_140035106
0x140035030  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x140035037  test    rcx, rcx
0x14003503a  jz      short loc_14003506C
0x14003503c  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x140035043  movdqu  [rbp+57h+var_50], xmm0
0x140035048  mov     rax, [rcx]
0x14003504b  mov     [rsp+0A0h+var_78], 1
0x140035053  mov     [rsp+0A0h+var_80], rbx
0x140035058  lea     r9, [rbp+57h+var_50]
0x14003505c  lea     edx, [rdi+1]
0x14003505f  lea     r8d, [rdi+2]
0x140035063  mov     rax, [rax+48h]
0x140035067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003506c  mov     [rbp+57h+var_60], 0
0x140035074  lea     rcx, [rbp+57h+var_60]
0x140035078  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003507d  lea     r8, [rbp+57h+var_60]; struct IRpcOptions **
0x140035081  mov     rcx, [rbp+57h+var_40]; struct IUnknown *
0x140035085  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x14003508a  mov     r9, [rbp+57h+var_40]
0x14003508e  mov     r8, [rbp+57h+var_38]
0x140035092  mov     rdx, [rbp+57h+var_60]
0x140035096  lea     rcx, [rbp+57h+ppstm]; ppstm
0x14003509a  call    ?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@56@@Z; BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *> *)
0x14003509f  nop
0x1400350a0  mov     rcx, [rbp+57h+var_40]
0x1400350a4  mov     rax, [rcx]
0x1400350a7  mov     r8d, esi
0x1400350aa  mov     rdx, [rbp+57h+var_38]
0x1400350ae  mov     rax, [rax+18h]
0x1400350b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400350b7  mov     r8, [rbx+98h]
0x1400350be  mov     rdx, [rbp+57h+var_40]
0x1400350c2  mov     ecx, eax
0x1400350c4  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x1400350c9  mov     edi, eax
0x1400350cb  mov     r10, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1400350d2  test    r10, r10
0x1400350d5  jz      short loc_1400350F3
0x1400350d7  mov     rcx, [r10]
0x1400350da  mov     rax, [rcx+50h]
0x1400350de  mov     edx, 1
0x1400350e3  mov     r9d, edx
0x1400350e6  lea     r8d, [rdx+1]
0x1400350ea  mov     rcx, r10
0x1400350ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400350f2  nop
0x1400350f3  lea     rcx, [rbp+57h+ppstm]
0x1400350f7  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>(void)
0x1400350fc  nop
0x1400350fd  lea     rcx, [rbp+57h+var_60]
0x140035101  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140035106  mov     rcx, rbx
0x140035109  call    ?UnlockProgressDelegate@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockProgressDelegate(void)
0x14003510e  nop
0x14003510f  lea     rcx, [rbp+57h+var_40]
0x140035113  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140035118  nop
0x140035119  lea     rcx, [rbp+57h+var_38]
0x14003511d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140035122  nop
0x140035123  lea     rcx, [rbp+57h+var_58]
0x140035127  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003512c  mov     eax, edi
0x14003512e  mov     rcx, [rbp+57h+var_20]
0x140035132  xor     rcx, rsp; StackCookie
0x140035135  call    __security_check_cookie
0x14003513a  mov     rbx, [rsp+0A0h+arg_10]
0x140035142  add     rsp, 90h
0x140035149  pop     rdi
0x14003514a  pop     rsi
0x14003514b  pop     rbp
0x14003514c  retn
```
