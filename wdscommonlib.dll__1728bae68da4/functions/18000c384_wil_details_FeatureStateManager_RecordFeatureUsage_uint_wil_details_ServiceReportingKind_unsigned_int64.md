# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000c384`
- end: `0x18000c4c6`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000e170`

## callees

- `0x18000a7a4`
- `0x18000a884`
- `0x18000c384`
- `0x18000c50c`
- `0x18000c544`
- `0x18000c57c`
- `0x180031010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c3f1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c484`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c3f1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000c484`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c445`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c4a0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c445`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000c4a0`

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
0x18000c384  mov     [rsp+arg_0], rbx
0x18000c389  mov     [rsp+arg_8], rbp
0x18000c38e  mov     [rsp+arg_10], rsi
0x18000c393  push    rdi
0x18000c394  push    r14
0x18000c396  push    r15
0x18000c398  sub     rsp, 20h
0x18000c39c  cmp     byte ptr [rcx], 0
0x18000c39f  mov     r15, r9
0x18000c3a2  mov     ebx, r8d
0x18000c3a5  mov     r14d, edx
0x18000c3a8  mov     rsi, rcx
0x18000c3ab  jz      loc_18000C4AC
0x18000c3b1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000c3b6  test    al, al
0x18000c3b8  jz      loc_18000C4AC
0x18000c3be  mov     rdi, [rsi+18h]
0x18000c3c2  cmp     ebx, 0FEh
0x18000c3c8  jz      loc_18000C457
0x18000c3ce  cmp     ebx, 0C8h
0x18000c3d4  jb      short loc_18000C3EE
0x18000c3d6  cmp     ebx, 100h
0x18000c3dc  jl      loc_18000C4AC
0x18000c3e2  cmp     ebx, 200h
0x18000c3e8  jnb     loc_18000C4AC
0x18000c3ee  mov     rcx, rdi; SRWLock
0x18000c3f1  call    cs:__imp_AcquireSRWLockExclusive
0x18000c3f8  nop     dword ptr [rax+rax+00h]
0x18000c3fd  cmp     ebx, 7
0x18000c400  ja      short loc_18000C40C
0x18000c402  mov     eax, 0CCh
0x18000c407  bt      eax, ebx
0x18000c40a  jb      short loc_18000C42C
0x18000c40c  lea     eax, [rbx-100h]
0x18000c412  cmp     eax, 7Fh
0x18000c415  jbe     short loc_18000C42C
0x18000c417  lea     rcx, [rdi+48h]
0x18000c41b  mov     r9d, r15d
0x18000c41e  mov     r8d, r14d
0x18000c421  mov     edx, ebx
0x18000c423  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c428  mov     bl, al
0x18000c42a  jmp     short loc_18000C43D
0x18000c42c  mov     r8d, r14d
0x18000c42f  lea     rcx, [rdi+8]
0x18000c433  mov     edx, ebx
0x18000c435  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000c43a  mov     bl, [rdi+40h]
0x18000c43d  test    rdi, rdi
0x18000c440  jz      short loc_18000C451
0x18000c442  mov     rcx, rdi; SRWLock
0x18000c445  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c44c  nop     dword ptr [rax+rax+00h]
0x18000c451  test    bl, bl
0x18000c453  jz      short loc_18000C4AC
0x18000c455  jmp     short loc_18000C45F
0x18000c457  mov     rcx, rdi; SRWLock
0x18000c45a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000c45f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000c466  jnz     short loc_18000C4AC
0x18000c468  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000c46f  test    rax, rax
0x18000c472  jz      short loc_18000C47D
0x18000c474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c479  test    al, al
0x18000c47b  jnz     short loc_18000C4AC
0x18000c47d  lea     rbx, [rsi+20h]
0x18000c481  mov     rcx, rbx; SRWLock
0x18000c484  call    cs:__imp_AcquireSRWLockExclusive
0x18000c48b  nop     dword ptr [rax+rax+00h]
0x18000c490  mov     rcx, rsi; pv
0x18000c493  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000c498  test    rbx, rbx
0x18000c49b  jz      short loc_18000C4AC
0x18000c49d  mov     rcx, rbx; SRWLock
0x18000c4a0  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c4a7  nop     dword ptr [rax+rax+00h]
0x18000c4ac  mov     rbx, [rsp+38h+arg_0]
0x18000c4b1  mov     rbp, [rsp+38h+arg_8]
0x18000c4b6  mov     rsi, [rsp+38h+arg_10]
0x18000c4bb  add     rsp, 20h
0x18000c4bf  pop     r15
0x18000c4c1  pop     r14
0x18000c4c3  pop     rdi
0x18000c4c4  retn
```
