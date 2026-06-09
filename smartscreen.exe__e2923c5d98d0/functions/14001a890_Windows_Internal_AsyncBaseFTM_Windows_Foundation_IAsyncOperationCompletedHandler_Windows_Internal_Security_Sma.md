# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x14001a890`
- end: `0x14001aae1`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003c630`

## callees

- `0x140005e4c`
- `0x1400077d0`
- `0x14000dff0`
- `0x14000e118`
- `0x14000f1f0`
- `0x14001a890`
- `0x14001aae8`
- `0x14001ab18`
- `0x14001ab60`
- `0x14001aba0`
- `0x140025aa0`
- `0x140068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001a9de`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x14001a9de`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001a9b3`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x14001a9b3`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001aa50`
- `api-ms-win-core-com-l1-1-0!CoReleaseMarshalData` at `0x14001aa50`

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
0x14001a890  mov     [rsp-18h+arg_8], rbx
0x14001a895  mov     [rsp-18h+arg_10], rsi
0x14001a89a  push    rbp
0x14001a89b  push    rdi
0x14001a89c  push    r14
0x14001a89e  mov     rbp, rsp
0x14001a8a1  sub     rsp, 70h
0x14001a8a5  mov     rax, cs:__security_cookie
0x14001a8ac  xor     rax, rsp
0x14001a8af  mov     [rbp+var_8], rax
0x14001a8b3  mov     rdi, rcx
0x14001a8b6  xor     r14d, r14d
0x14001a8b9  mov     esi, r14d
0x14001a8bc  lea     edx, [r14+1]
0x14001a8c0  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14001a8c5  cmp     [rdi+88h], r14d
0x14001a8cc  jle     loc_14001AABE
0x14001a8d2  mov     eax, edx
0x14001a8d4  lock xadd [rdi+10h], eax
0x14001a8d9  inc     eax
0x14001a8db  cmp     eax, edx
0x14001a8dd  jnz     loc_14001AABE
0x14001a8e3  mov     [rbp+var_38], rdi
0x14001a8e7  mov     rax, [rdi]
0x14001a8ea  mov     rcx, rdi
0x14001a8ed  mov     rax, [rax+8]
0x14001a8f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a8f6  nop
0x14001a8f7  mov     [rbp+pUnk], r14
0x14001a8fb  mov     rcx, rdi
0x14001a8fe  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x14001a903  nop
0x14001a904  mov     rax, [rdi]
0x14001a907  mov     rbx, [rax]
0x14001a90a  lea     rcx, [rbp+pUnk]
0x14001a90e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001a913  lea     r8, [rbp+pUnk]
0x14001a917  lea     rdx, _GUID_b2b6814f_02c2_5b0c_9e14_159eb77f4462
0x14001a91e  mov     rcx, rdi
0x14001a921  mov     rax, rbx
0x14001a924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a929  nop
0x14001a92a  test    eax, eax
0x14001a92c  js      loc_14001AA94
0x14001a932  mov     [rbp+var_30], 0FFFFFFFEh
0x14001a939  mov     ecx, [rdi+38h]
0x14001a93c  mov     eax, [rbp+var_30]
0x14001a93f  lock cmpxchg [rbp+var_30], ecx
0x14001a944  mov     [rbp+var_28], r14
0x14001a948  lea     rcx, [rbp+var_28]
0x14001a94c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001a951  lea     rcx, [rdi+78h]
0x14001a955  lea     r8, [rbp+var_28]
0x14001a959  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>>::CopyLocal(_GUID const &,void * *)
0x14001a95e  test    eax, eax
0x14001a960  js      loc_14001AA7A
0x14001a966  mov     rcx, rdi
0x14001a969  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x14001a96e  mov     [rbp+var_40], r14
0x14001a972  lea     rcx, [rbp+var_40]
0x14001a976  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001a97b  lea     r8, [rbp+var_40]; struct IRpcOptions **
0x14001a97f  mov     rcx, [rbp+var_28]; struct IUnknown *
0x14001a983  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x14001a988  mov     [rbp+ppstm], r14
0x14001a98c  mov     [rbp+var_10], r14d
0x14001a990  cmp     [rbp+var_40], r14
0x14001a994  jz      short loc_14001A9E9
0x14001a996  cmp     [rbp+var_28], r14
0x14001a99a  jz      short loc_14001A9E9
0x14001a99c  mov     rbx, [rbp+pUnk]
0x14001a9a0  lea     rcx, [rbp+ppstm]
0x14001a9a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001a9a9  lea     r8, [rbp+ppstm]; ppstm
0x14001a9ad  lea     edx, [r14+1]; fDeleteOnRelease
0x14001a9b1  xor     ecx, ecx; hGlobal
0x14001a9b3  call    cs:__imp_CreateStreamOnHGlobal
0x14001a9b9  mov     [rbp+var_10], eax
0x14001a9bc  test    eax, eax
0x14001a9be  js      short loc_14001A9F0
0x14001a9c0  mov     [rsp+70h+mshlflags], 1; mshlflags
0x14001a9c8  mov     [rsp+70h+pvDestContext], r14; pvDestContext
0x14001a9cd  xor     r9d, r9d; dwDestContext
0x14001a9d0  mov     r8, rbx; pUnk
0x14001a9d3  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x14001a9da  mov     rcx, [rbp+ppstm]; pStm
0x14001a9de  call    cs:__imp_CoMarshalInterface
0x14001a9e4  mov     [rbp+var_10], eax
0x14001a9e7  jmp     short loc_14001A9F0
0x14001a9e9  mov     [rbp+var_10], 80004002h
0x14001a9f0  mov     rcx, [rbp+var_28]
0x14001a9f4  mov     rax, [rcx]
0x14001a9f7  mov     r8d, [rbp+var_30]
0x14001a9fb  mov     rdx, [rbp+pUnk]
0x14001a9ff  mov     rax, [rax+18h]
0x14001aa03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa08  mov     r8, [rdi+80h]
0x14001aa0f  mov     rdx, [rbp+var_28]
0x14001aa13  mov     ecx, eax
0x14001aa15  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x14001aa1a  mov     esi, eax
0x14001aa1c  mov     rcx, rdi
0x14001aa1f  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x14001aa24  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x14001aa29  nop
0x14001aa2a  cmp     [rbp+var_10], r14d
0x14001aa2e  jl      short loc_14001AA56
0x14001aa30  mov     r10, [rbp+ppstm]
0x14001aa34  mov     rdx, r14
0x14001aa37  mov     rcx, [r10]
0x14001aa3a  mov     rax, [rcx+28h]
0x14001aa3e  xor     r9d, r9d
0x14001aa41  xor     r8d, r8d
0x14001aa44  mov     rcx, r10
0x14001aa47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa4c  mov     rcx, [rbp+ppstm]; pStm
0x14001aa50  call    cs:__imp_CoReleaseMarshalData
0x14001aa56  lea     rcx, [rbp+ppstm]
0x14001aa5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001aa5f  nop
0x14001aa60  mov     rcx, [rbp+var_40]
0x14001aa64  test    rcx, rcx
0x14001aa67  jz      short loc_14001AA7A
0x14001aa69  mov     [rbp+var_40], r14
0x14001aa6d  mov     rax, [rcx]
0x14001aa70  mov     rax, [rax+10h]
0x14001aa74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa79  nop
0x14001aa7a  mov     rcx, [rbp+var_28]
0x14001aa7e  test    rcx, rcx
0x14001aa81  jz      short loc_14001AA94
0x14001aa83  mov     [rbp+var_28], r14
0x14001aa87  mov     rax, [rcx]
0x14001aa8a  mov     rax, [rax+10h]
0x14001aa8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aa93  nop
0x14001aa94  mov     rcx, [rbp+pUnk]
0x14001aa98  test    rcx, rcx
0x14001aa9b  jz      short loc_14001AAAE
0x14001aa9d  mov     [rbp+pUnk], r14
0x14001aaa1  mov     rax, [rcx]
0x14001aaa4  mov     rax, [rax+10h]
0x14001aaa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aaad  nop
0x14001aaae  mov     rax, [rdi]
0x14001aab1  mov     rcx, rdi
0x14001aab4  mov     rax, [rax+10h]
0x14001aab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001aabd  nop
0x14001aabe  mov     eax, esi
0x14001aac0  mov     rcx, [rbp+var_8]
0x14001aac4  xor     rcx, rsp; StackCookie
0x14001aac7  call    __security_check_cookie
0x14001aacc  lea     r11, [rsp+70h+var_s0]
0x14001aad1  mov     rbx, [r11+28h]
0x14001aad5  mov     rsi, [r11+30h]
0x14001aad9  mov     rsp, r11
0x14001aadc  pop     r14
0x14001aade  pop     rdi
0x14001aadf  pop     rbp
0x14001aae0  retn
```
