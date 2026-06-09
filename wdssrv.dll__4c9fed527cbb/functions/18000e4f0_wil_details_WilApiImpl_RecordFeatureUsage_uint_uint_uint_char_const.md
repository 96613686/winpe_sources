# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000e4f0`
- end: `0x18000e62a`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `314`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180008644`
- `0x18000a92c`
- `0x18000ae68`
- `0x18000b804`
- `0x18000ba34`
- `0x18000e4f0`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e5cb`
- `KERNEL32!GetModuleHandleW` at `0x18000e5cb`
- `KERNEL32!GetProcAddress` at `0x18000e5e8`
- `KERNEL32!GetProcAddress` at `0x18000e5e8`

## string_xrefs

- `0x18000e5c4`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // edx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (v4 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        v4,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)v4;
      if ( a2 < 0 )
        HIWORD(v8) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_19;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_19:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180028070[25], qword_180028070);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180028070);
  }
}

```

## disassembly

```asm
0x18000e4f0  sub     rsp, 38h
0x18000e4f4  mov     eax, edx
0x18000e4f6  btr     edx, 1Fh
0x18000e4fa  test    ecx, ecx
0x18000e4fc  jnz     short loc_18000E563
0x18000e4fe  test    r8d, r8d
0x18000e501  jnz     short loc_18000E563
0x18000e503  test    edx, edx
0x18000e505  jnz     short loc_18000E563
0x18000e507  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x18000e50d  jnz     loc_18000E624
0x18000e513  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000e51a  test    rax, rax
0x18000e51d  jz      short loc_18000E52C
0x18000e51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e524  test    al, al
0x18000e526  jnz     loc_18000E624
0x18000e52c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000e533  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000e538  test    al, al
0x18000e53a  jz      loc_18000E624
0x18000e540  mov     rdx, cs:qword_180028070; SRWLock
0x18000e547  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000e54e  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000e553  mov     rcx, cs:qword_180028070; SRWLock
0x18000e55a  add     rsp, 38h
0x18000e55e  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000e563  bt      edx, 1Eh
0x18000e567  jnb     short loc_18000E582
0x18000e569  mov     r9d, r8d; unsigned int
0x18000e56c  movzx   r8d, dx; unsigned __int16
0x18000e570  mov     edx, ecx; unsigned int
0x18000e572  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000e579  add     rsp, 38h
0x18000e57d  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000e582  test    r8d, r8d
0x18000e585  jnz     loc_18000E610
0x18000e58b  cmp     edx, 0FEh
0x18000e591  jz      short loc_18000E610
0x18000e593  and     [rsp+38h+var_18], 0
0x18000e599  mov     dword ptr [rsp+38h+var_18], ecx
0x18000e59d  mov     word ptr [rsp+38h+var_18+4], dx
0x18000e5a2  test    eax, eax
0x18000e5a4  jns     short loc_18000E5AC
0x18000e5a6  or      word ptr [rsp+38h+var_18+6], 1
0x18000e5ac  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000e5b3  test    rax, rax
0x18000e5b6  jnz     short loc_18000E600
0x18000e5b8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e5bf  test    rax, rax
0x18000e5c2  jnz     short loc_18000E5DE
0x18000e5c4  lea     rcx, ModuleName; "ntdll.dll"
0x18000e5cb  call    cs:__imp_GetModuleHandleW
0x18000e5d2  nop     dword ptr [rax+rax+00h]
0x18000e5d7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e5de  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000e5e5  mov     rcx, rax; hModule
0x18000e5e8  call    cs:__imp_GetProcAddress
0x18000e5ef  nop     dword ptr [rax+rax+00h]
0x18000e5f4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000e5fb  test    rax, rax
0x18000e5fe  jz      short loc_18000E624
0x18000e600  lea     rcx, [rsp+38h+var_18]
0x18000e605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e60a  add     rsp, 38h
0x18000e60e  retn
0x18000e610  mov     r9d, r8d
0x18000e613  mov     r8d, edx
0x18000e616  mov     edx, ecx
0x18000e618  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000e61f  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000e624  add     rsp, 38h
0x18000e628  retn
```
