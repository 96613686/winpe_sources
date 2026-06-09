# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180017190`
- end: `0x18001721e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015404`
- `0x1800156e4`

## callees

- `0x18000d158`
- `0x180017190`
- `0x180017b9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171b5`

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
      || a3 != dword_180028274
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180028298, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x180017190  push    rbx
0x180017192  push    rbp
0x180017193  push    rsi
0x180017194  push    rdi
0x180017195  sub     rsp, 38h
0x180017199  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001719f  mov     esi, r8d
0x1800171a2  mov     ebx, edx
0x1800171a4  mov     rdi, rcx
0x1800171a7  test    eax, eax
0x1800171a9  jz      short loc_180017215
0x1800171ab  lea     rbp, SRWLock
0x1800171b2  mov     rcx, rbp; SRWLock
0x1800171b5  call    cs:__imp_AcquireSRWLockExclusive
0x1800171bb  mov     eax, cs:dword_180028274
0x1800171c1  mov     [rsp+58h+arg_18], rbp
0x1800171c6  test    esi, esi
0x1800171c8  jz      short loc_1800171FA
0x1800171ca  cmp     esi, eax
0x1800171cc  jnz     short loc_1800171FA
0x1800171ce  mov     r8d, 10h; unsigned __int64
0x1800171d4  mov     [rsp+58h+var_34], 0
0x1800171dc  lea     rdx, [rsp+58h+var_38]; void *
0x1800171e1  mov     [rsp+58h+var_38], ebx
0x1800171e5  lea     rcx, qword_180028298; this
0x1800171ec  mov     [rsp+58h+var_30], rdi
0x1800171f1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800171f6  test    al, al
0x1800171f8  jnz     short loc_18001720B
0x1800171fa  neg     ebx
0x1800171fc  sbb     eax, eax
0x1800171fe  and     eax, 83Ah
0x180017203  add     eax, 0FFFFF7C1h
0x180017208  lock and [rdi], eax
0x18001720b  lea     rcx, [rsp+58h+arg_18]
0x180017210  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017215  add     rsp, 38h
0x180017219  pop     rdi
0x18001721a  pop     rsi
0x18001721b  pop     rbp
0x18001721c  pop     rbx
0x18001721d  retn
```
