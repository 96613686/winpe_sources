# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000da58`
- end: `0x18000daf7`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008e78`
- `0x18000a338`

## callees

- `0x18000da58`
- `0x18000ec2c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000da7f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000da7f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000dada`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000dada`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180028344
      || (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180028378, Source, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000da58  mov     [rsp+arg_0], rbx
0x18000da5d  mov     [rsp+arg_8], rsi
0x18000da62  push    rdi
0x18000da63  sub     rsp, 30h
0x18000da67  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000da6e  mov     esi, r8d
0x18000da71  mov     ebx, edx
0x18000da73  mov     rdi, rcx
0x18000da76  jz      short loc_18000DAE6
0x18000da78  lea     rcx, SRWLock; SRWLock
0x18000da7f  call    cs:__imp_AcquireSRWLockExclusive
0x18000da86  nop     dword ptr [rax+rax+00h]
0x18000da8b  mov     eax, cs:dword_180028344
0x18000da91  test    esi, esi
0x18000da93  jz      short loc_18000DAC2
0x18000da95  cmp     esi, eax
0x18000da97  jnz     short loc_18000DAC2
0x18000da99  and     [rsp+38h+var_14], 0
0x18000da9e  lea     rdx, [rsp+38h+Source]; Source
0x18000daa3  mov     r8d, 10h; SourceSize
0x18000daa9  mov     [rsp+38h+Source], ebx
0x18000daad  lea     rcx, qword_180028378; this
0x18000dab4  mov     [rsp+38h+var_10], rdi
0x18000dab9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000dabe  test    al, al
0x18000dac0  jnz     short loc_18000DAD3
0x18000dac2  neg     ebx
0x18000dac4  sbb     eax, eax
0x18000dac6  and     eax, 83Ah
0x18000dacb  add     eax, 0FFFFF7C1h
0x18000dad0  lock and [rdi], eax
0x18000dad3  lea     rcx, SRWLock; SRWLock
0x18000dada  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dae1  nop     dword ptr [rax+rax+00h]
0x18000dae6  mov     rbx, [rsp+38h+arg_0]
0x18000daeb  mov     rsi, [rsp+38h+arg_8]
0x18000daf0  add     rsp, 30h
0x18000daf4  pop     rdi
0x18000daf5  retn
```
