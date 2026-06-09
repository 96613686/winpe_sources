# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x14000b9b0`
- end: `0x14000bab4`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140009b0c`
- `0x140009bec`
- `0x140009eb4`
- `0x14000f780`

## callees

- `0x1400027fe`
- `0x1400028b8`
- `0x14000b9b0`
- `0x14000c354`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b9dc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b9dc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ba9e`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000ba9e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ba41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ba6b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ba41`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000ba6b`

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
      || a3 != dword_140021474
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_140021498, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1400214A8 - (_QWORD)qword_1400214A0) & -(__int64)((unsigned __int64)qword_1400214A0 < qword_1400214A8);
    if ( qword_1400214A0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1400214A0 = v12;
LABEL_11:
        qword_1400214A0 = (char *)qword_1400214A0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1400214A0, 0, v8);
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
0x14000b9b0  mov     [rsp+arg_0], rbx
0x14000b9b5  mov     [rsp+arg_8], rsi
0x14000b9ba  push    rdi
0x14000b9bb  sub     rsp, 30h
0x14000b9bf  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000b9c5  mov     esi, r8d
0x14000b9c8  mov     ebx, edx
0x14000b9ca  mov     rdi, rcx
0x14000b9cd  test    eax, eax
0x14000b9cf  jz      loc_14000BAA4
0x14000b9d5  lea     rcx, SRWLock; SRWLock
0x14000b9dc  call    cs:__imp_AcquireSRWLockExclusive
0x14000b9e2  mov     eax, cs:dword_140021474
0x14000b9e8  test    esi, esi
0x14000b9ea  jz      loc_14000BA86
0x14000b9f0  cmp     esi, eax
0x14000b9f2  jnz     loc_14000BA86
0x14000b9f8  mov     edx, 10h; unsigned __int64
0x14000b9fd  mov     dword ptr [rsp+38h+var_18+4], 0
0x14000ba05  lea     rcx, qword_140021498; this
0x14000ba0c  mov     dword ptr [rsp+38h+var_18], ebx
0x14000ba10  mov     qword ptr [rsp+38h+var_18+8], rdi
0x14000ba15  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x14000ba1a  test    al, al
0x14000ba1c  jz      short loc_14000BA86
0x14000ba1e  mov     r9, cs:qword_1400214A0
0x14000ba25  mov     rax, cs:qword_1400214A8
0x14000ba2c  sub     rax, r9
0x14000ba2f  cmp     r9, cs:qword_1400214A8
0x14000ba36  sbb     r8, r8
0x14000ba39  and     r8, rax; Size
0x14000ba3c  test    r9, r9
0x14000ba3f  jnz     short loc_14000BA4F
0x14000ba41  call    cs:__imp__o__errno
0x14000ba47  mov     dword ptr [rax], 16h
0x14000ba4d  jmp     short loc_14000BA77
0x14000ba4f  cmp     r8, 10h
0x14000ba53  jb      short loc_14000BA61
0x14000ba55  movups  xmm0, [rsp+38h+var_18]
0x14000ba5a  movdqu  xmmword ptr [r9], xmm0
0x14000ba5f  jmp     short loc_14000BA7C
0x14000ba61  xor     edx, edx; Val
0x14000ba63  mov     rcx, r9; void *
0x14000ba66  call    memset_0
0x14000ba6b  call    cs:__imp__o__errno
0x14000ba71  mov     dword ptr [rax], 22h ; '"'
0x14000ba77  call    _invalid_parameter_noinfo
0x14000ba7c  add     cs:qword_1400214A0, 10h
0x14000ba84  jmp     short loc_14000BA97
0x14000ba86  neg     ebx
0x14000ba88  sbb     eax, eax
0x14000ba8a  and     eax, 83Ah
0x14000ba8f  add     eax, 0FFFFF7C1h
0x14000ba94  lock and [rdi], eax
0x14000ba97  lea     rcx, SRWLock; SRWLock
0x14000ba9e  call    cs:__imp_ReleaseSRWLockExclusive
0x14000baa4  mov     rbx, [rsp+38h+arg_0]
0x14000baa9  mov     rsi, [rsp+38h+arg_8]
0x14000baae  add     rsp, 30h
0x14000bab2  pop     rdi
0x14000bab3  retn
```
