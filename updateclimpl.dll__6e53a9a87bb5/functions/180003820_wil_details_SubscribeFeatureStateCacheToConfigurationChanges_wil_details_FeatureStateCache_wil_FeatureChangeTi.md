# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180003820`
- end: `0x1800038af`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `143`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180002214`
- `0x1800026f8`
- `0x1800029dc`

## callees

- `0x180003744`
- `0x180003820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003847`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003847`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003899`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003899`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  unsigned __int64 v6; // r8
  _DWORD v7[2]; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-10h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_18001F1EC
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18001F220, v7, v6)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180003820  mov     [rsp+arg_8], rbx
0x180003825  mov     [rsp+arg_10], rsi
0x18000382a  push    rdi
0x18000382b  sub     rsp, 30h
0x18000382f  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180003836  mov     esi, r8d
0x180003839  mov     ebx, edx
0x18000383b  mov     rdi, rcx
0x18000383e  jz      short loc_18000389F
0x180003840  lea     rcx, SRWLock; SRWLock
0x180003847  call    cs:__imp_AcquireSRWLockExclusive
0x18000384d  mov     eax, cs:dword_18001F1EC
0x180003853  test    esi, esi
0x180003855  jz      short loc_180003881
0x180003857  cmp     esi, eax
0x180003859  jnz     short loc_180003881
0x18000385b  lea     rdx, [rsp+38h+var_18]; void *
0x180003860  mov     [rsp+38h+var_14], 0
0x180003868  lea     rcx, qword_18001F220; this
0x18000386f  mov     [rsp+38h+var_18], ebx
0x180003873  mov     [rsp+38h+var_10], rdi
0x180003878  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000387d  test    al, al
0x18000387f  jnz     short loc_180003892
0x180003881  neg     ebx
0x180003883  sbb     eax, eax
0x180003885  and     eax, 83Ah
0x18000388a  add     eax, 0FFFFF7C1h
0x18000388f  lock and [rdi], eax
0x180003892  lea     rcx, SRWLock; SRWLock
0x180003899  call    cs:__imp_ReleaseSRWLockExclusive
0x18000389f  mov     rbx, [rsp+38h+arg_8]
0x1800038a4  mov     rsi, [rsp+38h+arg_10]
0x1800038a9  add     rsp, 30h
0x1800038ad  pop     rdi
0x1800038ae  retn
```
