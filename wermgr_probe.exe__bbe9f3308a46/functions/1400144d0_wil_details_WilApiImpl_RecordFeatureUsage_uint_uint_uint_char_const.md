# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1400144d0`
- end: `0x1400145f0`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `288`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x1400112c0`
- `0x140012124`
- `0x1400121e8`
- `0x140012540`
- `0x140012700`
- `0x1400144d0`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400145bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400145bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400145a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400145a5`

## string_xrefs

- `0x14001459e`: `ntdll.dll`

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
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_14002C090[25], qword_14002C090);
    wil::details_abi::FeatureStateData::RecordUsage(qword_14002C090);
  }
}

```

## disassembly

```asm
0x1400144d0  sub     rsp, 38h
0x1400144d4  mov     eax, r8d
0x1400144d7  mov     r8d, edx
0x1400144da  btr     r8d, 1Fh; unsigned __int16
0x1400144df  test    ecx, ecx
0x1400144e1  jnz     short loc_14001453F
0x1400144e3  test    eax, eax
0x1400144e5  jnz     short loc_14001453F
0x1400144e7  test    r8d, r8d
0x1400144ea  jnz     short loc_14001453F
0x1400144ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1400144f3  jnz     short loc_14001453A
0x1400144f5  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x1400144fc  test    rax, rax
0x1400144ff  jz      short loc_14001450A
0x140014501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014506  test    al, al
0x140014508  jnz     short loc_14001453A
0x14001450a  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x140014511  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x140014516  test    al, al
0x140014518  jz      short loc_14001453A
0x14001451a  mov     rdx, cs:qword_14002C090; SRWLock
0x140014521  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140014528  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x14001452d  mov     rcx, cs:qword_14002C090; SRWLock
0x140014534  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x140014539  nop
0x14001453a  jmp     loc_1400145EB
0x14001453f  bt      r8d, 1Eh
0x140014544  jnb     short loc_14001455C
0x140014546  mov     r9d, eax; unsigned int
0x140014549  mov     edx, ecx; unsigned int
0x14001454b  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x140014552  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x140014557  jmp     loc_1400145EB
0x14001455c  test    eax, eax
0x14001455e  jnz     short loc_1400145DA
0x140014560  cmp     r8d, 0FEh
0x140014567  jz      short loc_1400145DA
0x140014569  mov     [rsp+38h+var_18], 0
0x140014572  mov     dword ptr [rsp+38h+var_18], ecx
0x140014576  mov     word ptr [rsp+38h+var_18+4], r8w
0x14001457c  test    edx, edx
0x14001457e  jns     short loc_140014586
0x140014580  or      word ptr [rsp+38h+var_18+6], 1
0x140014586  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14001458d  test    rax, rax
0x140014590  jnz     short loc_1400145CE
0x140014592  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014599  test    rax, rax
0x14001459c  jnz     short loc_1400145B2
0x14001459e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1400145a5  call    cs:__imp_GetModuleHandleW
0x1400145ab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400145b2  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1400145b9  mov     rcx, rax; hModule
0x1400145bc  call    cs:__imp_GetProcAddress
0x1400145c2  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1400145c9  test    rax, rax
0x1400145cc  jz      short loc_1400145EB
0x1400145ce  lea     rcx, [rsp+38h+var_18]
0x1400145d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400145d8  jmp     short loc_1400145EB
0x1400145da  mov     r9, rax
0x1400145dd  mov     edx, ecx
0x1400145df  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1400145e6  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1400145eb  add     rsp, 38h
0x1400145ef  retn
```
