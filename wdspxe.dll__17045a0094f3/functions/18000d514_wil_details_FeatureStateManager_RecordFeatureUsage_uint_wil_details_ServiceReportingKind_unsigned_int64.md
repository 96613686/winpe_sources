# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000d514`
- end: `0x18000d656`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180010600`

## callees

- `0x18000b0d8`
- `0x18000b1b8`
- `0x18000d514`
- `0x18000d69c`
- `0x18000d6d4`
- `0x18000d70c`
- `0x180013010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000d581`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000d614`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000d581`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000d614`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d5d5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d630`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d5d5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d630`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::RecordFeatureUsage(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4)
{
  __int64 v8; // rdi
  int v9; // eax
  char v10; // bl

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)a1) )
    return;
  v8 = *(_QWORD *)(a1 + 24);
  if ( a3 == 254 )
  {
    wil::details_abi::FeatureStateData::RecordUsage(*(PSRWLOCK *)(a1 + 24));
LABEL_17:
    if ( !wil::details::g_processShutdownInProgress
      && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress()) )
    {
      AcquireSRWLockExclusive((PSRWLOCK)(a1 + 32));
      wil::details::FeatureStateManager::EnsureTimerUnderLock((struct _TP_TIMER **)a1);
      if ( a1 != -32 )
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
    }
    return;
  }
  if ( a3 < 0xC8 || (int)a3 >= 256 && a3 < 0x200 )
  {
    if ( (AcquireSRWLockExclusive(*(PSRWLOCK *)(a1 + 24)), a3 <= 7) && (v9 = 204, _bittest(&v9, a3)) || a3 - 256 <= 0x7F )
    {
      wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(v8 + 8, a3, a2);
      v10 = *(_BYTE *)(v8 + 64);
    }
    else
    {
      v10 = wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
              v8 + 72,
              a3,
              a2,
              a4);
    }
    if ( v8 )
      ReleaseSRWLockExclusive((PSRWLOCK)v8);
    if ( v10 )
      goto LABEL_17;
  }
}

```

## disassembly

```asm
0x18000d514  mov     [rsp+arg_0], rbx
0x18000d519  mov     [rsp+arg_8], rbp
0x18000d51e  mov     [rsp+arg_10], rsi
0x18000d523  push    rdi
0x18000d524  push    r14
0x18000d526  push    r15
0x18000d528  sub     rsp, 20h
0x18000d52c  cmp     byte ptr [rcx], 0
0x18000d52f  mov     r15, r9
0x18000d532  mov     ebx, r8d
0x18000d535  mov     r14d, edx
0x18000d538  mov     rsi, rcx
0x18000d53b  jz      loc_18000D63C
0x18000d541  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000d546  test    al, al
0x18000d548  jz      loc_18000D63C
0x18000d54e  mov     rdi, [rsi+18h]
0x18000d552  cmp     ebx, 0FEh
0x18000d558  jz      loc_18000D5E7
0x18000d55e  cmp     ebx, 0C8h
0x18000d564  jb      short loc_18000D57E
0x18000d566  cmp     ebx, 100h
0x18000d56c  jl      loc_18000D63C
0x18000d572  cmp     ebx, 200h
0x18000d578  jnb     loc_18000D63C
0x18000d57e  mov     rcx, rdi; SRWLock
0x18000d581  call    cs:__imp_AcquireSRWLockExclusive
0x18000d588  nop     dword ptr [rax+rax+00h]
0x18000d58d  cmp     ebx, 7
0x18000d590  ja      short loc_18000D59C
0x18000d592  mov     eax, 0CCh
0x18000d597  bt      eax, ebx
0x18000d59a  jb      short loc_18000D5BC
0x18000d59c  lea     eax, [rbx-100h]
0x18000d5a2  cmp     eax, 7Fh
0x18000d5a5  jbe     short loc_18000D5BC
0x18000d5a7  lea     rcx, [rdi+48h]
0x18000d5ab  mov     r9d, r15d
0x18000d5ae  mov     r8d, r14d
0x18000d5b1  mov     edx, ebx
0x18000d5b3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d5b8  mov     bl, al
0x18000d5ba  jmp     short loc_18000D5CD
0x18000d5bc  mov     r8d, r14d
0x18000d5bf  lea     rcx, [rdi+8]
0x18000d5c3  mov     edx, ebx
0x18000d5c5  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d5ca  mov     bl, [rdi+40h]
0x18000d5cd  test    rdi, rdi
0x18000d5d0  jz      short loc_18000D5E1
0x18000d5d2  mov     rcx, rdi; SRWLock
0x18000d5d5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d5dc  nop     dword ptr [rax+rax+00h]
0x18000d5e1  test    bl, bl
0x18000d5e3  jz      short loc_18000D63C
0x18000d5e5  jmp     short loc_18000D5EF
0x18000d5e7  mov     rcx, rdi; SRWLock
0x18000d5ea  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000d5ef  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d5f6  jnz     short loc_18000D63C
0x18000d5f8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d5ff  test    rax, rax
0x18000d602  jz      short loc_18000D60D
0x18000d604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d609  test    al, al
0x18000d60b  jnz     short loc_18000D63C
0x18000d60d  lea     rbx, [rsi+20h]
0x18000d611  mov     rcx, rbx; SRWLock
0x18000d614  call    cs:__imp_AcquireSRWLockExclusive
0x18000d61b  nop     dword ptr [rax+rax+00h]
0x18000d620  mov     rcx, rsi; pv
0x18000d623  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000d628  test    rbx, rbx
0x18000d62b  jz      short loc_18000D63C
0x18000d62d  mov     rcx, rbx; SRWLock
0x18000d630  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d637  nop     dword ptr [rax+rax+00h]
0x18000d63c  mov     rbx, [rsp+38h+arg_0]
0x18000d641  mov     rbp, [rsp+38h+arg_8]
0x18000d646  mov     rsi, [rsp+38h+arg_10]
0x18000d64b  add     rsp, 20h
0x18000d64f  pop     r15
0x18000d651  pop     r14
0x18000d653  pop     rdi
0x18000d654  retn
```
