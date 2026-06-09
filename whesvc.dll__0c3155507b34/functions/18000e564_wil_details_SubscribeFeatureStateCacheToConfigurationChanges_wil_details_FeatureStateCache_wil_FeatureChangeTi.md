# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000e564`
- end: `0x18000e668`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `44`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000cee8`
- `0x18001267c`
- `0x180012850`
- `0x180012a24`
- `0x180012b98`
- `0x180012d0c`
- `0x180012e80`
- `0x180012ff4`
- `0x180013168`
- `0x1800132dc`
- `0x1800133bc`
- `0x18001349c`
- `0x18001357c`
- `0x18001365c`
- `0x18001373c`
- `0x18001381c`
- `0x18001cf78`
- `0x18001d148`
- `0x18001d31c`
- `0x18001d4f0`
- `0x18001d6c4`
- `0x18001d898`
- `0x18001da6c`
- `0x18001dc40`
- `0x18001de14`
- `0x18001dfe8`
- `0x18001e1b8`
- `0x18001e38c`
- `0x18001e560`
- `0x18001e734`
- `0x18001e904`
- `0x18001ead4`
- `0x18001eca8`
- `0x18001ee7c`
- `0x18001f050`
- `0x18001f1c4`
- `0x18001f344`
- `0x18001f518`
- `0x18001f5f8`
- `0x18001f7c8`
- `0x18001f99c`
- `0x18001fb70`
- `0x18001fc50`
- `0x18001fe20`

## callees

- `0x180003d0a`
- `0x180003da4`
- `0x18000e564`
- `0x18000ee54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e5f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e61f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e5f5`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000e61f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e590`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000e590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e652`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e652`

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
      || a3 != dword_1800346C4
      || (*(_QWORD *)&v12 = a2,
          *((_QWORD *)&v12 + 1) = a1,
          !wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)&qword_1800346E8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
      goto LABEL_13;
    }
    v8 = (qword_1800346F8 - (_QWORD)qword_1800346F0) & -(__int64)((unsigned __int64)qword_1800346F0 < qword_1800346F8);
    if ( qword_1800346F0 )
    {
      if ( v8 >= 0x10 )
      {
        *(_OWORD *)qword_1800346F0 = v12;
LABEL_11:
        qword_1800346F0 = (char *)qword_1800346F0 + 16;
LABEL_13:
        ReleaseSRWLockExclusive(&SRWLock);
        return;
      }
      memset_0(qword_1800346F0, 0, v8);
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
0x18000e564  mov     [rsp+arg_0], rbx
0x18000e569  mov     [rsp+arg_8], rsi
0x18000e56e  push    rdi
0x18000e56f  sub     rsp, 30h
0x18000e573  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000e579  mov     esi, r8d
0x18000e57c  mov     ebx, edx
0x18000e57e  mov     rdi, rcx
0x18000e581  test    eax, eax
0x18000e583  jz      loc_18000E658
0x18000e589  lea     rcx, SRWLock; SRWLock
0x18000e590  call    cs:__imp_AcquireSRWLockExclusive
0x18000e596  mov     eax, cs:dword_1800346C4
0x18000e59c  test    esi, esi
0x18000e59e  jz      loc_18000E63A
0x18000e5a4  cmp     esi, eax
0x18000e5a6  jnz     loc_18000E63A
0x18000e5ac  mov     edx, 10h; unsigned __int64
0x18000e5b1  mov     dword ptr [rsp+38h+var_18+4], 0
0x18000e5b9  lea     rcx, qword_1800346E8; this
0x18000e5c0  mov     dword ptr [rsp+38h+var_18], ebx
0x18000e5c4  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18000e5c9  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000e5ce  test    al, al
0x18000e5d0  jz      short loc_18000E63A
0x18000e5d2  mov     r9, cs:qword_1800346F0
0x18000e5d9  mov     rax, cs:qword_1800346F8
0x18000e5e0  sub     rax, r9
0x18000e5e3  cmp     r9, cs:qword_1800346F8
0x18000e5ea  sbb     r8, r8
0x18000e5ed  and     r8, rax; Size
0x18000e5f0  test    r9, r9
0x18000e5f3  jnz     short loc_18000E603
0x18000e5f5  call    cs:__imp__o__errno
0x18000e5fb  mov     dword ptr [rax], 16h
0x18000e601  jmp     short loc_18000E62B
0x18000e603  cmp     r8, 10h
0x18000e607  jb      short loc_18000E615
0x18000e609  movups  xmm0, [rsp+38h+var_18]
0x18000e60e  movdqu  xmmword ptr [r9], xmm0
0x18000e613  jmp     short loc_18000E630
0x18000e615  xor     edx, edx; Val
0x18000e617  mov     rcx, r9; void *
0x18000e61a  call    memset_0
0x18000e61f  call    cs:__imp__o__errno
0x18000e625  mov     dword ptr [rax], 22h ; '"'
0x18000e62b  call    _invalid_parameter_noinfo
0x18000e630  add     cs:qword_1800346F0, 10h
0x18000e638  jmp     short loc_18000E64B
0x18000e63a  neg     ebx
0x18000e63c  sbb     eax, eax
0x18000e63e  and     eax, 83Ah
0x18000e643  add     eax, 0FFFFF7C1h
0x18000e648  lock and [rdi], eax
0x18000e64b  lea     rcx, SRWLock; SRWLock
0x18000e652  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e658  mov     rbx, [rsp+38h+arg_0]
0x18000e65d  mov     rsi, [rsp+38h+arg_8]
0x18000e662  add     rsp, 30h
0x18000e666  pop     rdi
0x18000e667  retn
```
