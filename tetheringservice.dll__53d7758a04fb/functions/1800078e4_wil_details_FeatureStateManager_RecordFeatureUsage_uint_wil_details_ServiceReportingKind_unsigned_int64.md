# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800078e4`
- end: `0x1800079f3`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180009cd0`

## callees

- `0x180005c44`
- `0x180005dbc`
- `0x1800078e4`
- `0x180007a74`
- `0x180007aa8`
- `0x180007ae0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800079df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007990`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800079df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800079c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180007942`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800079c9`

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
0x1800078e4  push    rbx
0x1800078e6  push    rbp
0x1800078e7  push    rsi
0x1800078e8  push    rdi
0x1800078e9  push    r14
0x1800078eb  push    r15
0x1800078ed  sub     rsp, 28h
0x1800078f1  mov     r15, r9
0x1800078f4  mov     ebx, r8d
0x1800078f7  mov     r14d, edx
0x1800078fa  mov     rsi, rcx
0x1800078fd  cmp     byte ptr [rcx], 0
0x180007900  jz      loc_1800079E6
0x180007906  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000790b  test    al, al
0x18000790d  jz      loc_1800079E6
0x180007913  mov     rdi, [rsi+18h]
0x180007917  cmp     ebx, 0FEh
0x18000791d  jz      short loc_18000799C
0x18000791f  cmp     ebx, 0C8h
0x180007925  jb      short loc_18000793F
0x180007927  cmp     ebx, 100h
0x18000792d  jl      loc_1800079E6
0x180007933  cmp     ebx, 200h
0x180007939  jnb     loc_1800079E6
0x18000793f  mov     rcx, rdi; SRWLock
0x180007942  call    cs:__imp_AcquireSRWLockExclusive
0x180007948  cmp     ebx, 7
0x18000794b  ja      short loc_180007957
0x18000794d  mov     eax, 0CCh
0x180007952  bt      eax, ebx
0x180007955  jb      short loc_180007977
0x180007957  lea     eax, [rbx-100h]
0x18000795d  cmp     eax, 7Fh
0x180007960  jbe     short loc_180007977
0x180007962  mov     r9d, r15d
0x180007965  lea     rcx, [rdi+48h]
0x180007969  mov     r8d, r14d
0x18000796c  mov     edx, ebx
0x18000796e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007973  mov     bl, al
0x180007975  jmp     short loc_180007988
0x180007977  mov     r8d, r14d
0x18000797a  mov     edx, ebx
0x18000797c  lea     rcx, [rdi+8]
0x180007980  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180007985  mov     bl, [rdi+40h]
0x180007988  test    rdi, rdi
0x18000798b  jz      short loc_180007996
0x18000798d  mov     rcx, rdi; SRWLock
0x180007990  call    cs:__imp_ReleaseSRWLockExclusive
0x180007996  test    bl, bl
0x180007998  jz      short loc_1800079E6
0x18000799a  jmp     short loc_1800079A4
0x18000799c  mov     rcx, rdi; SRWLock
0x18000799f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800079a4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800079ab  jnz     short loc_1800079E6
0x1800079ad  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800079b4  test    rax, rax
0x1800079b7  jz      short loc_1800079C2
0x1800079b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079be  test    al, al
0x1800079c0  jnz     short loc_1800079E6
0x1800079c2  lea     rbx, [rsi+20h]
0x1800079c6  mov     rcx, rbx; SRWLock
0x1800079c9  call    cs:__imp_AcquireSRWLockExclusive
0x1800079cf  mov     rcx, rsi; pv
0x1800079d2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800079d7  test    rbx, rbx
0x1800079da  jz      short loc_1800079E6
0x1800079dc  mov     rcx, rbx; SRWLock
0x1800079df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800079e5  nop
0x1800079e6  add     rsp, 28h
0x1800079ea  pop     r15
0x1800079ec  pop     r14
0x1800079ee  pop     rdi
0x1800079ef  pop     rsi
0x1800079f0  pop     rbp
0x1800079f1  pop     rbx
0x1800079f2  retn
```
