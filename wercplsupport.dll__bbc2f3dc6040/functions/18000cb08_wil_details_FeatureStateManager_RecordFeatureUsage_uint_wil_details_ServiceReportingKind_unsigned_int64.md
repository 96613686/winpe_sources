# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000cb08`
- end: `0x18000cc16`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000eb10`

## callees

- `0x18000a8ac`
- `0x18000a960`
- `0x18000cb08`
- `0x18000cc54`
- `0x18000cc88`
- `0x18000ccc0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cbb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cbb4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cc03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cb66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cbed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cb66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000cbed`

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
0x18000cb08  push    rbx
0x18000cb0a  push    rbp
0x18000cb0b  push    rsi
0x18000cb0c  push    rdi
0x18000cb0d  push    r14
0x18000cb0f  push    r15
0x18000cb11  sub     rsp, 28h
0x18000cb15  cmp     byte ptr [rcx], 0
0x18000cb18  mov     r15, r9
0x18000cb1b  mov     ebx, r8d
0x18000cb1e  mov     r14d, edx
0x18000cb21  mov     rsi, rcx
0x18000cb24  jz      loc_18000CC09
0x18000cb2a  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000cb2f  test    al, al
0x18000cb31  jz      loc_18000CC09
0x18000cb37  mov     rdi, [rsi+18h]
0x18000cb3b  cmp     ebx, 0FEh
0x18000cb41  jz      short loc_18000CBC0
0x18000cb43  cmp     ebx, 0C8h
0x18000cb49  jb      short loc_18000CB63
0x18000cb4b  cmp     ebx, 100h
0x18000cb51  jl      loc_18000CC09
0x18000cb57  cmp     ebx, 200h
0x18000cb5d  jnb     loc_18000CC09
0x18000cb63  mov     rcx, rdi; SRWLock
0x18000cb66  call    cs:__imp_AcquireSRWLockExclusive
0x18000cb6c  cmp     ebx, 7
0x18000cb6f  ja      short loc_18000CB7B
0x18000cb71  mov     eax, 0CCh
0x18000cb76  bt      eax, ebx
0x18000cb79  jb      short loc_18000CB9B
0x18000cb7b  lea     eax, [rbx-100h]
0x18000cb81  cmp     eax, 7Fh
0x18000cb84  jbe     short loc_18000CB9B
0x18000cb86  mov     r9d, r15d
0x18000cb89  lea     rcx, [rdi+48h]
0x18000cb8d  mov     r8d, r14d
0x18000cb90  mov     edx, ebx
0x18000cb92  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000cb97  mov     bl, al
0x18000cb99  jmp     short loc_18000CBAC
0x18000cb9b  mov     r8d, r14d
0x18000cb9e  lea     rcx, [rdi+8]
0x18000cba2  mov     edx, ebx
0x18000cba4  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000cba9  mov     bl, [rdi+40h]
0x18000cbac  test    rdi, rdi
0x18000cbaf  jz      short loc_18000CBBA
0x18000cbb1  mov     rcx, rdi; SRWLock
0x18000cbb4  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cbba  test    bl, bl
0x18000cbbc  jz      short loc_18000CC09
0x18000cbbe  jmp     short loc_18000CBC8
0x18000cbc0  mov     rcx, rdi; SRWLock
0x18000cbc3  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000cbc8  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000cbcf  jnz     short loc_18000CC09
0x18000cbd1  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000cbd8  test    rax, rax
0x18000cbdb  jz      short loc_18000CBE6
0x18000cbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe2  test    al, al
0x18000cbe4  jnz     short loc_18000CC09
0x18000cbe6  lea     rbx, [rsi+20h]
0x18000cbea  mov     rcx, rbx; SRWLock
0x18000cbed  call    cs:__imp_AcquireSRWLockExclusive
0x18000cbf3  mov     rcx, rsi; pv
0x18000cbf6  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000cbfb  test    rbx, rbx
0x18000cbfe  jz      short loc_18000CC09
0x18000cc00  mov     rcx, rbx; SRWLock
0x18000cc03  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cc09  add     rsp, 28h
0x18000cc0d  pop     r15
0x18000cc0f  pop     r14
0x18000cc11  pop     rdi
0x18000cc12  pop     rsi
0x18000cc13  pop     rbp
0x18000cc14  pop     rbx
0x18000cc15  retn
```
