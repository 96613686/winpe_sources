# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x180076ef0`
- end: `0x18007708b`
- name: `?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800770a0`

## callees

- `0x1800038e0`
- `0x1800085d4`
- `0x180016064`
- `0x1800383d8`
- `0x18003cbcc`
- `0x180044098`
- `0x18004a950`
- `0x180073ce0`
- `0x18007620c`
- `0x180076ef0`
- `0x1800785f0`
- `0x18007cac8`
- `0x18007cc6c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180076fd5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180076fd5`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180077004`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180077004`

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
  __int64 v9; // [rsp+30h] [rbp-20h] BYREF
  LPSTREAM ppstm; // [rsp+38h] [rbp-18h] BYREF
  HRESULT v11; // [rsp+40h] [rbp-10h]
  unsigned int v12; // [rsp+70h] [rbp+20h] BYREF
  struct IUnknown *v13; // [rsp+78h] [rbp+28h] BYREF
  struct IRpcOptions *v14; // [rsp+80h] [rbp+30h] BYREF
  LPUNKNOWN pUnk; // [rsp+88h] [rbp+38h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  if ( *(int *)(a1 + 136) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), v3) + 1 == v3 )
  {
    v9 = a1;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v9);
    pUnk = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const Windows::UI::Core::CoreAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(&v9, &pUnk) >= 0 )
    {
      v12 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v12, *(_DWORD *)(a1 + 56), -2);
      v13 = 0;
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v13);
      if ( (int)Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(
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
0x180076ef0  push    rbp
0x180076ef2  push    rbx
0x180076ef3  push    rdi
0x180076ef4  mov     rbp, rsp
0x180076ef7  sub     rsp, 50h
0x180076efb  mov     rbx, rcx
0x180076efe  xor     edi, edi
0x180076f00  lea     edx, [rdi+1]
0x180076f03  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180076f08  cmp     [rbx+88h], edi
0x180076f0e  jle     loc_180077081
0x180076f14  mov     eax, edx
0x180076f16  lock xadd [rbx+10h], eax
0x180076f1b  inc     eax
0x180076f1d  cmp     eax, edx
0x180076f1f  jnz     loc_180077081
0x180076f25  mov     [rbp+var_20], rbx
0x180076f29  lea     rcx, [rbp+var_20]
0x180076f2d  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180076f32  nop
0x180076f33  mov     [rbp+pUnk], rdi
0x180076f37  mov     rcx, rbx
0x180076f3a  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?CoreAsyncOperationName@Core@UI@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::UI::Core::CoreAsyncOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180076f3f  lea     rdx, [rbp+pUnk]
0x180076f43  lea     rcx, [rbp+var_20]
0x180076f47  call    ??$As@U?$IAsyncOperation@_N@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@_N@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<bool>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<bool>>>)
0x180076f4c  test    eax, eax
0x180076f4e  js      loc_18007706E
0x180076f54  mov     [rbp+arg_0], 0FFFFFFFEh
0x180076f5b  mov     ecx, [rbx+38h]
0x180076f5e  mov     eax, [rbp+arg_0]
0x180076f61  lock cmpxchg [rbp+arg_0], ecx
0x180076f66  mov     [rbp+arg_8], rdi
0x180076f6a  lea     rcx, [rbp+arg_8]
0x180076f6e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180076f73  lea     rcx, [rbx+78h]
0x180076f77  lea     r8, [rbp+arg_8]
0x180076f7b  call    ?CopyLocal@?$GitPtrSupportsAgile@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::GitPtrSupportsAgile<Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::CopyLocal(_GUID const &,void * *)
0x180076f80  test    eax, eax
0x180076f82  js      loc_180077064
0x180076f88  mov     rcx, rbx
0x180076f8b  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x180076f90  mov     [rbp+arg_10], rdi
0x180076f94  lea     rcx, [rbp+arg_10]
0x180076f98  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180076f9d  lea     r8, [rbp+arg_10]; struct IRpcOptions **
0x180076fa1  mov     rcx, [rbp+arg_8]; struct IUnknown *
0x180076fa5  call    ?GetRpcOptions@RpcOptionsHelper@@SAJPEAUIUnknown@@_NPEAPEAUIRpcOptions@@@Z; RpcOptionsHelper::GetRpcOptions(IUnknown *,bool,IRpcOptions * *)
0x180076faa  mov     [rbp+ppstm], rdi
0x180076fae  mov     [rbp+var_10], edi
0x180076fb1  cmp     [rbp+arg_10], rdi
0x180076fb5  jz      short loc_18007700F
0x180076fb7  cmp     [rbp+arg_8], rdi
0x180076fbb  jz      short loc_18007700F
0x180076fbd  mov     rdi, [rbp+pUnk]
0x180076fc1  lea     rcx, [rbp+ppstm]
0x180076fc5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180076fca  lea     r8, [rbp+ppstm]; ppstm
0x180076fce  mov     edx, 1; fDeleteOnRelease
0x180076fd3  xor     ecx, ecx; hGlobal
0x180076fd5  call    cs:__imp_CreateStreamOnHGlobal
0x180076fdb  mov     [rbp+var_10], eax
0x180076fde  test    eax, eax
0x180076fe0  js      short loc_180077016
0x180076fe2  mov     [rsp+50h+mshlflags], 1; mshlflags
0x180076fea  mov     [rsp+50h+pvDestContext], 0; pvDestContext
0x180076ff3  xor     r9d, r9d; dwDestContext
0x180076ff6  mov     r8, rdi; pUnk
0x180076ff9  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180077000  mov     rcx, [rbp+ppstm]; pStm
0x180077004  call    cs:__imp_CoMarshalInterface
0x18007700a  mov     [rbp+var_10], eax
0x18007700d  jmp     short loc_180077016
0x18007700f  mov     [rbp+var_10], 80004002h
0x180077016  mov     rcx, [rbp+arg_8]
0x18007701a  mov     rax, [rcx]
0x18007701d  mov     r8d, [rbp+arg_0]
0x180077021  mov     rdx, [rbp+pUnk]
0x180077025  mov     rax, [rax+18h]
0x180077029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007702e  mov     r8, [rbx+80h]
0x180077035  mov     rdx, [rbp+arg_8]
0x180077039  mov     ecx, eax
0x18007703b  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180077040  mov     edi, eax
0x180077042  mov     rcx, rbx
0x180077045  call    ?UnlockCompleteDelegate@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::UnlockCompleteDelegate(void)
0x18007704a  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUIUICommand@Popups@UI@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18007704f  nop
0x180077050  lea     rcx, [rbp+ppstm]
0x180077054  call    ??1?$AutoStubBias@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@@@QEAA@XZ; AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>::~AutoStubBias<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>>(void)
0x180077059  nop
0x18007705a  lea     rcx, [rbp+arg_10]
0x18007705e  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180077063  nop
0x180077064  lea     rcx, [rbp+arg_8]
0x180077068  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18007706d  nop
0x18007706e  lea     rcx, [rbp+pUnk]
0x180077072  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180077077  nop
0x180077078  lea     rcx, [rbp+var_20]
0x18007707c  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180077081  mov     eax, edi
0x180077083  add     rsp, 50h
0x180077087  pop     rdi
0x180077088  pop     rbx
0x180077089  pop     rbp
0x18007708a  retn
```
