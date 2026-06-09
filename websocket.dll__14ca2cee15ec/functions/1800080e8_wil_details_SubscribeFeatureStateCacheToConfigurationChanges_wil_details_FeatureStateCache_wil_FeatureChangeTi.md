# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800080e8`
- end: `0x1800081b2`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005fdc`

## callees

- `0x180001f8c`
- `0x1800080e8`
- `0x180008d9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008114`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008114`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000819c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000819c`

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
    if ( a3
      && a3 == dword_1800122BC
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800122E0, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_1800122F0 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_1800122F0),
        Source,
        0x10u);
      Destination = (char *)Destination + 16;
    }
    else
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x1800080e8  mov     [rsp+arg_0], rbx
0x1800080ed  mov     [rsp+arg_8], rsi
0x1800080f2  push    rdi
0x1800080f3  sub     rsp, 30h
0x1800080f7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800080fd  mov     esi, r8d
0x180008100  mov     ebx, edx
0x180008102  mov     rdi, rcx
0x180008105  test    eax, eax
0x180008107  jz      loc_1800081A2
0x18000810d  lea     rcx, SRWLock; SRWLock
0x180008114  call    cs:__imp_AcquireSRWLockExclusive
0x18000811a  mov     eax, cs:dword_1800122BC
0x180008120  test    esi, esi
0x180008122  jz      short loc_180008184
0x180008124  cmp     esi, eax
0x180008126  jnz     short loc_180008184
0x180008128  mov     esi, 10h
0x18000812d  mov     [rsp+38h+var_14], 0
0x180008135  mov     edx, esi; unsigned __int64
0x180008137  mov     [rsp+38h+Source], ebx
0x18000813b  lea     rcx, qword_1800122E0; this
0x180008142  mov     [rsp+38h+var_10], rdi
0x180008147  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000814c  test    al, al
0x18000814e  jz      short loc_180008184
0x180008150  mov     rcx, cs:Destination; Destination
0x180008157  lea     r8, [rsp+38h+Source]; Source
0x18000815c  mov     rax, cs:qword_1800122F0
0x180008163  mov     r9d, esi; SourceSize
0x180008166  sub     rax, rcx
0x180008169  cmp     rcx, cs:qword_1800122F0
0x180008170  sbb     rdx, rdx
0x180008173  and     rdx, rax; DestinationSize
0x180008176  call    memcpy_s
0x18000817b  add     cs:Destination, rsi
0x180008182  jmp     short loc_180008195
0x180008184  neg     ebx
0x180008186  sbb     eax, eax
0x180008188  and     eax, 83Ah
0x18000818d  add     eax, 0FFFFF7C1h
0x180008192  lock and [rdi], eax
0x180008195  lea     rcx, SRWLock; SRWLock
0x18000819c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800081a2  mov     rbx, [rsp+38h+arg_0]
0x1800081a7  mov     rsi, [rsp+38h+arg_8]
0x1800081ac  add     rsp, 30h
0x1800081b0  pop     rdi
0x1800081b1  retn
```
