# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000a780`
- end: `0x18000a884`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007020`
- `0x1800078e8`

## callees

- `0x18000218a`
- `0x1800021f4`
- `0x18000a780`
- `0x18000b74c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a811`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a83b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a811`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a83b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a7ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a7ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a86e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a86e`

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
      || a3 != dword_18001584C
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_180015870, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_180015880 - (_QWORD)qword_180015878) & -(__int64)((unsigned __int64)qword_180015878 < qword_180015880);
    if ( qword_180015878 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_180015878 = v12;
LABEL_11:
        qword_180015878 = (char *)qword_180015878 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_180015878, 0, v8);
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
0x18000a780  mov     [rsp+arg_0], rbx
0x18000a785  mov     [rsp+arg_8], rsi
0x18000a78a  push    rdi
0x18000a78b  sub     rsp, 30h
0x18000a78f  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000a795  mov     esi, r8d
0x18000a798  mov     ebx, edx
0x18000a79a  mov     rdi, rcx
0x18000a79d  test    eax, eax
0x18000a79f  jz      loc_18000A874
0x18000a7a5  lea     rcx, SRWLock; SRWLock
0x18000a7ac  call    cs:__imp_AcquireSRWLockExclusive
0x18000a7b2  mov     eax, cs:dword_18001584C
0x18000a7b8  test    esi, esi
0x18000a7ba  jz      loc_18000A856
0x18000a7c0  cmp     esi, eax
0x18000a7c2  jnz     loc_18000A856
0x18000a7c8  mov     edx, 10h; unsigned __int64
0x18000a7cd  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000a7d5  lea     rcx, qword_180015870; this
0x18000a7dc  mov     dword ptr [rsp+38h+var_18], ebx
0x18000a7e0  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000a7e5  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000a7ea  test    al, al
0x18000a7ec  jz      short loc_18000A856
0x18000a7ee  mov     r9, cs:qword_180015878
0x18000a7f5  mov     rax, cs:qword_180015880
0x18000a7fc  sub     rax, r9
0x18000a7ff  cmp     r9, cs:qword_180015880
0x18000a806  sbb     r8, r8
0x18000a809  and     r8, rax; Size
0x18000a80c  test    r9, r9
0x18000a80f  jnz     short loc_18000A81F
0x18000a811  call    cs:__imp__o__errno
0x18000a817  mov     dword ptr [rax], 16h
0x18000a81d  jmp     short loc_18000A847
0x18000a81f  cmp     r8, 10h
0x18000a823  jb      short loc_18000A831
0x18000a825  movups  xmm0, [rsp+38h+var_18]
0x18000a82a  movdqu  xmmword ptr [r9], xmm0
0x18000a82f  jmp     short loc_18000A84C
0x18000a831  xor     edx, edx; Val
0x18000a833  mov     rcx, r9; void *
0x18000a836  call    memset_0
0x18000a83b  call    cs:__imp__o__errno
0x18000a841  mov     dword ptr [rax], 22h ; '"'
0x18000a847  call    _invalid_parameter_noinfo
0x18000a84c  add     cs:qword_180015878, 10h
0x18000a854  jmp     short loc_18000A867
0x18000a856  neg     ebx
0x18000a858  sbb     eax, eax
0x18000a85a  and     eax, 83Ah
0x18000a85f  add     eax, 0FFFFF7C1h
0x18000a864  lock and [rdi], eax
0x18000a867  lea     rcx, SRWLock; SRWLock
0x18000a86e  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a874  mov     rbx, [rsp+38h+arg_0]
0x18000a879  mov     rsi, [rsp+38h+arg_8]
0x18000a87e  add     rsp, 30h
0x18000a882  pop     rdi
0x18000a883  retn
```
