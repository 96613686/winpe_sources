# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180011590`
- end: `0x18001161e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000da28`
- `0x18000db08`
- `0x18000dbe8`
- `0x18000ec7c`

## callees

- `0x18000cb5c`
- `0x180011590`
- `0x1800124fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800115b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800115b5`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  _DWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v9; // [rsp+78h] [rbp+20h] BYREF

  result = (unsigned int)wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v9 = &SRWLock;
    if ( !a3
      || a3 != dword_18004B59C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004B5C0, v7, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  return result;
}

```

## disassembly

```asm
0x180011590  push    rbx
0x180011592  push    rbp
0x180011593  push    rsi
0x180011594  push    rdi
0x180011595  sub     rsp, 38h
0x180011599  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001159f  mov     esi, r8d
0x1800115a2  mov     ebx, edx
0x1800115a4  mov     rdi, rcx
0x1800115a7  test    eax, eax
0x1800115a9  jz      short loc_180011615
0x1800115ab  lea     rbp, SRWLock
0x1800115b2  mov     rcx, rbp; SRWLock
0x1800115b5  call    cs:__imp_AcquireSRWLockExclusive
0x1800115bb  mov     eax, cs:dword_18004B59C
0x1800115c1  mov     [rsp+58h+arg_18], rbp
0x1800115c6  test    esi, esi
0x1800115c8  jz      short loc_1800115FA
0x1800115ca  cmp     esi, eax
0x1800115cc  jnz     short loc_1800115FA
0x1800115ce  mov     r8d, 10h; unsigned __int64
0x1800115d4  mov     [rsp+58h+var_34], 0
0x1800115dc  lea     rdx, [rsp+58h+var_38]; void *
0x1800115e1  mov     [rsp+58h+var_38], ebx
0x1800115e5  lea     rcx, qword_18004B5C0; this
0x1800115ec  mov     [rsp+58h+var_30], rdi
0x1800115f1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800115f6  test    al, al
0x1800115f8  jnz     short loc_18001160B
0x1800115fa  neg     ebx
0x1800115fc  sbb     eax, eax
0x1800115fe  and     eax, 83Ah
0x180011603  add     eax, 0FFFFF7C1h
0x180011608  lock and [rdi], eax
0x18001160b  lea     rcx, [rsp+58h+arg_18]
0x180011610  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011615  add     rsp, 38h
0x180011619  pop     rdi
0x18001161a  pop     rsi
0x18001161b  pop     rbp
0x18001161c  pop     rbx
0x18001161d  retn
```
