# StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StartActivity(void)

- ea: `0x18006b004`
- end: `0x18006b0de`
- name: `?StartActivity@QueryStorageReserve@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ`
- size: `218`
- prototype: `void __fastcall(StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180069f08`

## callees

- `0x180004ccc`
- `0x180013fc0`
- `0x18001dc9c`
- `0x18006a2f4`
- `0x18006a768`
- `0x18006b004`
- `0x18006b0e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b067`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006b067`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006b039`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18006b039`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve::StartActivity(
        StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  int v4; // edi
  __int64 v5; // r8
  int v6; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)StorageReserveTelemetry::Internal::StorageReserveProvider::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v3 = StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
  v4 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4) || _tlgGuidIsZero((const struct _GUID *)(v5 + 24)) )
      v6 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&byte_1800A8E3F,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((StorageReserveTelemetry::Internal::SRProvider::QueryStorageReserve *)((char *)this + 288));
}

```

## disassembly

```asm
0x18006b004  mov     [rsp+arg_10], rbx
0x18006b009  push    rdi
0x18006b00a  sub     rsp, 30h
0x18006b00e  mov     rbx, rcx
0x18006b011  lea     rdx, [rsp+38h+arg_0]
0x18006b016  call    ?LockExclusive@?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006b01b  mov     rdi, [rbx+110h]
0x18006b022  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18006b027  mov     r8d, [rax]
0x18006b02a  cmp     r8d, 5
0x18006b02e  jbe     short loc_18006B041
0x18006b030  lea     rdx, [rdi+8]; ActivityId
0x18006b034  mov     ecx, 3; ControlCode
0x18006b039  call    cs:__imp_EventActivityIdControl
0x18006b03f  jmp     short loc_18006B048
0x18006b041  xorps   xmm0, xmm0
0x18006b044  movups  xmmword ptr [rdi+8], xmm0
0x18006b048  mov     dword ptr [rdi], 1
0x18006b04e  lea     rcx, [rsp+38h+arg_0]
0x18006b053  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006b058  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x18006b05d  mov     rdi, rax
0x18006b060  mov     ecx, [rax]
0x18006b062  cmp     ecx, 5
0x18006b065  jbe     short loc_18006B0C1
0x18006b067  call    cs:__imp_GetCurrentThreadId
0x18006b06d  mov     [rsp+38h+arg_0], eax
0x18006b071  mov     [rsp+38h+arg_8], 0
0x18006b07a  mov     r8, [rbx+110h]
0x18006b081  cmp     byte ptr [r8+4], 0
0x18006b086  jz      short loc_18006B095
0x18006b088  lea     rcx, [r8+18h]; struct _GUID *
0x18006b08c  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18006b091  test    al, al
0x18006b093  jz      short loc_18006B097
0x18006b095  xor     ecx, ecx
0x18006b097  add     r8, 8
0x18006b09b  lea     rax, [rsp+38h+arg_0]
0x18006b0a0  mov     [rsp+38h+var_10], rax
0x18006b0a5  lea     rax, [rsp+38h+arg_8]
0x18006b0aa  mov     [rsp+38h+var_18], rax
0x18006b0af  mov     r9, rcx
0x18006b0b2  lea     rdx, byte_1800A8E3F
0x18006b0b9  mov     rcx, rdi
0x18006b0bc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18006b0c1  lea     rcx, [rbx+120h]; this
0x18006b0c8  cmp     dword ptr [rcx+18h], 0
0x18006b0cc  jnz     short loc_18006B0D3
0x18006b0ce  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18006b0d3  mov     rbx, [rsp+38h+arg_10]
0x18006b0d8  add     rsp, 30h
0x18006b0dc  pop     rdi
0x18006b0dd  retn
```
