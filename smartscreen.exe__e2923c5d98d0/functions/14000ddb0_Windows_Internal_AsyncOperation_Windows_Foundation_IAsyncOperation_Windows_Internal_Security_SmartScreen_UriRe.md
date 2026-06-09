# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x14000ddb0`
- end: `0x14000df60`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140011bc0`
- `0x14003e190`

## callees

- `0x14000db28`
- `0x14000ddb0`
- `0x14000df68`
- `0x140025aa0`
- `0x14003f8d0`
- `0x14003f9b8`
- `0x140068010`

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
0x14000ddb0  push    rbx
0x14000ddb2  push    rbp
0x14000ddb3  push    rdi
0x14000ddb4  sub     rsp, 40h
0x14000ddb8  mov     rax, cs:__security_cookie
0x14000ddbf  xor     rax, rsp
0x14000ddc2  mov     [rsp+58h+var_20], rax
0x14000ddc7  mov     rbx, rcx
0x14000ddca  mov     edi, 1
0x14000ddcf  cmp     edx, 2
0x14000ddd2  jnz     loc_14000DE67
0x14000ddd8  mov     eax, edi
0x14000ddda  lock xadd [rcx+0FCh], eax
0x14000dde2  add     eax, edi
0x14000dde4  cmp     eax, edi
0x14000dde6  jnz     loc_14000DF4B
0x14000ddec  lea     rbp, [rcx+120h]
0x14000ddf3  mov     rcx, [rcx+108h]
0x14000ddfa  mov     r9, rbp
0x14000ddfd  mov     rax, [rcx]
0x14000de00  mov     rax, [rax+8]
0x14000de04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de09  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000de11  setz    cl
0x14000de14  mov     eax, edi
0x14000de16  lock xadd [rbx+100h], eax
0x14000de1e  add     eax, edi
0x14000de20  cmp     eax, edi
0x14000de22  jnz     short loc_14000DE5A
0x14000de24  mov     rcx, [rbx+108h]
0x14000de2b  mov     r9, rbp
0x14000de2e  mov     r8d, 800704C7h
0x14000de34  mov     edx, edi
0x14000de36  mov     rax, [rcx]
0x14000de39  mov     rax, [rax+8]
0x14000de3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de42  or      eax, 0FFFFFFFFh
0x14000de45  lock xadd [rbx+104h], eax
0x14000de4d  cmp     eax, edi
0x14000de4f  jz      loc_14000DF43
0x14000de55  jmp     loc_14000DF4B
0x14000de5a  test    cl, cl
0x14000de5c  jz      loc_14000DF4B
0x14000de62  jmp     loc_14000DF43
0x14000de67  cmp     edx, edi
0x14000de69  jnz     loc_14000DF4B
0x14000de6f  mov     eax, edi
0x14000de71  lock xadd [rcx+100h], eax
0x14000de79  add     eax, edi
0x14000de7b  cmp     eax, edi
0x14000de7d  jnz     loc_14000DF4B
0x14000de83  mov     rcx, [rcx+108h]
0x14000de8a  lea     r9, [rbx+120h]
0x14000de91  mov     edx, edi
0x14000de93  mov     rax, [rcx]
0x14000de96  mov     rax, [rax+8]
0x14000de9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de9f  mov     r8d, eax
0x14000dea2  test    eax, eax
0x14000dea4  js      short loc_14000DED2
0x14000dea6  cmp     byte ptr [rbx+129h], 0
0x14000dead  jz      short loc_14000DED2
0x14000deaf  or      eax, 0FFFFFFFFh
0x14000deb2  lock xadd [rbx+118h], eax
0x14000deba  cmp     eax, edi
0x14000debc  jnz     loc_14000DF4B
0x14000dec2  mov     edx, [rbx+11Ch]
0x14000dec8  mov     rcx, rbx
0x14000decb  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x14000ded0  jmp     short loc_14000DF4B
0x14000ded2  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000deda  setz    bpl
0x14000dede  mov     eax, edi
0x14000dee0  lock xadd [rbx+0FCh], eax
0x14000dee8  add     eax, edi
0x14000deea  cmp     eax, edi
0x14000deec  jnz     short loc_14000DEFA
0x14000deee  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000def6  setz    bpl
0x14000defa  lea     rcx, [rbx+8]
0x14000defe  test    r8d, r8d
0x14000df01  jns     short loc_14000DF29
0x14000df03  mov     edx, [rcx+38h]
0x14000df06  mov     [rsp+58h+var_28], 0FFFFFFFEh
0x14000df0e  mov     eax, [rsp+58h+var_28]
0x14000df12  lock cmpxchg [rsp+58h+var_28], edx
0x14000df18  cmp     [rsp+58h+var_28], 2
0x14000df1d  jz      short loc_14000DF3E
0x14000df1f  mov     edx, r8d
0x14000df22  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x14000df27  jmp     short loc_14000DF3E
0x14000df29  mov     edx, edi
0x14000df2b  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14000df30  test    al, al
0x14000df32  jnz     short loc_14000DF3E
0x14000df34  mov     eax, 2
0x14000df39  lock cmpxchg [rbx+40h], edi
0x14000df3e  test    bpl, bpl
0x14000df41  jz      short loc_14000DF4B
0x14000df43  mov     rcx, rbx
0x14000df46  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationResult@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationResult@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationResult *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationResult>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x14000df4b  mov     rcx, [rsp+58h+var_20]
0x14000df50  xor     rcx, rsp; StackCookie
0x14000df53  call    __security_check_cookie
0x14000df58  add     rsp, 40h
0x14000df5c  pop     rdi
0x14000df5d  pop     rbp
0x14000df5e  pop     rbx
0x14000df5f  retn
```
