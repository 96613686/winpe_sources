# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18009d950`
- end: `0x18009daeb`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009db00`

## callees

- `0x1800038e0`
- `0x180016064`
- `0x1800383d8`
- `0x18003cbcc`
- `0x18003d1c0`
- `0x18004a950`
- `0x180073ce0`
- `0x1800785f0`
- `0x18007cac8`
- `0x18007cc6c`
- `0x18009ab2c`
- `0x18009d368`
- `0x18009d950`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009da35`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009da35`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18009da64`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18009da64`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // edi
  unsigned int v3; // edx
  __int64 v4; // rdx
  bool v5; // dl
  IUnknown *v6; // rdi
  unsigned int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::UI::Core::CoreAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(
                &v9,
                &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>>::CopyLocal(
                  a1 + 120,
                  v4,
                  &v13) >= 0 )
      {
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
        v14 = 0;
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
        RpcOptionsHelper::GetRpcOptions(v13, v5, &v14);
        ppstm = 0;
        v11 = 0;
        if ( v14 && v13 )
        {
          v6 = pUnk;
          Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&ppstm);
          v11 = CreateStreamOnHGlobal(0, 1, &ppstm);
          if ( v11 >= 0 )
            v11 = CoMarshalInterface(ppstm, &GUID_00000000_0000_0000_c000_000000000046, v6, 0, 0, 1u);
        }
        else
        {
          v11 = -2147467262;
        }
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPUNKNOWN, _QWORD))v13->lpVtbl[1].QueryInterface)(
               v13,
               pUnk,
               v12);
        v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(
               v7,
               v13,
               *(_QWORD *)(a1 + 128));
        Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(a1);
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
        AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(&ppstm);
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v14);
      }
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v13);
    }
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&pUnk);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x18009d950  push    rbp
0x18009d952  push    rbx
0x18009d953  push    rdi
0x18009d954  mov     rbp, rsp
0x18009d957  sub     rsp, 50h
0x18009d95b  mov     rbx, rcx
0x18009d95e  xor     edi, edi
0x18009d960  lea     edx, [rdi+1]
0x18009d963  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18009d968  cmp     [rbx+88h], edi
0x18009d96e  jle     loc_18009DAE1
0x18009d974  mov     eax, edx
0x18009d976  lock xadd [rbx+10h], eax
0x18009d97b  inc     eax
0x18009d97d  cmp     eax, edx
0x18009d97f  jnz     loc_18009DAE1
0x18009d985  mov     [rbp+var_20], rbx
0x18009d989  lea     rcx, [rbp+var_20]
0x18009d98d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18009d992  nop
0x18009d993  mov     [rbp+pUnk], rdi
0x18009d997  mov     rcx, rbx
0x18009d99a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CoreAsyncOperationName@Core@UI@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::UI::Core::CoreAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18009d99f  lea     rdx, [rbp+pUnk]
0x18009d9a3  lea     rcx, [rbp+var_20]
0x18009d9a7  call    ??$As@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *>>>)
0x18009d9ac  test    eax, eax
0x18009d9ae  js      loc_18009DACE
0x18009d9b4  mov     [rbp+arg_0], 0FFFFFFFEh
0x18009d9bb  mov     ecx, [rbx+38h]
0x18009d9be  mov     eax, [rbp+arg_0]
0x18009d9c1  lock cmpxchg [rbp+arg_0], ecx
0x18009d9c6  mov     [rbp+arg_8], rdi
0x18009d9ca  lea     rcx, [rbp+arg_8]
0x18009d9ce  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009d9d3  lea     rcx, [rbx+78h]
0x18009d9d7  lea     r8, [rbp+arg_8]
0x18009d9db  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>>::CopyLocal(_GUID const &,void * *)
0x18009d9e0  test    eax, eax
0x18009d9e2  js      loc_18009DAC4
0x18009d9e8  mov     rcx, rbx
0x18009d9eb  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18009d9f0  mov     [rbp+arg_10], rdi
0x18009d9f4  lea     rcx, [rbp+arg_10]
0x18009d9f8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009d9fd  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x18009da01  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x18009da05  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x18009da0a  mov     [rbp+ppstm], rdi
0x18009da0e  mov     [rbp+var_10], edi
0x18009da11  cmp     [rbp+arg_10], rdi
0x18009da15  jz      short loc_18009DA6F
0x18009da17  cmp     [rbp+arg_8], rdi
0x18009da1b  jz      short loc_18009DA6F
0x18009da1d  mov     rdi, [rbp+pUnk]
0x18009da21  lea     rcx, [rbp+ppstm]
0x18009da25  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009da2a  lea     r8, [rbp+ppstm]; ppstm
0x18009da2e  mov     edx, 1; fDeleteOnRelease
0x18009da33  xor     ecx, ecx; hGlobal
0x18009da35  call    cs:__imp_CreateStreamOnHGlobal
0x18009da3b  mov     [rbp+var_10], eax
0x18009da3e  test    eax, eax
0x18009da40  js      short loc_18009DA76
0x18009da42  mov     [rsp+50h+mshlflags], 1; mshlflags
0x18009da4a  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x18009da53  xor     r9d, r9d; dwDestContext
0x18009da56  mov     r8, rdi; pUnk
0x18009da59  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x18009da60  mov     rcx, [rbp+ppstm]; pStm
0x18009da64  call    cs:__imp_CoMarshalInterface
0x18009da6a  mov     [rbp+var_10], eax
0x18009da6d  jmp     short loc_18009DA76
0x18009da6f  mov     [rbp+var_10], 80004002h
0x18009da76  mov     rcx, [rbp+arg_8]
0x18009da7a  mov     rax, [rcx]
0x18009da7d  mov     r8d, [rbp+arg_0]
0x18009da81  mov     rdx, [rbp+pUnk]
0x18009da85  mov     rax, [rax+18h]
0x18009da89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009da8e  mov     r8, [rbx+80h]
0x18009da95  mov     rdx, [rbp+arg_8]
0x18009da99  mov     ecx, eax
0x18009da9b  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18009daa0  mov     edi, eax
0x18009daa2  mov     rcx, rbx
0x18009daa5  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18009daaa  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18009daaf  nop
0x18009dab0  lea     rcx, [rbp+ppstm]
0x18009dab4  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x18009dab9  nop
0x18009daba  lea     rcx, [rbp+arg_10]
0x18009dabe  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009dac3  nop
0x18009dac4  lea     rcx, [rbp+arg_8]
0x18009dac8  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009dacd  nop
0x18009dace  lea     rcx, [rbp+pUnk]
0x18009dad2  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009dad7  nop
0x18009dad8  lea     rcx, [rbp+var_20]
0x18009dadc  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009dae1  mov     eax, edi
0x18009dae3  add     rsp, 50h
0x18009dae7  pop     rdi
0x18009dae8  pop     rbx
0x18009dae9  pop     rbp
0x18009daea  retn
```
