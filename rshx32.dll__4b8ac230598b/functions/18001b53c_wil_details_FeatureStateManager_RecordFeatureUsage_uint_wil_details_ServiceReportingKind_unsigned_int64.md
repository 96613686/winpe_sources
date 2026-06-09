# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18001b53c`
- end: `0x18001b64a`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18001c980`

## callees

- `0x18001a518`
- `0x18001a5cc`
- `0x18001b53c`
- `0x18001b684`
- `0x18001b6b8`
- `0x18001b6f0`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b5e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b637`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b5e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b637`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b59a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b621`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b59a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b621`

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
0x18001b53c  push    rbx
0x18001b53e  push    rbp
0x18001b53f  push    rsi
0x18001b540  push    rdi
0x18001b541  push    r14
0x18001b543  push    r15
0x18001b545  sub     rsp, 28h
0x18001b549  cmp     byte ptr [rcx], 0
0x18001b54c  mov     r15, r9
0x18001b54f  mov     ebx, r8d
0x18001b552  mov     r14d, edx
0x18001b555  mov     rsi, rcx
0x18001b558  jz      loc_18001B63D
0x18001b55e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18001b563  test    al, al
0x18001b565  jz      loc_18001B63D
0x18001b56b  mov     rdi, [rsi+18h]
0x18001b56f  cmp     ebx, 0FEh
0x18001b575  jz      short loc_18001B5F4
0x18001b577  cmp     ebx, 0C8h
0x18001b57d  jb      short loc_18001B597
0x18001b57f  cmp     ebx, 100h
0x18001b585  jl      loc_18001B63D
0x18001b58b  cmp     ebx, 200h
0x18001b591  jnb     loc_18001B63D
0x18001b597  mov     rcx, rdi; SRWLock
0x18001b59a  call    cs:__imp_AcquireSRWLockExclusive
0x18001b5a0  cmp     ebx, 7
0x18001b5a3  ja      short loc_18001B5AF
0x18001b5a5  mov     eax, 0CCh
0x18001b5aa  bt      eax, ebx
0x18001b5ad  jb      short loc_18001B5CF
0x18001b5af  lea     eax, [rbx-100h]
0x18001b5b5  cmp     eax, 7Fh
0x18001b5b8  jbe     short loc_18001B5CF
0x18001b5ba  mov     r9d, r15d
0x18001b5bd  lea     rcx, [rdi+48h]
0x18001b5c1  mov     r8d, r14d
0x18001b5c4  mov     edx, ebx
0x18001b5c6  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001b5cb  mov     bl, al
0x18001b5cd  jmp     short loc_18001B5E0
0x18001b5cf  mov     r8d, r14d
0x18001b5d2  lea     rcx, [rdi+8]
0x18001b5d6  mov     edx, ebx
0x18001b5d8  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18001b5dd  mov     bl, [rdi+40h]
0x18001b5e0  test    rdi, rdi
0x18001b5e3  jz      short loc_18001B5EE
0x18001b5e5  mov     rcx, rdi; SRWLock
0x18001b5e8  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b5ee  test    bl, bl
0x18001b5f0  jz      short loc_18001B63D
0x18001b5f2  jmp     short loc_18001B5FC
0x18001b5f4  mov     rcx, rdi; SRWLock
0x18001b5f7  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18001b5fc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18001b603  jnz     short loc_18001B63D
0x18001b605  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18001b60c  test    rax, rax
0x18001b60f  jz      short loc_18001B61A
0x18001b611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b616  test    al, al
0x18001b618  jnz     short loc_18001B63D
0x18001b61a  lea     rbx, [rsi+20h]
0x18001b61e  mov     rcx, rbx; SRWLock
0x18001b621  call    cs:__imp_AcquireSRWLockExclusive
0x18001b627  mov     rcx, rsi; pv
0x18001b62a  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18001b62f  test    rbx, rbx
0x18001b632  jz      short loc_18001B63D
0x18001b634  mov     rcx, rbx; SRWLock
0x18001b637  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b63d  add     rsp, 28h
0x18001b641  pop     r15
0x18001b643  pop     r14
0x18001b645  pop     rdi
0x18001b646  pop     rsi
0x18001b647  pop     rbp
0x18001b648  pop     rbx
0x18001b649  retn
```
