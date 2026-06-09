# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000cf7c`
- end: `0x18000d080`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000abb8`
- `0x180026a90`
- `0x180026c10`
- `0x180026cf0`

## callees

- `0x18000355e`
- `0x1800035e8`
- `0x18000cf7c`
- `0x18001171c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d00d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d037`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d00d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000d037`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cfa8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cfa8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d06a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d06a`

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
  __int64 v11; // r8
  __int128 v12; // [rsp+20h] [rbp-18h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !a3
      || a3 != dword_180047434
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&unk_180047458, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180047468 - (_QWORD)qword_180047460) & -(__int64)((unsigned __int64)qword_180047460 < qword_180047468);
    if ( qword_180047460 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180047460 = v12;
LABEL_11:
        qword_180047460 = (char *)qword_180047460 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180047460, 0, v8);
      *(_DWORD *)_o__errno(v10, v9, v11) = 34;
    }
    else
    {
      *(_DWORD *)_o__errno(v7, v6, v8) = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x18000cf7c  mov     [rsp+arg_0], rbx
0x18000cf81  mov     [rsp+arg_8], rsi
0x18000cf86  push    rdi
0x18000cf87  sub     rsp, 30h
0x18000cf8b  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000cf91  mov     esi, r8d
0x18000cf94  mov     ebx, edx
0x18000cf96  mov     rdi, rcx
0x18000cf99  test    eax, eax
0x18000cf9b  jz      loc_18000D070
0x18000cfa1  lea     rcx, SRWLock; SRWLock
0x18000cfa8  call    cs:__imp_AcquireSRWLockExclusive
0x18000cfae  mov     eax, cs:dword_180047434
0x18000cfb4  test    esi, esi
0x18000cfb6  jz      loc_18000D052
0x18000cfbc  cmp     esi, eax
0x18000cfbe  jnz     loc_18000D052
0x18000cfc4  mov     edx, 10h; unsigned __int64
0x18000cfc9  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000cfd1  lea     rcx, unk_180047458; this
0x18000cfd8  mov     dword ptr [rsp+38h+var_18], ebx
0x18000cfdc  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000cfe1  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000cfe6  test    al, al
0x18000cfe8  jz      short loc_18000D052
0x18000cfea  mov     r9, cs:qword_180047460
0x18000cff1  mov     rax, cs:qword_180047468
0x18000cff8  sub     rax, r9
0x18000cffb  cmp     r9, cs:qword_180047468
0x18000d002  sbb     r8, r8
0x18000d005  and     r8, rax; Size
0x18000d008  test    r9, r9
0x18000d00b  jnz     short loc_18000D01B
0x18000d00d  call    cs:__imp__o__errno
0x18000d013  mov     dword ptr [rax], 16h
0x18000d019  jmp     short loc_18000D043
0x18000d01b  cmp     r8, 10h
0x18000d01f  jb      short loc_18000D02D
0x18000d021  movups  xmm0, [rsp+38h+var_18]
0x18000d026  movdqu  xmmword ptr [r9], xmm0
0x18000d02b  jmp     short loc_18000D048
0x18000d02d  xor     edx, edx; Val
0x18000d02f  mov     rcx, r9; void *
0x18000d032  call    memset_0
0x18000d037  call    cs:__imp__o__errno
0x18000d03d  mov     dword ptr [rax], 22h ; '"'
0x18000d043  call    _invalid_parameter_noinfo
0x18000d048  add     cs:qword_180047460, 10h
0x18000d050  jmp     short loc_18000D063
0x18000d052  neg     ebx
0x18000d054  sbb     eax, eax
0x18000d056  and     eax, 83Ah
0x18000d05b  add     eax, 0FFFFF7C1h
0x18000d060  lock and [rdi], eax
0x18000d063  lea     rcx, SRWLock; SRWLock
0x18000d06a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d070  mov     rbx, [rsp+38h+arg_0]
0x18000d075  mov     rsi, [rsp+38h+arg_8]
0x18000d07a  add     rsp, 30h
0x18000d07e  pop     rdi
0x18000d07f  retn
```
