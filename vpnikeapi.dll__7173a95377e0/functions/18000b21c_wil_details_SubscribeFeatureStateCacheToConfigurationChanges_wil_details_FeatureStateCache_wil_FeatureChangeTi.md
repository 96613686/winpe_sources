# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b21c`
- end: `0x18000b2aa`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009434`

## callees

- `0x180007b44`
- `0x18000b21c`
- `0x18000be9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b241`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b241`

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
      || a3 != dword_18001619C
      || (v6[1] = 0, v6[0] = a2, v7 = a1, !wil::details_abi::heap_buffer::push_back((void **)qword_1800161C0, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x18000b21c  push    rbx
0x18000b21e  push    rbp
0x18000b21f  push    rsi
0x18000b220  push    rdi
0x18000b221  sub     rsp, 38h
0x18000b225  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b22b  mov     esi, r8d
0x18000b22e  mov     ebx, edx
0x18000b230  mov     rdi, rcx
0x18000b233  test    eax, eax
0x18000b235  jz      short loc_18000B2A1
0x18000b237  lea     rbp, SRWLock
0x18000b23e  mov     rcx, rbp; SRWLock
0x18000b241  call    cs:__imp_AcquireSRWLockExclusive
0x18000b247  mov     eax, cs:dword_18001619C
0x18000b24d  mov     [rsp+58h+arg_18], rbp
0x18000b252  test    esi, esi
0x18000b254  jz      short loc_18000B286
0x18000b256  cmp     esi, eax
0x18000b258  jnz     short loc_18000B286
0x18000b25a  mov     r8d, 10h; unsigned __int64
0x18000b260  mov     [rsp+58h+var_34], 0
0x18000b268  lea     rdx, [rsp+58h+var_38]; void *
0x18000b26d  mov     [rsp+58h+var_38], ebx
0x18000b271  lea     rcx, qword_1800161C0; this
0x18000b278  mov     [rsp+58h+var_30], rdi
0x18000b27d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b282  test    al, al
0x18000b284  jnz     short loc_18000B297
0x18000b286  neg     ebx
0x18000b288  sbb     eax, eax
0x18000b28a  and     eax, 83Ah
0x18000b28f  add     eax, 0FFFFF7C1h
0x18000b294  lock and [rdi], eax
0x18000b297  lea     rcx, [rsp+58h+arg_18]
0x18000b29c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b2a1  add     rsp, 38h
0x18000b2a5  pop     rdi
0x18000b2a6  pop     rsi
0x18000b2a7  pop     rbp
0x18000b2a8  pop     rbx
0x18000b2a9  retn
```
