# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000bf74`
- end: `0x18000c00a`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `150`
- prototype: ``
- caller_count: `27`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a89c`
- `0x180014c10`
- `0x180014cf0`
- `0x180014e50`
- `0x180014fb0`
- `0x180015110`
- `0x180015270`
- `0x1800153d0`
- `0x1800154b0`
- `0x180015590`
- `0x180015670`
- `0x180015750`
- `0x180017698`
- `0x180017778`
- `0x180017858`
- `0x1800179b0`
- `0x180017a94`
- `0x180017b78`
- `0x180018c94`
- `0x18002454c`
- `0x18002a094`
- `0x18002a178`
- `0x18002a258`
- `0x18002a33c`
- `0x18002a41c`
- `0x18002a4fc`
- `0x18002a5dc`

## callees

- `0x18000bf74`
- `0x18000c644`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf9c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000bf9c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bff4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bff4`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD v6[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180041834
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180041858, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x18000bf74  mov     [rsp+arg_0], rbx
0x18000bf79  mov     [rsp+arg_8], rsi
0x18000bf7e  push    rdi
0x18000bf7f  sub     rsp, 30h
0x18000bf83  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000bf89  mov     esi, r8d
0x18000bf8c  mov     ebx, edx
0x18000bf8e  mov     rdi, rcx
0x18000bf91  test    eax, eax
0x18000bf93  jz      short loc_18000BFFA
0x18000bf95  lea     rcx, SRWLock; SRWLock
0x18000bf9c  call    cs:__imp_AcquireSRWLockExclusive
0x18000bfa2  mov     eax, cs:dword_180041834
0x18000bfa8  test    esi, esi
0x18000bfaa  jz      short loc_18000BFDC
0x18000bfac  cmp     esi, eax
0x18000bfae  jnz     short loc_18000BFDC
0x18000bfb0  mov     r8d, 10h; unsigned __int64
0x18000bfb6  mov     [rsp+38h+var_14], 0
0x18000bfbe  lea     rdx, [rsp+38h+var_18]; void *
0x18000bfc3  mov     [rsp+38h+var_18], ebx
0x18000bfc7  lea     rcx, qword_180041858; this
0x18000bfce  mov     [rsp+38h+var_10], rdi
0x18000bfd3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000bfd8  test    al, al
0x18000bfda  jnz     short loc_18000BFED
0x18000bfdc  neg     ebx
0x18000bfde  sbb     eax, eax
0x18000bfe0  and     eax, 83Ah
0x18000bfe5  add     eax, 0FFFFF7C1h
0x18000bfea  lock and [rdi], eax
0x18000bfed  lea     rcx, SRWLock; SRWLock
0x18000bff4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bffa  mov     rbx, [rsp+38h+arg_0]
0x18000bfff  mov     rsi, [rsp+38h+arg_8]
0x18000c004  add     rsp, 30h
0x18000c008  pop     rdi
0x18000c009  retn
```
