# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800091f4`
- end: `0x180009303`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000aeb0`

## callees

- `0x18000668c`
- `0x180006804`
- `0x1800091f4`
- `0x180009384`
- `0x1800093b8`
- `0x1800093f0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009252`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800092d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009252`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800092d9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800092a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800092ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800092a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800092ef`

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
0x1800091f4  push    rbx
0x1800091f6  push    rbp
0x1800091f7  push    rsi
0x1800091f8  push    rdi
0x1800091f9  push    r14
0x1800091fb  push    r15
0x1800091fd  sub     rsp, 28h
0x180009201  mov     r15, r9
0x180009204  mov     ebx, r8d
0x180009207  mov     r14d, edx
0x18000920a  mov     rsi, rcx
0x18000920d  cmp     byte ptr [rcx], 0
0x180009210  jz      loc_1800092F6
0x180009216  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000921b  test    al, al
0x18000921d  jz      loc_1800092F6
0x180009223  mov     rdi, [rsi+18h]
0x180009227  cmp     ebx, 0FEh
0x18000922d  jz      short loc_1800092AC
0x18000922f  cmp     ebx, 0C8h
0x180009235  jb      short loc_18000924F
0x180009237  cmp     ebx, 100h
0x18000923d  jl      loc_1800092F6
0x180009243  cmp     ebx, 200h
0x180009249  jnb     loc_1800092F6
0x18000924f  mov     rcx, rdi; SRWLock
0x180009252  call    cs:__imp_AcquireSRWLockExclusive
0x180009258  cmp     ebx, 7
0x18000925b  ja      short loc_180009267
0x18000925d  mov     eax, 0CCh
0x180009262  bt      eax, ebx
0x180009265  jb      short loc_180009287
0x180009267  lea     eax, [rbx-100h]
0x18000926d  cmp     eax, 7Fh
0x180009270  jbe     short loc_180009287
0x180009272  mov     r9d, r15d
0x180009275  lea     rcx, [rdi+48h]
0x180009279  mov     r8d, r14d
0x18000927c  mov     edx, ebx
0x18000927e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009283  mov     bl, al
0x180009285  jmp     short loc_180009298
0x180009287  mov     r8d, r14d
0x18000928a  mov     edx, ebx
0x18000928c  lea     rcx, [rdi+8]
0x180009290  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180009295  mov     bl, [rdi+40h]
0x180009298  test    rdi, rdi
0x18000929b  jz      short loc_1800092A6
0x18000929d  mov     rcx, rdi; SRWLock
0x1800092a0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800092a6  test    bl, bl
0x1800092a8  jz      short loc_1800092F6
0x1800092aa  jmp     short loc_1800092B4
0x1800092ac  mov     rcx, rdi; SRWLock
0x1800092af  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x1800092b4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x1800092bb  jnz     short loc_1800092F6
0x1800092bd  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800092c4  test    rax, rax
0x1800092c7  jz      short loc_1800092D2
0x1800092c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ce  test    al, al
0x1800092d0  jnz     short loc_1800092F6
0x1800092d2  lea     rbx, [rsi+20h]
0x1800092d6  mov     rcx, rbx; SRWLock
0x1800092d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800092df  mov     rcx, rsi; pv
0x1800092e2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x1800092e7  test    rbx, rbx
0x1800092ea  jz      short loc_1800092F6
0x1800092ec  mov     rcx, rbx; SRWLock
0x1800092ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800092f5  nop
0x1800092f6  add     rsp, 28h
0x1800092fa  pop     r15
0x1800092fc  pop     r14
0x1800092fe  pop     rdi
0x1800092ff  pop     rsi
0x180009300  pop     rbp
0x180009301  pop     rbx
0x180009302  retn
```
