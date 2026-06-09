# wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180025b70`
- end: `0x180025c31`
- name: `?Stop@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `193`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800255e8`
- `0x1800303c4`
- `0x18003101c`
- `0x180031474`
- `0x180068708`
- `0x18007ef18`

## callees

- `0x180025b70`
- `0x18005d564`
- `0x18006125c`
- `0x1800615e0`
- `0x180062e98`
- `0x1800674b4`
- `0x18006cadc`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025bd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025bd3`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  _DWORD *v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  DWORD v10; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  v10 = 0;
  wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(a1, &v11);
  v4 = wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v10);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = *(_DWORD **)(wil::details::static_lazy<AnimationClockLogging>::get() + 8);
    if ( *v5 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v10 = CurrentThreadId;
      v11 = a2;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v5,
        (unsigned __int8 *)byte_18010005D,
        v7 + 8,
        v8,
        (__int64)&v12,
        (__int64)&v11,
        (__int64)&v10);
    }
  }
  return wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180025b70  push    rbx
0x180025b72  push    rsi
0x180025b73  push    rdi
0x180025b74  sub     rsp, 40h
0x180025b78  mov     esi, edx
0x180025b7a  mov     [rsp+58h+arg_0], 0
0x180025b82  lea     rdx, [rsp+58h+arg_10]
0x180025b87  mov     rdi, rcx
0x180025b8a  call    ?LockExclusive@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025b8f  mov     rcx, [rdi+110h]
0x180025b96  lea     r8, [rsp+58h+arg_0]
0x180025b9b  mov     edx, esi
0x180025b9d  call    ?SetStopResult@?$ActivityData@VAnimationClockLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAnimationClockLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<AnimationClockLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AnimationClockLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180025ba2  lea     rcx, [rsp+58h+arg_10]
0x180025ba7  mov     bl, al
0x180025ba9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025bae  test    bl, bl
0x180025bb0  jz      short loc_180025BC3
0x180025bb2  mov     rax, [rdi]
0x180025bb5  mov     rcx, rdi
0x180025bb8  mov     rax, [rax+8]
0x180025bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bc1  jmp     short loc_180025C22
0x180025bc3  call    ?get@?$static_lazy@VAnimationClockLogging@@@details@wil@@QEAAPEAVAnimationClockLogging@@P6AXXZ@Z; wil::details::static_lazy<AnimationClockLogging>::get(void (*)(void))
0x180025bc8  mov     rbx, [rax+8]
0x180025bcc  mov     eax, [rbx]
0x180025bce  cmp     eax, 5
0x180025bd1  jbe     short loc_180025C22
0x180025bd3  call    cs:__imp_GetCurrentThreadId
0x180025bd9  mov     r8, [rdi+110h]
0x180025be0  lea     rdx, byte_18010005D
0x180025be7  mov     [rsp+58h+arg_0], eax
0x180025beb  add     r8, 8
0x180025bef  lea     rax, [rsp+58h+arg_0]
0x180025bf4  mov     [rsp+58h+arg_10], esi
0x180025bf8  mov     [rsp+58h+var_28], rax
0x180025bfd  mov     rcx, rbx
0x180025c00  lea     rax, [rsp+58h+arg_10]
0x180025c05  mov     [rsp+58h+arg_18], 1000000h
0x180025c0e  mov     [rsp+58h+var_30], rax
0x180025c13  lea     rax, [rsp+58h+arg_18]
0x180025c18  mov     [rsp+58h+var_38], rax
0x180025c1d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180025c22  mov     rcx, rdi
0x180025c25  add     rsp, 40h
0x180025c29  pop     rdi
0x180025c2a  pop     rsi
0x180025c2b  pop     rbx
0x180025c2c  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWindowFrameLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WindowFrameLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
