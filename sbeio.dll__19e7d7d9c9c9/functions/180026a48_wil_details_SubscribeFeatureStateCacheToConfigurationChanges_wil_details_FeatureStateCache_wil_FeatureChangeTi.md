# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180026a48`
- end: `0x180026ad7`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `143`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001b090`
- `0x18001b184`
- `0x18001b278`
- `0x18001b36c`
- `0x18001b460`
- `0x18001b554`
- `0x18001b648`
- `0x18001b73c`
- `0x18001b830`
- `0x18001b924`

## callees

- `0x180015800`
- `0x180026a48`
- `0x180027180`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180026a70`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026a70`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  unsigned __int64 v7; // r8
  RTL_SRWLOCK *v8; // [rsp+20h] [rbp-38h] BYREF
  _DWORD Source[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v10; // [rsp+30h] [rbp-28h]

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v8 = &SRWLock;
    if ( !a3
      || a3 != dword_180032214
      || (Source[1] = 0,
          Source[0] = a2,
          v10 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180032238, Source, v7)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
  return result;
}

```

## disassembly

```asm
0x180026a48  mov     [rsp+arg_10], rbx
0x180026a4d  push    rbp
0x180026a4e  push    rsi
0x180026a4f  push    rdi
0x180026a50  sub     rsp, 40h
0x180026a54  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180026a5a  mov     esi, r8d
0x180026a5d  mov     edi, edx
0x180026a5f  mov     rbx, rcx
0x180026a62  test    eax, eax
0x180026a64  jz      short loc_180026ACA
0x180026a66  lea     rbp, SRWLock
0x180026a6d  mov     rcx, rbp; SRWLock
0x180026a70  call    cs:__imp_AcquireSRWLockExclusive
0x180026a76  mov     eax, cs:dword_180032214
0x180026a7c  mov     [rsp+58h+var_38], rbp
0x180026a81  test    esi, esi
0x180026a83  jz      short loc_180026AAF
0x180026a85  cmp     esi, eax
0x180026a87  jnz     short loc_180026AAF
0x180026a89  lea     rdx, [rsp+58h+Source]; Source
0x180026a8e  mov     [rsp+58h+var_2C], 0
0x180026a96  lea     rcx, qword_180032238; this
0x180026a9d  mov     [rsp+58h+Source], edi
0x180026aa1  mov     [rsp+58h+var_28], rbx
0x180026aa6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026aab  test    al, al
0x180026aad  jnz     short loc_180026AC0
0x180026aaf  neg     edi
0x180026ab1  sbb     eax, eax
0x180026ab3  and     eax, 83Ah
0x180026ab8  add     eax, 0FFFFF7C1h
0x180026abd  lock and [rbx], eax
0x180026ac0  lea     rcx, [rsp+58h+var_38]
0x180026ac5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026aca  mov     rbx, [rsp+58h+arg_10]
0x180026acf  add     rsp, 40h
0x180026ad3  pop     rdi
0x180026ad4  pop     rsi
0x180026ad5  pop     rbp
0x180026ad6  retn
```
