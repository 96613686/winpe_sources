# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b3d8`
- end: `0x18000b4dc`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006324`
- `0x1800064f4`
- `0x180006674`
- `0x180007684`
- `0x180011e5c`
- `0x180011f3c`
- `0x18001201c`
- `0x1800121f0`
- `0x1800122d0`
- `0x1800124a4`
- `0x180012624`
- `0x1800127f8`
- `0x1800129cc`
- `0x180012aac`
- `0x180012c80`
- `0x180012dfc`
- `0x180012f70`
- `0x180013d4c`

## callees

- `0x180002846`
- `0x1800028b4`
- `0x18000b3d8`
- `0x18000c82c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b469`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b493`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b469`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000b493`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b404`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b404`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b4c6`

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
      || a3 != dword_1800234A4
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800234C8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1800234D8 - (_QWORD)qword_1800234D0) & -(__int64)((unsigned __int64)qword_1800234D0 < qword_1800234D8);
    if ( qword_1800234D0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1800234D0 = v12;
LABEL_11:
        qword_1800234D0 = (char *)qword_1800234D0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1800234D0, 0, v8);
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
0x18000b3d8  mov     [rsp+arg_0], rbx
0x18000b3dd  mov     [rsp+arg_8], rsi
0x18000b3e2  push    rdi
0x18000b3e3  sub     rsp, 30h
0x18000b3e7  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b3ed  mov     esi, r8d
0x18000b3f0  mov     ebx, edx
0x18000b3f2  mov     rdi, rcx
0x18000b3f5  test    eax, eax
0x18000b3f7  jz      loc_18000B4CC
0x18000b3fd  lea     rcx, SRWLock; SRWLock
0x18000b404  call    cs:__imp_AcquireSRWLockExclusive
0x18000b40a  mov     eax, cs:dword_1800234A4
0x18000b410  test    esi, esi
0x18000b412  jz      loc_18000B4AE
0x18000b418  cmp     esi, eax
0x18000b41a  jnz     loc_18000B4AE
0x18000b420  mov     edx, 10h; unsigned __int64
0x18000b425  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000b42d  lea     rcx, qword_1800234C8; this
0x18000b434  mov     dword ptr [rsp+38h+var_18], ebx
0x18000b438  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000b43d  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b442  test    al, al
0x18000b444  jz      short loc_18000B4AE
0x18000b446  mov     r9, cs:qword_1800234D0
0x18000b44d  mov     rax, cs:qword_1800234D8
0x18000b454  sub     rax, r9
0x18000b457  cmp     r9, cs:qword_1800234D8
0x18000b45e  sbb     r8, r8
0x18000b461  and     r8, rax; Size
0x18000b464  test    r9, r9
0x18000b467  jnz     short loc_18000B477
0x18000b469  call    cs:__imp__o__errno
0x18000b46f  mov     dword ptr [rax], 16h
0x18000b475  jmp     short loc_18000B49F
0x18000b477  cmp     r8, 10h
0x18000b47b  jb      short loc_18000B489
0x18000b47d  movups  xmm0, [rsp+38h+var_18]
0x18000b482  movdqu  xmmword ptr [r9], xmm0
0x18000b487  jmp     short loc_18000B4A4
0x18000b489  xor     edx, edx; Val
0x18000b48b  mov     rcx, r9; void *
0x18000b48e  call    memset_0
0x18000b493  call    cs:__imp__o__errno
0x18000b499  mov     dword ptr [rax], 22h ; '"'
0x18000b49f  call    _invalid_parameter_noinfo
0x18000b4a4  add     cs:qword_1800234D0, 10h
0x18000b4ac  jmp     short loc_18000B4BF
0x18000b4ae  neg     ebx
0x18000b4b0  sbb     eax, eax
0x18000b4b2  and     eax, 83Ah
0x18000b4b7  add     eax, 0FFFFF7C1h
0x18000b4bc  lock and [rdi], eax
0x18000b4bf  lea     rcx, SRWLock; SRWLock
0x18000b4c6  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b4cc  mov     rbx, [rsp+38h+arg_0]
0x18000b4d1  mov     rsi, [rsp+38h+arg_8]
0x18000b4d6  add     rsp, 30h
0x18000b4da  pop     rdi
0x18000b4db  retn
```
