# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000b804`
- end: `0x18000b946`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000e4f0`

## callees

- `0x180008644`
- `0x180008804`
- `0x18000b804`
- `0x18000b9c4`
- `0x18000b9fc`
- `0x18000ba34`
- `0x18001d010`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b871`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b904`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b871`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b904`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b8c5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b920`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b8c5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b920`

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
0x18000b804  mov     [rsp+arg_0], rbx
0x18000b809  mov     [rsp+arg_8], rbp
0x18000b80e  mov     [rsp+arg_10], rsi
0x18000b813  push    rdi
0x18000b814  push    r14
0x18000b816  push    r15
0x18000b818  sub     rsp, 20h
0x18000b81c  cmp     byte ptr [rcx], 0
0x18000b81f  mov     r15, r9
0x18000b822  mov     ebx, r8d
0x18000b825  mov     r14d, edx
0x18000b828  mov     rsi, rcx
0x18000b82b  jz      loc_18000B92C
0x18000b831  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000b836  test    al, al
0x18000b838  jz      loc_18000B92C
0x18000b83e  mov     rdi, [rsi+18h]
0x18000b842  cmp     ebx, 0FEh
0x18000b848  jz      loc_18000B8D7
0x18000b84e  cmp     ebx, 0C8h
0x18000b854  jb      short loc_18000B86E
0x18000b856  cmp     ebx, 100h
0x18000b85c  jl      loc_18000B92C
0x18000b862  cmp     ebx, 200h
0x18000b868  jnb     loc_18000B92C
0x18000b86e  mov     rcx, rdi; SRWLock
0x18000b871  call    cs:__imp_AcquireSRWLockExclusive
0x18000b878  nop     dword ptr [rax+rax+00h]
0x18000b87d  cmp     ebx, 7
0x18000b880  ja      short loc_18000B88C
0x18000b882  mov     eax, 0CCh
0x18000b887  bt      eax, ebx
0x18000b88a  jb      short loc_18000B8AC
0x18000b88c  lea     eax, [rbx-100h]
0x18000b892  cmp     eax, 7Fh
0x18000b895  jbe     short loc_18000B8AC
0x18000b897  lea     rcx, [rdi+48h]
0x18000b89b  mov     r9d, r15d
0x18000b89e  mov     r8d, r14d
0x18000b8a1  mov     edx, ebx
0x18000b8a3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b8a8  mov     bl, al
0x18000b8aa  jmp     short loc_18000B8BD
0x18000b8ac  mov     r8d, r14d
0x18000b8af  lea     rcx, [rdi+8]
0x18000b8b3  mov     edx, ebx
0x18000b8b5  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000b8ba  mov     bl, [rdi+40h]
0x18000b8bd  test    rdi, rdi
0x18000b8c0  jz      short loc_18000B8D1
0x18000b8c2  mov     rcx, rdi; SRWLock
0x18000b8c5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b8cc  nop     dword ptr [rax+rax+00h]
0x18000b8d1  test    bl, bl
0x18000b8d3  jz      short loc_18000B92C
0x18000b8d5  jmp     short loc_18000B8DF
0x18000b8d7  mov     rcx, rdi; SRWLock
0x18000b8da  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000b8df  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000b8e6  jnz     short loc_18000B92C
0x18000b8e8  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000b8ef  test    rax, rax
0x18000b8f2  jz      short loc_18000B8FD
0x18000b8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8f9  test    al, al
0x18000b8fb  jnz     short loc_18000B92C
0x18000b8fd  lea     rbx, [rsi+20h]
0x18000b901  mov     rcx, rbx; SRWLock
0x18000b904  call    cs:__imp_AcquireSRWLockExclusive
0x18000b90b  nop     dword ptr [rax+rax+00h]
0x18000b910  mov     rcx, rsi; pv
0x18000b913  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x18000b918  test    rbx, rbx
0x18000b91b  jz      short loc_18000B92C
0x18000b91d  mov     rcx, rbx; SRWLock
0x18000b920  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b927  nop     dword ptr [rax+rax+00h]
0x18000b92c  mov     rbx, [rsp+38h+arg_0]
0x18000b931  mov     rbp, [rsp+38h+arg_8]
0x18000b936  mov     rsi, [rsp+38h+arg_10]
0x18000b93b  add     rsp, 20h
0x18000b93f  pop     r15
0x18000b941  pop     r14
0x18000b943  pop     rdi
0x18000b944  retn
```
