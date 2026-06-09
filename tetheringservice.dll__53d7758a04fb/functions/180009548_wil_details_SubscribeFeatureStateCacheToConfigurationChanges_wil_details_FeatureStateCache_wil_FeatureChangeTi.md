# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009548`
- end: `0x18000964c`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006e10`
- `0x18001708c`
- `0x180017260`
- `0x1800173d4`
- `0x180017548`
- `0x1800176bc`
- `0x18001779c`
- `0x18001787c`
- `0x18001795c`

## callees

- `0x180002ffa`
- `0x180003088`
- `0x180009548`
- `0x18000a35c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800095d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009603`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800095d9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180009603`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009636`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009636`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009574`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009574`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        unsigned int a2,
        int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  size_t v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int128 v11; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_1800419B4
      || (*(_QWORD *)&v11 = a2,
          *((_QWORD *)&v11 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800419D8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1800419E8 - (_QWORD)qword_1800419E0) & -(__int64)((unsigned __int64)qword_1800419E0 < qword_1800419E8);
    if ( qword_1800419E0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1800419E0 = v11;
LABEL_11:
        qword_1800419E0 = (char *)qword_1800419E0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1800419E0, 0, v8);
      *(_DWORD *)_o__errno(v10, v9) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v7, v6) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x180009548  mov     [rsp+arg_0], rbx
0x18000954d  mov     [rsp+arg_8], rsi
0x180009552  push    rdi
0x180009553  sub     rsp, 30h
0x180009557  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000955d  mov     esi, r8d
0x180009560  mov     ebx, edx
0x180009562  mov     rdi, rcx
0x180009565  test    eax, eax
0x180009567  jz      loc_18000963C
0x18000956d  lea     rcx, SRWLock; SRWLock
0x180009574  call    cs:__imp_AcquireSRWLockExclusive
0x18000957a  mov     eax, cs:dword_1800419B4
0x180009580  test    esi, esi
0x180009582  jz      loc_18000961E
0x180009588  cmp     esi, eax
0x18000958a  jnz     loc_18000961E
0x180009590  mov     edx, 10h; unsigned __int64
0x180009595  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000959d  lea     rcx, qword_1800419D8; this
0x1800095a4  mov     dword ptr [rsp+38h+var_18], ebx
0x1800095a8  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800095ad  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800095b2  test    al, al
0x1800095b4  jz      short loc_18000961E
0x1800095b6  mov     r9, cs:qword_1800419E0
0x1800095bd  mov     rax, cs:qword_1800419E8
0x1800095c4  sub     rax, r9
0x1800095c7  cmp     r9, cs:qword_1800419E8
0x1800095ce  sbb     r8, r8
0x1800095d1  and     r8, rax; Size
0x1800095d4  test    r9, r9
0x1800095d7  jnz     short loc_1800095E7
0x1800095d9  call    cs:__imp__o__errno
0x1800095df  mov     dword ptr [rax], 16h
0x1800095e5  jmp     short loc_18000960F
0x1800095e7  cmp     r8, 10h
0x1800095eb  jb      short loc_1800095F9
0x1800095ed  movups  xmm0, [rsp+38h+var_18]
0x1800095f2  movdqu  xmmword ptr [r9], xmm0
0x1800095f7  jmp     short loc_180009614
0x1800095f9  xor     edx, edx; Val
0x1800095fb  mov     rcx, r9; void *
0x1800095fe  call    memset_0
0x180009603  call    cs:__imp__o__errno
0x180009609  mov     dword ptr [rax], 22h ; '"'
0x18000960f  call    _invalid_parameter_noinfo
0x180009614  add     cs:qword_1800419E0, 10h
0x18000961c  jmp     short loc_18000962F
0x18000961e  neg     ebx
0x180009620  sbb     eax, eax
0x180009622  and     eax, 83Ah
0x180009627  add     eax, 0FFFFF7C1h
0x18000962c  lock and [rdi], eax
0x18000962f  lea     rcx, SRWLock; SRWLock
0x180009636  call    cs:__imp_ReleaseSRWLockExclusive
0x18000963c  mov     rbx, [rsp+38h+arg_0]
0x180009641  mov     rsi, [rsp+38h+arg_8]
0x180009646  add     rsp, 30h
0x18000964a  pop     rdi
0x18000964b  retn
```
