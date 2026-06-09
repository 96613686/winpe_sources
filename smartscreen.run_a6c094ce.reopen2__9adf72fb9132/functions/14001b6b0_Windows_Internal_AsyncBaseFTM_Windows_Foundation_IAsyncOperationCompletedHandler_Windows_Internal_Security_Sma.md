# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x14001b6b0`
- end: `0x14001b914`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `612`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003dd00`

## callees

- `0x1400061cc`
- `0x140007ba0`
- `0x14000e724`
- `0x14000e84c`
- `0x14000fa34`
- `0x14001b6b0`
- `0x14001b91c`
- `0x14001b950`
- `0x14001b984`
- `0x14001b9c8`
- `0x140026c20`
- `0x14006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001b804`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001b804`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001b7d3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001b7d3`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001b87c`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001b87c`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        int (__fastcall ***a1)(_QWORD, GUID *, LPUNKNOWN *))
{
  unsigned int v2; // esi
  unsigned int v3; // edx
  int (__fastcall *v4)(_QWORD, GUID *, LPUNKNOWN *); // rbx
  __int64 v5; // rdx
  bool v6; // dl
  IUnknown *v7; // rbx
  unsigned int v8; // eax
  struct IRpcOptions *v9; // rcx
  struct IUnknown *v10; // rcx
  LPUNKNOWN v11; // rcx
  struct IRpcOptions *v13[2]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v14; // [rsp+40h] [rbp-30h] BYREF
  struct IUnknown *v15; // [rsp+48h] [rbp-28h] BYREF
  LPUNKNOWN pUnk; // [rsp+50h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+58h] [rbp-18h] BYREF
  HRESULT v18; // [rsp+60h] [rbp-10h]

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *((int *)a1 + 34) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 4, v3) + 1 == v3 )
  {
    v13[1] = (struct IRpcOptions *)a1;
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, LPUNKNOWN *)))(*a1)[1])(a1);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    v4 = **a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pUnk);
    if ( v4(a1, &GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462, &pUnk) >= 0 )
    {
      v14 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v14, *((_DWORD *)a1 + 14), -2);
      v15 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>>::CopyLocal(
                  a1 + 15,
                  v5,
                  &v15) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v13[0] = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v13);
        RpcOptionsHelper::GetRpcOptions(v15, v6, v13);
        ppstm = 0;
        v18 = 0;
        if ( v13[0] && v15 )
        {
          v7 = pUnk;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
          v18 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v18 >= 0 )
            v18 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v7, 0, 0, 1u);
        }
        else
        {
          v18 = -2147467262;
        }
        v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v15->lpVtbl[1].QueryInterface)(
               v15,
               pUnk,
               v14);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v8,
               v15,
               a1[16]);
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        if ( v18 >= 0 )
        {
          (*(void (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
          CoReleaseMarshalData(ppstm);
        }
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppstm);
        v9 = v13[0];
        if ( v13[0] )
        {
          v13[0] = 0;
          ((void (__fastcall *)(struct IRpcOptions *))v9->lpVtbl->Release)(v9);
        }
      }
      v10 = v15;
      if ( v15 )
      {
        v15 = 0;
        ((void (__fastcall *)(struct IUnknown *))v10->lpVtbl->Release)(v10);
      }
    }
    v11 = pUnk;
    if ( pUnk )
    {
      pUnk = 0;
      ((void (__fastcall *)(LPUNKNOWN))v11->lpVtbl->Release)(v11);
    }
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, LPUNKNOWN *)))(*a1)[2])(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x14001b6b0  mov     [rsp-18h+arg_8], rbx
0x14001b6b5  mov     [rsp-18h+arg_10], rsi
0x14001b6ba  push    rbp
0x14001b6bb  push    rdi
0x14001b6bc  push    r14
0x14001b6be  mov     rbp, rsp
0x14001b6c1  sub     rsp, 70h
0x14001b6c5  mov     rax, cs:__security_cookie
0x14001b6cc  xor     rax, rsp
0x14001b6cf  mov     [rbp+var_8], rax
0x14001b6d3  mov     rdi, rcx
0x14001b6d6  xor     r14d, r14d
0x14001b6d9  mov     esi, r14d
0x14001b6dc  lea     edx, [r14+1]
0x14001b6e0  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14001b6e5  cmp     [rdi+88h], r14d
0x14001b6ec  jle     loc_14001B8F0
0x14001b6f2  mov     eax, edx
0x14001b6f4  lock xadd [rdi+10h], eax
0x14001b6f9  inc     eax
0x14001b6fb  cmp     eax, edx
0x14001b6fd  jnz     loc_14001B8F0
0x14001b703  mov     [rbp+var_38], rdi
0x14001b707  mov     rax, [rdi]
0x14001b70a  mov     rcx, rdi
0x14001b70d  mov     rax, [rax+8]
0x14001b711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b716  nop
0x14001b717  mov     [rbp+pUnk], r14
0x14001b71b  mov     rcx, rdi
0x14001b71e  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x14001b723  nop
0x14001b724  mov     rax, [rdi]
0x14001b727  mov     rbx, [rax]
0x14001b72a  lea     rcx, [rbp+pUnk]
0x14001b72e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001b733  lea     r8, [rbp+pUnk]
0x14001b737  lea     rdx, _GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462
0x14001b73e  mov     rcx, rdi
0x14001b741  mov     rax, rbx
0x14001b744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b749  nop
0x14001b74a  test    eax, eax
0x14001b74c  js      loc_14001B8C6
0x14001b752  mov     [rbp+var_30], 0FFFFFFFEh
0x14001b759  mov     ecx, [rdi+38h]
0x14001b75c  mov     eax, [rbp+var_30]
0x14001b75f  lock cmpxchg [rbp+var_30], ecx
0x14001b764  mov     [rbp+var_28], r14
0x14001b768  lea     rcx, [rbp+var_28]
0x14001b76c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001b771  lea     rcx, [rdi+78h]
0x14001b775  lea     r8, [rbp+var_28]
0x14001b779  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>>::CopyLocal(_GUID const &,void * *)
0x14001b77e  test    eax, eax
0x14001b780  js      loc_14001B8AC
0x14001b786  mov     rcx, rdi
0x14001b789  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x14001b78e  mov     [rbp+var_40], r14
0x14001b792  lea     rcx, [rbp+var_40]
0x14001b796  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001b79b  lea     r8, [rbp+var_40]; struct IRpcOptions **
0x14001b79f  mov     rcx, [rbp+var_28]; struct IUnknown *
0x14001b7a3  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x14001b7a8  mov     [rbp+ppstm], r14
0x14001b7ac  mov     [rbp+var_10], r14d
0x14001b7b0  cmp     [rbp+var_40], r14
0x14001b7b4  jz      short loc_14001B815
0x14001b7b6  cmp     [rbp+var_28], r14
0x14001b7ba  jz      short loc_14001B815
0x14001b7bc  mov     rbx, [rbp+pUnk]
0x14001b7c0  lea     rcx, [rbp+ppstm]
0x14001b7c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001b7c9  lea     r8, [rbp+ppstm]; ppstm
0x14001b7cd  lea     edx, [r14+1]; fDeleteOnRelease
0x14001b7d1  xor     ecx, ecx; hGlobal
0x14001b7d3  call    cs:__imp_CreateStreamOnHGlobal
0x14001b7da  nop     dword ptr [rax+rax+00h]
0x14001b7df  mov     [rbp+var_10], eax
0x14001b7e2  test    eax, eax
0x14001b7e4  js      short loc_14001B81C
0x14001b7e6  mov     [rsp+70h+mshlflags], 1; mshlflags
0x14001b7ee  mov     [rsp+70h+pvDestContext], r14; pvDestContext
0x14001b7f3  xor     r9d, r9d; dwDestContext
0x14001b7f6  mov     r8, rbx; pUnk
0x14001b7f9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14001b800  mov     rcx, [rbp+ppstm]; pStm
0x14001b804  call    cs:__imp_CoMarshalInterface
0x14001b80b  nop     dword ptr [rax+rax+00h]
0x14001b810  mov     [rbp+var_10], eax
0x14001b813  jmp     short loc_14001B81C
0x14001b815  mov     [rbp+var_10], 80004002h
0x14001b81c  mov     rcx, [rbp+var_28]
0x14001b820  mov     rax, [rcx]
0x14001b823  mov     r8d, [rbp+var_30]
0x14001b827  mov     rdx, [rbp+pUnk]
0x14001b82b  mov     rax, [rax+18h]
0x14001b82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b834  mov     r8, [rdi+80h]
0x14001b83b  mov     rdx, [rbp+var_28]
0x14001b83f  mov     ecx, eax
0x14001b841  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x14001b846  mov     esi, eax
0x14001b848  mov     rcx, rdi
0x14001b84b  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x14001b850  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x14001b855  nop
0x14001b856  cmp     [rbp+var_10], r14d
0x14001b85a  jl      short loc_14001B888
0x14001b85c  mov     r10, [rbp+ppstm]
0x14001b860  mov     rdx, r14
0x14001b863  mov     rcx, [r10]
0x14001b866  mov     rax, [rcx+28h]
0x14001b86a  xor     r9d, r9d
0x14001b86d  xor     r8d, r8d
0x14001b870  mov     rcx, r10
0x14001b873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b878  mov     rcx, [rbp+ppstm]; pStm
0x14001b87c  call    cs:__imp_CoReleaseMarshalData
0x14001b883  nop     dword ptr [rax+rax+00h]
0x14001b888  lea     rcx, [rbp+ppstm]
0x14001b88c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001b891  nop
0x14001b892  mov     rcx, [rbp+var_40]
0x14001b896  test    rcx, rcx
0x14001b899  jz      short loc_14001B8AC
0x14001b89b  mov     [rbp+var_40], r14
0x14001b89f  mov     rax, [rcx]
0x14001b8a2  mov     rax, [rax+10h]
0x14001b8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b8ab  nop
0x14001b8ac  mov     rcx, [rbp+var_28]
0x14001b8b0  test    rcx, rcx
0x14001b8b3  jz      short loc_14001B8C6
0x14001b8b5  mov     [rbp+var_28], r14
0x14001b8b9  mov     rax, [rcx]
0x14001b8bc  mov     rax, [rax+10h]
0x14001b8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b8c5  nop
0x14001b8c6  mov     rcx, [rbp+pUnk]
0x14001b8ca  test    rcx, rcx
0x14001b8cd  jz      short loc_14001B8E0
0x14001b8cf  mov     [rbp+pUnk], r14
0x14001b8d3  mov     rax, [rcx]
0x14001b8d6  mov     rax, [rax+10h]
0x14001b8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b8df  nop
0x14001b8e0  mov     rax, [rdi]
0x14001b8e3  mov     rcx, rdi
0x14001b8e6  mov     rax, [rax+10h]
0x14001b8ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b8ef  nop
0x14001b8f0  mov     eax, esi
0x14001b8f2  mov     rcx, [rbp+var_8]
0x14001b8f6  xor     rcx, rsp; StackCookie
0x14001b8f9  call    __security_check_cookie
0x14001b8fe  lea     r11, [rsp+70h+var_s0]
0x14001b903  mov     rbx, [r11+28h]
0x14001b907  mov     rsi, [r11+30h]
0x14001b90b  mov     rsp, r11
0x14001b90e  pop     r14
0x14001b910  pop     rdi
0x14001b911  pop     rbp
0x14001b912  retn
```
