# wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000d88c`
- end: `0x18000d953`
- name: `?Stop@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `199`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000cec8`

## callees

- `0x18000176c`
- `0x18000c848`
- `0x18000ca18`
- `0x18000ca50`
- `0x18000cea8`
- `0x18000d154`
- `0x18000d67c`
- `0x18000d88c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d8ee`

## pseudocode

```c
void __fastcall wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  bool v2; // bl
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  RTL_SRWLOCK *v8; // [rsp+50h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  v9 = 0;
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v8);
  v2 = wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v9);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  if ( v2 )
  {
    wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(
      a1,
      v9);
  }
  else
  {
    v4 = MSAClientTraceTelemetry::Provider(v3);
    if ( *(_DWORD *)v4 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v6 = a1[34];
      v9 = CurrentThreadId;
      LODWORD(v8) = 0;
      v10 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v4,
        (__int64)byte_18001BB49,
        v6 + 8,
        v7,
        (__int64)&v10,
        (__int64)&v8,
        (__int64)&v9);
    }
  }
  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x18000d88c  mov     rax, rsp
0x18000d88f  mov     [rax+20h], rbx
0x18000d893  mov     [rax+10h], edx
0x18000d896  push    rdi
0x18000d897  sub     rsp, 40h
0x18000d89b  lea     rdx, [rax+8]
0x18000d89f  mov     dword ptr [rax+10h], 0
0x18000d8a6  mov     rdi, rcx
0x18000d8a9  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d8ae  mov     rcx, [rdi+110h]
0x18000d8b5  lea     r8, [rsp+48h+arg_8]
0x18000d8ba  xor     edx, edx
0x18000d8bc  call    ?SetStopResult@?$ActivityData@VMSAClientTraceTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000d8c1  lea     rcx, [rsp+48h+arg_0]
0x18000d8c6  mov     bl, al
0x18000d8c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d8cd  test    bl, bl
0x18000d8cf  jz      short loc_18000D8DF
0x18000d8d1  mov     edx, [rsp+48h+arg_8]
0x18000d8d5  mov     rcx, rdi
0x18000d8d8  call    ?ReportStopActivity@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000d8dd  jmp     short loc_18000D941
0x18000d8df  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000d8e4  mov     rbx, rax
0x18000d8e7  mov     ecx, [rax]
0x18000d8e9  cmp     ecx, 5
0x18000d8ec  jbe     short loc_18000D941
0x18000d8ee  call    cs:__imp_GetCurrentThreadId
0x18000d8f4  mov     r8, [rdi+110h]
0x18000d8fb  lea     rdx, byte_18001BB49
0x18000d902  mov     [rsp+48h+arg_8], eax
0x18000d906  add     r8, 8
0x18000d90a  lea     rax, [rsp+48h+arg_8]
0x18000d90f  mov     dword ptr [rsp+48h+arg_0], 0
0x18000d917  mov     [rsp+48h+var_18], rax
0x18000d91c  mov     rcx, rbx
0x18000d91f  lea     rax, [rsp+48h+arg_0]
0x18000d924  mov     [rsp+48h+arg_10], 1000000h
0x18000d92d  mov     [rsp+48h+var_20], rax
0x18000d932  lea     rax, [rsp+48h+arg_10]
0x18000d937  mov     [rsp+48h+var_28], rax
0x18000d93c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000d941  mov     rcx, rdi
0x18000d944  mov     rbx, [rsp+48h+arg_18]
0x18000d949  add     rsp, 40h
0x18000d94d  pop     rdi
0x18000d94e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
