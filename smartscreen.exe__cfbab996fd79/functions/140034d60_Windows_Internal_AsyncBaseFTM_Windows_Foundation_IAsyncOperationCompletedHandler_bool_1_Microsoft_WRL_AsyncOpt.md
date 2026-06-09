# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x140034d60`
- end: `0x140034f33`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140034f40`

## callees

- `0x1400061cc`
- `0x140007ba0`
- `0x14000e724`
- `0x14000e84c`
- `0x140011ed0`
- `0x14001b91c`
- `0x14001b984`
- `0x14001b9c8`
- `0x14001ebcc`
- `0x14001f264`
- `0x140026c20`
- `0x140030c4c`
- `0x14003494c`
- `0x140034d60`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140034e8f`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x140034e8f`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140034e5a`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x140034e5a`

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
0x140034d60  mov     [rsp-8+arg_8], rbx
0x140034d65  mov     [rsp-8+arg_10], rdi
0x140034d6a  push    rbp
0x140034d6b  mov     rbp, rsp
0x140034d6e  sub     rsp, 70h
0x140034d72  mov     rax, cs:__security_cookie
0x140034d79  xor     rax, rsp
0x140034d7c  mov     [rbp+var_8], rax
0x140034d80  mov     rbx, rcx
0x140034d83  xor     edi, edi
0x140034d85  lea     edx, [rdi+1]
0x140034d88  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x140034d8d  cmp     [rbx+88h], edi
0x140034d93  jle     loc_140034F12
0x140034d99  mov     eax, edx
0x140034d9b  lock xadd [rbx+10h], eax
0x140034da0  inc     eax
0x140034da2  cmp     eax, edx
0x140034da4  jnz     loc_140034F12
0x140034daa  mov     [rbp+var_38], rbx
0x140034dae  lea     rcx, [rbp+var_38]
0x140034db2  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x140034db7  nop
0x140034db8  mov     [rbp+pUnk], rdi
0x140034dbc  mov     rcx, rbx
0x140034dbf  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x140034dc4  lea     rdx, [rbp+pUnk]
0x140034dc8  lea     rcx, [rbp+var_38]
0x140034dcc  call    ??$As@U?$IAsyncOperation@_N@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<bool>>>)
0x140034dd1  test    eax, eax
0x140034dd3  js      loc_140034EFF
0x140034dd9  mov     [rbp+var_30], 0FFFFFFFEh
0x140034de0  mov     ecx, [rbx+38h]
0x140034de3  mov     eax, [rbp+var_30]
0x140034de6  lock cmpxchg [rbp+var_30], ecx
0x140034deb  mov     [rbp+var_28], rdi
0x140034def  lea     rcx, [rbp+var_28]
0x140034df3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140034df8  lea     rcx, [rbx+78h]
0x140034dfc  lea     r8, [rbp+var_28]
0x140034e00  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(_GUID const &,void * *)
0x140034e05  test    eax, eax
0x140034e07  js      loc_140034EF5
0x140034e0d  mov     rcx, rbx
0x140034e10  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x140034e15  mov     [rbp+var_40], rdi
0x140034e19  lea     rcx, [rbp+var_40]
0x140034e1d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140034e22  lea     r8, [rbp+var_40]; struct IRpcOptions **
0x140034e26  mov     rcx, [rbp+var_28]; struct IUnknown *
0x140034e2a  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x140034e2f  mov     [rbp+ppstm], rdi
0x140034e33  mov     [rbp+var_10], edi
0x140034e36  cmp     [rbp+var_40], rdi
0x140034e3a  jz      short loc_140034EA0
0x140034e3c  cmp     [rbp+var_28], rdi
0x140034e40  jz      short loc_140034EA0
0x140034e42  mov     rdi, [rbp+pUnk]
0x140034e46  lea     rcx, [rbp+ppstm]
0x140034e4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140034e4f  lea     r8, [rbp+ppstm]; ppstm
0x140034e53  mov     edx, 1; fDeleteOnRelease
0x140034e58  xor     ecx, ecx; hGlobal
0x140034e5a  call    cs:__imp_CreateStreamOnHGlobal
0x140034e61  nop     dword ptr [rax+rax+00h]
0x140034e66  mov     [rbp+var_10], eax
0x140034e69  test    eax, eax
0x140034e6b  js      short loc_140034EA7
0x140034e6d  mov     [rsp+70h+mshlflags], 1; mshlflags
0x140034e75  mov     [rsp+70h+pvDestContext], 0; pvDestContext
0x140034e7e  xor     r9d, r9d; dwDestContext
0x140034e81  mov     r8, rdi; pUnk
0x140034e84  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x140034e8b  mov     rcx, [rbp+ppstm]; pStm
0x140034e8f  call    cs:__imp_CoMarshalInterface
0x140034e96  nop     dword ptr [rax+rax+00h]
0x140034e9b  mov     [rbp+var_10], eax
0x140034e9e  jmp     short loc_140034EA7
0x140034ea0  mov     [rbp+var_10], 80004002h
0x140034ea7  mov     rcx, [rbp+var_28]
0x140034eab  mov     rax, [rcx]
0x140034eae  mov     r8d, [rbp+var_30]
0x140034eb2  mov     rdx, [rbp+pUnk]
0x140034eb6  mov     rax, [rax+18h]
0x140034eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034ebf  mov     r8, [rbx+80h]
0x140034ec6  mov     rdx, [rbp+var_28]
0x140034eca  mov     ecx, eax
0x140034ecc  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x140034ed1  mov     edi, eax
0x140034ed3  mov     rcx, rbx
0x140034ed6  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x140034edb  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x140034ee0  nop
0x140034ee1  lea     rcx, [rbp+ppstm]
0x140034ee5  call    ??1?$AutoStubBias@U?$IAsyncOperation@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::AppReputationResult>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>>(void)
0x140034eea  nop
0x140034eeb  lea     rcx, [rbp+var_40]
0x140034eef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140034ef4  nop
0x140034ef5  lea     rcx, [rbp+var_28]
0x140034ef9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140034efe  nop
0x140034eff  lea     rcx, [rbp+pUnk]
0x140034f03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140034f08  nop
0x140034f09  lea     rcx, [rbp+var_38]
0x140034f0d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140034f12  mov     eax, edi
0x140034f14  mov     rcx, [rbp+var_8]
0x140034f18  xor     rcx, rsp; StackCookie
0x140034f1b  call    __security_check_cookie
0x140034f20  lea     r11, [rsp+70h+var_s0]
0x140034f25  mov     rbx, [r11+18h]
0x140034f29  mov     rdi, [r11+20h]
0x140034f2d  mov     rsp, r11
0x140034f30  pop     rbp
0x140034f31  retn
```
