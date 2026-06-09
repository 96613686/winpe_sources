# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000964c`
- end: `0x14000975a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000a710`

## callees

- `0x140008d4c`
- `0x140008e00`
- `0x14000964c`
- `0x140009760`
- `0x140009794`
- `0x1400097cc`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400096f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009747`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400096f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009747`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400096aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009731`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400096aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140009731`

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

  if ( !*(_BYTE *)a1 || !wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)a1) )
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
0x14000964c  push    rbx
0x14000964e  push    rbp
0x14000964f  push    rsi
0x140009650  push    rdi
0x140009651  push    r14
0x140009653  push    r15
0x140009655  sub     rsp, 28h
0x140009659  cmp     byte ptr [rcx], 0
0x14000965c  mov     r15, r9
0x14000965f  mov     ebx, r8d
0x140009662  mov     r14d, edx
0x140009665  mov     rsi, rcx
0x140009668  jz      loc_14000974D
0x14000966e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140009673  test    al, al
0x140009675  jz      loc_14000974D
0x14000967b  mov     rdi, [rsi+18h]
0x14000967f  cmp     ebx, 0FEh
0x140009685  jz      short loc_140009704
0x140009687  cmp     ebx, 0C8h
0x14000968d  jb      short loc_1400096A7
0x14000968f  cmp     ebx, 100h
0x140009695  jl      loc_14000974D
0x14000969b  cmp     ebx, 200h
0x1400096a1  jnb     loc_14000974D
0x1400096a7  mov     rcx, rdi; SRWLock
0x1400096aa  call    cs:__imp_AcquireSRWLockExclusive
0x1400096b0  cmp     ebx, 7
0x1400096b3  ja      short loc_1400096BF
0x1400096b5  mov     eax, 0CCh
0x1400096ba  bt      eax, ebx
0x1400096bd  jb      short loc_1400096DF
0x1400096bf  lea     eax, [rbx-100h]
0x1400096c5  cmp     eax, 7Fh
0x1400096c8  jbe     short loc_1400096DF
0x1400096ca  mov     r9d, r15d
0x1400096cd  lea     rcx, [rdi+48h]
0x1400096d1  mov     r8d, r14d
0x1400096d4  mov     edx, ebx
0x1400096d6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400096db  mov     bl, al
0x1400096dd  jmp     short loc_1400096F0
0x1400096df  mov     r8d, r14d
0x1400096e2  lea     rcx, [rdi+8]
0x1400096e6  mov     edx, ebx
0x1400096e8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1400096ed  mov     bl, [rdi+40h]
0x1400096f0  test    rdi, rdi
0x1400096f3  jz      short loc_1400096FE
0x1400096f5  mov     rcx, rdi; SRWLock
0x1400096f8  call    cs:__imp_ReleaseSRWLockExclusive
0x1400096fe  test    bl, bl
0x140009700  jz      short loc_14000974D
0x140009702  jmp     short loc_14000970C
0x140009704  mov     rcx, rdi; SRWLock
0x140009707  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000970c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140009713  jnz     short loc_14000974D
0x140009715  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000971c  test    rax, rax
0x14000971f  jz      short loc_14000972A
0x140009721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009726  test    al, al
0x140009728  jnz     short loc_14000974D
0x14000972a  lea     rbx, [rsi+20h]
0x14000972e  mov     rcx, rbx; SRWLock
0x140009731  call    cs:__imp_AcquireSRWLockExclusive
0x140009737  mov     rcx, rsi; pv
0x14000973a  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000973f  test    rbx, rbx
0x140009742  jz      short loc_14000974D
0x140009744  mov     rcx, rbx; SRWLock
0x140009747  call    cs:__imp_ReleaseSRWLockExclusive
0x14000974d  add     rsp, 28h
0x140009751  pop     r15
0x140009753  pop     r14
0x140009755  pop     rdi
0x140009756  pop     rsi
0x140009757  pop     rbp
0x140009758  pop     rbx
0x140009759  retn
```
