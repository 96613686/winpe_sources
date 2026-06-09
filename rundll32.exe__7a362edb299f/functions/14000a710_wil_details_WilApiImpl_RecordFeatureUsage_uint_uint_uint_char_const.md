# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000a710`
- end: `0x14000a83b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *this, int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140008d4c`
- `0x140009200`
- `0x1400092c4`
- `0x14000964c`
- `0x1400097cc`
- `0x14000a710`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a7f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a7f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a807`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a807`

## string_xrefs

- `0x14000a7e9`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((RTL_SRWLOCK *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140012028[25], qword_140012028);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140012028);
  }
}

```

## disassembly

```asm
0x14000a710  sub     rsp, 38h
0x14000a714  mov     eax, r8d
0x14000a717  mov     r8d, edx
0x14000a71a  btr     r8d, 1Fh; unsigned __int16
0x14000a71f  test    ecx, ecx
0x14000a721  jnz     short loc_14000A78A
0x14000a723  test    eax, eax
0x14000a725  jnz     short loc_14000A78A
0x14000a727  test    r8d, r8d
0x14000a72a  jnz     short loc_14000A78A
0x14000a72c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000a733  jnz     loc_14000A836
0x14000a739  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a740  test    rax, rax
0x14000a743  jz      short loc_14000A752
0x14000a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a74a  test    al, al
0x14000a74c  jnz     loc_14000A836
0x14000a752  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000a759  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000a75e  test    al, al
0x14000a760  jz      loc_14000A836
0x14000a766  mov     rdx, cs:qword_140012028; SRWLock
0x14000a76d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000a774  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000a779  mov     rcx, cs:qword_140012028; SRWLock
0x14000a780  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000a785  jmp     loc_14000A836
0x14000a78a  bt      r8d, 1Eh
0x14000a78f  jnb     short loc_14000A7A7
0x14000a791  mov     edx, ecx; unsigned int
0x14000a793  mov     r9d, eax; unsigned int
0x14000a796  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000a79d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000a7a2  jmp     loc_14000A836
0x14000a7a7  test    eax, eax
0x14000a7a9  jnz     short loc_14000A825
0x14000a7ab  cmp     r8d, 0FEh
0x14000a7b2  jz      short loc_14000A825
0x14000a7b4  mov     [rsp+38h+var_18], 0
0x14000a7bd  mov     dword ptr [rsp+38h+var_18], ecx
0x14000a7c1  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000a7c7  test    edx, edx
0x14000a7c9  jns     short loc_14000A7D1
0x14000a7cb  or      word ptr [rsp+38h+var_18+6], 1
0x14000a7d1  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000a7d8  test    rax, rax
0x14000a7db  jnz     short loc_14000A819
0x14000a7dd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a7e4  test    rax, rax
0x14000a7e7  jnz     short loc_14000A7FD
0x14000a7e9  lea     rcx, ModuleName; "ntdll.dll"
0x14000a7f0  call    cs:__imp_GetModuleHandleW
0x14000a7f6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a7fd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000a804  mov     rcx, rax; hModule
0x14000a807  call    cs:__imp_GetProcAddress
0x14000a80d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000a814  test    rax, rax
0x14000a817  jz      short loc_14000A836
0x14000a819  lea     rcx, [rsp+38h+var_18]
0x14000a81e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a823  jmp     short loc_14000A836
0x14000a825  mov     edx, ecx
0x14000a827  mov     r9, rax
0x14000a82a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000a831  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000a836  add     rsp, 38h
0x14000a83a  retn
```
