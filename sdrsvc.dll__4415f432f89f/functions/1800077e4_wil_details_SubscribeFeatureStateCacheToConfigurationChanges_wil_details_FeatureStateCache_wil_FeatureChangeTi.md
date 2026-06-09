# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800077e4`
- end: `0x1800078af`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005640`

## callees

- `0x1800077e4`
- `0x18000847c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180007872`
- `msvcrt!memcpy_s` at `0x180007872`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007810`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007810`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007899`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007899`

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
      && a3 == dword_18002D87C
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_18002D8A0, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_18002D8B0 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_18002D8B0),
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
0x1800077e4  mov     [rsp+arg_0], rbx
0x1800077e9  mov     [rsp+arg_8], rsi
0x1800077ee  push    rdi
0x1800077ef  sub     rsp, 30h
0x1800077f3  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800077f9  mov     esi, r8d
0x1800077fc  mov     ebx, edx
0x1800077fe  mov     rdi, rcx
0x180007801  test    eax, eax
0x180007803  jz      loc_18000789F
0x180007809  lea     rcx, SRWLock; SRWLock
0x180007810  call    cs:__imp_AcquireSRWLockExclusive
0x180007816  mov     eax, cs:dword_18002D87C
0x18000781c  test    esi, esi
0x18000781e  jz      short loc_180007881
0x180007820  cmp     esi, eax
0x180007822  jnz     short loc_180007881
0x180007824  mov     esi, 10h
0x180007829  mov     [rsp+38h+var_14], 0
0x180007831  mov     edx, esi; unsigned __int64
0x180007833  mov     [rsp+38h+Source], ebx
0x180007837  lea     rcx, qword_18002D8A0; this
0x18000783e  mov     [rsp+38h+var_10], rdi
0x180007843  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007848  test    al, al
0x18000784a  jz      short loc_180007881
0x18000784c  mov     rcx, cs:Destination; Destination
0x180007853  lea     r8, [rsp+38h+Source]; Source
0x180007858  mov     rax, cs:qword_18002D8B0
0x18000785f  mov     r9d, esi; SourceSize
0x180007862  sub     rax, rcx
0x180007865  cmp     rcx, cs:qword_18002D8B0
0x18000786c  sbb     rdx, rdx
0x18000786f  and     rdx, rax; DestinationSize
0x180007872  call    cs:__imp_memcpy_s
0x180007878  add     cs:Destination, rsi
0x18000787f  jmp     short loc_180007892
0x180007881  neg     ebx
0x180007883  sbb     eax, eax
0x180007885  and     eax, 83Ah
0x18000788a  add     eax, 0FFFFF7C1h
0x18000788f  lock and [rdi], eax
0x180007892  lea     rcx, SRWLock; SRWLock
0x180007899  call    cs:__imp_ReleaseSRWLockExclusive
0x18000789f  mov     rbx, [rsp+38h+arg_0]
0x1800078a4  mov     rsi, [rsp+38h+arg_8]
0x1800078a9  add     rsp, 30h
0x1800078ad  pop     rdi
0x1800078ae  retn
```
