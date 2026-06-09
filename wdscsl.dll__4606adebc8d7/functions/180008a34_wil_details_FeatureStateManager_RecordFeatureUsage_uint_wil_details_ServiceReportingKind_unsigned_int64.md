# wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x180008a34`
- end: `0x180008b76`
- name: `?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x18000b3e0`

## callees

- `0x1800053c8`
- `0x1800054a8`
- `0x180008a34`
- `0x180008bbc`
- `0x180008bf4`
- `0x180008c2c`
- `0x18000e010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008af5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008b50`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008af5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180008b50`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008aa1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008b34`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008aa1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180008b34`

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
0x180008a34  mov     [rsp+arg_0], rbx
0x180008a39  mov     [rsp+arg_8], rbp
0x180008a3e  mov     [rsp+arg_10], rsi
0x180008a43  push    rdi
0x180008a44  push    r14
0x180008a46  push    r15
0x180008a48  sub     rsp, 20h
0x180008a4c  cmp     byte ptr [rcx], 0
0x180008a4f  mov     r15, r9
0x180008a52  mov     ebx, r8d
0x180008a55  mov     r14d, edx
0x180008a58  mov     rsi, rcx
0x180008a5b  jz      loc_180008B5C
0x180008a61  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x180008a66  test    al, al
0x180008a68  jz      loc_180008B5C
0x180008a6e  mov     rdi, [rsi+18h]
0x180008a72  cmp     ebx, 0FEh
0x180008a78  jz      loc_180008B07
0x180008a7e  cmp     ebx, 0C8h
0x180008a84  jb      short loc_180008A9E
0x180008a86  cmp     ebx, 100h
0x180008a8c  jl      loc_180008B5C
0x180008a92  cmp     ebx, 200h
0x180008a98  jnb     loc_180008B5C
0x180008a9e  mov     rcx, rdi; SRWLock
0x180008aa1  call    cs:__imp_AcquireSRWLockExclusive
0x180008aa8  nop     dword ptr [rax+rax+00h]
0x180008aad  cmp     ebx, 7
0x180008ab0  ja      short loc_180008ABC
0x180008ab2  mov     eax, 0CCh
0x180008ab7  bt      eax, ebx
0x180008aba  jb      short loc_180008ADC
0x180008abc  lea     eax, [rbx-100h]
0x180008ac2  cmp     eax, 7Fh
0x180008ac5  jbe     short loc_180008ADC
0x180008ac7  lea     rcx, [rdi+48h]
0x180008acb  mov     r9d, r15d
0x180008ace  mov     r8d, r14d
0x180008ad1  mov     edx, ebx
0x180008ad3  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008ad8  mov     bl, al
0x180008ada  jmp     short loc_180008AED
0x180008adc  mov     r8d, r14d
0x180008adf  lea     rcx, [rdi+8]
0x180008ae3  mov     edx, ebx
0x180008ae5  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x180008aea  mov     bl, [rdi+40h]
0x180008aed  test    rdi, rdi
0x180008af0  jz      short loc_180008B01
0x180008af2  mov     rcx, rdi; SRWLock
0x180008af5  call    cs:__imp_ReleaseSRWLockExclusive
0x180008afc  nop     dword ptr [rax+rax+00h]
0x180008b01  test    bl, bl
0x180008b03  jz      short loc_180008B5C
0x180008b05  jmp     short loc_180008B0F
0x180008b07  mov     rcx, rdi; SRWLock
0x180008b0a  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008b0f  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x180008b16  jnz     short loc_180008B5C
0x180008b18  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008b1f  test    rax, rax
0x180008b22  jz      short loc_180008B2D
0x180008b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b29  test    al, al
0x180008b2b  jnz     short loc_180008B5C
0x180008b2d  lea     rbx, [rsi+20h]
0x180008b31  mov     rcx, rbx; SRWLock
0x180008b34  call    cs:__imp_AcquireSRWLockExclusive
0x180008b3b  nop     dword ptr [rax+rax+00h]
0x180008b40  mov     rcx, rsi; pv
0x180008b43  call    ?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ; wil::details::FeatureStateManager::EnsureTimerUnderLock(void)
0x180008b48  test    rbx, rbx
0x180008b4b  jz      short loc_180008B5C
0x180008b4d  mov     rcx, rbx; SRWLock
0x180008b50  call    cs:__imp_ReleaseSRWLockExclusive
0x180008b57  nop     dword ptr [rax+rax+00h]
0x180008b5c  mov     rbx, [rsp+38h+arg_0]
0x180008b61  mov     rbp, [rsp+38h+arg_8]
0x180008b66  mov     rsi, [rsp+38h+arg_10]
0x180008b6b  add     rsp, 20h
0x180008b6f  pop     r15
0x180008b71  pop     r14
0x180008b73  pop     rdi
0x180008b74  retn
```
