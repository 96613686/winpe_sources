# wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180009d00`
- end: `0x180009dd6`
- name: `?Stop@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009400`

## callees

- `0x18000133c`
- `0x180001acc`
- `0x180005cb8`
- `0x180007d94`
- `0x180007fd4`
- `0x180008c00`
- `0x180009b0c`
- `0x180009d00`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d78`

## pseudocode

```c
void __fastcall wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF
  RTL_SRWLOCK *v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v11 = 0;
  wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v12);
  v4 = wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PicturePasswordLogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v5 = PicturePasswordLogger::Provider();
    v7 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v12) = a2;
      v13 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)byte_180024DDD,
        v9 + 8,
        v10,
        (__int64)&v13,
        (__int64)&v12,
        (__int64)&v11);
    }
  }
  wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180009d00  push    rbx
0x180009d02  push    rsi
0x180009d03  push    rdi
0x180009d04  sub     rsp, 40h
0x180009d08  mov     esi, edx
0x180009d0a  mov     [rsp+58h+arg_0], 0
0x180009d12  lea     rdx, [rsp+58h+arg_10]
0x180009d17  mov     rdi, rcx
0x180009d1a  call    ?LockExclusive@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180009d1f  mov     rcx, [rdi+110h]
0x180009d26  lea     r8, [rsp+58h+arg_0]
0x180009d2b  mov     edx, esi
0x180009d2d  call    ?SetStopResult@?$ActivityData@VPicturePasswordLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PicturePasswordLogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180009d32  lea     rcx, [rsp+58h+arg_10]
0x180009d37  mov     bl, al
0x180009d39  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009d3e  test    bl, bl
0x180009d40  jz      short loc_180009D53
0x180009d42  mov     rax, [rdi]
0x180009d45  mov     rcx, rdi
0x180009d48  mov     rax, [rax+8]
0x180009d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d51  jmp     short loc_180009DC7
0x180009d53  call    ?Provider@PicturePasswordLogger@@SAPEBU_tlgProvider_t@@XZ; PicturePasswordLogger::Provider(void)
0x180009d58  mov     rbx, rax
0x180009d5b  mov     ecx, [rax]
0x180009d5d  cmp     ecx, 5
0x180009d60  jbe     short loc_180009DC7
0x180009d62  mov     rdx, 200000000000h
0x180009d6c  mov     rcx, rax
0x180009d6f  call    _tlgKeywordOn
0x180009d74  test    al, al
0x180009d76  jz      short loc_180009DC7
0x180009d78  call    cs:__imp_GetCurrentThreadId
0x180009d7e  mov     r8, [rdi+110h]
0x180009d85  lea     rdx, byte_180024DDD
0x180009d8c  mov     [rsp+58h+arg_0], eax
0x180009d90  add     r8, 8
0x180009d94  lea     rax, [rsp+58h+arg_0]
0x180009d99  mov     dword ptr [rsp+58h+arg_10], esi
0x180009d9d  mov     [rsp+58h+var_28], rax
0x180009da2  mov     rcx, rbx
0x180009da5  lea     rax, [rsp+58h+arg_10]
0x180009daa  mov     [rsp+58h+arg_18], 1000000h
0x180009db3  mov     [rsp+58h+var_30], rax
0x180009db8  lea     rax, [rsp+58h+arg_18]
0x180009dbd  mov     [rsp+58h+var_38], rax
0x180009dc2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009dc7  mov     rcx, rdi
0x180009dca  add     rsp, 40h
0x180009dce  pop     rdi
0x180009dcf  pop     rsi
0x180009dd0  pop     rbx
0x180009dd1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
