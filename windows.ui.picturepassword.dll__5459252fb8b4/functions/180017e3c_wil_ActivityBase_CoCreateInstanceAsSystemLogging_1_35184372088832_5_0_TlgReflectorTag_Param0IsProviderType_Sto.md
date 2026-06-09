# wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180017e3c`
- end: `0x180017f1c`
- name: `?Stop@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800185b4`

## callees

- `0x18000133c`
- `0x180001acc`
- `0x180005cb8`
- `0x180007d94`
- `0x180007fd4`
- `0x180009b0c`
- `0x180017bd8`
- `0x180017e3c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017eb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017eb7`

## pseudocode

```c
void __fastcall wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v10);
  v2 = wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PicturePasswordLogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v4 = CoCreateInstanceAsSystemLogging::Provider(v3);
    v6 = (__int64)v4;
    if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v10) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)word_180024E62,
        v8 + 8,
        v9,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x180017e3c  mov     rax, rsp
0x180017e3f  mov     [rax+20h], rbx
0x180017e43  mov     [rax+10h], edx
0x180017e46  push    rdi
0x180017e47  sub     rsp, 40h
0x180017e4b  lea     rdx, [rax+8]
0x180017e4f  mov     dword ptr [rax+10h], 0
0x180017e56  mov     rdi, rcx
0x180017e59  call    ?LockExclusive@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017e5e  mov     rcx, [rdi+110h]
0x180017e65  lea     r8, [rsp+48h+arg_8]
0x180017e6a  xor     edx, edx
0x180017e6c  call    ?SetStopResult@?$ActivityData@VPicturePasswordLogger@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<PicturePasswordLogger,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180017e71  lea     rcx, [rsp+48h+arg_0]
0x180017e76  mov     bl, al
0x180017e78  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017e7d  test    bl, bl
0x180017e7f  jz      short loc_180017E92
0x180017e81  mov     rax, [rdi]
0x180017e84  mov     rcx, rdi
0x180017e87  mov     rax, [rax+8]
0x180017e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e90  jmp     short loc_180017F0A
0x180017e92  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x180017e97  mov     rbx, rax
0x180017e9a  mov     ecx, [rax]
0x180017e9c  cmp     ecx, 5
0x180017e9f  jbe     short loc_180017F0A
0x180017ea1  mov     rdx, 200000000000h
0x180017eab  mov     rcx, rax
0x180017eae  call    _tlgKeywordOn
0x180017eb3  test    al, al
0x180017eb5  jz      short loc_180017F0A
0x180017eb7  call    cs:__imp_GetCurrentThreadId
0x180017ebd  mov     r8, [rdi+110h]
0x180017ec4  lea     rdx, word_180024E62
0x180017ecb  mov     [rsp+48h+arg_8], eax
0x180017ecf  add     r8, 8
0x180017ed3  lea     rax, [rsp+48h+arg_8]
0x180017ed8  mov     dword ptr [rsp+48h+arg_0], 0
0x180017ee0  mov     [rsp+48h+var_18], rax
0x180017ee5  mov     rcx, rbx
0x180017ee8  lea     rax, [rsp+48h+arg_0]
0x180017eed  mov     [rsp+48h+arg_10], 1000000h
0x180017ef6  mov     [rsp+48h+var_20], rax
0x180017efb  lea     rax, [rsp+48h+arg_10]
0x180017f00  mov     [rsp+48h+var_28], rax
0x180017f05  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017f0a  mov     rcx, rdi
0x180017f0d  mov     rbx, [rsp+48h+arg_18]
0x180017f12  add     rsp, 40h
0x180017f16  pop     rdi
0x180017f17  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPicturePasswordLogger@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<PicturePasswordLogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
