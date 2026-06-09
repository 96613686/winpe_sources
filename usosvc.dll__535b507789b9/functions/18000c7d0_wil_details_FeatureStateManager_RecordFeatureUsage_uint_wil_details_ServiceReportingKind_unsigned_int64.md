# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000c7d0`
- end: `0x18000c8df`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000dc00`

## callees

- `0x18000b754`
- `0x18000b808`
- `0x18000c7d0`
- `0x18000c8e8`
- `0x18000c91c`
- `0x18000c954`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c82e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c8b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c82e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c8b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c87c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8cb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c87c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c8cb`

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
0x18000c7d0  push    rbx
0x18000c7d2  push    rbp
0x18000c7d3  push    rsi
0x18000c7d4  push    rdi
0x18000c7d5  push    r14
0x18000c7d7  push    r15
0x18000c7d9  sub     rsp, 28h
0x18000c7dd  mov     r15, r9
0x18000c7e0  mov     ebx, r8d
0x18000c7e3  mov     r14d, edx
0x18000c7e6  mov     rsi, rcx
0x18000c7e9  cmp     byte ptr [rcx], 0
0x18000c7ec  jz      loc_18000C8D2
0x18000c7f2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c7f7  test    al, al
0x18000c7f9  jz      loc_18000C8D2
0x18000c7ff  mov     rdi, [rsi+18h]
0x18000c803  cmp     ebx, 0FEh
0x18000c809  jz      short loc_18000C888
0x18000c80b  cmp     ebx, 0C8h
0x18000c811  jb      short loc_18000C82B
0x18000c813  cmp     ebx, 100h
0x18000c819  jl      loc_18000C8D2
0x18000c81f  cmp     ebx, 200h
0x18000c825  jnb     loc_18000C8D2
0x18000c82b  mov     rcx, rdi; SRWLock
0x18000c82e  call    cs:__imp_AcquireSRWLockExclusive
0x18000c834  cmp     ebx, 7
0x18000c837  ja      short loc_18000C843
0x18000c839  mov     eax, 0CCh
0x18000c83e  bt      eax, ebx
0x18000c841  jb      short loc_18000C863
0x18000c843  lea     eax, [rbx-100h]
0x18000c849  cmp     eax, 7Fh
0x18000c84c  jbe     short loc_18000C863
0x18000c84e  mov     r9d, r15d
0x18000c851  lea     rcx, [rdi+48h]
0x18000c855  mov     r8d, r14d
0x18000c858  mov     edx, ebx
0x18000c85a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c85f  mov     bl, al
0x18000c861  jmp     short loc_18000C874
0x18000c863  mov     r8d, r14d
0x18000c866  mov     edx, ebx
0x18000c868  lea     rcx, [rdi+8]
0x18000c86c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c871  mov     bl, [rdi+40h]
0x18000c874  test    rdi, rdi
0x18000c877  jz      short loc_18000C882
0x18000c879  mov     rcx, rdi; SRWLock
0x18000c87c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c882  test    bl, bl
0x18000c884  jz      short loc_18000C8D2
0x18000c886  jmp     short loc_18000C890
0x18000c888  mov     rcx, rdi; SRWLock
0x18000c88b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c890  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c897  jnz     short loc_18000C8D2
0x18000c899  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c8a0  test    rax, rax
0x18000c8a3  jz      short loc_18000C8AE
0x18000c8a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8aa  test    al, al
0x18000c8ac  jnz     short loc_18000C8D2
0x18000c8ae  lea     rbx, [rsi+20h]
0x18000c8b2  mov     rcx, rbx; SRWLock
0x18000c8b5  call    cs:__imp_AcquireSRWLockExclusive
0x18000c8bb  mov     rcx, rsi; pv
0x18000c8be  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000c8c3  test    rbx, rbx
0x18000c8c6  jz      short loc_18000C8D2
0x18000c8c8  mov     rcx, rbx; SRWLock
0x18000c8cb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c8d1  nop
0x18000c8d2  add     rsp, 28h
0x18000c8d6  pop     r15
0x18000c8d8  pop     r14
0x18000c8da  pop     rdi
0x18000c8db  pop     rsi
0x18000c8dc  pop     rbp
0x18000c8dd  pop     rbx
0x18000c8de  retn
```
