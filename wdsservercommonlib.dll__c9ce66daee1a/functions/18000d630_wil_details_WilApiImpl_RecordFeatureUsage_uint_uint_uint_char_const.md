# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000d630`
- end: `0x18000d76a`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `314`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180009c64`
- `0x18000b2cc`
- `0x18000b4b0`
- `0x18000b844`
- `0x18000ba3c`
- `0x18000d630`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d728`
- `KERNEL32!GetProcAddress` at `0x18000d728`
- `KERNEL32!GetModuleHandleW` at `0x18000d70b`
- `KERNEL32!GetModuleHandleW` at `0x18000d70b`

## string_xrefs

- `0x18000d704`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_1800493B0[25], qword_1800493B0);
    wil::details_abi::FeatureStateData::RecordUsage(qword_1800493B0);
  }
}

```

## disassembly

```asm
0x18000d630  sub     rsp, 38h
0x18000d634  mov     eax, edx
0x18000d636  btr     edx, 1Fh
0x18000d63a  test    ecx, ecx
0x18000d63c  jnz     short loc_18000D6A3
0x18000d63e  test    r8d, r8d
0x18000d641  jnz     short loc_18000D6A3
0x18000d643  test    edx, edx
0x18000d645  jnz     short loc_18000D6A3
0x18000d647  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, dl; bool wil::details::g_processShutdownInProgress
0x18000d64d  jnz     loc_18000D764
0x18000d653  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000d65a  test    rax, rax
0x18000d65d  jz      short loc_18000D66C
0x18000d65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d664  test    al, al
0x18000d666  jnz     loc_18000D764
0x18000d66c  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000d673  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000d678  test    al, al
0x18000d67a  jz      loc_18000D764
0x18000d680  mov     rdx, cs:qword_1800493B0; SRWLock
0x18000d687  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000d68e  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000d693  mov     rcx, cs:qword_1800493B0; SRWLock
0x18000d69a  add     rsp, 38h
0x18000d69e  jmp     ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000d6a3  bt      edx, 1Eh
0x18000d6a7  jnb     short loc_18000D6C2
0x18000d6a9  mov     r9d, r8d; unsigned int
0x18000d6ac  movzx   r8d, dx; unsigned __int16
0x18000d6b0  mov     edx, ecx; unsigned int
0x18000d6b2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000d6b9  add     rsp, 38h
0x18000d6bd  jmp     ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000d6c2  test    r8d, r8d
0x18000d6c5  jnz     loc_18000D750
0x18000d6cb  cmp     edx, 0FEh
0x18000d6d1  jz      short loc_18000D750
0x18000d6d3  and     [rsp+38h+var_18], 0
0x18000d6d9  mov     dword ptr [rsp+38h+var_18], ecx
0x18000d6dd  mov     word ptr [rsp+38h+var_18+4], dx
0x18000d6e2  test    eax, eax
0x18000d6e4  jns     short loc_18000D6EC
0x18000d6e6  or      word ptr [rsp+38h+var_18+6], 1
0x18000d6ec  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000d6f3  test    rax, rax
0x18000d6f6  jnz     short loc_18000D740
0x18000d6f8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d6ff  test    rax, rax
0x18000d702  jnz     short loc_18000D71E
0x18000d704  lea     rcx, ModuleName; "ntdll.dll"
0x18000d70b  call    cs:__imp_GetModuleHandleW
0x18000d712  nop     dword ptr [rax+rax+00h]
0x18000d717  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d71e  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000d725  mov     rcx, rax; hModule
0x18000d728  call    cs:__imp_GetProcAddress
0x18000d72f  nop     dword ptr [rax+rax+00h]
0x18000d734  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000d73b  test    rax, rax
0x18000d73e  jz      short loc_18000D764
0x18000d740  lea     rcx, [rsp+38h+var_18]
0x18000d745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d74a  add     rsp, 38h
0x18000d74e  retn
0x18000d750  mov     r9d, r8d
0x18000d753  mov     r8d, edx
0x18000d756  mov     edx, ecx
0x18000d758  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000d75f  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000d764  add     rsp, 38h
0x18000d768  retn
```
