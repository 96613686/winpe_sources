# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000ea00`
- end: `0x18000eb20`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c9c0`
- `0x18000d02c`
- `0x18000d18c`
- `0x18000d6fc`
- `0x18000d8c0`
- `0x18000ea00`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ead5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ead5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eaec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eaec`

## string_xrefs

- `0x18000eace`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        goto LABEL_20;
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      ProcAddress = GetProcAddress(ModuleHandleW, "RtlNotifyFeatureUsage");
      g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)ProcAddress;
      if ( ProcAddress )
LABEL_20:
        ((void (__fastcall *)(int *))ProcAddress)(&v7);
    }
  }
  else if ( !wil::details::g_processShutdownInProgress
         && (!wil::details::g_pfnDllShutdownInProgress || !(unsigned __int8)wil::details::g_pfnDllShutdownInProgress())
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180034060[25], qword_180034060);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180034060);
  }
}

```

## disassembly

```asm
0x18000ea00  sub     rsp, 38h
0x18000ea04  mov     eax, r8d
0x18000ea07  mov     r8d, edx
0x18000ea0a  btr     r8d, 1Fh; unsigned __int16
0x18000ea0f  test    ecx, ecx
0x18000ea11  jnz     short loc_18000EA6F
0x18000ea13  test    eax, eax
0x18000ea15  jnz     short loc_18000EA6F
0x18000ea17  test    r8d, r8d
0x18000ea1a  jnz     short loc_18000EA6F
0x18000ea1c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000ea23  jnz     short loc_18000EA6A
0x18000ea25  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000ea2c  test    rax, rax
0x18000ea2f  jz      short loc_18000EA3A
0x18000ea31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea36  test    al, al
0x18000ea38  jnz     short loc_18000EA6A
0x18000ea3a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000ea41  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000ea46  test    al, al
0x18000ea48  jz      short loc_18000EA6A
0x18000ea4a  mov     rdx, cs:qword_180034060; SRWLock
0x18000ea51  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000ea58  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000ea5d  mov     rcx, cs:qword_180034060; SRWLock
0x18000ea64  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000ea69  nop
0x18000ea6a  jmp     loc_18000EB1B
0x18000ea6f  bt      r8d, 1Eh
0x18000ea74  jnb     short loc_18000EA8C
0x18000ea76  mov     r9d, eax; unsigned int
0x18000ea79  mov     edx, ecx; unsigned int
0x18000ea7b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000ea82  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000ea87  jmp     loc_18000EB1B
0x18000ea8c  test    eax, eax
0x18000ea8e  jnz     short loc_18000EB0A
0x18000ea90  cmp     r8d, 0FEh
0x18000ea97  jz      short loc_18000EB0A
0x18000ea99  mov     [rsp+38h+var_18], 0
0x18000eaa2  mov     dword ptr [rsp+38h+var_18], ecx
0x18000eaa6  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000eaac  test    edx, edx
0x18000eaae  jns     short loc_18000EAB6
0x18000eab0  or      word ptr [rsp+38h+var_18+6], 1
0x18000eab6  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000eabd  test    rax, rax
0x18000eac0  jnz     short loc_18000EAFE
0x18000eac2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000eac9  test    rax, rax
0x18000eacc  jnz     short loc_18000EAE2
0x18000eace  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ead5  call    cs:__imp_GetModuleHandleW
0x18000eadb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000eae2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000eae9  mov     rcx, rax; hModule
0x18000eaec  call    cs:__imp_GetProcAddress
0x18000eaf2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000eaf9  test    rax, rax
0x18000eafc  jz      short loc_18000EB1B
0x18000eafe  lea     rcx, [rsp+38h+var_18]
0x18000eb03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb08  jmp     short loc_18000EB1B
0x18000eb0a  mov     r9, rax
0x18000eb0d  mov     edx, ecx
0x18000eb0f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000eb16  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000eb1b  add     rsp, 38h
0x18000eb1f  retn
```
