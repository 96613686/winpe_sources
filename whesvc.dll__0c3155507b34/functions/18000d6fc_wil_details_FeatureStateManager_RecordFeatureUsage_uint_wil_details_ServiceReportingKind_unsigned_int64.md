# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000d6fc`
- end: `0x18000d80b`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ea00`

## callees

- `0x18000c9c0`
- `0x18000cb38`
- `0x18000d6fc`
- `0x18000d854`
- `0x18000d888`
- `0x18000d8c0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d75a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d7e1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d75a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d7e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d7f7`

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
0x18000d6fc  push    rbx
0x18000d6fe  push    rbp
0x18000d6ff  push    rsi
0x18000d700  push    rdi
0x18000d701  push    r14
0x18000d703  push    r15
0x18000d705  sub     rsp, 28h
0x18000d709  mov     r15, r9
0x18000d70c  mov     ebx, r8d
0x18000d70f  mov     r14d, edx
0x18000d712  mov     rsi, rcx
0x18000d715  cmp     byte ptr [rcx], 0
0x18000d718  jz      loc_18000D7FE
0x18000d71e  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000d723  test    al, al
0x18000d725  jz      loc_18000D7FE
0x18000d72b  mov     rdi, [rsi+18h]
0x18000d72f  cmp     ebx, 0FEh
0x18000d735  jz      short loc_18000D7B4
0x18000d737  cmp     ebx, 0C8h
0x18000d73d  jb      short loc_18000D757
0x18000d73f  cmp     ebx, 100h
0x18000d745  jl      loc_18000D7FE
0x18000d74b  cmp     ebx, 200h
0x18000d751  jnb     loc_18000D7FE
0x18000d757  mov     rcx, rdi; SRWLock
0x18000d75a  call    cs:__imp_AcquireSRWLockExclusive
0x18000d760  cmp     ebx, 7
0x18000d763  ja      short loc_18000D76F
0x18000d765  mov     eax, 0CCh
0x18000d76a  bt      eax, ebx
0x18000d76d  jb      short loc_18000D78F
0x18000d76f  lea     eax, [rbx-100h]
0x18000d775  cmp     eax, 7Fh
0x18000d778  jbe     short loc_18000D78F
0x18000d77a  mov     r9d, r15d
0x18000d77d  lea     rcx, [rdi+48h]
0x18000d781  mov     r8d, r14d
0x18000d784  mov     edx, ebx
0x18000d786  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d78b  mov     bl, al
0x18000d78d  jmp     short loc_18000D7A0
0x18000d78f  mov     r8d, r14d
0x18000d792  mov     edx, ebx
0x18000d794  lea     rcx, [rdi+8]
0x18000d798  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000d79d  mov     bl, [rdi+40h]
0x18000d7a0  test    rdi, rdi
0x18000d7a3  jz      short loc_18000D7AE
0x18000d7a5  mov     rcx, rdi; SRWLock
0x18000d7a8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d7ae  test    bl, bl
0x18000d7b0  jz      short loc_18000D7FE
0x18000d7b2  jmp     short loc_18000D7BC
0x18000d7b4  mov     rcx, rdi; SRWLock
0x18000d7b7  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000d7bc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000d7c3  jnz     short loc_18000D7FE
0x18000d7c5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d7cc  test    rax, rax
0x18000d7cf  jz      short loc_18000D7DA
0x18000d7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d6  test    al, al
0x18000d7d8  jnz     short loc_18000D7FE
0x18000d7da  lea     rbx, [rsi+20h]
0x18000d7de  mov     rcx, rbx; SRWLock
0x18000d7e1  call    cs:__imp_AcquireSRWLockExclusive
0x18000d7e7  mov     rcx, rsi; pv
0x18000d7ea  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000d7ef  test    rbx, rbx
0x18000d7f2  jz      short loc_18000D7FE
0x18000d7f4  mov     rcx, rbx; SRWLock
0x18000d7f7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d7fd  nop
0x18000d7fe  add     rsp, 28h
0x18000d802  pop     r15
0x18000d804  pop     r14
0x18000d806  pop     rdi
0x18000d807  pop     rsi
0x18000d808  pop     rbp
0x18000d809  pop     rbx
0x18000d80a  retn
```
