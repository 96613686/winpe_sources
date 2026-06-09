# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008614`
- end: `0x180008723`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000bf70`

## callees

- `0x180005d24`
- `0x180005e9c`
- `0x180008614`
- `0x1800087a4`
- `0x1800087d8`
- `0x180008810`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008672`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008672`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800086f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000870f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800086c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000870f`

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
0x180008614  push    rbx
0x180008616  push    rbp
0x180008617  push    rsi
0x180008618  push    rdi
0x180008619  push    r14
0x18000861b  push    r15
0x18000861d  sub     rsp, 28h
0x180008621  mov     r15, r9
0x180008624  mov     ebx, r8d
0x180008627  mov     r14d, edx
0x18000862a  mov     rsi, rcx
0x18000862d  cmp     byte ptr [rcx], 0
0x180008630  jz      loc_180008716
0x180008636  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000863b  test    al, al
0x18000863d  jz      loc_180008716
0x180008643  mov     rdi, [rsi+18h]
0x180008647  cmp     ebx, 0FEh
0x18000864d  jz      short loc_1800086CC
0x18000864f  cmp     ebx, 0C8h
0x180008655  jb      short loc_18000866F
0x180008657  cmp     ebx, 100h
0x18000865d  jl      loc_180008716
0x180008663  cmp     ebx, 200h
0x180008669  jnb     loc_180008716
0x18000866f  mov     rcx, rdi; SRWLock
0x180008672  call    cs:__imp_AcquireSRWLockExclusive
0x180008678  cmp     ebx, 7
0x18000867b  ja      short loc_180008687
0x18000867d  mov     eax, 0CCh
0x180008682  bt      eax, ebx
0x180008685  jb      short loc_1800086A7
0x180008687  lea     eax, [rbx-100h]
0x18000868d  cmp     eax, 7Fh
0x180008690  jbe     short loc_1800086A7
0x180008692  mov     r9d, r15d
0x180008695  lea     rcx, [rdi+48h]
0x180008699  mov     r8d, r14d
0x18000869c  mov     edx, ebx
0x18000869e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800086a3  mov     bl, al
0x1800086a5  jmp     short loc_1800086B8
0x1800086a7  mov     r8d, r14d
0x1800086aa  mov     edx, ebx
0x1800086ac  lea     rcx, [rdi+8]
0x1800086b0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800086b5  mov     bl, [rdi+40h]
0x1800086b8  test    rdi, rdi
0x1800086bb  jz      short loc_1800086C6
0x1800086bd  mov     rcx, rdi; SRWLock
0x1800086c0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800086c6  test    bl, bl
0x1800086c8  jz      short loc_180008716
0x1800086ca  jmp     short loc_1800086D4
0x1800086cc  mov     rcx, rdi; SRWLock
0x1800086cf  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800086d4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800086db  jnz     short loc_180008716
0x1800086dd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800086e4  test    rax, rax
0x1800086e7  jz      short loc_1800086F2
0x1800086e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ee  test    al, al
0x1800086f0  jnz     short loc_180008716
0x1800086f2  lea     rbx, [rsi+20h]
0x1800086f6  mov     rcx, rbx; SRWLock
0x1800086f9  call    cs:__imp_AcquireSRWLockExclusive
0x1800086ff  mov     rcx, rsi; pv
0x180008702  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180008707  test    rbx, rbx
0x18000870a  jz      short loc_180008716
0x18000870c  mov     rcx, rbx; SRWLock
0x18000870f  call    cs:__imp_ReleaseSRWLockExclusive
0x180008715  nop
0x180008716  add     rsp, 28h
0x18000871a  pop     r15
0x18000871c  pop     r14
0x18000871e  pop     rdi
0x18000871f  pop     rsi
0x180008720  pop     rbp
0x180008721  pop     rbx
0x180008722  retn
```
