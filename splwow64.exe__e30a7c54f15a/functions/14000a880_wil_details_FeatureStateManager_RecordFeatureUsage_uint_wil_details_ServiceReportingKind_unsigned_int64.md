# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000a880`
- end: `0x14000a98e`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x14000be50`

## callees

- `0x1400095e4`
- `0x14000975c`
- `0x14000a880`
- `0x14000a9d4`
- `0x14000aa08`
- `0x14000aa40`
- `0x140016010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a8de`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a965`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a8de`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000a965`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a92c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a97b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a92c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x14000a97b`

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
0x14000a880  push    rbx
0x14000a882  push    rbp
0x14000a883  push    rsi
0x14000a884  push    rdi
0x14000a885  push    r14
0x14000a887  push    r15
0x14000a889  sub     rsp, 28h
0x14000a88d  cmp     byte ptr [rcx], 0
0x14000a890  mov     r15, r9
0x14000a893  mov     ebx, r8d
0x14000a896  mov     r14d, edx
0x14000a899  mov     rsi, rcx
0x14000a89c  jz      loc_14000A981
0x14000a8a2  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000a8a7  test    al, al
0x14000a8a9  jz      loc_14000A981
0x14000a8af  mov     rdi, [rsi+18h]
0x14000a8b3  cmp     ebx, 0FEh
0x14000a8b9  jz      short loc_14000A938
0x14000a8bb  cmp     ebx, 0C8h
0x14000a8c1  jb      short loc_14000A8DB
0x14000a8c3  cmp     ebx, 100h
0x14000a8c9  jl      loc_14000A981
0x14000a8cf  cmp     ebx, 200h
0x14000a8d5  jnb     loc_14000A981
0x14000a8db  mov     rcx, rdi; SRWLock
0x14000a8de  call    cs:__imp_AcquireSRWLockExclusive
0x14000a8e4  cmp     ebx, 7
0x14000a8e7  ja      short loc_14000A8F3
0x14000a8e9  mov     eax, 0CCh
0x14000a8ee  bt      eax, ebx
0x14000a8f1  jb      short loc_14000A913
0x14000a8f3  lea     eax, [rbx-100h]
0x14000a8f9  cmp     eax, 7Fh
0x14000a8fc  jbe     short loc_14000A913
0x14000a8fe  mov     r9d, r15d
0x14000a901  lea     rcx, [rdi+48h]
0x14000a905  mov     r8d, r14d
0x14000a908  mov     edx, ebx
0x14000a90a  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000a90f  mov     bl, al
0x14000a911  jmp     short loc_14000A924
0x14000a913  mov     r8d, r14d
0x14000a916  lea     rcx, [rdi+8]
0x14000a91a  mov     edx, ebx
0x14000a91c  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000a921  mov     bl, [rdi+40h]
0x14000a924  test    rdi, rdi
0x14000a927  jz      short loc_14000A932
0x14000a929  mov     rcx, rdi; SRWLock
0x14000a92c  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a932  test    bl, bl
0x14000a934  jz      short loc_14000A981
0x14000a936  jmp     short loc_14000A940
0x14000a938  mov     rcx, rdi; SRWLock
0x14000a93b  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000a940  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a947  jnz     short loc_14000A981
0x14000a949  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a950  test    rax, rax
0x14000a953  jz      short loc_14000A95E
0x14000a955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a95a  test    al, al
0x14000a95c  jnz     short loc_14000A981
0x14000a95e  lea     rbx, [rsi+20h]
0x14000a962  mov     rcx, rbx; SRWLock
0x14000a965  call    cs:__imp_AcquireSRWLockExclusive
0x14000a96b  mov     rcx, rsi; pv
0x14000a96e  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x14000a973  test    rbx, rbx
0x14000a976  jz      short loc_14000A981
0x14000a978  mov     rcx, rbx; SRWLock
0x14000a97b  call    cs:__imp_ReleaseSRWLockExclusive
0x14000a981  add     rsp, 28h
0x14000a985  pop     r15
0x14000a987  pop     r14
0x14000a989  pop     rdi
0x14000a98a  pop     rsi
0x14000a98b  pop     rbp
0x14000a98c  pop     rbx
0x14000a98d  retn
```
