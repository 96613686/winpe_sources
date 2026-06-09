# wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000ed34`
- end: `0x18000ee14`
- name: `?Stop@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000b010`
- `0x18000b3f0`
- `0x18000b5d0`
- `0x18000d180`
- `0x18000d670`
- `0x180047030`

## callees

- `0x1800013e4`
- `0x180001b6c`
- `0x18000a2ac`
- `0x18000c5a8`
- `0x18000c6a0`
- `0x18000d15c`
- `0x18000e8a0`
- `0x18000ed34`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000edaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000edaf`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  RTL_SRWLOCK *v12; // [rsp+50h] [rbp+8h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v12);
  v2 = wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WoscLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = WoscLoggingProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL, v4) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      LODWORD(v12) = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (__int64)&unk_180066AF0,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x18000ed34  mov     rax, rsp
0x18000ed37  mov     [rax+20h], rbx
0x18000ed3b  mov     [rax+10h], edx
0x18000ed3e  push    rdi
0x18000ed3f  sub     rsp, 40h
0x18000ed43  lea     rdx, [rax+8]
0x18000ed47  mov     dword ptr [rax+10h], 0
0x18000ed4e  mov     rdi, rcx
0x18000ed51  call    ?LockExclusive@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ed56  mov     rcx, [rdi+110h]
0x18000ed5d  lea     r8, [rsp+48h+arg_8]
0x18000ed62  xor     edx, edx
0x18000ed64  call    ?SetStopResult@?$ActivityData@VWoscLoggingProvider@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WoscLoggingProvider,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000ed69  lea     rcx, [rsp+48h+arg_0]
0x18000ed6e  mov     bl, al
0x18000ed70  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ed75  test    bl, bl
0x18000ed77  jz      short loc_18000ED8A
0x18000ed79  mov     rax, [rdi]
0x18000ed7c  mov     rcx, rdi
0x18000ed7f  mov     rax, [rax+8]
0x18000ed83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed88  jmp     short loc_18000EE02
0x18000ed8a  call    ?Provider@WoscLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; WoscLoggingProvider::Provider(void)
0x18000ed8f  mov     rbx, rax
0x18000ed92  mov     ecx, [rax]
0x18000ed94  cmp     ecx, 5
0x18000ed97  jbe     short loc_18000EE02
0x18000ed99  mov     rdx, 400000000000h
0x18000eda3  mov     rcx, rax
0x18000eda6  call    _tlgKeywordOn
0x18000edab  test    al, al
0x18000edad  jz      short loc_18000EE02
0x18000edaf  call    cs:__imp_GetCurrentThreadId
0x18000edb5  mov     r8, [rdi+110h]
0x18000edbc  lea     rdx, unk_180066AF0
0x18000edc3  mov     [rsp+48h+arg_8], eax
0x18000edc7  add     r8, 8
0x18000edcb  lea     rax, [rsp+48h+arg_8]
0x18000edd0  mov     dword ptr [rsp+48h+arg_0], 0
0x18000edd8  mov     [rsp+48h+var_18], rax
0x18000eddd  mov     rcx, rbx
0x18000ede0  lea     rax, [rsp+48h+arg_0]
0x18000ede5  mov     [rsp+48h+arg_10], 1000000h
0x18000edee  mov     [rsp+48h+var_20], rax
0x18000edf3  lea     rax, [rsp+48h+arg_10]
0x18000edf8  mov     [rsp+48h+var_28], rax
0x18000edfd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000ee02  mov     rcx, rdi
0x18000ee05  mov     rbx, [rsp+48h+arg_18]
0x18000ee0a  add     rsp, 40h
0x18000ee0e  pop     rdi
0x18000ee0f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWoscLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0IAAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WoscLoggingProvider,1,70368744177664,5,2147483648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
