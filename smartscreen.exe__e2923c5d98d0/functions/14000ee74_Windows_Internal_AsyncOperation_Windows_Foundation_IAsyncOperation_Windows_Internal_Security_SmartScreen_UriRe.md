# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x14000ee74`
- end: `0x14000f024`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `432`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14003e170`
- `0x14003e1e0`

## callees

- `0x14000ee74`
- `0x14000f1f0`
- `0x14001dbe0`
- `0x140025aa0`
- `0x1400351a0`
- `0x14003f960`
- `0x140068010`

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
0x14000ee74  push    rbx
0x14000ee76  push    rbp
0x14000ee77  push    rdi
0x14000ee78  sub     rsp, 40h
0x14000ee7c  mov     rax, cs:__security_cookie
0x14000ee83  xor     rax, rsp
0x14000ee86  mov     [rsp+58h+var_20], rax
0x14000ee8b  mov     rbx, rcx
0x14000ee8e  mov     edi, 1
0x14000ee93  cmp     edx, 2
0x14000ee96  jnz     loc_14000EF2B
0x14000ee9c  mov     eax, edi
0x14000ee9e  lock xadd [rcx+0FCh], eax
0x14000eea6  add     eax, edi
0x14000eea8  cmp     eax, edi
0x14000eeaa  jnz     loc_14000F00F
0x14000eeb0  lea     rbp, [rcx+120h]
0x14000eeb7  mov     rcx, [rcx+108h]
0x14000eebe  mov     r9, rbp
0x14000eec1  mov     rax, [rcx]
0x14000eec4  mov     rax, [rax+8]
0x14000eec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eecd  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000eed5  setz    cl
0x14000eed8  mov     eax, edi
0x14000eeda  lock xadd [rbx+100h], eax
0x14000eee2  add     eax, edi
0x14000eee4  cmp     eax, edi
0x14000eee6  jnz     short loc_14000EF1E
0x14000eee8  mov     rcx, [rbx+108h]
0x14000eeef  mov     r9, rbp
0x14000eef2  mov     r8d, 800704C7h
0x14000eef8  mov     edx, edi
0x14000eefa  mov     rax, [rcx]
0x14000eefd  mov     rax, [rax+8]
0x14000ef01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef06  or      eax, 0FFFFFFFFh
0x14000ef09  lock xadd [rbx+104h], eax
0x14000ef11  cmp     eax, edi
0x14000ef13  jz      loc_14000F007
0x14000ef19  jmp     loc_14000F00F
0x14000ef1e  test    cl, cl
0x14000ef20  jz      loc_14000F00F
0x14000ef26  jmp     loc_14000F007
0x14000ef2b  cmp     edx, edi
0x14000ef2d  jnz     loc_14000F00F
0x14000ef33  mov     eax, edi
0x14000ef35  lock xadd [rcx+100h], eax
0x14000ef3d  add     eax, edi
0x14000ef3f  cmp     eax, edi
0x14000ef41  jnz     loc_14000F00F
0x14000ef47  mov     rcx, [rcx+108h]
0x14000ef4e  lea     r9, [rbx+120h]
0x14000ef55  mov     edx, edi
0x14000ef57  mov     rax, [rcx]
0x14000ef5a  mov     rax, [rax+8]
0x14000ef5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef63  mov     r8d, eax
0x14000ef66  test    eax, eax
0x14000ef68  js      short loc_14000EF96
0x14000ef6a  cmp     byte ptr [rbx+129h], 0
0x14000ef71  jz      short loc_14000EF96
0x14000ef73  or      eax, 0FFFFFFFFh
0x14000ef76  lock xadd [rbx+118h], eax
0x14000ef7e  cmp     eax, edi
0x14000ef80  jnz     loc_14000F00F
0x14000ef86  mov     edx, [rbx+11Ch]
0x14000ef8c  mov     rcx, rbx
0x14000ef8f  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x14000ef94  jmp     short loc_14000F00F
0x14000ef96  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000ef9e  setz    bpl
0x14000efa2  mov     eax, edi
0x14000efa4  lock xadd [rbx+0FCh], eax
0x14000efac  add     eax, edi
0x14000efae  cmp     eax, edi
0x14000efb0  jnz     short loc_14000EFBE
0x14000efb2  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x14000efba  setz    bpl
0x14000efbe  lea     rcx, [rbx+8]
0x14000efc2  test    r8d, r8d
0x14000efc5  jns     short loc_14000EFED
0x14000efc7  mov     edx, [rcx+38h]
0x14000efca  mov     [rsp+58h+var_28], 0FFFFFFFEh
0x14000efd2  mov     eax, [rsp+58h+var_28]
0x14000efd6  lock cmpxchg [rsp+58h+var_28], edx
0x14000efdc  cmp     [rsp+58h+var_28], 2
0x14000efe1  jz      short loc_14000F002
0x14000efe3  mov     edx, r8d
0x14000efe6  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x14000efeb  jmp     short loc_14000F002
0x14000efed  mov     edx, edi
0x14000efef  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x14000eff4  test    al, al
0x14000eff6  jnz     short loc_14000F002
0x14000eff8  mov     eax, 2
0x14000effd  lock cmpxchg [rbx+40h], edi
0x14000f002  test    bpl, bpl
0x14000f005  jz      short loc_14000F00F
0x14000f007  mov     rcx, rbx
0x14000f00a  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@23@V?$CMarshaledInterfaceResult@UIUriReputationExperienceInfo@SmartScreen@Security@Internal@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::SmartScreen::UriReputationExperienceInfo *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::Security::SmartScreen::IUriReputationExperienceInfo>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x14000f00f  mov     rcx, [rsp+58h+var_20]
0x14000f014  xor     rcx, rsp; StackCookie
0x14000f017  call    __security_check_cookie
0x14000f01c  add     rsp, 40h
0x14000f020  pop     rdi
0x14000f021  pop     rbp
0x14000f022  pop     rbx
0x14000f023  retn
```
