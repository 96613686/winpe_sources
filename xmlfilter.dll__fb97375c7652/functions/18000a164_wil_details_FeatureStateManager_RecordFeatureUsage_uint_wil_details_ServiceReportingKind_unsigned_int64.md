# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000a164`
- end: `0x18000a273`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `271`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000ccc0`

## callees

- `0x180005d1c`
- `0x180005e94`
- `0x18000a164`
- `0x18000a2f4`
- `0x18000a328`
- `0x18000a360`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a210`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a25f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a210`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a25f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a1c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a249`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a1c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a249`

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
0x18000a164  push    rbx
0x18000a166  push    rbp
0x18000a167  push    rsi
0x18000a168  push    rdi
0x18000a169  push    r14
0x18000a16b  push    r15
0x18000a16d  sub     rsp, 28h
0x18000a171  mov     r15, r9
0x18000a174  mov     ebx, r8d
0x18000a177  mov     r14d, edx
0x18000a17a  mov     rsi, rcx
0x18000a17d  cmp     byte ptr [rcx], 0
0x18000a180  jz      loc_18000A266
0x18000a186  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000a18b  test    al, al
0x18000a18d  jz      loc_18000A266
0x18000a193  mov     rdi, [rsi+18h]
0x18000a197  cmp     ebx, 0FEh
0x18000a19d  jz      short loc_18000A21C
0x18000a19f  cmp     ebx, 0C8h
0x18000a1a5  jb      short loc_18000A1BF
0x18000a1a7  cmp     ebx, 100h
0x18000a1ad  jl      loc_18000A266
0x18000a1b3  cmp     ebx, 200h
0x18000a1b9  jnb     loc_18000A266
0x18000a1bf  mov     rcx, rdi; SRWLock
0x18000a1c2  call    cs:__imp_AcquireSRWLockExclusive
0x18000a1c8  cmp     ebx, 7
0x18000a1cb  ja      short loc_18000A1D7
0x18000a1cd  mov     eax, 0CCh
0x18000a1d2  bt      eax, ebx
0x18000a1d5  jb      short loc_18000A1F7
0x18000a1d7  lea     eax, [rbx-100h]
0x18000a1dd  cmp     eax, 7Fh
0x18000a1e0  jbe     short loc_18000A1F7
0x18000a1e2  mov     r9d, r15d
0x18000a1e5  lea     rcx, [rdi+48h]
0x18000a1e9  mov     r8d, r14d
0x18000a1ec  mov     edx, ebx
0x18000a1ee  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a1f3  mov     bl, al
0x18000a1f5  jmp     short loc_18000A208
0x18000a1f7  mov     r8d, r14d
0x18000a1fa  mov     edx, ebx
0x18000a1fc  lea     rcx, [rdi+8]
0x18000a200  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000a205  mov     bl, [rdi+40h]
0x18000a208  test    rdi, rdi
0x18000a20b  jz      short loc_18000A216
0x18000a20d  mov     rcx, rdi; SRWLock
0x18000a210  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a216  test    bl, bl
0x18000a218  jz      short loc_18000A266
0x18000a21a  jmp     short loc_18000A224
0x18000a21c  mov     rcx, rdi; SRWLock
0x18000a21f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000a224  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000a22b  jnz     short loc_18000A266
0x18000a22d  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000a234  test    rax, rax
0x18000a237  jz      short loc_18000A242
0x18000a239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a23e  test    al, al
0x18000a240  jnz     short loc_18000A266
0x18000a242  lea     rbx, [rsi+20h]
0x18000a246  mov     rcx, rbx; SRWLock
0x18000a249  call    cs:__imp_AcquireSRWLockExclusive
0x18000a24f  mov     rcx, rsi; pv
0x18000a252  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000a257  test    rbx, rbx
0x18000a25a  jz      short loc_18000A266
0x18000a25c  mov     rcx, rbx; SRWLock
0x18000a25f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a265  nop
0x18000a266  add     rsp, 28h
0x18000a26a  pop     r15
0x18000a26c  pop     r14
0x18000a26e  pop     rdi
0x18000a26f  pop     rsi
0x18000a270  pop     rbp
0x18000a271  pop     rbx
0x18000a272  retn
```
