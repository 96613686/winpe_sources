# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800144b0`
- end: `0x1800145db`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1800111d4`
- `0x1800127b4`
- `0x18001291c`
- `0x180012ce4`
- `0x180012e9c`
- `0x1800144b0`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800145a7`
- `KERNEL32!GetProcAddress` at `0x1800145a7`
- `KERNEL32!GetModuleHandleW` at `0x180014590`
- `KERNEL32!GetModuleHandleW` at `0x180014590`

## string_xrefs

- `0x180014589`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_18001D178[25], qword_18001D178);
    wil::details_abi::FeatureStateData::RecordUsage(qword_18001D178);
  }
}

```

## disassembly

```asm
0x1800144b0  sub     rsp, 38h
0x1800144b4  mov     eax, r8d
0x1800144b7  mov     r8d, edx
0x1800144ba  btr     r8d, 1Fh; unsigned __int16
0x1800144bf  test    ecx, ecx
0x1800144c1  jnz     short loc_18001452A
0x1800144c3  test    eax, eax
0x1800144c5  jnz     short loc_18001452A
0x1800144c7  test    r8d, r8d
0x1800144ca  jnz     short loc_18001452A
0x1800144cc  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800144d3  jnz     loc_1800145D6
0x1800144d9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1800144e0  test    rax, rax
0x1800144e3  jz      short loc_1800144F2
0x1800144e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144ea  test    al, al
0x1800144ec  jnz     loc_1800145D6
0x1800144f2  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x1800144f9  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x1800144fe  test    al, al
0x180014500  jz      loc_1800145D6
0x180014506  mov     rdx, cs:qword_18001D178; SRWLock
0x18001450d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180014514  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180014519  mov     rcx, cs:qword_18001D178; SRWLock
0x180014520  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180014525  jmp     loc_1800145D6
0x18001452a  bt      r8d, 1Eh
0x18001452f  jnb     short loc_180014547
0x180014531  mov     edx, ecx; unsigned int
0x180014533  mov     r9d, eax; unsigned int
0x180014536  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18001453d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180014542  jmp     loc_1800145D6
0x180014547  test    eax, eax
0x180014549  jnz     short loc_1800145C5
0x18001454b  cmp     r8d, 0FEh
0x180014552  jz      short loc_1800145C5
0x180014554  mov     [rsp+38h+var_18], 0
0x18001455d  mov     dword ptr [rsp+38h+var_18], ecx
0x180014561  mov     word ptr [rsp+38h+var_18+4], r8w
0x180014567  test    edx, edx
0x180014569  jns     short loc_180014571
0x18001456b  or      word ptr [rsp+38h+var_18+6], 1
0x180014571  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180014578  test    rax, rax
0x18001457b  jnz     short loc_1800145B9
0x18001457d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014584  test    rax, rax
0x180014587  jnz     short loc_18001459D
0x180014589  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180014590  call    cs:__imp_GetModuleHandleW
0x180014596  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001459d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800145a4  mov     rcx, rax; hModule
0x1800145a7  call    cs:__imp_GetProcAddress
0x1800145ad  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800145b4  test    rax, rax
0x1800145b7  jz      short loc_1800145D6
0x1800145b9  lea     rcx, [rsp+38h+var_18]
0x1800145be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145c3  jmp     short loc_1800145D6
0x1800145c5  mov     edx, ecx
0x1800145c7  mov     r9, rax
0x1800145ca  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800145d1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800145d6  add     rsp, 38h
0x1800145da  retn
```
