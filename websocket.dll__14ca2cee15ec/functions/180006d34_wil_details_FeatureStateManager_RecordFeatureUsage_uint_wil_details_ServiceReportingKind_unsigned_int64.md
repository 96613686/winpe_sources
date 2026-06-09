# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180006d34`
- end: `0x180006e42`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800087d0`

## callees

- `0x180004b04`
- `0x180004c7c`
- `0x180006d34`
- `0x180006eb4`
- `0x180006ee8`
- `0x180006f20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006d92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006e19`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006d92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006e19`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006de0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006de0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e2f`

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
0x180006d34  push    rbx
0x180006d36  push    rbp
0x180006d37  push    rsi
0x180006d38  push    rdi
0x180006d39  push    r14
0x180006d3b  push    r15
0x180006d3d  sub     rsp, 28h
0x180006d41  cmp     byte ptr [rcx], 0
0x180006d44  mov     r15, r9
0x180006d47  mov     ebx, r8d
0x180006d4a  mov     r14d, edx
0x180006d4d  mov     rsi, rcx
0x180006d50  jz      loc_180006E35
0x180006d56  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180006d5b  test    al, al
0x180006d5d  jz      loc_180006E35
0x180006d63  mov     rdi, [rsi+18h]
0x180006d67  cmp     ebx, 0FEh
0x180006d6d  jz      short loc_180006DEC
0x180006d6f  cmp     ebx, 0C8h
0x180006d75  jb      short loc_180006D8F
0x180006d77  cmp     ebx, 100h
0x180006d7d  jl      loc_180006E35
0x180006d83  cmp     ebx, 200h
0x180006d89  jnb     loc_180006E35
0x180006d8f  mov     rcx, rdi; SRWLock
0x180006d92  call    cs:__imp_AcquireSRWLockExclusive
0x180006d98  cmp     ebx, 7
0x180006d9b  ja      short loc_180006DA7
0x180006d9d  mov     eax, 0CCh
0x180006da2  bt      eax, ebx
0x180006da5  jb      short loc_180006DC7
0x180006da7  lea     eax, [rbx-100h]
0x180006dad  cmp     eax, 7Fh
0x180006db0  jbe     short loc_180006DC7
0x180006db2  mov     r9d, r15d
0x180006db5  lea     rcx, [rdi+48h]
0x180006db9  mov     r8d, r14d
0x180006dbc  mov     edx, ebx
0x180006dbe  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006dc3  mov     bl, al
0x180006dc5  jmp     short loc_180006DD8
0x180006dc7  mov     r8d, r14d
0x180006dca  lea     rcx, [rdi+8]
0x180006dce  mov     edx, ebx
0x180006dd0  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180006dd5  mov     bl, [rdi+40h]
0x180006dd8  test    rdi, rdi
0x180006ddb  jz      short loc_180006DE6
0x180006ddd  mov     rcx, rdi; SRWLock
0x180006de0  call    cs:__imp_ReleaseSRWLockExclusive
0x180006de6  test    bl, bl
0x180006de8  jz      short loc_180006E35
0x180006dea  jmp     short loc_180006DF4
0x180006dec  mov     rcx, rdi; SRWLock
0x180006def  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180006df4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180006dfb  jnz     short loc_180006E35
0x180006dfd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180006e04  test    rax, rax
0x180006e07  jz      short loc_180006E12
0x180006e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e0e  test    al, al
0x180006e10  jnz     short loc_180006E35
0x180006e12  lea     rbx, [rsi+20h]
0x180006e16  mov     rcx, rbx; SRWLock
0x180006e19  call    cs:__imp_AcquireSRWLockExclusive
0x180006e1f  mov     rcx, rsi; pv
0x180006e22  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180006e27  test    rbx, rbx
0x180006e2a  jz      short loc_180006E35
0x180006e2c  mov     rcx, rbx; SRWLock
0x180006e2f  call    cs:__imp_ReleaseSRWLockExclusive
0x180006e35  add     rsp, 28h
0x180006e39  pop     r15
0x180006e3b  pop     r14
0x180006e3d  pop     rdi
0x180006e3e  pop     rsi
0x180006e3f  pop     rbp
0x180006e40  pop     rbx
0x180006e41  retn
```
