# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x18000bf70`
- end: `0x18000c090`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180005d24`
- `0x180007c64`
- `0x180007e68`
- `0x180008614`
- `0x180008810`
- `0x18000bf70`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c045`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c045`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c05c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c05c`

## string_xrefs

- `0x18000c03e`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
        goto LABEL_20;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180023088[25], qword_180023088);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180023088);
  }
}

```

## disassembly

```asm
0x18000bf70  sub     rsp, 38h
0x18000bf74  mov     eax, r8d
0x18000bf77  mov     r8d, edx
0x18000bf7a  btr     r8d, 1Fh; unsigned __int16
0x18000bf7f  test    ecx, ecx
0x18000bf81  jnz     short loc_18000BFDF
0x18000bf83  test    eax, eax
0x18000bf85  jnz     short loc_18000BFDF
0x18000bf87  test    r8d, r8d
0x18000bf8a  jnz     short loc_18000BFDF
0x18000bf8c  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x18000bf93  jnz     short loc_18000BFDA
0x18000bf95  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x18000bf9c  test    rax, rax
0x18000bf9f  jz      short loc_18000BFAA
0x18000bfa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa6  test    al, al
0x18000bfa8  jnz     short loc_18000BFDA
0x18000bfaa  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x18000bfb1  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000bfb6  test    al, al
0x18000bfb8  jz      short loc_18000BFDA
0x18000bfba  mov     rdx, cs:qword_180023088; SRWLock
0x18000bfc1  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000bfc8  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x18000bfcd  mov     rcx, cs:qword_180023088; SRWLock
0x18000bfd4  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x18000bfd9  nop
0x18000bfda  jmp     loc_18000C08B
0x18000bfdf  bt      r8d, 1Eh
0x18000bfe4  jnb     short loc_18000BFFC
0x18000bfe6  mov     r9d, eax; unsigned int
0x18000bfe9  mov     edx, ecx; unsigned int
0x18000bfeb  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000bff2  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x18000bff7  jmp     loc_18000C08B
0x18000bffc  test    eax, eax
0x18000bffe  jnz     short loc_18000C07A
0x18000c000  cmp     r8d, 0FEh
0x18000c007  jz      short loc_18000C07A
0x18000c009  mov     [rsp+38h+var_18], 0
0x18000c012  mov     dword ptr [rsp+38h+var_18], ecx
0x18000c016  mov     word ptr [rsp+38h+var_18+4], r8w
0x18000c01c  test    edx, edx
0x18000c01e  jns     short loc_18000C026
0x18000c020  or      word ptr [rsp+38h+var_18+6], 1
0x18000c026  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000c02d  test    rax, rax
0x18000c030  jnz     short loc_18000C06E
0x18000c032  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c039  test    rax, rax
0x18000c03c  jnz     short loc_18000C052
0x18000c03e  lea     rcx, ModuleName; "ntdll.dll"
0x18000c045  call    cs:__imp_GetModuleHandleW
0x18000c04b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c052  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000c059  mov     rcx, rax; hModule
0x18000c05c  call    cs:__imp_GetProcAddress
0x18000c062  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000c069  test    rax, rax
0x18000c06c  jz      short loc_18000C08B
0x18000c06e  lea     rcx, [rsp+38h+var_18]
0x18000c073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c078  jmp     short loc_18000C08B
0x18000c07a  mov     r9, rax
0x18000c07d  mov     edx, ecx
0x18000c07f  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x18000c086  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x18000c08b  add     rsp, 38h
0x18000c08f  retn
```
