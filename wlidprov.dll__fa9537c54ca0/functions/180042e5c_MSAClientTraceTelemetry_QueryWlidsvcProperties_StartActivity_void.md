# MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(void)

- ea: `0x180042e5c`
- end: `0x180042f37`
- name: `?StartActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAAXXZ`
- size: `219`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180041988`

## callees

- `0x1800023b8`
- `0x180015bc0`
- `0x180018a24`
- `0x18002afd4`
- `0x18002e160`
- `0x18002f880`
- `0x180042e5c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180042e91`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180042e91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042ebf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042ebf`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  int v4; // edi
  __int64 v5; // r8
  int v6; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)MSAClientTraceTelemetry::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v3 = MSAClientTraceTelemetry::Provider();
  v4 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0x1000000;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4) || _tlgGuidIsZero((const struct _GUID *)(v5 + 24)) )
      v6 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)byte_180077AD5,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((MSAClientTraceTelemetry::QueryWlidsvcProperties *)((char *)this + 288));
}

```

## disassembly

```asm
0x180042e5c  mov     [rsp+arg_10], rbx
0x180042e61  push    rdi
0x180042e62  sub     rsp, 30h
0x180042e66  mov     rbx, rcx
0x180042e69  lea     rdx, [rsp+38h+arg_0]
0x180042e6e  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180042e73  mov     rdi, [rbx+110h]
0x180042e7a  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180042e7f  mov     r8d, [rax]
0x180042e82  cmp     r8d, 5
0x180042e86  jbe     short loc_180042E99
0x180042e88  lea     rdx, [rdi+8]; ActivityId
0x180042e8c  mov     ecx, 3; ControlCode
0x180042e91  call    cs:__imp_EventActivityIdControl
0x180042e97  jmp     short loc_180042EA0
0x180042e99  xorps   xmm0, xmm0
0x180042e9c  movups  xmmword ptr [rdi+8], xmm0
0x180042ea0  mov     dword ptr [rdi], 1
0x180042ea6  lea     rcx, [rsp+38h+arg_0]
0x180042eab  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180042eb0  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180042eb5  mov     rdi, rax
0x180042eb8  mov     ecx, [rax]
0x180042eba  cmp     ecx, 5
0x180042ebd  jbe     short loc_180042F19
0x180042ebf  call    cs:__imp_GetCurrentThreadId
0x180042ec5  mov     [rsp+38h+arg_0], eax
0x180042ec9  mov     [rsp+38h+arg_8], 1000000h
0x180042ed2  mov     r8, [rbx+110h]
0x180042ed9  cmp     byte ptr [r8+4], 0
0x180042ede  jz      short loc_180042EED
0x180042ee0  lea     rcx, [r8+18h]; struct _GUID *
0x180042ee4  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180042ee9  test    al, al
0x180042eeb  jz      short loc_180042EEF
0x180042eed  xor     ecx, ecx
0x180042eef  add     r8, 8
0x180042ef3  lea     rax, [rsp+38h+arg_0]
0x180042ef8  mov     [rsp+38h+var_10], rax
0x180042efd  lea     rax, [rsp+38h+arg_8]
0x180042f02  mov     [rsp+38h+var_18], rax
0x180042f07  mov     r9, rcx
0x180042f0a  lea     rdx, byte_180077AD5
0x180042f11  mov     rcx, rdi
0x180042f14  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180042f19  lea     rcx, [rbx+120h]; this
0x180042f20  cmp     dword ptr [rcx+18h], 0
0x180042f24  jnz     short loc_180042F2C
0x180042f26  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180042f2b  nop
0x180042f2c  mov     rbx, [rsp+38h+arg_10]
0x180042f31  add     rsp, 30h
0x180042f35  pop     rdi
0x180042f36  retn
```
