# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b6a0`
- end: `0x18000b7af`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180011010`

## callees

- `0x180009aa8`
- `0x180009c20`
- `0x18000b6a0`
- `0x18000b824`
- `0x18000b858`
- `0x18000b890`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b785`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b6fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b785`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b74c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b79b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b74c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b79b`

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
0x18000b6a0  push    rbx
0x18000b6a2  push    rbp
0x18000b6a3  push    rsi
0x18000b6a4  push    rdi
0x18000b6a5  push    r14
0x18000b6a7  push    r15
0x18000b6a9  sub     rsp, 28h
0x18000b6ad  mov     r15, r9
0x18000b6b0  mov     ebx, r8d
0x18000b6b3  mov     r14d, edx
0x18000b6b6  mov     rsi, rcx
0x18000b6b9  cmp     byte ptr [rcx], 0
0x18000b6bc  jz      loc_18000B7A2
0x18000b6c2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b6c7  test    al, al
0x18000b6c9  jz      loc_18000B7A2
0x18000b6cf  mov     rdi, [rsi+18h]
0x18000b6d3  cmp     ebx, 0FEh
0x18000b6d9  jz      short loc_18000B758
0x18000b6db  cmp     ebx, 0C8h
0x18000b6e1  jb      short loc_18000B6FB
0x18000b6e3  cmp     ebx, 100h
0x18000b6e9  jl      loc_18000B7A2
0x18000b6ef  cmp     ebx, 200h
0x18000b6f5  jnb     loc_18000B7A2
0x18000b6fb  mov     rcx, rdi; SRWLock
0x18000b6fe  call    cs:__imp_AcquireSRWLockExclusive
0x18000b704  cmp     ebx, 7
0x18000b707  ja      short loc_18000B713
0x18000b709  mov     eax, 0CCh
0x18000b70e  bt      eax, ebx
0x18000b711  jb      short loc_18000B733
0x18000b713  lea     eax, [rbx-100h]
0x18000b719  cmp     eax, 7Fh
0x18000b71c  jbe     short loc_18000B733
0x18000b71e  mov     r9d, r15d
0x18000b721  lea     rcx, [rdi+48h]
0x18000b725  mov     r8d, r14d
0x18000b728  mov     edx, ebx
0x18000b72a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b72f  mov     bl, al
0x18000b731  jmp     short loc_18000B744
0x18000b733  mov     r8d, r14d
0x18000b736  mov     edx, ebx
0x18000b738  lea     rcx, [rdi+8]
0x18000b73c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b741  mov     bl, [rdi+40h]
0x18000b744  test    rdi, rdi
0x18000b747  jz      short loc_18000B752
0x18000b749  mov     rcx, rdi; SRWLock
0x18000b74c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b752  test    bl, bl
0x18000b754  jz      short loc_18000B7A2
0x18000b756  jmp     short loc_18000B760
0x18000b758  mov     rcx, rdi; SRWLock
0x18000b75b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b760  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b767  jnz     short loc_18000B7A2
0x18000b769  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b770  test    rax, rax
0x18000b773  jz      short loc_18000B77E
0x18000b775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b77a  test    al, al
0x18000b77c  jnz     short loc_18000B7A2
0x18000b77e  lea     rbx, [rsi+20h]
0x18000b782  mov     rcx, rbx; SRWLock
0x18000b785  call    cs:__imp_AcquireSRWLockExclusive
0x18000b78b  mov     rcx, rsi; pv
0x18000b78e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000b793  test    rbx, rbx
0x18000b796  jz      short loc_18000B7A2
0x18000b798  mov     rcx, rbx; SRWLock
0x18000b79b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b7a1  nop
0x18000b7a2  add     rsp, 28h
0x18000b7a6  pop     r15
0x18000b7a8  pop     r14
0x18000b7aa  pop     rdi
0x18000b7ab  pop     rsi
0x18000b7ac  pop     rbp
0x18000b7ad  pop     rbx
0x18000b7ae  retn
```
