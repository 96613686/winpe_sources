# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140007bb4`
- end: `0x140007cc2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140009b30`

## callees

- `0x1400060a4`
- `0x140006158`
- `0x140007bb4`
- `0x140007d00`
- `0x140007d34`
- `0x140007d6c`
- `0x14000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007c60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007caf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007c60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140007caf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007c99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007c12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140007c99`

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
0x140007bb4  push    rbx
0x140007bb6  push    rbp
0x140007bb7  push    rsi
0x140007bb8  push    rdi
0x140007bb9  push    r14
0x140007bbb  push    r15
0x140007bbd  sub     rsp, 28h
0x140007bc1  cmp     byte ptr [rcx], 0
0x140007bc4  mov     r15, r9
0x140007bc7  mov     ebx, r8d
0x140007bca  mov     r14d, edx
0x140007bcd  mov     rsi, rcx
0x140007bd0  jz      loc_140007CB5
0x140007bd6  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140007bdb  test    al, al
0x140007bdd  jz      loc_140007CB5
0x140007be3  mov     rdi, [rsi+18h]
0x140007be7  cmp     ebx, 0FEh
0x140007bed  jz      short loc_140007C6C
0x140007bef  cmp     ebx, 0C8h
0x140007bf5  jb      short loc_140007C0F
0x140007bf7  cmp     ebx, 100h
0x140007bfd  jl      loc_140007CB5
0x140007c03  cmp     ebx, 200h
0x140007c09  jnb     loc_140007CB5
0x140007c0f  mov     rcx, rdi; SRWLock
0x140007c12  call    cs:__imp_AcquireSRWLockExclusive
0x140007c18  cmp     ebx, 7
0x140007c1b  ja      short loc_140007C27
0x140007c1d  mov     eax, 0CCh
0x140007c22  bt      eax, ebx
0x140007c25  jb      short loc_140007C47
0x140007c27  lea     eax, [rbx-100h]
0x140007c2d  cmp     eax, 7Fh
0x140007c30  jbe     short loc_140007C47
0x140007c32  mov     r9d, r15d
0x140007c35  lea     rcx, [rdi+48h]
0x140007c39  mov     r8d, r14d
0x140007c3c  mov     edx, ebx
0x140007c3e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140007c43  mov     bl, al
0x140007c45  jmp     short loc_140007C58
0x140007c47  mov     r8d, r14d
0x140007c4a  lea     rcx, [rdi+8]
0x140007c4e  mov     edx, ebx
0x140007c50  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140007c55  mov     bl, [rdi+40h]
0x140007c58  test    rdi, rdi
0x140007c5b  jz      short loc_140007C66
0x140007c5d  mov     rcx, rdi; SRWLock
0x140007c60  call    cs:__imp_ReleaseSRWLockExclusive
0x140007c66  test    bl, bl
0x140007c68  jz      short loc_140007CB5
0x140007c6a  jmp     short loc_140007C74
0x140007c6c  mov     rcx, rdi; SRWLock
0x140007c6f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140007c74  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x140007c7b  jnz     short loc_140007CB5
0x140007c7d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x140007c84  test    rax, rax
0x140007c87  jz      short loc_140007C92
0x140007c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c8e  test    al, al
0x140007c90  jnz     short loc_140007CB5
0x140007c92  lea     rbx, [rsi+20h]
0x140007c96  mov     rcx, rbx; SRWLock
0x140007c99  call    cs:__imp_AcquireSRWLockExclusive
0x140007c9f  mov     rcx, rsi; pv
0x140007ca2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x140007ca7  test    rbx, rbx
0x140007caa  jz      short loc_140007CB5
0x140007cac  mov     rcx, rbx; SRWLock
0x140007caf  call    cs:__imp_ReleaseSRWLockExclusive
0x140007cb5  add     rsp, 28h
0x140007cb9  pop     r15
0x140007cbb  pop     r14
0x140007cbd  pop     rdi
0x140007cbe  pop     rsi
0x140007cbf  pop     rbp
0x140007cc0  pop     rbx
0x140007cc1  retn
```
