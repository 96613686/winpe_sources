# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180016068`
- end: `0x1800160f0`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `136`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001420c`
- `0x18001ad9c`
- `0x18001ae7c`
- `0x18001af5c`
- `0x18001b03c`
- `0x18001b11c`
- `0x18001b1fc`
- `0x18001b2dc`
- `0x18001b3bc`
- `0x18001b49c`
- `0x18001b57c`
- `0x18001b65c`
- `0x18001b73c`

## callees

- `0x180013b04`
- `0x180016068`
- `0x18001666c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001608d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001608d`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  unsigned __int64 v7; // r8
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v9; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v10; // [rsp+78h] [rbp+20h] BYREF

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v10 = &SRWLock;
    if ( !a3
      || a3 != dword_18002C3BC
      || (Source[1] = 0,
          Source[0] = a2,
          v9 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002C3E0, Source, v7)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
  return result;
}

```

## disassembly

```asm
0x180016068  push    rbx
0x18001606a  push    rbp
0x18001606b  push    rsi
0x18001606c  push    rdi
0x18001606d  sub     rsp, 38h
0x180016071  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016077  mov     esi, r8d
0x18001607a  mov     ebx, edx
0x18001607c  mov     rdi, rcx
0x18001607f  test    eax, eax
0x180016081  jz      short loc_1800160E7
0x180016083  lea     rbp, SRWLock
0x18001608a  mov     rcx, rbp; SRWLock
0x18001608d  call    cs:__imp_AcquireSRWLockExclusive
0x180016093  mov     eax, cs:dword_18002C3BC
0x180016099  mov     [rsp+58h+arg_18], rbp
0x18001609e  test    esi, esi
0x1800160a0  jz      short loc_1800160CC
0x1800160a2  cmp     esi, eax
0x1800160a4  jnz     short loc_1800160CC
0x1800160a6  lea     rdx, [rsp+58h+Source]; Source
0x1800160ab  mov     [rsp+58h+var_34], 0
0x1800160b3  lea     rcx, qword_18002C3E0; this
0x1800160ba  mov     [rsp+58h+Source], ebx
0x1800160be  mov     [rsp+58h+var_30], rdi
0x1800160c3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800160c8  test    al, al
0x1800160ca  jnz     short loc_1800160DD
0x1800160cc  neg     ebx
0x1800160ce  sbb     eax, eax
0x1800160d0  and     eax, 83Ah
0x1800160d5  add     eax, 0FFFFF7C1h
0x1800160da  lock and [rdi], eax
0x1800160dd  lea     rcx, [rsp+58h+arg_18]
0x1800160e2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800160e7  add     rsp, 38h
0x1800160eb  pop     rdi
0x1800160ec  pop     rsi
0x1800160ed  pop     rbp
0x1800160ee  pop     rbx
0x1800160ef  retn
```
