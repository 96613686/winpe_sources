# wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800085b8`
- end: `0x18000868e`
- name: `?Stop@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800075ec`
- `0x18000a670`
- `0x1800100c4`
- `0x180015ca8`
- `0x18001d8c0`

## callees

- `0x18000133c`
- `0x180001acc`
- `0x1800051d0`
- `0x1800067f4`
- `0x1800069fc`
- `0x180007908`
- `0x180008424`
- `0x1800085b8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008630`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008630`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rax
  int v9; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  DWORD v14; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TimeDateTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v8 = TimeDateTraceLogging::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v14 = CurrentThreadId;
      v15 = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&unk_18003114D,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x1800085b8  push    rbx
0x1800085ba  push    rsi
0x1800085bb  push    rdi
0x1800085bc  sub     rsp, 40h
0x1800085c0  mov     esi, edx
0x1800085c2  mov     [rsp+58h+arg_0], 0
0x1800085ca  lea     rdx, [rsp+58h+arg_10]
0x1800085cf  mov     rdi, rcx
0x1800085d2  call    ?LockExclusive@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800085d7  mov     rcx, [rdi+110h]
0x1800085de  lea     r8, [rsp+58h+arg_0]
0x1800085e3  mov     edx, esi
0x1800085e5  call    ?SetStopResult@?$ActivityData@VTimeDateTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<TimeDateTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800085ea  lea     rcx, [rsp+58h+arg_10]
0x1800085ef  mov     bl, al
0x1800085f1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800085f6  test    bl, bl
0x1800085f8  jz      short loc_18000860B
0x1800085fa  mov     rax, [rdi]
0x1800085fd  mov     rcx, rdi
0x180008600  mov     rax, [rax+8]
0x180008604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008609  jmp     short loc_18000867F
0x18000860b  call    ?Provider@TimeDateTraceLogging@@SAPEBU_tlgProvider_t@@XZ; TimeDateTraceLogging::Provider(void)
0x180008610  mov     rbx, rax
0x180008613  mov     ecx, [rax]
0x180008615  cmp     ecx, 5
0x180008618  jbe     short loc_18000867F
0x18000861a  mov     rdx, 200000000000h
0x180008624  mov     rcx, rax
0x180008627  call    _tlgKeywordOn
0x18000862c  test    al, al
0x18000862e  jz      short loc_18000867F
0x180008630  call    cs:__imp_GetCurrentThreadId
0x180008636  mov     r8, [rdi+110h]
0x18000863d  lea     rdx, unk_18003114D
0x180008644  mov     [rsp+58h+arg_0], eax
0x180008648  add     r8, 8
0x18000864c  lea     rax, [rsp+58h+arg_0]
0x180008651  mov     [rsp+58h+arg_10], esi
0x180008655  mov     [rsp+58h+var_28], rax
0x18000865a  mov     rcx, rbx
0x18000865d  lea     rax, [rsp+58h+arg_10]
0x180008662  mov     [rsp+58h+arg_18], 1000000h
0x18000866b  mov     [rsp+58h+var_30], rax
0x180008670  lea     rax, [rsp+58h+arg_18]
0x180008675  mov     [rsp+58h+var_38], rax
0x18000867a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000867f  mov     rcx, rdi
0x180008682  add     rsp, 40h
0x180008686  pop     rdi
0x180008687  pop     rsi
0x180008688  pop     rbx
0x180008689  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTimeDateTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TimeDateTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
