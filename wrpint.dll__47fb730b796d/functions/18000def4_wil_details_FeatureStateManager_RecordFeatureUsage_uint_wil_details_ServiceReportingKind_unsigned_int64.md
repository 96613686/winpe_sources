# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000def4`
- end: `0x18000e009`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `277`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000f970`

## callees

- `0x18000c344`
- `0x18000c3f8`
- `0x18000def4`
- `0x18000e048`
- `0x18000e09c`
- `0x18000e0f4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dfa3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dff2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dfa3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000dff2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfdc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000df55`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000dfdc`

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
0x18000def4  mov     [rsp+arg_18], rbx
0x18000def9  push    rbp
0x18000defa  push    rsi
0x18000defb  push    rdi
0x18000defc  push    r14
0x18000defe  push    r15
0x18000df00  sub     rsp, 20h
0x18000df04  cmp     byte ptr [rcx], 0
0x18000df07  mov     r15, r9
0x18000df0a  mov     ebx, r8d
0x18000df0d  mov     r14d, edx
0x18000df10  mov     rsi, rcx
0x18000df13  jz      loc_18000DFF8
0x18000df19  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000df1e  test    al, al
0x18000df20  jz      loc_18000DFF8
0x18000df26  mov     rdi, [rsi+18h]
0x18000df2a  cmp     ebx, 0FEh
0x18000df30  jz      short loc_18000DFAF
0x18000df32  cmp     ebx, 0C8h
0x18000df38  jb      short loc_18000DF52
0x18000df3a  cmp     ebx, 100h
0x18000df40  jl      loc_18000DFF8
0x18000df46  cmp     ebx, 200h
0x18000df4c  jnb     loc_18000DFF8
0x18000df52  mov     rcx, rdi; SRWLock
0x18000df55  call    cs:__imp_AcquireSRWLockExclusive
0x18000df5b  cmp     ebx, 7
0x18000df5e  ja      short loc_18000DF6A
0x18000df60  mov     eax, 0CCh
0x18000df65  bt      eax, ebx
0x18000df68  jb      short loc_18000DF8A
0x18000df6a  lea     eax, [rbx-100h]
0x18000df70  cmp     eax, 7Fh
0x18000df73  jbe     short loc_18000DF8A
0x18000df75  mov     r9d, r15d
0x18000df78  lea     rcx, [rdi+48h]
0x18000df7c  mov     r8d, r14d
0x18000df7f  mov     edx, ebx
0x18000df81  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000df86  mov     bl, al
0x18000df88  jmp     short loc_18000DF9B
0x18000df8a  mov     r8d, r14d
0x18000df8d  lea     rcx, [rdi+8]
0x18000df91  mov     edx, ebx
0x18000df93  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000df98  mov     bl, [rdi+40h]
0x18000df9b  test    rdi, rdi
0x18000df9e  jz      short loc_18000DFA9
0x18000dfa0  mov     rcx, rdi; SRWLock
0x18000dfa3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dfa9  test    bl, bl
0x18000dfab  jz      short loc_18000DFF8
0x18000dfad  jmp     short loc_18000DFB7
0x18000dfaf  mov     rcx, rdi; SRWLock
0x18000dfb2  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000dfb7  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000dfbe  jnz     short loc_18000DFF8
0x18000dfc0  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000dfc7  test    rax, rax
0x18000dfca  jz      short loc_18000DFD5
0x18000dfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfd1  test    al, al
0x18000dfd3  jnz     short loc_18000DFF8
0x18000dfd5  lea     rbx, [rsi+20h]
0x18000dfd9  mov     rcx, rbx; SRWLock
0x18000dfdc  call    cs:__imp_AcquireSRWLockExclusive
0x18000dfe2  mov     rcx, rsi; pv
0x18000dfe5  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000dfea  test    rbx, rbx
0x18000dfed  jz      short loc_18000DFF8
0x18000dfef  mov     rcx, rbx; SRWLock
0x18000dff2  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dff8  mov     rbx, [rsp+48h+arg_18]
0x18000dffd  add     rsp, 20h
0x18000e001  pop     r15
0x18000e003  pop     r14
0x18000e005  pop     rdi
0x18000e006  pop     rsi
0x18000e007  pop     rbp
0x18000e008  retn
```
