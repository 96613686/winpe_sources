# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b844`
- end: `0x18000b986`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000d630`

## callees

- `0x180009c64`
- `0x180009d44`
- `0x18000b844`
- `0x18000b9cc`
- `0x18000ba04`
- `0x18000ba3c`
- `0x180030010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b8b1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b944`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b8b1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b944`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b905`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b960`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b905`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b960`

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
0x18000b844  mov     [rsp+arg_0], rbx
0x18000b849  mov     [rsp+arg_8], rbp
0x18000b84e  mov     [rsp+arg_10], rsi
0x18000b853  push    rdi
0x18000b854  push    r14
0x18000b856  push    r15
0x18000b858  sub     rsp, 20h
0x18000b85c  cmp     byte ptr [rcx], 0
0x18000b85f  mov     r15, r9
0x18000b862  mov     ebx, r8d
0x18000b865  mov     r14d, edx
0x18000b868  mov     rsi, rcx
0x18000b86b  jz      loc_18000B96C
0x18000b871  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b876  test    al, al
0x18000b878  jz      loc_18000B96C
0x18000b87e  mov     rdi, [rsi+18h]
0x18000b882  cmp     ebx, 0FEh
0x18000b888  jz      loc_18000B917
0x18000b88e  cmp     ebx, 0C8h
0x18000b894  jb      short loc_18000B8AE
0x18000b896  cmp     ebx, 100h
0x18000b89c  jl      loc_18000B96C
0x18000b8a2  cmp     ebx, 200h
0x18000b8a8  jnb     loc_18000B96C
0x18000b8ae  mov     rcx, rdi; SRWLock
0x18000b8b1  call    cs:__imp_AcquireSRWLockExclusive
0x18000b8b8  nop     dword ptr [rax+rax+00h]
0x18000b8bd  cmp     ebx, 7
0x18000b8c0  ja      short loc_18000B8CC
0x18000b8c2  mov     eax, 0CCh
0x18000b8c7  bt      eax, ebx
0x18000b8ca  jb      short loc_18000B8EC
0x18000b8cc  lea     eax, [rbx-100h]
0x18000b8d2  cmp     eax, 7Fh
0x18000b8d5  jbe     short loc_18000B8EC
0x18000b8d7  lea     rcx, [rdi+48h]
0x18000b8db  mov     r9d, r15d
0x18000b8de  mov     r8d, r14d
0x18000b8e1  mov     edx, ebx
0x18000b8e3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b8e8  mov     bl, al
0x18000b8ea  jmp     short loc_18000B8FD
0x18000b8ec  mov     r8d, r14d
0x18000b8ef  lea     rcx, [rdi+8]
0x18000b8f3  mov     edx, ebx
0x18000b8f5  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b8fa  mov     bl, [rdi+40h]
0x18000b8fd  test    rdi, rdi
0x18000b900  jz      short loc_18000B911
0x18000b902  mov     rcx, rdi; SRWLock
0x18000b905  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b90c  nop     dword ptr [rax+rax+00h]
0x18000b911  test    bl, bl
0x18000b913  jz      short loc_18000B96C
0x18000b915  jmp     short loc_18000B91F
0x18000b917  mov     rcx, rdi; SRWLock
0x18000b91a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b91f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b926  jnz     short loc_18000B96C
0x18000b928  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b92f  test    rax, rax
0x18000b932  jz      short loc_18000B93D
0x18000b934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b939  test    al, al
0x18000b93b  jnz     short loc_18000B96C
0x18000b93d  lea     rbx, [rsi+20h]
0x18000b941  mov     rcx, rbx; SRWLock
0x18000b944  call    cs:__imp_AcquireSRWLockExclusive
0x18000b94b  nop     dword ptr [rax+rax+00h]
0x18000b950  mov     rcx, rsi; pv
0x18000b953  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000b958  test    rbx, rbx
0x18000b95b  jz      short loc_18000B96C
0x18000b95d  mov     rcx, rbx; SRWLock
0x18000b960  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b967  nop     dword ptr [rax+rax+00h]
0x18000b96c  mov     rbx, [rsp+38h+arg_0]
0x18000b971  mov     rbp, [rsp+38h+arg_8]
0x18000b976  mov     rsi, [rsp+38h+arg_10]
0x18000b97b  add     rsp, 20h
0x18000b97f  pop     r15
0x18000b981  pop     r14
0x18000b983  pop     rdi
0x18000b984  retn
```
