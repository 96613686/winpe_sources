# MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(void)

- ea: `0x18000d6dc`
- end: `0x18000d812`
- name: `?StartActivity@QueryWlidsvcProperties@MSAClientTraceTelemetry@@QEAAXXZ`
- size: `310`
- prototype: `void __fastcall(MSAClientTraceTelemetry::QueryWlidsvcProperties *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000c3ac`

## callees

- `0x180002018`
- `0x1800027f0`
- `0x18000c848`
- `0x18000ca50`
- `0x18000cea8`
- `0x18000d6dc`
- `0x18000d818`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d72b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000d72b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d75c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d75c`

## pseudocode

```c
void __fastcall MSAClientTraceTelemetry::QueryWlidsvcProperties::StartActivity(
        MSAClientTraceTelemetry::QueryWlidsvcProperties *this)
{
  __int64 v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  RTL_SRWLOCK *v8; // [rsp+30h] [rbp-9h] BYREF
  __int64 v9; // [rsp+38h] [rbp-1h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v11; // [rsp+60h] [rbp+27h]
  __int64 v12; // [rsp+68h] [rbp+2Fh]
  RTL_SRWLOCK **v13; // [rsp+70h] [rbp+37h]
  __int64 v14; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)this,
    &v8);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)MSAClientTraceTelemetry::Provider(v3) <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  v5 = MSAClientTraceTelemetry::Provider(v4);
  if ( *(_DWORD *)v5 > 5u )
  {
    LODWORD(v8) = GetCurrentThreadId();
    v9 = 0x1000000;
    v6 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    v13 = &v8;
    v14 = 4;
    v11 = &v9;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer(v5, &word_18001BE96, v6 + 8, v7, 4, v10);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((MSAClientTraceTelemetry::QueryWlidsvcProperties *)((char *)this + 288));
}

```

## disassembly

```asm
0x18000d6dc  mov     [rsp-8+arg_8], rbx
0x18000d6e1  mov     [rsp-8+arg_10], rdi
0x18000d6e6  push    rbp
0x18000d6e7  lea     rbp, [rsp-57h]
0x18000d6ec  sub     rsp, 90h
0x18000d6f3  mov     rax, cs:__security_cookie
0x18000d6fa  xor     rax, rsp
0x18000d6fd  mov     [rbp+57h+var_10], rax
0x18000d701  mov     rbx, rcx
0x18000d704  lea     rdx, [rbp+57h+var_60]
0x18000d708  call    ?LockExclusive@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0A@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<MSAClientTraceTelemetry,1,0,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000d70d  mov     rdi, [rbx+110h]
0x18000d714  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000d719  mov     r8d, [rax]
0x18000d71c  cmp     r8d, 5
0x18000d720  jbe     short loc_18000D733
0x18000d722  lea     rdx, [rdi+8]; ActivityId
0x18000d726  mov     ecx, 3; ControlCode
0x18000d72b  call    cs:__imp_EventActivityIdControl
0x18000d731  jmp     short loc_18000D73A
0x18000d733  xorps   xmm0, xmm0
0x18000d736  movups  xmmword ptr [rdi+8], xmm0
0x18000d73a  mov     dword ptr [rdi], 1
0x18000d740  lea     rcx, [rbp+57h+var_60]
0x18000d744  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d749  call    ?Provider@MSAClientTraceTelemetry@@SAPEBU_tlgProvider_t@@XZ; MSAClientTraceTelemetry::Provider(void)
0x18000d74e  mov     rdi, rax
0x18000d751  mov     ecx, [rax]
0x18000d753  cmp     ecx, 5
0x18000d756  jbe     loc_18000D7DE
0x18000d75c  call    cs:__imp_GetCurrentThreadId
0x18000d762  mov     dword ptr [rbp+57h+var_60], eax
0x18000d765  mov     [rbp+57h+var_58], 1000000h
0x18000d76d  mov     r8, [rbx+110h]
0x18000d774  cmp     byte ptr [r8+4], 0
0x18000d779  jz      short loc_18000D79A
0x18000d77b  lea     r9, [r8+18h]
0x18000d77f  cmp     dword ptr [r9], 0
0x18000d783  jnz     short loc_18000D79D
0x18000d785  cmp     dword ptr [r9+4], 0
0x18000d78a  jnz     short loc_18000D79D
0x18000d78c  cmp     dword ptr [r9+8], 0
0x18000d791  jnz     short loc_18000D79D
0x18000d793  cmp     dword ptr [r9+0Ch], 0
0x18000d798  jnz     short loc_18000D79D
0x18000d79a  xor     r9d, r9d
0x18000d79d  lea     rax, [rbp+57h+var_60]
0x18000d7a1  mov     [rbp+57h+var_20], rax
0x18000d7a5  mov     ecx, 4
0x18000d7aa  mov     [rbp+57h+var_18], rcx
0x18000d7ae  lea     rax, [rbp+57h+var_58]
0x18000d7b2  mov     [rbp+57h+var_30], rax
0x18000d7b6  mov     [rbp+57h+var_28], 8
0x18000d7be  add     r8, 8
0x18000d7c2  lea     rax, [rbp+57h+var_50]
0x18000d7c6  mov     [rsp+90h+var_68], rax
0x18000d7cb  mov     [rsp+90h+var_70], ecx
0x18000d7cf  lea     rdx, word_18001BE96
0x18000d7d6  mov     rcx, rdi
0x18000d7d9  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d7de  lea     rcx, [rbx+120h]; this
0x18000d7e5  cmp     dword ptr [rcx+18h], 0
0x18000d7e9  jnz     short loc_18000D7F1
0x18000d7eb  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000d7f0  nop
0x18000d7f1  mov     rcx, [rbp+57h+var_10]
0x18000d7f5  xor     rcx, rsp; StackCookie
0x18000d7f8  call    __security_check_cookie
0x18000d7fd  lea     r11, [rsp+90h+var_s0]
0x18000d805  mov     rbx, [r11+18h]
0x18000d809  mov     rdi, [r11+20h]
0x18000d80d  mov     rsp, r11
0x18000d810  pop     rbp
0x18000d811  retn
```
