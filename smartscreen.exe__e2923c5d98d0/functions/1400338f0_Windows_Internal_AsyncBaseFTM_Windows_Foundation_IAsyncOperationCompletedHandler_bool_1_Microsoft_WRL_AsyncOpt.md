# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1400338f0`
- end: `0x140033ab6`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `454`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140033ac0`

## callees

- `0x140005e4c`
- `0x1400077d0`
- `0x14000dff0`
- `0x14000e118`
- `0x14001158c`
- `0x14001aae8`
- `0x14001ab60`
- `0x14001aba0`
- `0x14001dbbc`
- `0x14001e178`
- `0x140025aa0`
- `0x14002f970`
- `0x1400334a0`
- `0x1400338f0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140033a19`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140033a19`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1400339ea`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1400339ea`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  struct IRpcOptions *v9; // [rsp+30h] [rbp-40h] BYREF
  __int64 v10; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-30h] BYREF
  struct IUnknown *v12; // [rsp+48h] [rbp-28h] BYREF
  LPUNKNOWN pUnk; // [rsp+50h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-18h] BYREF
  HRESULT v15; // [rsp+60h] [rbp-10h]

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v10 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v10);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(&v10, &pUnk) >= 0 )
    {
      v11 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v11, *(_DWORD *)(a1 + 56), -2);
      v12 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v12) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v9 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
        RpcOptionsHelper::GetRpcOptions(v12, v5, &v9);
        ppstm = 0;
        v15 = 0;
        if ( v9 && v12 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v15 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v15 >= 0 )
            v15 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
        }
        else
        {
          v15 = -2147467262;
        }
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v12->lpVtbl[1].QueryInterface)(
               v12,
               pUnk,
               v11);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v7,
               v12,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>>(&ppstm);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
  return v2;
}

```

## disassembly

```asm
0x1400338f0  mov     [rsp-8+arg_8], rbx
0x1400338f5  mov     [rsp-8+arg_10], rdi
0x1400338fa  push    rbp
0x1400338fb  mov     rbp, rsp
0x1400338fe  sub     rsp, 70h
0x140033902  mov     rax, cs:__security_cookie
0x140033909  xor     rax, rsp
0x14003390c  mov     [rbp+var_8], rax
0x140033910  mov     rbx, rcx
0x140033913  xor     edi, edi
0x140033915  lea     edx, [rdi+1]
0x140033918  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14003391d  cmp     [rbx+88h], edi
0x140033923  jle     loc_140033A96
0x140033929  mov     eax, edx
0x14003392b  lock xadd [rbx+10h], eax
0x140033930  inc     eax
0x140033932  cmp     eax, edx
0x140033934  jnz     loc_140033A96
0x14003393a  mov     [rbp+var_38], rbx
0x14003393e  lea     rcx, [rbp+var_38]
0x140033942  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x140033947  nop
0x140033948  mov     [rbp+pUnk], rdi
0x14003394c  mov     rcx, rbx
0x14003394f  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x140033954  lea     rdx, [rbp+pUnk]
0x140033958  lea     rcx, [rbp+var_38]
0x14003395c  call    ??$As@U?$IAsyncOperation@_N@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<bool>>>)
0x140033961  test    eax, eax
0x140033963  js      loc_140033A83
0x140033969  mov     [rbp+var_30], 0FFFFFFFEh
0x140033970  mov     ecx, [rbx+38h]
0x140033973  mov     eax, [rbp+var_30]
0x140033976  lock cmpxchg [rbp+var_30], ecx
0x14003397b  mov     [rbp+var_28], rdi
0x14003397f  lea     rcx, [rbp+var_28]
0x140033983  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033988  lea     rcx, [rbx+78h]
0x14003398c  lea     r8, [rbp+var_28]
0x140033990  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(_GUID const &,void * *)
0x140033995  test    eax, eax
0x140033997  js      loc_140033A79
0x14003399d  mov     rcx, rbx
0x1400339a0  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x1400339a5  mov     [rbp+var_40], rdi
0x1400339a9  lea     rcx, [rbp+var_40]
0x1400339ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400339b2  lea     r8, [rbp+var_40]; struct IRpcOptions **
0x1400339b6  mov     rcx, [rbp+var_28]; struct IUnknown *
0x1400339ba  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x1400339bf  mov     [rbp+ppstm], rdi
0x1400339c3  mov     [rbp+var_10], edi
0x1400339c6  cmp     [rbp+var_40], rdi
0x1400339ca  jz      short loc_140033A24
0x1400339cc  cmp     [rbp+var_28], rdi
0x1400339d0  jz      short loc_140033A24
0x1400339d2  mov     rdi, [rbp+pUnk]
0x1400339d6  lea     rcx, [rbp+ppstm]
0x1400339da  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400339df  lea     r8, [rbp+ppstm]; ppstm
0x1400339e3  mov     edx, 1; fDeleteOnRelease
0x1400339e8  xor     ecx, ecx; hGlobal
0x1400339ea  call    cs:__imp_CreateStreamOnHGlobal
0x1400339f0  mov     [rbp+var_10], eax
0x1400339f3  test    eax, eax
0x1400339f5  js      short loc_140033A2B
0x1400339f7  mov     [rsp+70h+mshlflags], 1; mshlflags
0x1400339ff  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x140033a08  xor     r9d, r9d; dwDestContext
0x140033a0b  mov     r8, rdi; pUnk
0x140033a0e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140033a15  mov     rcx, [rbp+ppstm]; pStm
0x140033a19  call    cs:__imp_CoMarshalInterface
0x140033a1f  mov     [rbp+var_10], eax
0x140033a22  jmp     short loc_140033A2B
0x140033a24  mov     [rbp+var_10], 80004002h
0x140033a2b  mov     rcx, [rbp+var_28]
0x140033a2f  mov     rax, [rcx]
0x140033a32  mov     r8d, [rbp+var_30]
0x140033a36  mov     rdx, [rbp+pUnk]
0x140033a3a  mov     rax, [rax+18h]
0x140033a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140033a43  mov     r8, [rbx+80h]
0x140033a4a  mov     rdx, [rbp+var_28]
0x140033a4e  mov     ecx, eax
0x140033a50  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x140033a55  mov     edi, eax
0x140033a57  mov     rcx, rbx
0x140033a5a  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x140033a5f  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x140033a64  nop
0x140033a65  lea     rcx, [rbp+ppstm]
0x140033a69  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>(void)
0x140033a6e  nop
0x140033a6f  lea     rcx, [rbp+var_40]
0x140033a73  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033a78  nop
0x140033a79  lea     rcx, [rbp+var_28]
0x140033a7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033a82  nop
0x140033a83  lea     rcx, [rbp+pUnk]
0x140033a87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033a8c  nop
0x140033a8d  lea     rcx, [rbp+var_38]
0x140033a91  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140033a96  mov     eax, edi
0x140033a98  mov     rcx, [rbp+var_8]
0x140033a9c  xor     rcx, rsp; StackCookie
0x140033a9f  call    __security_check_cookie
0x140033aa4  lea     r11, [rsp+70h+var_s0]
0x140033aa9  mov     rbx, [r11+18h]
0x140033aad  mov     rdi, [r11+20h]
0x140033ab1  mov     rsp, r11
0x140033ab4  pop     rbp
0x140033ab5  retn
```
