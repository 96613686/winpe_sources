# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x14003c530`
- end: `0x14003c622`
- name: `?FireCompletion@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `242`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140005e4c`
- `0x1400077d0`
- `0x14000df68`
- `0x14000e118`
- `0x14001aae8`
- `0x14001aba0`
- `0x14001dbbc`
- `0x14001dfd4`
- `0x140025aa0`
- `0x14003c530`
- `0x140068010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  signed __int32 v3; // edx
  __int64 *v4; // rdi
  unsigned int v5; // eax
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v8; // [rsp+28h] [rbp-20h] BYREF
  __int64 v9; // [rsp+30h] [rbp-18h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  v4 = (__int64 *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 24) && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v3, 0) )
  {
    v7 = a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v7);
    v9 = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>>(
                &v7,
                &v9) >= 0 )
    {
      v8 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v8, *(_DWORD *)(a1 + 56), -2);
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)*v4 + 24LL))(*v4, v9, v8);
      v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(v5, *v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)(a1 + 24));
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  }
  return v2;
}

```

## disassembly

```asm
0x14003c530  push    rbp
0x14003c532  push    rbx
0x14003c533  push    rsi
0x14003c534  push    rdi
0x14003c535  mov     rbp, rsp
0x14003c538  sub     rsp, 48h
0x14003c53c  mov     rax, cs:__security_cookie
0x14003c543  xor     rax, rsp
0x14003c546  mov     [rbp+var_10], rax
0x14003c54a  mov     rbx, rcx
0x14003c54d  xor     esi, esi
0x14003c54f  lea     edx, [rsi+1]
0x14003c552  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14003c557  lea     rdi, [rbx+18h]
0x14003c55b  cmp     [rdi], rsi
0x14003c55e  jz      loc_14003C60B
0x14003c564  xor     eax, eax
0x14003c566  lock cmpxchg [rbx+10h], edx
0x14003c56b  jnz     loc_14003C60B
0x14003c571  mov     [rbp+var_28], rbx
0x14003c575  lea     rcx, [rbp+var_28]
0x14003c579  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x14003c57e  nop
0x14003c57f  mov     [rbp+var_18], rsi
0x14003c583  mov     rcx, rbx
0x14003c586  call    ?TraceOperationComplete@?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?k_OperationLogEventStr@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const k_OperationLogEventStr,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x14003c58b  lea     rdx, [rbp+var_18]
0x14003c58f  lea     rcx, [rbp+var_28]
0x14003c593  call    ??$As@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>>>)
0x14003c598  test    eax, eax
0x14003c59a  js      short loc_14003C5F8
0x14003c59c  mov     [rbp+var_20], 0FFFFFFFEh
0x14003c5a3  mov     ecx, [rbx+38h]
0x14003c5a6  mov     eax, [rbp+var_20]
0x14003c5a9  lock cmpxchg [rbp+var_20], ecx
0x14003c5ae  mov     rcx, rbx
0x14003c5b1  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::AppReputationResult>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x14003c5b6  mov     rcx, [rdi]
0x14003c5b9  mov     rax, [rcx]
0x14003c5bc  mov     r8d, [rbp+var_20]
0x14003c5c0  mov     rdx, [rbp+var_18]
0x14003c5c4  mov     rax, [rax+18h]
0x14003c5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c5cd  mov     r8, [rbx+28h]
0x14003c5d1  mov     rdx, [rdi]
0x14003c5d4  mov     ecx, eax
0x14003c5d6  call    ?FireCompletionErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireCompletionErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x14003c5db  mov     esi, eax
0x14003c5dd  or      edx, 0FFFFFFFFh
0x14003c5e0  lock xadd [rbx+20h], edx
0x14003c5e5  cmp     edx, 1
0x14003c5e8  jnz     short loc_14003C5F2
0x14003c5ea  mov     rcx, rdi
0x14003c5ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003c5f2  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x14003c5f7  nop
0x14003c5f8  lea     rcx, [rbp+var_18]
0x14003c5fc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003c601  nop
0x14003c602  lea     rcx, [rbp+var_28]
0x14003c606  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14003c60b  mov     eax, esi
0x14003c60d  mov     rcx, [rbp+var_10]
0x14003c611  xor     rcx, rsp; StackCookie
0x14003c614  call    __security_check_cookie
0x14003c619  add     rsp, 48h
0x14003c61d  pop     rdi
0x14003c61e  pop     rsi
0x14003c61f  pop     rbx
0x14003c620  pop     rbp
0x14003c621  retn
```
