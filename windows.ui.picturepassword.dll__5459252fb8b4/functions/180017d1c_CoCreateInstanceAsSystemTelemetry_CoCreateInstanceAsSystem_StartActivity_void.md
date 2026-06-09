# CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StartActivity(void)

- ea: `0x180017d1c`
- end: `0x180017e34`
- name: `?StartActivity@CoCreateInstanceAsSystem@CoCreateInstanceAsSystemTelemetry@@QEAAXXZ`
- size: `280`
- prototype: `void __fastcall(CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800185b4`

## callees

- `0x1800012cc`
- `0x180001acc`
- `0x180005cb8`
- `0x180007fd4`
- `0x180009c8c`
- `0x180017bd8`
- `0x180017d1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017dad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017dad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017d65`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017d65`

## pseudocode

```c
void __fastcall CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem::StartActivity(
        CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *this)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rcx
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &v13);
  v2 = *((_QWORD *)this + 34);
  v4 = CoCreateInstanceAsSystemLogging::Provider(v3);
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  v7 = CoCreateInstanceAsSystemLogging::Provider(v6);
  v9 = (__int64)v7;
  if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL, v8) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v11 = *((_QWORD *)this + 34);
    LODWORD(v13) = CurrentThreadId;
    v14 = 0;
    if ( !*(_BYTE *)(v11 + 4)
      || (v12 = v11 + 24, !*(_DWORD *)(v11 + 24))
      && !*(_DWORD *)(v11 + 28)
      && !*(_DWORD *)(v11 + 32)
      && !*(_DWORD *)(v11 + 36) )
    {
      v12 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v9,
      (__int64)&unk_180025108,
      v11 + 8,
      v12,
      (__int64)&v14,
      (__int64)&v13);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((CoCreateInstanceAsSystemTelemetry::CoCreateInstanceAsSystem *)((char *)this + 288));
}

```

## disassembly

```asm
0x180017d1c  mov     [rsp+arg_10], rbx
0x180017d21  push    rdi
0x180017d22  sub     rsp, 30h
0x180017d26  lea     rdx, [rsp+38h+arg_0]
0x180017d2b  mov     rdi, rcx
0x180017d2e  call    ?LockExclusive@?$ActivityBase@VCoCreateInstanceAsSystemLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoCreateInstanceAsSystemLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017d33  mov     rbx, [rdi+110h]
0x180017d3a  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x180017d3f  mov     edx, [rax]
0x180017d41  cmp     edx, 5
0x180017d44  jbe     short loc_180017D6D
0x180017d46  mov     rdx, 200000000000h
0x180017d50  mov     rcx, rax
0x180017d53  call    _tlgKeywordOn
0x180017d58  test    al, al
0x180017d5a  jz      short loc_180017D6D
0x180017d5c  lea     rdx, [rbx+8]; ActivityId
0x180017d60  mov     ecx, 3; ControlCode
0x180017d65  call    cs:__imp_EventActivityIdControl
0x180017d6b  jmp     short loc_180017D74
0x180017d6d  xorps   xmm0, xmm0
0x180017d70  movups  xmmword ptr [rbx+8], xmm0
0x180017d74  lea     rcx, [rsp+38h+arg_0]
0x180017d79  mov     dword ptr [rbx], 1
0x180017d7f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017d84  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x180017d89  mov     rbx, rax
0x180017d8c  mov     ecx, [rax]
0x180017d8e  cmp     ecx, 5
0x180017d91  jbe     loc_180017E17
0x180017d97  mov     rdx, 200000000000h
0x180017da1  mov     rcx, rax
0x180017da4  call    _tlgKeywordOn
0x180017da9  test    al, al
0x180017dab  jz      short loc_180017E17
0x180017dad  call    cs:__imp_GetCurrentThreadId
0x180017db3  mov     r8, [rdi+110h]
0x180017dba  mov     dword ptr [rsp+38h+arg_0], eax
0x180017dbe  mov     [rsp+38h+arg_8], 0
0x180017dc7  cmp     byte ptr [r8+4], 0
0x180017dcc  jz      short loc_180017DED
0x180017dce  lea     r9, [r8+18h]
0x180017dd2  cmp     dword ptr [r9], 0
0x180017dd6  jnz     short loc_180017DF0
0x180017dd8  cmp     dword ptr [r9+4], 0
0x180017ddd  jnz     short loc_180017DF0
0x180017ddf  cmp     dword ptr [r9+8], 0
0x180017de4  jnz     short loc_180017DF0
0x180017de6  cmp     dword ptr [r9+0Ch], 0
0x180017deb  jnz     short loc_180017DF0
0x180017ded  xor     r9d, r9d
0x180017df0  lea     rax, [rsp+38h+arg_0]
0x180017df5  add     r8, 8
0x180017df9  mov     [rsp+38h+var_10], rax
0x180017dfe  lea     rdx, unk_180025108
0x180017e05  lea     rax, [rsp+38h+arg_8]
0x180017e0a  mov     rcx, rbx
0x180017e0d  mov     [rsp+38h+var_18], rax
0x180017e12  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180017e17  lea     rcx, [rdi+120h]; this
0x180017e1e  cmp     dword ptr [rcx+18h], 0
0x180017e22  jnz     short loc_180017E29
0x180017e24  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180017e29  mov     rbx, [rsp+38h+arg_10]
0x180017e2e  add     rsp, 30h
0x180017e32  pop     rdi
0x180017e33  retn
```
