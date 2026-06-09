# PicturePasswordTelemetry::RunEnrollmentUX::StartActivity(void)

- ea: `0x180009b6c`
- end: `0x180009c84`
- name: `?StartActivity@RunEnrollmentUX@PicturePasswordTelemetry@@QEAAXXZ`
- size: `280`
- prototype: `void __fastcall(PicturePasswordTelemetry::RunEnrollmentUX *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009400`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x180005cb8`
- `0x180007fd4`
- `0x180008c00`
- `0x180009b6c`
- `0x180009c8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bfd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009bfd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009bb5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180009bb5`

## pseudocode

```c
void __fastcall PicturePasswordTelemetry::RunEnrollmentUX::StartActivity(
        PicturePasswordTelemetry::RunEnrollmentUX *this)
{
  __int64 v2; // rbx
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  RTL_SRWLOCK *v11; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &v11);
  v2 = *((_QWORD *)this + 34);
  v3 = PicturePasswordLogger::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  v5 = PicturePasswordLogger::Provider();
  v7 = (__int64)v5;
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(v11) = CurrentThreadId;
    v12 = 0;
    if ( !*(_BYTE *)(v9 + 4)
      || (v10 = v9 + 24, !*(_DWORD *)(v9 + 24))
      && !*(_DWORD *)(v9 + 28)
      && !*(_DWORD *)(v9 + 32)
      && !*(_DWORD *)(v9 + 36) )
    {
      v10 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v7,
      (__int64)word_1800249D2,
      v9 + 8,
      v10,
      (__int64)&v12,
      (__int64)&v11);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((PicturePasswordTelemetry::RunEnrollmentUX *)((char *)this + 288));
}

```

## disassembly

```asm
0x180009b6c  mov     [rsp+arg_10], rbx
0x180009b71  push    rdi
0x180009b72  sub     rsp, 30h
0x180009b76  lea     rdx, [rsp+38h+arg_0]
0x180009b7b  mov     rdi, rcx
0x180009b7e  call    ?LockExclusive@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180009b83  mov     rbx, [rdi+110h]
0x180009b8a  call    ?Provider@PicturePasswordLogger@@SAPEBU_tlgProvider_t@@XZ; PicturePasswordLogger::Provider(void)
0x180009b8f  mov     edx, [rax]
0x180009b91  cmp     edx, 5
0x180009b94  jbe     short loc_180009BBD
0x180009b96  mov     rdx, 200000000000h
0x180009ba0  mov     rcx, rax
0x180009ba3  call    _tlgKeywordOn
0x180009ba8  test    al, al
0x180009baa  jz      short loc_180009BBD
0x180009bac  lea     rdx, [rbx+8]; ActivityId
0x180009bb0  mov     ecx, 3; ControlCode
0x180009bb5  call    cs:__imp_EventActivityIdControl
0x180009bbb  jmp     short loc_180009BC4
0x180009bbd  xorps   xmm0, xmm0
0x180009bc0  movups  xmmword ptr [rbx+8], xmm0
0x180009bc4  lea     rcx, [rsp+38h+arg_0]
0x180009bc9  mov     dword ptr [rbx], 1
0x180009bcf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009bd4  call    ?Provider@PicturePasswordLogger@@SAPEBU_tlgProvider_t@@XZ; PicturePasswordLogger::Provider(void)
0x180009bd9  mov     rbx, rax
0x180009bdc  mov     ecx, [rax]
0x180009bde  cmp     ecx, 5
0x180009be1  jbe     loc_180009C67
0x180009be7  mov     rdx, 200000000000h
0x180009bf1  mov     rcx, rax
0x180009bf4  call    _tlgKeywordOn
0x180009bf9  test    al, al
0x180009bfb  jz      short loc_180009C67
0x180009bfd  call    cs:__imp_GetCurrentThreadId
0x180009c03  mov     r8, [rdi+110h]
0x180009c0a  mov     dword ptr [rsp+38h+arg_0], eax
0x180009c0e  mov     [rsp+38h+arg_8], 0
0x180009c17  cmp     byte ptr [r8+4], 0
0x180009c1c  jz      short loc_180009C3D
0x180009c1e  lea     r9, [r8+18h]
0x180009c22  cmp     dword ptr [r9], 0
0x180009c26  jnz     short loc_180009C40
0x180009c28  cmp     dword ptr [r9+4], 0
0x180009c2d  jnz     short loc_180009C40
0x180009c2f  cmp     dword ptr [r9+8], 0
0x180009c34  jnz     short loc_180009C40
0x180009c36  cmp     dword ptr [r9+0Ch], 0
0x180009c3b  jnz     short loc_180009C40
0x180009c3d  xor     r9d, r9d
0x180009c40  lea     rax, [rsp+38h+arg_0]
0x180009c45  add     r8, 8
0x180009c49  mov     [rsp+38h+var_10], rax
0x180009c4e  lea     rdx, word_1800249D2
0x180009c55  lea     rax, [rsp+38h+arg_8]
0x180009c5a  mov     rcx, rbx
0x180009c5d  mov     [rsp+38h+var_18], rax
0x180009c62  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180009c67  lea     rcx, [rdi+120h]; this
0x180009c6e  cmp     dword ptr [rcx+18h], 0
0x180009c72  jnz     short loc_180009C79
0x180009c74  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180009c79  mov     rbx, [rsp+38h+arg_10]
0x180009c7e  add     rsp, 30h
0x180009c82  pop     rdi
0x180009c83  retn
```
