# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000954c`
- end: `0x14000965a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000bce0`

## callees

- `0x1400067f0`
- `0x140006968`
- `0x14000954c`
- `0x140009694`
- `0x1400096c8`
- `0x140009700`
- `0x140015010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400095aa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009631`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400095aa`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009631`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400095f8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009647`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400095f8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x140009647`

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
0x14000954c  push    rbx
0x14000954e  push    rbp
0x14000954f  push    rsi
0x140009550  push    rdi
0x140009551  push    r14
0x140009553  push    r15
0x140009555  sub     rsp, 28h
0x140009559  cmp     byte ptr [rcx], 0
0x14000955c  mov     r15, r9
0x14000955f  mov     ebx, r8d
0x140009562  mov     r14d, edx
0x140009565  mov     rsi, rcx
0x140009568  jz      loc_14000964D
0x14000956e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140009573  test    al, al
0x140009575  jz      loc_14000964D
0x14000957b  mov     rdi, [rsi+18h]
0x14000957f  cmp     ebx, 0FEh
0x140009585  jz      short loc_140009604
0x140009587  cmp     ebx, 0C8h
0x14000958d  jb      short loc_1400095A7
0x14000958f  cmp     ebx, 100h
0x140009595  jl      loc_14000964D
0x14000959b  cmp     ebx, 200h
0x1400095a1  jnb     loc_14000964D
0x1400095a7  mov     rcx, rdi; SRWLock
0x1400095aa  call    cs:__imp_AcquireSRWLockExclusive
0x1400095b0  cmp     ebx, 7
0x1400095b3  ja      short loc_1400095BF
0x1400095b5  mov     eax, 0CCh
0x1400095ba  bt      eax, ebx
0x1400095bd  jb      short loc_1400095DF
0x1400095bf  lea     eax, [rbx-100h]
0x1400095c5  cmp     eax, 7Fh
0x1400095c8  jbe     short loc_1400095DF
0x1400095ca  mov     r9d, r15d
0x1400095cd  lea     rcx, [rdi+48h]
0x1400095d1  mov     r8d, r14d
0x1400095d4  mov     edx, ebx
0x1400095d6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400095db  mov     bl, al
0x1400095dd  jmp     short loc_1400095F0
0x1400095df  mov     r8d, r14d
0x1400095e2  lea     rcx, [rdi+8]
0x1400095e6  mov     edx, ebx
0x1400095e8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400095ed  mov     bl, [rdi+40h]
0x1400095f0  test    rdi, rdi
0x1400095f3  jz      short loc_1400095FE
0x1400095f5  mov     rcx, rdi; SRWLock
0x1400095f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400095fe  test    bl, bl
0x140009600  jz      short loc_14000964D
0x140009602  jmp     short loc_14000960C
0x140009604  mov     rcx, rdi; SRWLock
0x140009607  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000960c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140009613  jnz     short loc_14000964D
0x140009615  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000961c  test    rax, rax
0x14000961f  jz      short loc_14000962A
0x140009621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009626  test    al, al
0x140009628  jnz     short loc_14000964D
0x14000962a  lea     rbx, [rsi+20h]
0x14000962e  mov     rcx, rbx; SRWLock
0x140009631  call    cs:__imp_AcquireSRWLockExclusive
0x140009637  mov     rcx, rsi; pv
0x14000963a  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000963f  test    rbx, rbx
0x140009642  jz      short loc_14000964D
0x140009644  mov     rcx, rbx; SRWLock
0x140009647  call    cs:__imp_ReleaseSRWLockExclusive
0x14000964d  add     rsp, 28h
0x140009651  pop     r15
0x140009653  pop     r14
0x140009655  pop     rdi
0x140009656  pop     rsi
0x140009657  pop     rbp
0x140009658  pop     rbx
0x140009659  retn
```
