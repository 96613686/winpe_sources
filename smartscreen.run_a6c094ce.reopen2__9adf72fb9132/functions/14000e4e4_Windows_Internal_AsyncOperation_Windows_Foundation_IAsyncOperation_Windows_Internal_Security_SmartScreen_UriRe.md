# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x14000e4e4`
- end: `0x14000e695`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140012580`
- `0x14003f8b0`

## callees

- `0x14000e24c`
- `0x14000e4e4`
- `0x14000e69c`
- `0x140026c20`
- `0x140040ffc`
- `0x1400410ec`
- `0x14006a010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  bool v5; // cl
  int v6; // eax
  bool v7; // bp
  __int64 v8; // rcx
  signed __int32 v9; // edx
  signed __int32 v10; // [rsp+30h] [rbp-28h] BYREF

  if ( (_DWORD)a2 == 2 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) != 1 )
      return;
    v4 = a1 + 288;
    (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
      *(_QWORD *)(a1 + 264),
      a2,
      a3,
      a1 + 288);
    v5 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
        *(_QWORD *)(a1 + 264),
        1,
        2147943623LL,
        v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) != 1 )
        return;
    }
    else if ( !v5 )
    {
      return;
    }
LABEL_22:
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
    return;
  }
  if ( (_DWORD)a2 == 1 && _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
           *(_QWORD *)(a1 + 264),
           1,
           a3,
           a1 + 288);
    if ( v6 >= 0 && *(_BYTE *)(a1 + 297) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 280), 0xFFFFFFFF) == 1 )
        Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
          a1,
          *(unsigned int *)(a1 + 284),
          (unsigned int)v6);
    }
    else
    {
      v7 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
      if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) == 1 )
        v7 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
      v8 = a1 + 8;
      if ( v6 >= 0 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
                                 v8,
                                 1) )
          _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), 1, 2);
      }
      else
      {
        v9 = *(_DWORD *)(a1 + 64);
        v10 = -2;
        _InterlockedCompareExchange(&v10, v9, -2);
        if ( v10 != 2 )
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
            v8,
            (unsigned int)v6);
      }
      if ( v7 )
        goto LABEL_22;
    }
  }
}

```

## disassembly

```asm
0x14000e4e4  push    rbx
0x14000e4e6  push    rbp
0x14000e4e7  push    rdi
0x14000e4e8  sub     rsp, 40h
0x14000e4ec  mov     rax, cs:__security_cookie
0x14000e4f3  xor     rax, rsp
0x14000e4f6  mov     [rsp+58h+var_20], rax
0x14000e4fb  mov     rbx, rcx
0x14000e4fe  mov     edi, 1
0x14000e503  cmp     edx, 2
0x14000e506  jnz     loc_14000E59B
0x14000e50c  mov     eax, edi
0x14000e50e  lock xadd [rcx+0FCh], eax
0x14000e516  add     eax, edi
0x14000e518  cmp     eax, edi
0x14000e51a  jnz     loc_14000E67F
0x14000e520  lea     rbp, [rcx+120h]
0x14000e527  mov     rcx, [rcx+108h]
0x14000e52e  mov     r9, rbp
0x14000e531  mov     rax, [rcx]
0x14000e534  mov     rax, [rax+8]
0x14000e538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e53d  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000e545  setz    cl
0x14000e548  mov     eax, edi
0x14000e54a  lock xadd [rbx+100h], eax
0x14000e552  add     eax, edi
0x14000e554  cmp     eax, edi
0x14000e556  jnz     short loc_14000E58E
0x14000e558  mov     rcx, [rbx+108h]
0x14000e55f  mov     r9, rbp
0x14000e562  mov     r8d, 800704C7h
0x14000e568  mov     edx, edi
0x14000e56a  mov     rax, [rcx]
0x14000e56d  mov     rax, [rax+8]
0x14000e571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e576  or      eax, 0FFFFFFFFh
0x14000e579  lock xadd [rbx+104h], eax
0x14000e581  cmp     eax, edi
0x14000e583  jz      loc_14000E677
0x14000e589  jmp     loc_14000E67F
0x14000e58e  test    cl, cl
0x14000e590  jz      loc_14000E67F
0x14000e596  jmp     loc_14000E677
0x14000e59b  cmp     edx, edi
0x14000e59d  jnz     loc_14000E67F
0x14000e5a3  mov     eax, edi
0x14000e5a5  lock xadd [rcx+100h], eax
0x14000e5ad  add     eax, edi
0x14000e5af  cmp     eax, edi
0x14000e5b1  jnz     loc_14000E67F
0x14000e5b7  mov     rcx, [rcx+108h]
0x14000e5be  lea     r9, [rbx+120h]
0x14000e5c5  mov     edx, edi
0x14000e5c7  mov     rax, [rcx]
0x14000e5ca  mov     rax, [rax+8]
0x14000e5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5d3  mov     r8d, eax
0x14000e5d6  test    eax, eax
0x14000e5d8  js      short loc_14000E606
0x14000e5da  cmp     byte ptr [rbx+129h], 0
0x14000e5e1  jz      short loc_14000E606
0x14000e5e3  or      eax, 0FFFFFFFFh
0x14000e5e6  lock xadd [rbx+118h], eax
0x14000e5ee  cmp     eax, edi
0x14000e5f0  jnz     loc_14000E67F
0x14000e5f6  mov     edx, [rbx+11Ch]
0x14000e5fc  mov     rcx, rbx
0x14000e5ff  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x14000e604  jmp     short loc_14000E67F
0x14000e606  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000e60e  setz    bpl
0x14000e612  mov     eax, edi
0x14000e614  lock xadd [rbx+0FCh], eax
0x14000e61c  add     eax, edi
0x14000e61e  cmp     eax, edi
0x14000e620  jnz     short loc_14000E62E
0x14000e622  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000e62a  setz    bpl
0x14000e62e  lea     rcx, [rbx+8]
0x14000e632  test    r8d, r8d
0x14000e635  jns     short loc_14000E65D
0x14000e637  mov     edx, [rcx+38h]
0x14000e63a  mov     [rsp+58h+var_28], 0FFFFFFFEh
0x14000e642  mov     eax, [rsp+58h+var_28]
0x14000e646  lock cmpxchg [rsp+58h+var_28], edx
0x14000e64c  cmp     [rsp+58h+var_28], 2
0x14000e651  jz      short loc_14000E672
0x14000e653  mov     edx, r8d
0x14000e656  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x14000e65b  jmp     short loc_14000E672
0x14000e65d  mov     edx, edi
0x14000e65f  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14000e664  test    al, al
0x14000e666  jnz     short loc_14000E672
0x14000e668  mov     eax, 2
0x14000e66d  lock cmpxchg [rbx+40h], edi
0x14000e672  test    bpl, bpl
0x14000e675  jz      short loc_14000E67F
0x14000e677  mov     rcx, rbx
0x14000e67a  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x14000e67f  mov     rcx, [rsp+58h+var_20]
0x14000e684  xor     rcx, rsp; StackCookie
0x14000e687  call    __security_check_cookie
0x14000e68c  add     rsp, 40h
0x14000e690  pop     rdi
0x14000e691  pop     rbp
0x14000e692  pop     rbx
0x14000e693  retn
```
