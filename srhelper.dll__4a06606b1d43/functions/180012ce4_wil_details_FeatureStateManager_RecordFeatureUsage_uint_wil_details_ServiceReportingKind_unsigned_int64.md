# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180012ce4`
- end: `0x180012df2`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `270`
- prototype: `void __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x1800144b0`

## callees

- `0x1800111d4`
- `0x180011288`
- `0x180012ce4`
- `0x180012e30`
- `0x180012e64`
- `0x180012e9c`
- `0x180016010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012d90`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012ddf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012d90`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180012ddf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012d42`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012dc9`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012d42`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012dc9`

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
0x180012ce4  push    rbx
0x180012ce6  push    rbp
0x180012ce7  push    rsi
0x180012ce8  push    rdi
0x180012ce9  push    r14
0x180012ceb  push    r15
0x180012ced  sub     rsp, 28h
0x180012cf1  cmp     byte ptr [rcx], 0
0x180012cf4  mov     r15, r9
0x180012cf7  mov     ebx, r8d
0x180012cfa  mov     r14d, edx
0x180012cfd  mov     rsi, rcx
0x180012d00  jz      loc_180012DE5
0x180012d06  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180012d0b  test    al, al
0x180012d0d  jz      loc_180012DE5
0x180012d13  mov     rdi, [rsi+18h]
0x180012d17  cmp     ebx, 0FEh
0x180012d1d  jz      short loc_180012D9C
0x180012d1f  cmp     ebx, 0C8h
0x180012d25  jb      short loc_180012D3F
0x180012d27  cmp     ebx, 100h
0x180012d2d  jl      loc_180012DE5
0x180012d33  cmp     ebx, 200h
0x180012d39  jnb     loc_180012DE5
0x180012d3f  mov     rcx, rdi; SRWLock
0x180012d42  call    cs:__imp_AcquireSRWLockExclusive
0x180012d48  cmp     ebx, 7
0x180012d4b  ja      short loc_180012D57
0x180012d4d  mov     eax, 0CCh
0x180012d52  bt      eax, ebx
0x180012d55  jb      short loc_180012D77
0x180012d57  lea     eax, [rbx-100h]
0x180012d5d  cmp     eax, 7Fh
0x180012d60  jbe     short loc_180012D77
0x180012d62  mov     r9d, r15d
0x180012d65  lea     rcx, [rdi+48h]
0x180012d69  mov     r8d, r14d
0x180012d6c  mov     edx, ebx
0x180012d6e  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180012d73  mov     bl, al
0x180012d75  jmp     short loc_180012D88
0x180012d77  mov     r8d, r14d
0x180012d7a  lea     rcx, [rdi+8]
0x180012d7e  mov     edx, ebx
0x180012d80  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180012d85  mov     bl, [rdi+40h]
0x180012d88  test    rdi, rdi
0x180012d8b  jz      short loc_180012D96
0x180012d8d  mov     rcx, rdi; SRWLock
0x180012d90  call    cs:__imp_ReleaseSRWLockExclusive
0x180012d96  test    bl, bl
0x180012d98  jz      short loc_180012DE5
0x180012d9a  jmp     short loc_180012DA4
0x180012d9c  mov     rcx, rdi; SRWLock
0x180012d9f  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180012da4  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180012dab  jnz     short loc_180012DE5
0x180012dad  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180012db4  test    rax, rax
0x180012db7  jz      short loc_180012DC2
0x180012db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dbe  test    al, al
0x180012dc0  jnz     short loc_180012DE5
0x180012dc2  lea     rbx, [rsi+20h]
0x180012dc6  mov     rcx, rbx; SRWLock
0x180012dc9  call    cs:__imp_AcquireSRWLockExclusive
0x180012dcf  mov     rcx, rsi; pv
0x180012dd2  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180012dd7  test    rbx, rbx
0x180012dda  jz      short loc_180012DE5
0x180012ddc  mov     rcx, rbx; SRWLock
0x180012ddf  call    cs:__imp_ReleaseSRWLockExclusive
0x180012de5  add     rsp, 28h
0x180012de9  pop     r15
0x180012deb  pop     r14
0x180012ded  pop     rdi
0x180012dee  pop     rsi
0x180012def  pop     rbp
0x180012df0  pop     rbx
0x180012df1  retn
```
