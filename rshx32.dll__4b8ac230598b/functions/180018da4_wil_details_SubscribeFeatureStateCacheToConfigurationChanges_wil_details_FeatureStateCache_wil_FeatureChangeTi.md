# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180018da4`
- end: `0x180018e6f`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `15`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016cac`
- `0x180016e80`
- `0x180016ff4`
- `0x180017168`
- `0x1800172dc`
- `0x180017450`
- `0x1800175c4`
- `0x180017738`
- `0x180017818`
- `0x1800178f8`
- `0x1800179d8`
- `0x180017ab8`
- `0x180017b98`
- `0x180017c78`
- `0x18001af30`

## callees

- `0x180018da4`
- `0x180019328`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180018e32`
- `msvcrt!memcpy_s` at `0x180018e32`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018e59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018e59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018dd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018dd0`

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
      && a3 == dword_180028C54
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180028C78, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_180028C88 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_180028C88),
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
0x180018da4  mov     [rsp+arg_0], rbx
0x180018da9  mov     [rsp+arg_8], rsi
0x180018dae  push    rdi
0x180018daf  sub     rsp, 30h
0x180018db3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180018db9  mov     esi, r8d
0x180018dbc  mov     ebx, edx
0x180018dbe  mov     rdi, rcx
0x180018dc1  test    eax, eax
0x180018dc3  jz      loc_180018E5F
0x180018dc9  lea     rcx, SRWLock; SRWLock
0x180018dd0  call    cs:__imp_AcquireSRWLockExclusive
0x180018dd6  mov     eax, cs:dword_180028C54
0x180018ddc  test    esi, esi
0x180018dde  jz      short loc_180018E41
0x180018de0  cmp     esi, eax
0x180018de2  jnz     short loc_180018E41
0x180018de4  mov     esi, 10h
0x180018de9  mov     [rsp+38h+var_14], 0
0x180018df1  mov     edx, esi; unsigned __int64
0x180018df3  mov     [rsp+38h+Source], ebx
0x180018df7  lea     rcx, qword_180028C78; this
0x180018dfe  mov     [rsp+38h+var_10], rdi
0x180018e03  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180018e08  test    al, al
0x180018e0a  jz      short loc_180018E41
0x180018e0c  mov     rcx, cs:Destination; Destination
0x180018e13  lea     r8, [rsp+38h+Source]; Source
0x180018e18  mov     rax, cs:qword_180028C88
0x180018e1f  mov     r9d, esi; SourceSize
0x180018e22  sub     rax, rcx
0x180018e25  cmp     rcx, cs:qword_180028C88
0x180018e2c  sbb     rdx, rdx
0x180018e2f  and     rdx, rax; DestinationSize
0x180018e32  call    cs:__imp_memcpy_s
0x180018e38  add     cs:Destination, rsi
0x180018e3f  jmp     short loc_180018E52
0x180018e41  neg     ebx
0x180018e43  sbb     eax, eax
0x180018e45  and     eax, 83Ah
0x180018e4a  add     eax, 0FFFFF7C1h
0x180018e4f  lock and [rdi], eax
0x180018e52  lea     rcx, SRWLock; SRWLock
0x180018e59  call    cs:__imp_ReleaseSRWLockExclusive
0x180018e5f  mov     rbx, [rsp+38h+arg_0]
0x180018e64  mov     rsi, [rsp+38h+arg_8]
0x180018e69  add     rsp, 30h
0x180018e6d  pop     rdi
0x180018e6e  retn
```
