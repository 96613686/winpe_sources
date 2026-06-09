# MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(void)

- ea: `0x1800467fc`
- end: `0x1800468e7`
- name: `?StartActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAAXXZ`
- size: `235`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180044c3c`

## callees

- `0x18000176c`
- `0x1800050b8`
- `0x180045b70`
- `0x180045fc8`
- `0x1800467fc`
- `0x1800468f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004685f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004685f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180046831`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180046831`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  __int64 v4; // r8
  __int64 v5; // r9
  RTL_SRWLOCK *v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v6);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)MSAClientTraceTelemetry::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  v3 = MSAClientTraceTelemetry::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    LODWORD(v6) = GetCurrentThreadId();
    v7 = 0x1000000;
    v4 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v4 + 4)
      || (v5 = v4 + 24, !*(_DWORD *)(v4 + 24))
      && !*(_DWORD *)(v4 + 28)
      && !*(_DWORD *)(v4 + 32)
      && !*(_DWORD *)(v4 + 36) )
    {
      v5 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (__int64)v3,
      (__int64)&word_180085F0E,
      v4 + 8,
      v5,
      (__int64)&v7,
      (__int64)&v6);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((MSAClientTraceTelemetry::QueryWlidsvcProperties *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800467fc  mov     [rsp+arg_10], rbx
0x180046801  push    rdi
0x180046802  sub     rsp, 30h
0x180046806  mov     rbx, rcx
0x180046809  lea     rdx, [rsp+38h+arg_0]
0x18004680e  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180046813  mov     rdi, [rbx+110h]
0x18004681a  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18004681f  mov     r8d, [rax]
0x180046822  cmp     r8d, 5
0x180046826  jbe     short loc_180046839
0x180046828  lea     rdx, [rdi+8]; ActivityId
0x18004682c  mov     ecx, 3; ControlCode
0x180046831  call    cs:__imp_EventActivityIdControl
0x180046837  jmp     short loc_180046840
0x180046839  xorps   xmm0, xmm0
0x18004683c  movups  xmmword ptr [rdi+8], xmm0
0x180046840  mov     dword ptr [rdi], 1
0x180046846  lea     rcx, [rsp+38h+arg_0]
0x18004684b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180046850  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x180046855  mov     rdi, rax
0x180046858  mov     ecx, [rax]
0x18004685a  cmp     ecx, 5
0x18004685d  jbe     short loc_1800468C9
0x18004685f  call    cs:__imp_GetCurrentThreadId
0x180046865  mov     dword ptr [rsp+38h+arg_0], eax
0x180046869  mov     [rsp+38h+arg_8], 1000000h
0x180046872  mov     r8, [rbx+110h]
0x180046879  cmp     byte ptr [r8+4], 0
0x18004687e  jz      short loc_18004689F
0x180046880  lea     r9, [r8+18h]
0x180046884  cmp     dword ptr [r9], 0
0x180046888  jnz     short loc_1800468A2
0x18004688a  cmp     dword ptr [r9+4], 0
0x18004688f  jnz     short loc_1800468A2
0x180046891  cmp     dword ptr [r9+8], 0
0x180046896  jnz     short loc_1800468A2
0x180046898  cmp     dword ptr [r9+0Ch], 0
0x18004689d  jnz     short loc_1800468A2
0x18004689f  xor     r9d, r9d
0x1800468a2  add     r8, 8
0x1800468a6  lea     rax, [rsp+38h+arg_0]
0x1800468ab  mov     [rsp+38h+var_10], rax
0x1800468b0  lea     rax, [rsp+38h+arg_8]
0x1800468b5  mov     [rsp+38h+var_18], rax
0x1800468ba  lea     rdx, word_180085F0E
0x1800468c1  mov     rcx, rdi
0x1800468c4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800468c9  lea     rcx, [rbx+120h]; this
0x1800468d0  cmp     dword ptr [rcx+18h], 0
0x1800468d4  jnz     short loc_1800468DC
0x1800468d6  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800468db  nop
0x1800468dc  mov     rbx, [rsp+38h+arg_10]
0x1800468e1  add     rsp, 30h
0x1800468e5  pop     rdi
0x1800468e6  retn
```
