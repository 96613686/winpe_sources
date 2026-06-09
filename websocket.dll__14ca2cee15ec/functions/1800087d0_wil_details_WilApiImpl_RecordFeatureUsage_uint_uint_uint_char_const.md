# wil::details::WilApiImpl_RecordFeatureUsage(uint,uint,uint,char const *)

- ea: `0x1800087d0`
- end: `0x1800088fb`
- name: `?WilApiImpl_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z`
- size: `299`
- prototype: `void __fastcall(wil::details *__hidden this, unsigned int, unsigned int, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004b04`
- `0x1800065b4`
- `0x1800067b8`
- `0x180006d34`
- `0x180006f20`
- `0x1800087d0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088c7`

## string_xrefs

- `0x1800088a9`: `ntdll.dll`

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
         && wil::details::FeatureStateManager::EnsureStateData((wil::details::FeatureStateManager *)&wil::details::g_featureStateManager) )
  {
    wil::details_abi::SubscriptionList::OnSignaled((LPCRITICAL_SECTION)&qword_180012088[25], qword_180012088);
    wil::details_abi::FeatureStateData::RecordUsage(qword_180012088);
  }
}

```

## disassembly

```asm
0x1800087d0  sub     rsp, 38h
0x1800087d4  mov     eax, r8d
0x1800087d7  mov     r8d, edx
0x1800087da  btr     r8d, 1Fh; unsigned __int16
0x1800087df  test    ecx, ecx
0x1800087e1  jnz     short loc_18000884A
0x1800087e3  test    eax, eax
0x1800087e5  jnz     short loc_18000884A
0x1800087e7  test    r8d, r8d
0x1800087ea  jnz     short loc_18000884A
0x1800087ec  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, r8b; bool wil::details::g_processShutdownInProgress
0x1800087f3  jnz     loc_1800088F6
0x1800087f9  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x180008800  test    rax, rax
0x180008803  jz      short loc_180008812
0x180008805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000880a  test    al, al
0x18000880c  jnz     loc_1800088F6
0x180008812  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; this
0x180008819  call    ?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ; wil::details::FeatureStateManager::EnsureStateData(void)
0x18000881e  test    al, al
0x180008820  jz      loc_1800088F6
0x180008826  mov     rdx, cs:qword_180012088; SRWLock
0x18000882d  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008834  call    ?OnSignaled@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@@Z; wil::details_abi::SubscriptionList::OnSignaled(wil::srwlock &)
0x180008839  mov     rcx, cs:qword_180012088; SRWLock
0x180008840  call    ?RecordUsage@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::RecordUsage(void)
0x180008845  jmp     loc_1800088F6
0x18000884a  bt      r8d, 1Eh
0x18000884f  jnb     short loc_180008867
0x180008851  mov     edx, ecx; unsigned int
0x180008853  mov     r9d, eax; unsigned int
0x180008856  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; pv
0x18000885d  call    ?QueueBackgroundSRUMUsageReporting@FeatureStateManager@details@wil@@QEAAXIGI@Z; wil::details::FeatureStateManager::QueueBackgroundSRUMUsageReporting(uint,ushort,uint)
0x180008862  jmp     loc_1800088F6
0x180008867  test    eax, eax
0x180008869  jnz     short loc_1800088E5
0x18000886b  cmp     r8d, 0FEh
0x180008872  jz      short loc_1800088E5
0x180008874  mov     [rsp+38h+var_18], 0
0x18000887d  mov     dword ptr [rsp+38h+var_18], ecx
0x180008881  mov     word ptr [rsp+38h+var_18+4], r8w
0x180008887  test    edx, edx
0x180008889  jns     short loc_180008891
0x18000888b  or      word ptr [rsp+38h+var_18+6], 1
0x180008891  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180008898  test    rax, rax
0x18000889b  jnz     short loc_1800088D9
0x18000889d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800088a4  test    rax, rax
0x1800088a7  jnz     short loc_1800088BD
0x1800088a9  lea     rcx, ModuleName; "ntdll.dll"
0x1800088b0  call    cs:__imp_GetModuleHandleW
0x1800088b6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800088bd  lea     rdx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800088c4  mov     rcx, rax; hModule
0x1800088c7  call    cs:__imp_GetProcAddress
0x1800088cd  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800088d4  test    rax, rax
0x1800088d7  jz      short loc_1800088F6
0x1800088d9  lea     rcx, [rsp+38h+var_18]
0x1800088de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e3  jmp     short loc_1800088F6
0x1800088e5  mov     edx, ecx
0x1800088e7  mov     r9, rax
0x1800088ea  lea     rcx, ?g_featureStateManager@details@wil@@3V?$shutdown_aware_object@VFeatureStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::FeatureStateManager> wil::details::g_featureStateManager
0x1800088f1  call    ?RecordFeatureUsage@FeatureStateManager@details@wil@@QEAAXIW4wil_details_ServiceReportingKind@@_K@Z; wil::details::FeatureStateManager::RecordFeatureUsage(uint,wil_details_ServiceReportingKind,unsigned __int64)
0x1800088f6  add     rsp, 38h
0x1800088fa  retn
```
