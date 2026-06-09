# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000a768`
- end: `0x14000a7fe`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `150`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006814`
- `0x14000698c`
- `0x140006b0c`
- `0x140011ec0`

## callees

- `0x14000a768`
- `0x14000dcc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a7e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000a7e8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a790`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000a790`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Src[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_14002C444
      || (Src[1] = 0,
          Src[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002C468, Src, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x14000a768  mov     [rsp+arg_0], rbx
0x14000a76d  mov     [rsp+arg_8], rsi
0x14000a772  push    rdi
0x14000a773  sub     rsp, 30h
0x14000a777  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000a77d  mov     esi, r8d
0x14000a780  mov     ebx, edx
0x14000a782  mov     rdi, rcx
0x14000a785  test    eax, eax
0x14000a787  jz      short loc_14000A7EE
0x14000a789  lea     rcx, SRWLock; SRWLock
0x14000a790  call    cs:__imp_AcquireSRWLockExclusive
0x14000a796  mov     eax, cs:dword_14002C444
0x14000a79c  test    esi, esi
0x14000a79e  jz      short loc_14000A7D0
0x14000a7a0  cmp     esi, eax
0x14000a7a2  jnz     short loc_14000A7D0
0x14000a7a4  mov     r8d, 10h; Size
0x14000a7aa  mov     [rsp+38h+var_14], 0
0x14000a7b2  lea     rdx, [rsp+38h+Src]; Src
0x14000a7b7  mov     [rsp+38h+Src], ebx
0x14000a7bb  lea     rcx, qword_14002C468; this
0x14000a7c2  mov     [rsp+38h+var_10], rdi
0x14000a7c7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000a7cc  test    al, al
0x14000a7ce  jnz     short loc_14000A7E1
0x14000a7d0  neg     ebx
0x14000a7d2  sbb     eax, eax
0x14000a7d4  and     eax, 83Ah
0x14000a7d9  add     eax, 0FFFFF7C1h
0x14000a7de  lock and [rdi], eax
0x14000a7e1  lea     rcx, SRWLock; SRWLock
0x14000a7e8  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a7ee  mov     rbx, [rsp+38h+arg_0]
0x14000a7f3  mov     rsi, [rsp+38h+arg_8]
0x14000a7f8  add     rsp, 30h
0x14000a7fc  pop     rdi
0x14000a7fd  retn
```
