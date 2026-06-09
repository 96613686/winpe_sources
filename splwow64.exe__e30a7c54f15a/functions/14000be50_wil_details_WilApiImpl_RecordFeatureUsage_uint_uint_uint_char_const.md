# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x14000be50`
- end: `0x14000bf7b`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400095e4`
- `0x140009ff8`
- `0x14000a158`
- `0x14000a880`
- `0x14000aa40`
- `0x14000be50`
- `0x140016010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000bf47`
- `KERNEL32!GetProcAddress` at `0x14000bf47`
- `KERNEL32!GetModuleHandleW` at `0x14000bf30`
- `KERNEL32!GetModuleHandleW` at `0x14000bf30`

## string_xrefs

- `0x14000bf29`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details::WilApiImpl_RecordFeatureUsage(wil::details *this, int a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v4; // r8
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+24h] [rbp-14h]

  v3 = a3;
  v4 = (unsigned int)a2;
  LODWORD(v4) = a2 & 0x7FFFFFFF;
  if ( (_DWORD)this || (_DWORD)v3 || (_DWORD)v4 )
  {
    if ( (a2 & 0x40000000) != 0 )
    {
      wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(
        (RTL_SRWLOCK *)&wil::details::g_featureStateManager,
        (int)this,
        a2,
        v3);
    }
    else if ( (_DWORD)v3 || (_DWORD)v4 == 254 )
    {
      wil::details::FeatureStateManager::RecordFeatureUsage(
        &wil::details::g_featureStateManager,
        (unsigned int)this,
        v4,
        v3);
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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_140021168[25], qword_140021168);
    wil::details_abi::FeatureStateData::RecordUsage(qword_140021168);
  }
}

```

## disassembly

```asm
0x14000be50  sub     rsp, 38h
0x14000be54  mov     eax, r8d
0x14000be57  mov     r8d, edx
0x14000be5a  btr     r8d, 1Fh; unsigned __int16
0x14000be5f  test    ecx, ecx
0x14000be61  jnz     short loc_14000BECA
0x14000be63  test    eax, eax
0x14000be65  jnz     short loc_14000BECA
0x14000be67  test    r8d, r8d
0x14000be6a  jnz     short loc_14000BECA
0x14000be6c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x14000be73  jnz     loc_14000BF76
0x14000be79  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000be80  test    rax, rax
0x14000be83  jz      short loc_14000BE92
0x14000be85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be8a  test    al, al
0x14000be8c  jnz     loc_14000BF76
0x14000be92  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x14000be99  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x14000be9e  test    al, al
0x14000bea0  jz      loc_14000BF76
0x14000bea6  mov     rdx, cs:qword_140021168; SRWLock
0x14000bead  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000beb4  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14000beb9  mov     rcx, cs:qword_140021168; SRWLock
0x14000bec0  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x14000bec5  jmp     loc_14000BF76
0x14000beca  bt      r8d, 1Eh
0x14000becf  jnb     short loc_14000BEE7
0x14000bed1  mov     edx, ecx; unsigned int
0x14000bed3  mov     r9d, eax; unsigned int
0x14000bed6  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x14000bedd  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x14000bee2  jmp     loc_14000BF76
0x14000bee7  test    eax, eax
0x14000bee9  jnz     short loc_14000BF65
0x14000beeb  cmp     r8d, 0FEh
0x14000bef2  jz      short loc_14000BF65
0x14000bef4  mov     [rsp+38h+var_18], 0
0x14000befd  mov     dword ptr [rsp+38h+var_18], ecx
0x14000bf01  mov     word ptr [rsp+38h+var_18+4], r8w
0x14000bf07  test    edx, edx
0x14000bf09  jns     short loc_14000BF11
0x14000bf0b  or      word ptr [rsp+38h+var_18+6], 1
0x14000bf11  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000bf18  test    rax, rax
0x14000bf1b  jnz     short loc_14000BF59
0x14000bf1d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bf24  test    rax, rax
0x14000bf27  jnz     short loc_14000BF3D
0x14000bf29  lea     rcx, ModuleName; "ntdll.dll"
0x14000bf30  call    cs:__imp_GetModuleHandleW
0x14000bf36  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAXXZ@4PEAXEA, rax; void * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bf3d  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000bf44  mov     rcx, rax; hModule
0x14000bf47  call    cs:__imp_GetProcAddress
0x14000bf4d  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000bf54  test    rax, rax
0x14000bf57  jz      short loc_14000BF76
0x14000bf59  lea     rcx, [rsp+38h+var_18]
0x14000bf5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bf63  jmp     short loc_14000BF76
0x14000bf65  mov     edx, ecx
0x14000bf67  mov     r9, rax
0x14000bf6a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x14000bf71  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x14000bf76  add     rsp, 38h
0x14000bf7a  retn
```
