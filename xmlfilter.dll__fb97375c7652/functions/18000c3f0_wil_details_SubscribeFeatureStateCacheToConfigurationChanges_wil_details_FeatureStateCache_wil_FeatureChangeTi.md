# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000c3f0`
- end: `0x18000c4f4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `void __fastcall(volatile signed __int32 *, unsigned int, int)`
- caller_count: `13`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800064d4`
- `0x1800066a8`
- `0x18000681c`
- `0x180006990`
- `0x180006b04`
- `0x180006c78`
- `0x180006dec`
- `0x180006ecc`
- `0x180006fac`
- `0x18000708c`
- `0x18000716c`
- `0x18000724c`
- `0x180008e50`

## callees

- `0x180002ae2`
- `0x180002b38`
- `0x18000c3f0`
- `0x18000d7e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c481`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4ab`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c481`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c4ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c4de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c4de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c41c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c41c`

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
      || a3 != dword_180021734
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180021758, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180021768 - (_QWORD)qword_180021760) & -(__int64)((unsigned __int64)qword_180021760 < qword_180021768);
    if ( qword_180021760 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180021760 = v12;
LABEL_11:
        qword_180021760 = (char *)qword_180021760 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180021760, 0, v8);
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
0x18000c3f0  mov     [rsp+arg_0], rbx
0x18000c3f5  mov     [rsp+arg_8], rsi
0x18000c3fa  push    rdi
0x18000c3fb  sub     rsp, 30h
0x18000c3ff  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000c405  mov     esi, r8d
0x18000c408  mov     ebx, edx
0x18000c40a  mov     rdi, rcx
0x18000c40d  test    eax, eax
0x18000c40f  jz      loc_18000C4E4
0x18000c415  lea     rcx, SRWLock; SRWLock
0x18000c41c  call    cs:__imp_AcquireSRWLockExclusive
0x18000c422  mov     eax, cs:dword_180021734
0x18000c428  test    esi, esi
0x18000c42a  jz      loc_18000C4C6
0x18000c430  cmp     esi, eax
0x18000c432  jnz     loc_18000C4C6
0x18000c438  mov     edx, 10h; unsigned __int64
0x18000c43d  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000c445  lea     rcx, qword_180021758; this
0x18000c44c  mov     dword ptr [rsp+38h+var_18], ebx
0x18000c450  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000c455  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000c45a  test    al, al
0x18000c45c  jz      short loc_18000C4C6
0x18000c45e  mov     r9, cs:qword_180021760
0x18000c465  mov     rax, cs:qword_180021768
0x18000c46c  sub     rax, r9
0x18000c46f  cmp     r9, cs:qword_180021768
0x18000c476  sbb     r8, r8
0x18000c479  and     r8, rax; Size
0x18000c47c  test    r9, r9
0x18000c47f  jnz     short loc_18000C48F
0x18000c481  call    cs:__imp__o__errno
0x18000c487  mov     dword ptr [rax], 16h
0x18000c48d  jmp     short loc_18000C4B7
0x18000c48f  cmp     r8, 10h
0x18000c493  jb      short loc_18000C4A1
0x18000c495  movups  xmm0, [rsp+38h+var_18]
0x18000c49a  movdqu  xmmword ptr [r9], xmm0
0x18000c49f  jmp     short loc_18000C4BC
0x18000c4a1  xor     edx, edx; Val
0x18000c4a3  mov     rcx, r9; void *
0x18000c4a6  call    memset_0
0x18000c4ab  call    cs:__imp__o__errno
0x18000c4b1  mov     dword ptr [rax], 22h ; '"'
0x18000c4b7  call    _invalid_parameter_noinfo
0x18000c4bc  add     cs:qword_180021760, 10h
0x18000c4c4  jmp     short loc_18000C4D7
0x18000c4c6  neg     ebx
0x18000c4c8  sbb     eax, eax
0x18000c4ca  and     eax, 83Ah
0x18000c4cf  add     eax, 0FFFFF7C1h
0x18000c4d4  lock and [rdi], eax
0x18000c4d7  lea     rcx, SRWLock; SRWLock
0x18000c4de  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c4e4  mov     rbx, [rsp+38h+arg_0]
0x18000c4e9  mov     rsi, [rsp+38h+arg_8]
0x18000c4ee  add     rsp, 30h
0x18000c4f2  pop     rdi
0x18000c4f3  retn
```
