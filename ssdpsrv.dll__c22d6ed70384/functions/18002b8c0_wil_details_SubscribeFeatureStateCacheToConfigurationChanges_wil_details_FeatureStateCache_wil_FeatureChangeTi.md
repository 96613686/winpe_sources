# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18002b8c0`
- end: `0x18002b94e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180029cd0`
- `0x18002deec`
- `0x180030848`
- `0x180030928`

## callees

- `0x1800232a8`
- `0x18002b8c0`
- `0x18002c4a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b8e5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002b8e5`

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
      || a3 != dword_1800412AC
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800412D0, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x18002b8c0  push    rbx
0x18002b8c2  push    rbp
0x18002b8c3  push    rsi
0x18002b8c4  push    rdi
0x18002b8c5  sub     rsp, 38h
0x18002b8c9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002b8cf  mov     esi, r8d
0x18002b8d2  mov     ebx, edx
0x18002b8d4  mov     rdi, rcx
0x18002b8d7  test    eax, eax
0x18002b8d9  jz      short loc_18002B945
0x18002b8db  lea     rbp, SRWLock
0x18002b8e2  mov     rcx, rbp; SRWLock
0x18002b8e5  call    cs:__imp_AcquireSRWLockExclusive
0x18002b8eb  mov     eax, cs:dword_1800412AC
0x18002b8f1  mov     [rsp+58h+arg_18], rbp
0x18002b8f6  test    esi, esi
0x18002b8f8  jz      short loc_18002B92A
0x18002b8fa  cmp     esi, eax
0x18002b8fc  jnz     short loc_18002B92A
0x18002b8fe  mov     r8d, 10h; unsigned __int64
0x18002b904  mov     [rsp+58h+var_34], 0
0x18002b90c  lea     rdx, [rsp+58h+var_38]; void *
0x18002b911  mov     [rsp+58h+var_38], ebx
0x18002b915  lea     rcx, qword_1800412D0; this
0x18002b91c  mov     [rsp+58h+var_30], rdi
0x18002b921  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002b926  test    al, al
0x18002b928  jnz     short loc_18002B93B
0x18002b92a  neg     ebx
0x18002b92c  sbb     eax, eax
0x18002b92e  and     eax, 83Ah
0x18002b933  add     eax, 0FFFFF7C1h
0x18002b938  lock and [rdi], eax
0x18002b93b  lea     rcx, [rsp+58h+arg_18]
0x18002b940  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b945  add     rsp, 38h
0x18002b949  pop     rdi
0x18002b94a  pop     rsi
0x18002b94b  pop     rbp
0x18002b94c  pop     rbx
0x18002b94d  retn
```
