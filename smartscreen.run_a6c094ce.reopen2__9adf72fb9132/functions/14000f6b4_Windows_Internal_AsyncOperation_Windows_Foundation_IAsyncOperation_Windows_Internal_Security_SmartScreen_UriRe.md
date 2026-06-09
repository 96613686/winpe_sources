# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x14000f6b4`
- end: `0x14000f865`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003f890`
- `0x14003f900`

## callees

- `0x14000f6b4`
- `0x14000fa34`
- `0x14001ec58`
- `0x140026c20`
- `0x1400366d8`
- `0x140041094`
- `0x14006a010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  bool v5; // cl
  signed __int32 v6; // eax
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
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
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
        Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
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
        if ( !Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
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
          Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
            v8,
            v6);
      }
      if ( v7 )
        goto LABEL_22;
    }
  }
}

```

## disassembly

```asm
0x14000f6b4  push    rbx
0x14000f6b6  push    rbp
0x14000f6b7  push    rdi
0x14000f6b8  sub     rsp, 40h
0x14000f6bc  mov     rax, cs:__security_cookie
0x14000f6c3  xor     rax, rsp
0x14000f6c6  mov     [rsp+58h+var_20], rax
0x14000f6cb  mov     rbx, rcx
0x14000f6ce  mov     edi, 1
0x14000f6d3  cmp     edx, 2
0x14000f6d6  jnz     loc_14000F76B
0x14000f6dc  mov     eax, edi
0x14000f6de  lock xadd [rcx+0FCh], eax
0x14000f6e6  add     eax, edi
0x14000f6e8  cmp     eax, edi
0x14000f6ea  jnz     loc_14000F84F
0x14000f6f0  lea     rbp, [rcx+120h]
0x14000f6f7  mov     rcx, [rcx+108h]
0x14000f6fe  mov     r9, rbp
0x14000f701  mov     rax, [rcx]
0x14000f704  mov     rax, [rax+8]
0x14000f708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f70d  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000f715  setz    cl
0x14000f718  mov     eax, edi
0x14000f71a  lock xadd [rbx+100h], eax
0x14000f722  add     eax, edi
0x14000f724  cmp     eax, edi
0x14000f726  jnz     short loc_14000F75E
0x14000f728  mov     rcx, [rbx+108h]
0x14000f72f  mov     r9, rbp
0x14000f732  mov     r8d, 800704C7h
0x14000f738  mov     edx, edi
0x14000f73a  mov     rax, [rcx]
0x14000f73d  mov     rax, [rax+8]
0x14000f741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f746  or      eax, 0FFFFFFFFh
0x14000f749  lock xadd [rbx+104h], eax
0x14000f751  cmp     eax, edi
0x14000f753  jz      loc_14000F847
0x14000f759  jmp     loc_14000F84F
0x14000f75e  test    cl, cl
0x14000f760  jz      loc_14000F84F
0x14000f766  jmp     loc_14000F847
0x14000f76b  cmp     edx, edi
0x14000f76d  jnz     loc_14000F84F
0x14000f773  mov     eax, edi
0x14000f775  lock xadd [rcx+100h], eax
0x14000f77d  add     eax, edi
0x14000f77f  cmp     eax, edi
0x14000f781  jnz     loc_14000F84F
0x14000f787  mov     rcx, [rcx+108h]
0x14000f78e  lea     r9, [rbx+120h]
0x14000f795  mov     edx, edi
0x14000f797  mov     rax, [rcx]
0x14000f79a  mov     rax, [rax+8]
0x14000f79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f7a3  mov     r8d, eax
0x14000f7a6  test    eax, eax
0x14000f7a8  js      short loc_14000F7D6
0x14000f7aa  cmp     byte ptr [rbx+129h], 0
0x14000f7b1  jz      short loc_14000F7D6
0x14000f7b3  or      eax, 0FFFFFFFFh
0x14000f7b6  lock xadd [rbx+118h], eax
0x14000f7be  cmp     eax, edi
0x14000f7c0  jnz     loc_14000F84F
0x14000f7c6  mov     edx, [rbx+11Ch]
0x14000f7cc  mov     rcx, rbx
0x14000f7cf  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x14000f7d4  jmp     short loc_14000F84F
0x14000f7d6  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000f7de  setz    bpl
0x14000f7e2  mov     eax, edi
0x14000f7e4  lock xadd [rbx+0FCh], eax
0x14000f7ec  add     eax, edi
0x14000f7ee  cmp     eax, edi
0x14000f7f0  jnz     short loc_14000F7FE
0x14000f7f2  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000f7fa  setz    bpl
0x14000f7fe  lea     rcx, [rbx+8]
0x14000f802  test    r8d, r8d
0x14000f805  jns     short loc_14000F82D
0x14000f807  mov     edx, [rcx+38h]
0x14000f80a  mov     [rsp+58h+var_28], 0FFFFFFFEh
0x14000f812  mov     eax, [rsp+58h+var_28]
0x14000f816  lock cmpxchg [rsp+58h+var_28], edx
0x14000f81c  cmp     [rsp+58h+var_28], 2
0x14000f821  jz      short loc_14000F842
0x14000f823  mov     edx, r8d
0x14000f826  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x14000f82b  jmp     short loc_14000F842
0x14000f82d  mov     edx, edi
0x14000f82f  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14000f834  test    al, al
0x14000f836  jnz     short loc_14000F842
0x14000f838  mov     eax, 2
0x14000f83d  lock cmpxchg [rbx+40h], edi
0x14000f842  test    bpl, bpl
0x14000f845  jz      short loc_14000F84F
0x14000f847  mov     rcx, rbx
0x14000f84a  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x14000f84f  mov     rcx, [rsp+58h+var_20]
0x14000f854  xor     rcx, rsp; StackCookie
0x14000f857  call    __security_check_cookie
0x14000f85c  add     rsp, 40h
0x14000f860  pop     rdi
0x14000f861  pop     rbp
0x14000f862  pop     rbx
0x14000f863  retn
```
