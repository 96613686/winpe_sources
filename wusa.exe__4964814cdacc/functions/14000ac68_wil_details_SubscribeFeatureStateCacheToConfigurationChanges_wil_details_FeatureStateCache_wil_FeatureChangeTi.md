# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000ac68`
- end: `0x14000ad33`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140006df4`
- `0x1400086fc`

## callees

- `0x14000ac68`
- `0x14000c16c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ac94`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ac94`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ad1d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ad1d`
- `msvcrt!memcpy_s` at `0x14000acf6`
- `msvcrt!memcpy_s` at `0x14000acf6`

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
      && a3 == dword_1400203EC
      && (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_140020410, 0x10u)) )
    {
      memcpy_s(
        Destination,
        (qword_140020420 - (_QWORD)Destination) & -(__int64)((unsigned __int64)Destination < qword_140020420),
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
0x14000ac68  mov     [rsp+arg_0], rbx
0x14000ac6d  mov     [rsp+arg_8], rsi
0x14000ac72  push    rdi
0x14000ac73  sub     rsp, 30h
0x14000ac77  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000ac7d  mov     esi, r8d
0x14000ac80  mov     ebx, edx
0x14000ac82  mov     rdi, rcx
0x14000ac85  test    eax, eax
0x14000ac87  jz      loc_14000AD23
0x14000ac8d  lea     rcx, SRWLock; SRWLock
0x14000ac94  call    cs:__imp_AcquireSRWLockExclusive
0x14000ac9a  mov     eax, cs:dword_1400203EC
0x14000aca0  test    esi, esi
0x14000aca2  jz      short loc_14000AD05
0x14000aca4  cmp     esi, eax
0x14000aca6  jnz     short loc_14000AD05
0x14000aca8  mov     esi, 10h
0x14000acad  mov     [rsp+38h+var_14], 0
0x14000acb5  mov     edx, esi; unsigned __int64
0x14000acb7  mov     [rsp+38h+Source], ebx
0x14000acbb  lea     rcx, qword_140020410; this
0x14000acc2  mov     [rsp+38h+var_10], rdi
0x14000acc7  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000accc  test    al, al
0x14000acce  jz      short loc_14000AD05
0x14000acd0  mov     rcx, cs:Destination; Destination
0x14000acd7  lea     r8, [rsp+38h+Source]; Source
0x14000acdc  mov     rax, cs:qword_140020420
0x14000ace3  mov     r9d, esi; SourceSize
0x14000ace6  sub     rax, rcx
0x14000ace9  cmp     rcx, cs:qword_140020420
0x14000acf0  sbb     rdx, rdx
0x14000acf3  and     rdx, rax; DestinationSize
0x14000acf6  call    cs:__imp_memcpy_s
0x14000acfc  add     cs:Destination, rsi
0x14000ad03  jmp     short loc_14000AD16
0x14000ad05  neg     ebx
0x14000ad07  sbb     eax, eax
0x14000ad09  and     eax, 83Ah
0x14000ad0e  add     eax, 0FFFFF7C1h
0x14000ad13  lock and [rdi], eax
0x14000ad16  lea     rcx, SRWLock; SRWLock
0x14000ad1d  call    cs:__imp_ReleaseSRWLockExclusive
0x14000ad23  mov     rbx, [rsp+38h+arg_0]
0x14000ad28  mov     rsi, [rsp+38h+arg_8]
0x14000ad2d  add     rsp, 30h
0x14000ad31  pop     rdi
0x14000ad32  retn
```
