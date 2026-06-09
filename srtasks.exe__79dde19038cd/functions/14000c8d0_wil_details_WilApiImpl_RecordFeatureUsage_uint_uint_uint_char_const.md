# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000c8d0`
- end: `0x14000c9fb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400096a4`
- `0x14000ac84`
- `0x14000ad48`
- `0x14000b104`
- `0x14000b2bc`
- `0x14000c8d0`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c9b0`
- `KERNEL32!GetModuleHandleW` at `0x14000c9b0`
- `KERNEL32!GetProcAddress` at `0x14000c9c7`
- `KERNEL32!GetProcAddress` at `0x14000c9c7`

## string_xrefs

- `0x14000c9a9`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v4 = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || a3 || v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        a3);
    }
    else if ( a3 || v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        (__int64)&wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        a3);
    }
    else
    {
      v7 = (int)this;
      v8 = (unsigned __int16)a2;
      if ( a2 < 0 )
        HIWORD(v8) |= 1u;
      ProcAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
      if ( g_wil_details_pfnRtlNotifyFeatureUsage )
        goto LABEL_19;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140016028[25], qword_140016028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140016028);
  }
}

```

## disassembly

```asm
0x14000c8d0  sub     rsp, 38h
0x14000c8d4  mov     eax, r8d
0x14000c8d7  mov     r8d, edx
0x14000c8da  btr     r8d, 1Fh; unsigned __int16
0x14000c8df  test    ecx, ecx
0x14000c8e1  jnz     short loc_14000C94A
0x14000c8e3  test    eax, eax
0x14000c8e5  jnz     short loc_14000C94A
0x14000c8e7  test    r8d, r8d
0x14000c8ea  jnz     short loc_14000C94A
0x14000c8ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000c8f3  jnz     loc_14000C9F6
0x14000c8f9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000c900  test    rax, rax
0x14000c903  jz      short loc_14000C912
0x14000c905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c90a  test    al, al
0x14000c90c  jnz     loc_14000C9F6
0x14000c912  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000c919  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000c91e  test    al, al
0x14000c920  jz      loc_14000C9F6
0x14000c926  mov     rdx, cs:qword_140016028; SRWLock
0x14000c92d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000c934  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000c939  mov     rcx, cs:qword_140016028; SRWLock
0x14000c940  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000c945  jmp     loc_14000C9F6
0x14000c94a  bt      r8d, 1Eh
0x14000c94f  jnb     short loc_14000C967
0x14000c951  mov     edx, ecx; unsigned int
0x14000c953  mov     r9d, eax; unsigned int
0x14000c956  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000c95d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000c962  jmp     loc_14000C9F6
0x14000c967  test    eax, eax
0x14000c969  jnz     short loc_14000C9E5
0x14000c96b  cmp     r8d, 0FEh
0x14000c972  jz      short loc_14000C9E5
0x14000c974  mov     [rsp+38h+var_18], 0
0x14000c97d  mov     dword ptr [rsp+38h+var_18], ecx
0x14000c981  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000c987  test    edx, edx
0x14000c989  jns     short loc_14000C991
0x14000c98b  or      word ptr [rsp+38h+var_18+6], 1
0x14000c991  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000c998  test    rax, rax
0x14000c99b  jnz     short loc_14000C9D9
0x14000c99d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c9a4  test    rax, rax
0x14000c9a7  jnz     short loc_14000C9BD
0x14000c9a9  lea     rcx, ModuleName; "ntdll.dll"
0x14000c9b0  call    cs:__imp_GetModuleHandleW
0x14000c9b6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c9bd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000c9c4  mov     rcx, rax; hModule
0x14000c9c7  call    cs:__imp_GetProcAddress
0x14000c9cd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000c9d4  test    rax, rax
0x14000c9d7  jz      short loc_14000C9F6
0x14000c9d9  lea     rcx, [rsp+38h+var_18]
0x14000c9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c9e3  jmp     short loc_14000C9F6
0x14000c9e5  mov     edx, ecx
0x14000c9e7  mov     r9, rax
0x14000c9ea  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000c9f1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000c9f6  add     rsp, 38h
0x14000c9fa  retn
```
