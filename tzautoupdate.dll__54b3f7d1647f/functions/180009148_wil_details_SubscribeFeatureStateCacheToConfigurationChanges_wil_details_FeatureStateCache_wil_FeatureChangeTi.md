# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009148`
- end: `0x1800091d6`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800057c4`
- `0x1800058a4`
- `0x180005984`
- `0x180006870`
- `0x180010e04`
- `0x180010ee4`

## callees

- `0x180004614`
- `0x180009148`
- `0x18000b5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000916d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000916d`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v8; // [rsp+78h] [rbp+20h] BYREF

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v8 = &SRWLock;
    if ( !a3
      || a3 != dword_180030A94
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180030AB8, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x180009148  push    rbx
0x18000914a  push    rbp
0x18000914b  push    rsi
0x18000914c  push    rdi
0x18000914d  sub     rsp, 38h
0x180009151  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009157  mov     esi, r8d
0x18000915a  mov     ebx, edx
0x18000915c  mov     rdi, rcx
0x18000915f  test    eax, eax
0x180009161  jz      short loc_1800091CD
0x180009163  lea     rbp, SRWLock
0x18000916a  mov     rcx, rbp; SRWLock
0x18000916d  call    cs:__imp_AcquireSRWLockExclusive
0x180009173  mov     eax, cs:dword_180030A94
0x180009179  mov     [rsp+58h+arg_18], rbp
0x18000917e  test    esi, esi
0x180009180  jz      short loc_1800091B2
0x180009182  cmp     esi, eax
0x180009184  jnz     short loc_1800091B2
0x180009186  mov     r8d, 10h; unsigned __int64
0x18000918c  mov     [rsp+58h+var_34], 0
0x180009194  lea     rdx, [rsp+58h+var_38]; void *
0x180009199  mov     [rsp+58h+var_38], ebx
0x18000919d  lea     rcx, qword_180030AB8; this
0x1800091a4  mov     [rsp+58h+var_30], rdi
0x1800091a9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800091ae  test    al, al
0x1800091b0  jnz     short loc_1800091C3
0x1800091b2  neg     ebx
0x1800091b4  sbb     eax, eax
0x1800091b6  and     eax, 83Ah
0x1800091bb  add     eax, 0FFFFF7C1h
0x1800091c0  lock and [rdi], eax
0x1800091c3  lea     rcx, [rsp+58h+arg_18]
0x1800091c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800091cd  add     rsp, 38h
0x1800091d1  pop     rdi
0x1800091d2  pop     rsi
0x1800091d3  pop     rbp
0x1800091d4  pop     rbx
0x1800091d5  retn
```
