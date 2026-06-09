# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180010298`
- end: `0x180010334`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `156`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000dbec`
- `0x180015660`
- `0x180015754`
- `0x180015848`
- `0x18001593c`
- `0x180015a30`
- `0x180015b24`
- `0x180015c18`
- `0x180015d0c`
- `0x18001c034`

## callees

- `0x18000bf04`
- `0x180010298`
- `0x180010dd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800102c0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800102c0`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  RTL_SRWLOCK *v7; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v8[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v9; // [rsp+30h] [rbp-28h]

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v7 = &SRWLock;
    if ( !a3
      || a3 != dword_18002A3C4
      || (v8[1] = 0,
          v8[0] = a2,
          v9 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002A3F8, v8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  }
  return result;
}

```

## disassembly

```asm
0x180010298  mov     [rsp+arg_10], rbx
0x18001029d  push    rbp
0x18001029e  push    rsi
0x18001029f  push    rdi
0x1800102a0  sub     rsp, 40h
0x1800102a4  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800102aa  mov     esi, r8d
0x1800102ad  mov     edi, edx
0x1800102af  mov     rbx, rcx
0x1800102b2  test    eax, eax
0x1800102b4  jz      short loc_180010326
0x1800102b6  lea     rbp, SRWLock
0x1800102bd  mov     rcx, rbp; SRWLock
0x1800102c0  call    cs:__imp_AcquireSRWLockExclusive
0x1800102c7  nop     dword ptr [rax+rax+00h]
0x1800102cc  mov     eax, cs:dword_18002A3C4
0x1800102d2  mov     [rsp+58h+var_38], rbp
0x1800102d7  test    esi, esi
0x1800102d9  jz      short loc_18001030B
0x1800102db  cmp     esi, eax
0x1800102dd  jnz     short loc_18001030B
0x1800102df  mov     r8d, 10h; unsigned __int64
0x1800102e5  mov     [rsp+58h+var_2C], 0
0x1800102ed  lea     rdx, [rsp+58h+var_30]; void *
0x1800102f2  mov     [rsp+58h+var_30], edi
0x1800102f6  lea     rcx, qword_18002A3F8; this
0x1800102fd  mov     [rsp+58h+var_28], rbx
0x180010302  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180010307  test    al, al
0x180010309  jnz     short loc_18001031C
0x18001030b  neg     edi
0x18001030d  sbb     eax, eax
0x18001030f  and     eax, 83Ah
0x180010314  add     eax, 0FFFFF7C1h
0x180010319  lock and [rbx], eax
0x18001031c  lea     rcx, [rsp+58h+var_38]
0x180010321  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180010326  mov     rbx, [rsp+58h+arg_10]
0x18001032b  add     rsp, 40h
0x18001032f  pop     rdi
0x180010330  pop     rsi
0x180010331  pop     rbp
0x180010332  retn
```
